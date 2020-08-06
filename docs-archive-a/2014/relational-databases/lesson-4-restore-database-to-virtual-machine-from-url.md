---
title: Lektion 5. Optionale Verschlüsseln der Datenbank mit TDE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619116"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="54333-103">Lektion 5.</span><span class="sxs-lookup"><span data-stu-id="54333-103">Lesson 5.</span></span> <span data-ttu-id="54333-104">(Optional) Verschlüsseln Ihrer Datenbank anhand von TDE</span><span class="sxs-lookup"><span data-stu-id="54333-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="54333-105">Optional können Sie die neu erstellte Datenbank verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="54333-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="54333-106">Die transparente Datenverschlüsselung (TDE) führt die E/A-Verschlüsselung und -Entschlüsselung der Daten und der Protokolldateien in Echtzeit durch.</span><span class="sxs-lookup"><span data-stu-id="54333-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="54333-107">Diese Art der Verschlüsselung verwendet einen Verschlüsselungsschlüssel für die Datenbank (Database Encryption Key, DEK), der in der Datenbankstartseite gespeichert wird, damit er während der Wiederherstellung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="54333-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="54333-108">Weitere Informationen finden Sie unter [transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) und [Verschieben einer TDE-geschützten Datenbank auf eine andere SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="54333-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="54333-109">In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="54333-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="54333-110">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="54333-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="54333-111">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="54333-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="54333-112">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="54333-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="54333-113">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="54333-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="54333-114">Sie haben die SQL Server-Anmeldeinformationen auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="54333-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="54333-115">Sie haben eine Datenbank erstellt, indem Sie die Schritte ausgeführt haben, die in Lektion 4 beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="54333-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="54333-116">Wenn Sie eine Datenbank verschlüsseln möchten, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="54333-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="54333-117">Ändern Sie folgende Anweisungen, und führen Sie sie auf dem Quellcomputer in einem Abfragefenster aus:</span><span class="sxs-lookup"><span data-stu-id="54333-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="54333-118">Verschlüsseln Sie anschließend die neue Datenbank auf dem Quellcomputer, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="54333-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="54333-119">Wenn Sie Informationen zum Verschlüsselungsstatus einer Datenbank und zu den ihr zugeordneten Verschlüsselungsschlüsseln erhalten möchten, führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="54333-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="54333-120">Ausführliche Informationen zu den in dieser Lektion verwendeten Transact-SQL-Anweisungen finden Sie unter [Create Database &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [Create Master Key &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [Create Certificate &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql)und [sys. dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54333-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="54333-121">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="54333-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="54333-122">Lektion 6: Migrieren einer Datenbank von einem lokalen Quellcomputer zu einem Zielcomputer in Azure</span><span class="sxs-lookup"><span data-stu-id="54333-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
