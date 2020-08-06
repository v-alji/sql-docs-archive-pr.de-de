---
title: 'Lektion 9: Wiederherstellen einer Datenbank aus Azure Storage | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622080"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="2ce44-103">Lektion 9:</span><span class="sxs-lookup"><span data-stu-id="2ce44-103">Lesson 9.</span></span> <span data-ttu-id="2ce44-104">Wiederherstellen einer Datenbank aus Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2ce44-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="2ce44-105">In dieser Lektion erfahren Sie, wie Sie eine Daten Bank Sicherungsdatei aus Azure Storage in einer Datenbank wiederherstellen, die sich entweder lokal oder auf einem virtuellen Computer in Azure befindet.</span><span class="sxs-lookup"><span data-stu-id="2ce44-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="2ce44-106">Für diese Lektion müssen Sie Lektion 4, 5, 6, 7 und 8 nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="2ce44-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="2ce44-107">In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="2ce44-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="2ce44-108">Sie haben eine Datenbank auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ce44-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="2ce44-109">Sie haben mithilfe des Features [SQL Server Sicherung und Wiederherstellung mit Azure BLOB Storage Dienst](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) eine Sicherung der-Datenbank (BAK) in Azure Storage erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ce44-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="2ce44-110">Beachten Sie, dass Sie in diesem Schritt andere SQL Server-Anmeldeinformationen erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="2ce44-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="2ce44-111">Diese Anmeldeinformationen verwenden Speicherkontoschlüssel.</span><span class="sxs-lookup"><span data-stu-id="2ce44-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="2ce44-112">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="2ce44-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2ce44-113">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ce44-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2ce44-114">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ce44-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="2ce44-115">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="2ce44-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="2ce44-116">Sie haben eine SQL Server Anmelde Informationen auf Ihrem Computer erstellt, um Azure Storage-Integrations Feature zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ce44-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="2ce44-117">Beachten Sie, dass diese Anmeldeinformationen einen Shared Access Signature (SAS)-Schlüssel erfordern.</span><span class="sxs-lookup"><span data-stu-id="2ce44-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="2ce44-118">Zum Wiederherstellen einer Datenbank aus Azure Storage können Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce44-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="2ce44-119">Starten Sie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2ce44-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="2ce44-120">Stellen Sie eine Verbindung mit der Standardinstanz her.</span><span class="sxs-lookup"><span data-stu-id="2ce44-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="2ce44-121">Klicken Sie auf der Standard Symbolleiste auf **neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="2ce44-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="2ce44-122">Kopieren Sie das folgenden komplette Skript, und fügen Sie es in das Abfrage-Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="2ce44-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="2ce44-123">Ändern Sie das Skript nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="2ce44-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="2ce44-124">**Hinweis:** Sie führen die- `RESTORE` Anweisung aus, um die Datenbanksicherung (BAK) in Azure Storage in einer Daten Bank Instanz auf einem anderen Computer wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="2ce44-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="2ce44-125">**Ende des Tutorials: SQL Server von Datendateien in Azure Storage Dienst**</span><span class="sxs-lookup"><span data-stu-id="2ce44-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
