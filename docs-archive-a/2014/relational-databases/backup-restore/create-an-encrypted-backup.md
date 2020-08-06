---
title: Erstellen einer verschlüsselten Sicherung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723954"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="bf72d-102">Erstellen einer verschlüsselten Sicherung</span><span class="sxs-lookup"><span data-stu-id="bf72d-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="bf72d-103">Dieses Thema beschreibt die Schritte, die notwendig sind, um eine verschlüsselte Sicherung mit Transact-SQL zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf72d-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="bf72d-104">Sicherung auf Datenträger mit Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="bf72d-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="bf72d-105">**Voraussetzungen:**</span><span class="sxs-lookup"><span data-stu-id="bf72d-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="bf72d-106">Zugriff auf einen lokalen Datenträger oder Speicher mit ausreichendem Speicherplatz, um eine Sicherung der Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf72d-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="bf72d-107">Ein Datenbank-Hauptschlüssel für die Masterdatenbank und ein Zertifikat oder ein asymmetrischer Schlüssel, das bzw. der für die SQL Server-Instanz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bf72d-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="bf72d-108">Informationen zu Verschlüsselungsanforderungen und Berechtigungen finden Sie unter [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="bf72d-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="bf72d-109">Führen Sie die folgenden Schritte aus, um eine verschlüsselte Sicherung einer Datenbank auf einem lokalen Datenträger zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf72d-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="bf72d-110">In diesem Beispiel wird eine Benutzerdatenbank mit dem Namen MyTestDB verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf72d-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="bf72d-111">**Erstellen eines Datenbankhauptschlüssels der Masterdatenbank:** Wählen Sie ein Kennwort aus, mit dem die in der Datenbank gespeicherte Kopie des Datenbank-Hauptschlüssels verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="bf72d-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="bf72d-112">Stellen Sie eine Verbindung mit der Datenbank-Engine her, öffnen Sie ein neues Abfragefenster, kopieren Sie das folgende Beispiel, fügen Sie es ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="bf72d-113">**Erstellen eines Sicherungszertifikats:** Erstellen Sie ein Sicherungszertifikat in der Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="bf72d-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="bf72d-114">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="bf72d-115">**Sichern der Datenbank:** Geben Sie den Verschlüsselungsalgorithmus und das Zertifikat an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf72d-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="bf72d-116">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="bf72d-117">Ein Beispiel zum Verschlüsseln einer durch EKM geschützten Sicherung finden Sie unter [Erweiterbare Schlüsselverwaltung mit Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bf72d-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="bf72d-118">Sichern im Azure Storage mit Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="bf72d-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="bf72d-119">Wenn Sie eine Sicherung in Azure Storage mithilfe der Option **SQL Server-Sicherung über URL** erstellen, sind die Verschlüsselungsschritte die gleichen, aber Sie müssen URL als Ziel und SQL-Anmeldeinformationen verwenden, um sich beim Azure-Speicher zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bf72d-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="bf72d-120">Wenn Sie [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] mit Verschlüsselungsoptionen konfigurieren möchten, finden Sie weitere Informationen unter [Einrichten SQL Server verwalteten Sicherung in Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) und [Einrichten SQL Server verwalteten Sicherung in Azure für Verfügbarkeits Gruppen](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bf72d-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="bf72d-121">**Voraussetzungen:**</span><span class="sxs-lookup"><span data-stu-id="bf72d-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="bf72d-122">Ein Windows-Speicherkonto und ein Container.</span><span class="sxs-lookup"><span data-stu-id="bf72d-122">A windows storage account and a container.</span></span> <span data-ttu-id="bf72d-123">Weitere Informationen finden Sie weiter oben unter</span><span class="sxs-lookup"><span data-stu-id="bf72d-123">For more information, see.</span></span> <span data-ttu-id="bf72d-124">[Lektion 1: Erstellen von Azure Storage-Objekten](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bf72d-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="bf72d-125">Ein Datenbank-Hauptschlüssel für die Masterdatenbank und ein Zertifikat oder ein asymmetrischer Schlüssel in der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="bf72d-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="bf72d-126">Informationen zu Verschlüsselungsanforderungen und Berechtigungen finden Sie unter [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="bf72d-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="bf72d-127">**Erstellen von SQL Server-Anmeldeinformationen:** Um SQL Server-Anmeldeinformationen zu erstellen, stellen Sie zunächst eine Verbindung mit der Datenbank-Engine her. Öffnen Sie dann ein neues Abfragefenster, kopieren Sie das folgende Beispiel, fügen Sie es ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="bf72d-128">**Erstellen Sie einen Datenbank-Hauptschlüssel:** Wählen Sie ein Kennwort aus, mit dem die in der Datenbank gespeicherte Kopie des Datenbank-Hauptschlüssels verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="bf72d-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="bf72d-129">Stellen Sie eine Verbindung mit der Datenbank-Engine her, öffnen Sie ein neues Abfragefenster, kopieren Sie das folgende Beispiel, fügen Sie es ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="bf72d-130">**Erstellen eines Sicherungszertifikats:** Erstellen Sie ein Sicherungszertifikat in der Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="bf72d-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="bf72d-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="bf72d-132">**Sichern der Datenbank:** Geben Sie den Verschlüsselungsalgorithmus und das Zertifikat an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf72d-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="bf72d-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf72d-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
