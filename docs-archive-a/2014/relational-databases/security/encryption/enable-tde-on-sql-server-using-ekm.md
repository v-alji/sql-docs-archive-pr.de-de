---
title: Aktivieren von TDE mithilfe von EKM | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725390"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="844c0-102">Aktivieren von TDE mit EKM</span><span class="sxs-lookup"><span data-stu-id="844c0-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="844c0-103">In diesem Thema wird beschrieben, wie die transparente Datenverschlüsselung (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] aktiviert wird, um einen Verschlüsselungsschlüssel für die Datenbank mithilfe eines asymmetrischen in einem erweiterbaren Schlüsselverwaltungsmodul mit (EKM) [!INCLUDE[tsql](../../../includes/tsql-md.md)]gespeicherten Schlüssels zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="844c0-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="844c0-104">TDE verschlüsselt die Speicherung einer gesamten Datenbank, indem ein symmetrischer Schlüssel verwendet wird, der als Datenbankverschlüsselungsschlüssel bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="844c0-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="844c0-105">Der Verschlüsselungsschlüssel für die Datenbank kann auch mithilfe eines Zertifikats geschützt werden, das mit dem Datenbank-Hauptschlüssel der Masterdatenbank geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="844c0-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="844c0-106">Weitere Informationen über das Schützen des Verschlüsselungsschlüssels für die Datenbank mit dem Datenbank-Hauptschlüssel finden Sie unter [Transparente Datenverschlüsselung &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="844c0-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="844c0-107">Informationen zum Konfigurieren von TDE, wenn [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf einem virtuellen Azure-Computer ausgeführt wird, finden Sie unter [Erweiterbare Schlüsselverwaltung mit Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="844c0-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="844c0-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="844c0-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="844c0-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="844c0-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="844c0-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="844c0-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="844c0-111">Security</span><span class="sxs-lookup"><span data-stu-id="844c0-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="844c0-112">So aktivieren Sie TDE unter Verwendung von EKM mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="844c0-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="844c0-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="844c0-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="844c0-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="844c0-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="844c0-115">Sie müssen ein Benutzer mit hohen Privilegien (z.&#160;B. ein Systemadministrator) sein, um einen Verschlüsselungsschlüssel für die Datenbank erstellen und eine Datenbank verschlüsseln zu können.</span><span class="sxs-lookup"><span data-stu-id="844c0-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="844c0-116">Dieser Benutzer muss vom EKM-Modul authentifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="844c0-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="844c0-117">Beim Starten muss [!INCLUDE[ssDE](../../../includes/ssde-md.md)] die Datenbank öffnen.</span><span class="sxs-lookup"><span data-stu-id="844c0-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="844c0-118">Dafür sollten Sie Anmeldeinformationen erstellen, die vom EKM authentifiziert werden, und sie einer Anmeldung hinzufügen, die auf einem asymmetrischen Schlüssel basiert.</span><span class="sxs-lookup"><span data-stu-id="844c0-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="844c0-119">Benutzer können sich mit dieser Anmeldung nicht anmelden, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] ist aber in der Lage, sich beim EKM-Gerät selbst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="844c0-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="844c0-120">Wenn der im EKM-Modul gespeicherte asymmetrische Schlüssel verloren geht, kann die Datenbank nicht von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="844c0-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="844c0-121">Wenn der Anbieter für erweiterbare Schlüsselverwaltung eine Sicherung des asymmetrischen Schlüssels erlaubt, sollten Sie eine Sicherung erstellen und diese an einem sicheren Ort aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="844c0-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="844c0-122">Die für Ihren EKM-Anbieter erforderlichen Optionen und Parameter können sich von denen im unten angegebenen Codebeispiel unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="844c0-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="844c0-123">Weitere Informationen erhalten Sie vom Anbieter für erweiterbare Schlüsselverwaltung.</span><span class="sxs-lookup"><span data-stu-id="844c0-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="844c0-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="844c0-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="844c0-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="844c0-125">Permissions</span></span>  
 <span data-ttu-id="844c0-126">In diesem Thema werden die folgenden Berechtigungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="844c0-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="844c0-127">Zum Ändern einer Konfigurationsoption und Ausführen der RECONFIGURE-Anweisung muss Ihnen die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="844c0-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="844c0-128">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="844c0-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="844c0-129">Erfordert die ALTER ANY CREDENTIAL-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="844c0-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="844c0-130">Erfordert die ALTER ANY LOGIN-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="844c0-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="844c0-131">Erfordert die CREATE ASYMMETRIC KEY-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="844c0-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="844c0-132">Erfordert die CONTROL-Berechtigung für die Datenbank, um die Datenbank zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="844c0-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="844c0-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="844c0-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="844c0-134">So aktivieren Sie TDE unter Verwendung von EKM</span><span class="sxs-lookup"><span data-stu-id="844c0-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="844c0-135">Kopieren Sie die Dateien, die vom Anbieter für erweiterbare Schlüsselverwaltung bereitgestellt wurden, an einen geeigneten Speicherort auf dem Computer mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="844c0-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="844c0-136">In diesem Beispiel wird der Ordner **C:\EKM** verwendet.</span><span class="sxs-lookup"><span data-stu-id="844c0-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="844c0-137">Installieren Sie Zertifikate auf dem Computer, die ggf. vom Anbieter für erweiterbare Schlüsselverwaltung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="844c0-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="844c0-138">stellt keinen Anbieter für erweiterbare Schlüsselverwaltung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="844c0-138">does not supply an EKM provider.</span></span> <span data-ttu-id="844c0-139">Jeder Anbieter für erweiterbare Schlüsselverwaltung kann über andere Prozeduren zum Installieren, Konfigurieren und Autorisieren von Benutzern verfügen.</span><span class="sxs-lookup"><span data-stu-id="844c0-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="844c0-140">Schlagen Sie in der Dokumentation Ihres Anbieters für erweiterbare Schlüsselverwaltung nach, um diesen Schritt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="844c0-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="844c0-141">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="844c0-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="844c0-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="844c0-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="844c0-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="844c0-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="844c0-144">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="844c0-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="844c0-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="844c0-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="844c0-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="844c0-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="844c0-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="844c0-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="844c0-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="844c0-152">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="844c0-153">Erweiterbare Schlüsselverwaltung mit Azure Key Vault &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="844c0-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="844c0-154">Transparent Data Encryption mit Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="844c0-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
