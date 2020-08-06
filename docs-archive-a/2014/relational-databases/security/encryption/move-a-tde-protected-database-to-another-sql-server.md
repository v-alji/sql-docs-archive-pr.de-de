---
title: Verschieben einer TDE-geschützten Datenbank auf einen anderen SQL-Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726849"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="e21f4-102">Verschieben einer TDE-geschützten Datenbank auf einen anderen SQL-Server</span><span class="sxs-lookup"><span data-stu-id="e21f4-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="e21f4-103">In diesem Thema wird die Vorgehensweise zum Schutz einer Datenbank anhand von Transparent Data Encryption (TDE) und das Verschieben der Datenbank in eine andere Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)] beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e21f4-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e21f4-104">TDE führt die E/A-Verschlüsselung und -Entschlüsselung der Daten- und Protokolldateien in Echtzeit durch.</span><span class="sxs-lookup"><span data-stu-id="e21f4-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="e21f4-105">Die Verschlüsselung verwendet einen Datenbank-Verschlüsselungsschlüssel (DEK), der im Startdatensatz der Datenbank gespeichert wird und während der Wiederherstellung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e21f4-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="e21f4-106">Der DEK ist ein symmetrischer Schlüssel, der durch ein in der `master`-Datenbank des Servers gespeichertes Zertifikat gesichert wird, oder ein asymmetrischer Schlüssel, der von einem EKM-Modul geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="e21f4-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="e21f4-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e21f4-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e21f4-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e21f4-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e21f4-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e21f4-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e21f4-110">Security</span><span class="sxs-lookup"><span data-stu-id="e21f4-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e21f4-111">**So erstellen Sie eine durch transparente Datenverschlüsselung geschützte Datenbank mit**</span><span class="sxs-lookup"><span data-stu-id="e21f4-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="e21f4-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e21f4-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="e21f4-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e21f4-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="e21f4-114">**So verschieben Sie eine Datenbank mit**</span><span class="sxs-lookup"><span data-stu-id="e21f4-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="e21f4-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e21f4-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="e21f4-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e21f4-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e21f4-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e21f4-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e21f4-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e21f4-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e21f4-119">Beim Verschieben einer TDE-geschützten Datenbank muss auch das Zertifikat oder der asymmetrische Schlüssel verschoben werden, mit dem der DEK geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e21f4-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="e21f4-120">Das Zertifikat oder der asymmetrische Schlüssel muss in der- `master` Datenbank des Zielservers installiert sein, damit auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Datenbankdateien zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="e21f4-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="e21f4-121">Weitere Informationen finden Sie unter [Transparente Datenverschlüsselung &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="e21f4-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="e21f4-122">Bewahren Sie Kopien der Zertifikatdatei und der Datei mit dem privaten Schlüssel auf, um das Zertifikat wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="e21f4-123">Das Kennwort für den privaten Schlüssel muss nicht mit dem Kennwort für den Datenbank-Hauptschlüssel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="e21f4-124">speichert die hier erstellten Dateien unter **c:\Programme\Microsoft SQL server\mssql12. MSSQLSERVER\MSSQL\Data** standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="e21f4-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="e21f4-125">Die Dateinamen und -orte können individuell abweichen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e21f4-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e21f4-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e21f4-127">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e21f4-127">Permissions</span></span>  
  
