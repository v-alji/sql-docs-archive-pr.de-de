---
title: Sichern, wiederherstellen und Verschieben des SSIS-Katalogs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616661"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="307d9-102">Sichern, Wiederherstellen und Verschieben des SSIS-Katalogs</span><span class="sxs-lookup"><span data-stu-id="307d9-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="307d9-103">schließt die SSISDB-Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="307d9-103">includes the SSISDB database.</span></span> <span data-ttu-id="307d9-104">Sie können Sichten in der SSISDB-Datenbank abfragen, um im **SSISDB** -Katalog gespeicherte Objekte, Einstellungen und operative Daten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="307d9-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="307d9-105">Dieses Thema enthält Anweisungen zum Sichern und Wiederherstellen der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="307d9-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="307d9-106">Der **SSISDB**-Katalog speichert die Pakete, die Sie auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="307d9-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="307d9-107">Weitere Informationen zum Katalog finden Sie unter [SSIS-Katalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="307d9-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="307d9-108">So sichern Sie die SSIS-Datenbank</span><span class="sxs-lookup"><span data-stu-id="307d9-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="307d9-109">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="307d9-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="307d9-110">Sichern Sie den Hauptschlüssel für die SSISDB-Datenbank, indem Sie die Anweisung BACKUP MASTER KEY (Transact-SQL) verwenden.</span><span class="sxs-lookup"><span data-stu-id="307d9-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="307d9-111">Der Schlüssel wird in einer von Ihnen angegebenen Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="307d9-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="307d9-112">Verwenden Sie ein Kennwort, um den Hauptschlüssel in der Datei zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="307d9-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="307d9-113">Weitere Informationen zur Anweisung finden Sie unter [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="307d9-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="307d9-114">Im folgenden Beispiel wird der Hauptschlüssel in die Datei `c:\temp directory\RCTestInstKey` exportiert.</span><span class="sxs-lookup"><span data-stu-id="307d9-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="307d9-115">Das `LS2Setup!` -Kennwort wird zum Verschlüsseln des Hauptschlüssels verwendet.</span><span class="sxs-lookup"><span data-stu-id="307d9-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="307d9-116">Sichern Sie die SSISDB-Datenbank mit dem Dialogfeld **Datenbank sichern** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="307d9-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="307d9-117">Weitere Informationen finden Sie unter [Vorgehensweise: Sichern einer Datenbank (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="307d9-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="307d9-118">Generieren Sie das CREATE LOGIN-Skript für ##MS_SSISServerCleanupJobLogin ##, indem Sie wie folgt vorgehen.</span><span class="sxs-lookup"><span data-stu-id="307d9-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="307d9-119">Weitere Informationen finden Sie unter [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="307d9-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="307d9-120">Erweitern Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]im Objekt-Explorer die Knoten **Sicherheit** und **Anmeldungen** .</span><span class="sxs-lookup"><span data-stu-id="307d9-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="307d9-121">Klicken Sie mit der rechten Maustaste auf **##MS_SSISServerCleanupJobLogin##** , und klicken Sie dann auf **Skript für Anmeldenamen als** > **CREATE in** > **Neues Abfrage-Editor-Fenster**.</span><span class="sxs-lookup"><span data-stu-id="307d9-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="307d9-122">Wenn Sie die SSISDB-Datenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz wiederherstellen, auf der der SSISDB-Katalog nie erstellt wurde, generieren Sie das CREATE PROCEDURE-Skript wie folgt für sp_ssis_startup.</span><span class="sxs-lookup"><span data-stu-id="307d9-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="307d9-123">Weitere Informationen finden Sie unter [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="307d9-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="307d9-124">Erweitern Sie in Objekt-Explorer den Knoten **Datenbanken** , und erweitern Sie dann den Knoten **System Datenbanken**  >  **Master**  >  **Programmierbarkeit**  >  **gespeicherte Prozeduren** .</span><span class="sxs-lookup"><span data-stu-id="307d9-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="307d9-125">Klicken Sie mit der rechten Maustaste auf **dbo.sp_ssis_startup**, und klicken Sie dann auf **Skript für gespeicherte Prozeduren als** > **CREATE in** > **Neues Abfrage-Editor-Fenster**.</span><span class="sxs-lookup"><span data-stu-id="307d9-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="307d9-126">Bestätigen Sie, dass der SQL Server-Agent gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="307d9-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="307d9-127">Wenn Sie die SSISDB-Datenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz wiederherstellen, auf der der SSISDB-Katalog nie erstellt wurde, generieren Sie wie folgt ein Skript für den SSIS-Server-Wartungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="307d9-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="307d9-128">Das Skript wird bei Erstellung des SSISDB-Katalogs automatisch im [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent erstellt.</span><span class="sxs-lookup"><span data-stu-id="307d9-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="307d9-129">Der Auftrag hilft beim Bereinigen von Bereinigungsvorgangsprotokollen außerhalb der Beibehaltungsdauer und entfernt ältere Projektversionen.</span><span class="sxs-lookup"><span data-stu-id="307d9-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="307d9-130">Erweitern Sie im Objekt-Explorer den Knoten **SQL Server-Agent** und dann den Knoten **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="307d9-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="307d9-131">Klicken Sie mit der rechten Maustaste auf SSIS-Server Wartungsauftrag, und klicken Sie dann auf **Skript für Auftrag als**  >  **Create to**  >  **New Query Editor Window**</span><span class="sxs-lookup"><span data-stu-id="307d9-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="307d9-132">So stellen Sie die SSIS-Datenbank wieder her</span><span class="sxs-lookup"><span data-stu-id="307d9-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="307d9-133">Wenn Sie die SSISDB-Datenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz wiederherstellen, auf der der SSISDB-Katalog nie erstellt wurde, aktivieren Sie Common Language Runtime (clr), indem Sie die gespeicherte Prozedur sp_configure ausführen.</span><span class="sxs-lookup"><span data-stu-id="307d9-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="307d9-134">Weitere Informationen finden Sie unter [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) und [CLR-fähig (Option)](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="307d9-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="307d9-135">Wenn Sie die SSISDB-Datenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz wiederherstellen, auf der der SSISDB-Katalog nie erstellt wurde, erstellen Sie den asymmetrischen Schlüssel und den Anmeldenamen aus dem asymmetrischen Schlüssel, und gewähren Sie dem Anmeldenamen die UNSAFE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="307d9-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="307d9-136">-CLR-gespeicherte Prozeduren erfordern UNSAFE-Berechtigungen, die der Anmeldung gewährt werden müssen, da die Anmeldung einen zusätzlichen Zugriff auf eingeschränkte Ressourcen (z. B. die Microsoft Win32-API) benötigt.</span><span class="sxs-lookup"><span data-stu-id="307d9-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="307d9-137">Weitere Informationen zur UNSAFE-Codeberechtigung finden Sie unter [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="307d9-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="307d9-138">Stellen Sie die SSISDB-Datenbank über die Sicherung wieder her. Verwenden Sie dazu das Dialogfeld **Datenbank wiederherstellen** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="307d9-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="307d9-139">Weitere Informationen finden Sie in den nachfolgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="307d9-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="307d9-140">Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="307d9-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="307d9-141">Datenbank wiederherstellen &#40;Seite Dateien&#41;</span><span class="sxs-lookup"><span data-stu-id="307d9-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="307d9-142">Datenbank wiederherstellen &#40;Seite Optionen&#41;</span><span class="sxs-lookup"><span data-stu-id="307d9-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="307d9-143">Führen Sie die Skripts aus, die Sie in [So sichern Sie die SSIS-Datenbank](#backup) für ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup und den SSIS-Serverwartungsauftrag erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="307d9-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="307d9-144">Bestätigen Sie, dass der SQL Server-Agent gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="307d9-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="307d9-145">Führen Sie die folgende Anweisung aus, um die Prozedur "sp_ssis_startup" für die automatische Ausführung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="307d9-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="307d9-146">Weitere Informationen finden Sie unter [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="307d9-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="307d9-147">Ordnen Sie den SSISDB-Benutzer ##MS_SSISServerCleanupJobUser## (SSISDB-Datenbank) ##MS_SSISServerCleanupJobLogin## zu, indem Sie das Dialogfeld **Anmeldungseigenschaften** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="307d9-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="307d9-148">Verwenden Sie zum Sichern des Hauptschlüssels eine der folgenden Methoden.</span><span class="sxs-lookup"><span data-stu-id="307d9-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="307d9-149">Weitere Informationen zur Verschlüsselung finden Sie unter [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="307d9-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="307d9-150">**Methode 1:**</span><span class="sxs-lookup"><span data-stu-id="307d9-150">**Method 1**</span></span>  
  
         <span data-ttu-id="307d9-151">Verwenden Sie diese Methode, wenn Sie bereits eine Sicherung des Datenbank-Hauptschlüssels ausgeführt haben und Sie über das Kennwort verfügen, das verwendet wurde, um den Hauptschlüssel zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="307d9-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="307d9-152">Bestätigen Sie, dass das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienstkonto über Berechtigungen verfügt, die Sicherungsschlüsseldatei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="307d9-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="307d9-153">Es wird die folgende Warnmeldung in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] angezeigt, wenn der Datenbank-Hauptschlüssel noch nicht vom Diensthauptschlüssel verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="307d9-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="307d9-154">Ignorieren Sie die Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="307d9-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="307d9-155">**Der aktuelle Hauptschlüssel kann nicht entschlüsselt werden. Dieser Fehler wurde ignoriert, weil die Option FORCE angegeben war.**</span><span class="sxs-lookup"><span data-stu-id="307d9-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="307d9-156">Das FORCE-Argument gibt an, dass der Wiederherstellungsprozess fortfahren sollte, auch wenn der aktuelle Datenbank-Hauptschlüssel nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="307d9-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="307d9-157">Diese Meldung wird für den SSISDB-Katalog angezeigt, da der Datenbank-Hauptschlüssel noch nicht auf der Instanz geöffnet wurde, auf der Sie die Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="307d9-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="307d9-158">**Methode 2:**</span><span class="sxs-lookup"><span data-stu-id="307d9-158">**Method 2**</span></span>  
  
         <span data-ttu-id="307d9-159">Verwenden Sie diese Methode, wenn Sie über das ursprüngliche Kennwort verfügen, das verwendet wurde, um SSISDB zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="307d9-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="307d9-160">Bestimmen Sie, ob das SSISDB-Katalogschema und die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Binärdateien (ISServerExec-Assembly und SQLCLR-Assembly) kompatibel sind, indem Sie [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version)ausführen.</span><span class="sxs-lookup"><span data-stu-id="307d9-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="307d9-161">Um zu bestätigen, dass die SSISDB-Datenbank erfolgreich wiederhergestellt wurde, führen Sie Vorgänge für den SSISDB-Katalog aus, beispielsweise das Ausführen von Paketen, die auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="307d9-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="307d9-162">Weitere Informationen finden Sie unter [Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="307d9-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="307d9-163">So verschieben Sie die SSIS-Datenbank</span><span class="sxs-lookup"><span data-stu-id="307d9-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="307d9-164">Folgen Sie den Anweisungen zum Verschieben von Benutzerdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="307d9-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="307d9-165">Weitere Informationen finden Sie unter [Move User Databases](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="307d9-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="307d9-166">Stellen Sie sicher, dass Sie den Hauptschlüssel für die SSISDB-Datenbank sichern und die Sicherungsdatei schützen.</span><span class="sxs-lookup"><span data-stu-id="307d9-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="307d9-167">Weitere Informationen finden Sie unter [So sichern Sie die SSIS-Datenbank](#backup).</span><span class="sxs-lookup"><span data-stu-id="307d9-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="307d9-168">Stellen Sie sicher, dass die für Integration Services (SSIS) relevanten Objekte in der neuen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz erstellt werden, auf der der SSISDB-Katalog noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="307d9-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
