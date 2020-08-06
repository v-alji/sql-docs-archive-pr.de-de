---
title: 'Lektion 7: Verschieben der Datendateien in Azure Storage | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620368"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="7684e-102">Lektion 7: Verschieben von Datendateien nach Azure Storage</span><span class="sxs-lookup"><span data-stu-id="7684e-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="7684e-103">In dieser Lektion erfahren Sie, wie Sie Ihre Datendateien in Azure Storage (aber nicht in Ihre SQL Server Instanz) verschieben.</span><span class="sxs-lookup"><span data-stu-id="7684e-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="7684e-104">Für diese Lektion müssen Sie Lektion 4, 5 und 6 nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="7684e-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="7684e-105">Wenn Sie die Datendateien in Azure Storage verschieben möchten, können Sie die-Anweisung verwenden, um `ALTER DATABASE` den Speicherort der Datendateien zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7684e-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="7684e-106">In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="7684e-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="7684e-107">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="7684e-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="7684e-108">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="7684e-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="7684e-109">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="7684e-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="7684e-110">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="7684e-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="7684e-111">Sie haben die SQL Server-Anmeldeinformationen auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="7684e-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="7684e-112">Führen Sie als nächstes die folgenden Schritte aus, um die Datendateien in Azure Storage zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="7684e-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="7684e-113">Erstellen Sie zunächst eine Testdatenbank auf dem Quellcomputer, und fügen Sie einige Daten hinzu.</span><span class="sxs-lookup"><span data-stu-id="7684e-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="7684e-114">Führen Sie den folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="7684e-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="7684e-115">Wenn Sie dies ausführen, wird folgende Meldung angezeigt: "die Datei" TestDB1Alter "wurde im System Katalog geändert.</span><span class="sxs-lookup"><span data-stu-id="7684e-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="7684e-116">Der neue Pfad wird beim nächsten Start der Datenbank verwendet. "</span><span class="sxs-lookup"><span data-stu-id="7684e-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="7684e-117">Schalten Sie dann die Datenbank offline.</span><span class="sxs-lookup"><span data-stu-id="7684e-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="7684e-118">Nun müssen Sie die Datendateien mit einer der folgenden Methoden in Azure Storage kopieren: [azcopy-Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx)oder ein Drittanbieter-Speicher-Explorer-Tool.</span><span class="sxs-lookup"><span data-stu-id="7684e-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="7684e-119">**Wichtig:** Wenn Sie diese neue Erweiterung verwenden, stellen Sie immer sicher, dass Sie ein seitenblob und kein blockblob erstellen.</span><span class="sxs-lookup"><span data-stu-id="7684e-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="7684e-120">Schalten Sie dann die Datenbank online.</span><span class="sxs-lookup"><span data-stu-id="7684e-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="7684e-121">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="7684e-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="7684e-122">Lektion 8. Wiederherstellen einer Datenbank auf Azure Storage</span><span class="sxs-lookup"><span data-stu-id="7684e-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