-   <span data-ttu-id="e21f4-128">Erfordert die- `CONTROL DATABASE` Berechtigung für die `master` Datenbank, um den Datenbank-Hauptschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="e21f4-129">Erfordert die- `CREATE CERTIFICATE` Berechtigung für die `master` Datenbank zum Erstellen des Zertifikats, mit dem der DEK geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="e21f4-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="e21f4-130">Erfordert die `CONTROL DATABASE`-Berechtigung für die verschlüsselte Datenbank und die `VIEW DEFINITION`-Berechtigung für das Zertifikat oder den asymmetrischen Schlüssel, die zum Verschlüsseln des Verschlüsselungsschlüssels für die Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e21f4-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e21f4-131">So erstellen Sie eine durch transparente Datenverschlüsselung geschützte Datenbank</span><span class="sxs-lookup"><span data-stu-id="e21f4-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="e21f4-132">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e21f4-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e21f4-133">Erstellen Sie einen Datenbank-Hauptschlüssel und ein Zertifikat in der `master` Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e21f4-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="e21f4-134">Weitere Informationen finden Sie weiter unten unter **Verwenden von Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="e21f4-135">Erstellen Sie eine Sicherung des Serverzertifikats in der `master` Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e21f4-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="e21f4-136">Weitere Informationen finden Sie weiter unten unter **Verwenden von Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="e21f4-137">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Ordner **Datenbanken** , und klicken Sie dann auf **Neue Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="e21f4-138">Geben Sie im Dialogfeld **Neue Datenbank** in das Feld **Datenbankname** den Namen der neuen Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="e21f4-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="e21f4-139">Geben Sie im Feld **Besitzer** den Namen des Besitzers der neuen Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="e21f4-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="e21f4-140">Klicken Sie alternativ auf die Auslassungspunkte **(…)** , um das Dialogfeld **Datenbankbesitzer auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="e21f4-141">Weitere Informationen zum Erstellen einer neuen Datenbank finden Sie unter [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="e21f4-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="e21f4-142">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um den Ordner **Datenbank** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e21f4-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="e21f4-143">Klicken Sie mit der rechten Maustaste auf die Datenbank, die Sie erstellt haben, zeigen Sie auf **Tasks**, und wählen Sie **Datenbankverschlüsselung verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="e21f4-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="e21f4-144">Die folgenden Optionen sind im Dialogfeld **Datenbankverschlüsselung verwalten** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e21f4-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="e21f4-145">**Verschlüsselungsalgorithmus**</span><span class="sxs-lookup"><span data-stu-id="e21f4-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="e21f4-146">Zeigt den für die Datenbankverschlüsselung zu verwendenden Algorithmus an oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="e21f4-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="e21f4-147">Der Standardalgorithmus ist `AES128`.</span><span class="sxs-lookup"><span data-stu-id="e21f4-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="e21f4-148">Dieses Feld darf nicht leer sein.</span><span class="sxs-lookup"><span data-stu-id="e21f4-148">This field cannot be blank.</span></span> <span data-ttu-id="e21f4-149">Weitere Informationen zur Verschlüsselung von Algorithmen finden Sie unter [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="e21f4-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="e21f4-150">**Serverzertifikat verwenden**</span><span class="sxs-lookup"><span data-stu-id="e21f4-150">**Use server certificate**</span></span>  
     <span data-ttu-id="e21f4-151">Legt fest, dass die Verschlüsselung durch ein Zertifikat gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="e21f4-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="e21f4-152">Wählen Sie einen Eintrag aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e21f4-152">Select one from the list.</span></span> <span data-ttu-id="e21f4-153">Wenn Sie nicht über die Berechtigung `VIEW DEFINITION` verfügen, ist diese Liste leer.</span><span class="sxs-lookup"><span data-stu-id="e21f4-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="e21f4-154">Wenn als Verschlüsselungsmethode das Zertifikat ausgewählt wird, darf dieser Wert nicht leer sein.</span><span class="sxs-lookup"><span data-stu-id="e21f4-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="e21f4-155">Weitere Informationen zu Zertifikaten finden Sie unter [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="e21f4-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="e21f4-156">**Asymmetrischen Serverschlüssel verwenden**</span><span class="sxs-lookup"><span data-stu-id="e21f4-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="e21f4-157">Legt fest, dass die Verschlüsselung durch einen asymmetrischen Schlüssel gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="e21f4-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="e21f4-158">Nur verfügbare asymmetrische Schlüssel werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="e21f4-159">Nur ein asymmetrischer von einem EKM-Modul geschützter Schlüssel kann mit TDE eine Datenbank verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="e21f4-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="e21f4-160">**Datenbankverschlüsselung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="e21f4-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="e21f4-161">Ändert die Datenbank, um TDE zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e21f4-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="e21f4-162">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="e21f4-163">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e21f4-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="e21f4-164">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e21f4-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e21f4-165">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e21f4-166">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="e21f4-167">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="e21f4-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e21f4-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="e21f4-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="e21f4-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="e21f4-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="e21f4-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="e21f4-173">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="e21f4-174">So verschieben Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="e21f4-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="e21f4-175">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e21f4-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e21f4-176">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Datenbank, die Sie oben verschlüsselt haben, zeigen Sie auf **Tasks**, und wählen Sie **Trennen...** aus.</span><span class="sxs-lookup"><span data-stu-id="e21f4-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="e21f4-177">Die folgenden Optionen sind im Dialogfeld **Datenbank trennen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e21f4-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="e21f4-178">**Zu trennende Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="e21f4-178">**Databases to detach**</span></span>  
     <span data-ttu-id="e21f4-179">Führt die zu trennenden Datenbanken auf.</span><span class="sxs-lookup"><span data-stu-id="e21f4-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="e21f4-180">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="e21f4-180">**Database Name**</span></span>  
     <span data-ttu-id="e21f4-181">Zeigt den Namen der zu trennenden Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="e21f4-182">**Verbindungen löschen**</span><span class="sxs-lookup"><span data-stu-id="e21f4-182">**Drop Connections**</span></span>  
     <span data-ttu-id="e21f4-183">Trennt die Verbindungen zu der angegebenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e21f4-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e21f4-184">Sie können eine Datenbank mit aktiven Verbindungen nicht trennen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="e21f4-185">**Statistikaktualisierung**</span><span class="sxs-lookup"><span data-stu-id="e21f4-185">**Update Statistics**</span></span>  
     <span data-ttu-id="e21f4-186">Standardmäßig werden durch den Trennvorgang beim Trennen der Datenbank die veralteten Optimierungsstatistiken beibehalten. Um die vorhandenen Optimierungsstatistiken zu aktualisieren, aktivieren Sie dieses Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="e21f4-187">**Volltextkataloge beibehalten**</span><span class="sxs-lookup"><span data-stu-id="e21f4-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="e21f4-188">Standardmäßig werden während des Trennvorgangs alle der Datenbank zugeordneten Volltextkataloge beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e21f4-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="e21f4-189">Um sie zu entfernen, deaktivieren Sie das Kontrollkästchen **Volltextkataloge beibehalten** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="e21f4-190">Diese Option wird nur beim Aktualisieren einer Datenbank von [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="e21f4-191">**Status**</span><span class="sxs-lookup"><span data-stu-id="e21f4-191">**Status**</span></span>  
     <span data-ttu-id="e21f4-192">Zeigt einen der folgenden Statuswerte an: **Ready** (Bereit) der **Not ready** (Nicht bereit).</span><span class="sxs-lookup"><span data-stu-id="e21f4-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="e21f4-193">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e21f4-193">**Message**</span></span>  
     <span data-ttu-id="e21f4-194">Unter **Meldung** können folgende Informationen zur Datenbank angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e21f4-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="e21f4-195">Wenn eine Datenbank an einer Replikation beteiligt ist, hat der **Status** den Wert **Nicht bereit** , und unter **Meldung** wird **Die Datenbank wurde repliziert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="e21f4-196">Wenn eine Datenbank über eine oder mehrere Verbindungen verfügt, weist der **Status** den Wert **Nicht bereit** auf, und in der Spalte **Meldung** wird _<Anzahl_aktiver_Verbindungen>_ **Aktive Verbindung(en)** angezeigt, z. B.: **1 Aktive Verbindung(en)** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="e21f4-197">Bevor Sie die Datenbank trennen können, müssen Sie durch Auswählen der Option **Verbindungen löschen**alle aktiven Verbindungen trennen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="e21f4-198">Weitere Informationen zu einer Meldung erhalten Sie, indem Sie auf den Linktext klicken, um den Aktivitätsmonitor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="e21f4-199">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="e21f4-200">Verwenden Sie den Windows-Explorer, um Datenbankdateien vom Quellserver an den gleichen Ort auf dem Zielserver zu verschieben oder zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="e21f4-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="e21f4-201">Verwenden Sie Windows-Explorer, um die Sicherung des Serverzertifikats und die Datei mit dem privaten Schlüssel vom Quellserver an den gleichen Ort auf dem Zielserver zu verschieben oder zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="e21f4-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="e21f4-202">Erstellen Sie für die Zielinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]einen Datenbank-Hauptschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e21f4-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e21f4-203">Weitere Informationen finden Sie weiter unten unter **Verwenden von Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="e21f4-204">Erstellen Sie anhand der entsprechenden Sicherungsdatei das Serverzertifikat neu.</span><span class="sxs-lookup"><span data-stu-id="e21f4-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="e21f4-205">Weitere Informationen finden Sie weiter unten unter **Verwenden von Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="e21f4-206">Klicken Sie im Objekt-Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] mit der rechten Maustaste auf den Ordner **Datenbanken**, und klicken Sie anschließend auf **Anfügen...** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="e21f4-207">Klicken Sie im Dialogfeld **Datenbanken anfügen** unter **Anzufügende Datenbanken**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="e21f4-208">Wählen Sie im Dialogfeld **Datenbankdateien suchen-**_server_name_ die Datenbankdatei aus, die dem neuen Server angefügt werden soll, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="e21f4-209">Die folgenden Optionen sind im Dialogfeld **Datenbanken anfügen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e21f4-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="e21f4-210">**Anzufügende Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="e21f4-210">**Databases to attach**</span></span>  
     <span data-ttu-id="e21f4-211">Zeigt Informationen zu den ausgewählten Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="e21f4-212">Zeigt ein Symbol an, das den Status des Anfügevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="e21f4-213">Die möglichen Symbole werden in der unten stehenden Beschreibung von **Status** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e21f4-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="e21f4-214">**Speicherort für MDF-Datei**</span><span class="sxs-lookup"><span data-stu-id="e21f4-214">**MDF File Location**</span></span>  
     <span data-ttu-id="e21f4-215">Zeigt den Pfad und den Dateinamen der ausgewählten MDF-Datei an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="e21f4-216">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="e21f4-216">**Database Name**</span></span>  
     <span data-ttu-id="e21f4-217">Zeigt den Namen der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="e21f4-218">**Anfügen als**</span><span class="sxs-lookup"><span data-stu-id="e21f4-218">**Attach As**</span></span>  
     <span data-ttu-id="e21f4-219">Gibt wahlweise einen anderen Namen für die anzufügende Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="e21f4-220">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="e21f4-220">**Owner**</span></span>  
     <span data-ttu-id="e21f4-221">Zeigt eine Dropdownliste mit möglichen Datenbankbesitzern an, aus der Sie wahlweise einen anderen Besitzer auswählen können.</span><span class="sxs-lookup"><span data-stu-id="e21f4-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="e21f4-222">**Status**</span><span class="sxs-lookup"><span data-stu-id="e21f4-222">**Status**</span></span>  
     <span data-ttu-id="e21f4-223">Zeigt den Status der Datenbank an (siehe folgende Tabelle).</span><span class="sxs-lookup"><span data-stu-id="e21f4-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="e21f4-224">Symbol</span><span class="sxs-lookup"><span data-stu-id="e21f4-224">Icon</span></span>|<span data-ttu-id="e21f4-225">Statustext</span><span class="sxs-lookup"><span data-stu-id="e21f4-225">Status text</span></span>|<span data-ttu-id="e21f4-226">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e21f4-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="e21f4-227">(Kein Symbol)</span><span class="sxs-lookup"><span data-stu-id="e21f4-227">(No icon)</span></span>|<span data-ttu-id="e21f4-228">(Kein Text)</span><span class="sxs-lookup"><span data-stu-id="e21f4-228">(No text)</span></span>|<span data-ttu-id="e21f4-229">Das Anfügen hat noch nicht begonnen oder steht für dieses Objekt noch aus.</span><span class="sxs-lookup"><span data-stu-id="e21f4-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="e21f4-230">Dies ist der Standardwert bei Öffnen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="e21f4-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="e21f4-231">Grünes, nach rechts zeigendes Dreieck</span><span class="sxs-lookup"><span data-stu-id="e21f4-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="e21f4-232">In Bearbeitung</span><span class="sxs-lookup"><span data-stu-id="e21f4-232">In progress</span></span>|<span data-ttu-id="e21f4-233">Das Anfügen hat begonnen, ist aber noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="e21f4-234">Grünes Häkchen</span><span class="sxs-lookup"><span data-stu-id="e21f4-234">Green check mark</span></span>|<span data-ttu-id="e21f4-235">Erfolg</span><span class="sxs-lookup"><span data-stu-id="e21f4-235">Success</span></span>|<span data-ttu-id="e21f4-236">Das Objekt wurde erfolgreich angefügt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="e21f4-237">Roter Kreis mit einem weißen Kreuz darin</span><span class="sxs-lookup"><span data-stu-id="e21f4-237">Red circle containing a white cross</span></span>|<span data-ttu-id="e21f4-238">Fehler</span><span class="sxs-lookup"><span data-stu-id="e21f4-238">Error</span></span>|<span data-ttu-id="e21f4-239">Beim Anfügen ist ein Fehler aufgetreten. Der Vorgang konnte deshalb nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e21f4-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="e21f4-240">Kreis mit zwei schwarzen Quadranten (links und rechts) und zwei weißen Quadranten (oben und unten) darin</span><span class="sxs-lookup"><span data-stu-id="e21f4-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="e21f4-241">Beendet</span><span class="sxs-lookup"><span data-stu-id="e21f4-241">Stopped</span></span>|<span data-ttu-id="e21f4-242">Das Anfügen wurde nicht erfolgreich abgeschlossen, weil der Benutzer den Vorgang angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="e21f4-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="e21f4-243">Kreis mit einem gekrümmten Pfeil darin, der entgegengesetzt der Uhrzeigerrichtung zeigt</span><span class="sxs-lookup"><span data-stu-id="e21f4-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="e21f4-244">Rollback wurde ausgeführt</span><span class="sxs-lookup"><span data-stu-id="e21f4-244">Rolled Back</span></span>|<span data-ttu-id="e21f4-245">Anfügen war erfolgreich, es wurde jedoch ein Rollback durchgeführt, weil beim Anfügen eines anderen Objekts ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e21f4-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="e21f4-246">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e21f4-246">**Message**</span></span>  
     <span data-ttu-id="e21f4-247">Zeigt entweder eine leere Meldung oder einen "Datei nicht gefunden"-Link an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="e21f4-248">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="e21f4-248">**Add**</span></span>  
     <span data-ttu-id="e21f4-249">Suchen Sie die erforderlichen Hauptdatenbankdateien.</span><span class="sxs-lookup"><span data-stu-id="e21f4-249">Find the necessary main database files.</span></span> <span data-ttu-id="e21f4-250">Wenn der Benutzer eine MDF-Datei auswählt, werden entsprechende Informationen automatisch in die jeweiligen Felder des Rasters **Anzufügende Datenbank** eingetragen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="e21f4-251">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e21f4-251">**Remove**</span></span>  
     <span data-ttu-id="e21f4-252">Entfernt die ausgewählte Datei aus dem Raster **Anzufügende Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="e21f4-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="e21f4-253">**"** _<datenbankname>_ **" Datenbankdetails**</span><span class="sxs-lookup"><span data-stu-id="e21f4-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="e21f4-254">Zeigt die Namen der anzufügenden Dateien an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="e21f4-255">Klicken Sie zum Überprüfen oder Ändern des Pfadnamens einer Datei auf die Schaltfläche **Durchsuchen** ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="e21f4-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e21f4-256">Wenn eine Datei nicht vorhanden ist, wird in der Spalte **Meldung** "Nicht gefunden" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e21f4-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="e21f4-257">Wenn keine Protokolldatei gefunden wird, liegt sie in einem anderen Verzeichnis oder wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e21f4-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="e21f4-258">Dann müssen Sie entweder den Dateipfad im Raster **Datenbankdetails** ändern, um auf den richtigen Pfad zu verweisen, oder die Protokolldatei aus dem Raster entfernen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="e21f4-259">Wenn keine .ndf-Datei gefunden wurde, müssen Sie ihren Pfad im Raster aktualisieren, um auf den richtigen Pfad zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e21f4-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="e21f4-260">**Originaldateiname**</span><span class="sxs-lookup"><span data-stu-id="e21f4-260">**Original File Name**</span></span>  
     <span data-ttu-id="e21f4-261">Zeigt den Namen der angefügten Datei an, die zur Datenbank gehört.</span><span class="sxs-lookup"><span data-stu-id="e21f4-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="e21f4-262">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="e21f4-262">**File Type**</span></span>  
     <span data-ttu-id="e21f4-263">Gibt den Dateityp an: **Datendatei** oder **Protokolldatei**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="e21f4-264">**Aktueller Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="e21f4-264">**Current File Path**</span></span>  
     <span data-ttu-id="e21f4-265">Zeigt den Pfad zur ausgewählten Datenbankdatei an</span><span class="sxs-lookup"><span data-stu-id="e21f4-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="e21f4-266">Die Pfadangabe kann manuell bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e21f4-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="e21f4-267">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e21f4-267">**Message**</span></span>  
     <span data-ttu-id="e21f4-268">Zeigt entweder eine leere Meldung oder einen „**Datei nicht gefunden**“-Hyperlink an.</span><span class="sxs-lookup"><span data-stu-id="e21f4-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="e21f4-269">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e21f4-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="e21f4-270">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e21f4-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e21f4-271">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e21f4-272">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e21f4-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="e21f4-273">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="e21f4-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e21f4-274">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="e21f4-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="e21f4-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="e21f4-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="e21f4-278">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e21f4-278">See Also</span></span>  
 [<span data-ttu-id="e21f4-279">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e21f4-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
