---
title: 'Lektion 8: Wiederherstellen einer Datenbank in Azure Storage | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622081"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="f5175-103">Lektion 8:</span><span class="sxs-lookup"><span data-stu-id="f5175-103">Lesson 8.</span></span> <span data-ttu-id="f5175-104">Wiederherstellen einer Datenbank in Azure Storage</span><span class="sxs-lookup"><span data-stu-id="f5175-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="f5175-105">In dieser Lektion erfahren Sie, wie Sie eine Sicherungsdatei lokal erstellen und anschließend in Azure Storage wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f5175-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="f5175-106">Beachten Sie, dass Sie Ihre Datenbank entweder lokal oder auf einem virtuellen Computer in Azure haben können.</span><span class="sxs-lookup"><span data-stu-id="f5175-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="f5175-107">Für diese Lektion müssen Sie Lektion 4, 5, 6 und 7 nicht abschließen.</span><span class="sxs-lookup"><span data-stu-id="f5175-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="f5175-108">In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="f5175-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="f5175-109">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="f5175-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="f5175-110">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5175-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="f5175-111">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5175-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="f5175-112">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="f5175-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="f5175-113">Sie haben SQL Server-Anmeldeinformationen auf dem Quellcomputer basierend auf der Shared Access Signature erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5175-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="f5175-114">Sie haben eine Datenbank auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5175-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="f5175-115">Führen Sie die folgenden Schritte aus, um die Azure Storage einer Datenbank wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="f5175-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="f5175-116">Starten Sie SQL Server Management Studio auf dem Quellcomputer.</span><span class="sxs-lookup"><span data-stu-id="f5175-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="f5175-117">Wenn Sie mit der neu erstellten Datenbank verbunden sind, öffnen Sie das Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="f5175-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="f5175-118">Führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="f5175-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="f5175-119">Kopieren Sie als Nächstes folgende Anweisungen in das Abfragefenster, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="f5175-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="f5175-120">Am Ende dieses Schritts sollte der Container Daten (.mdf) und Dateien (.ldf) im Verwaltungsportal auflisten.</span><span class="sxs-lookup"><span data-stu-id="f5175-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="f5175-121">Führen Sie zum Wiederherstellen einer Datenbank mit Daten-und Protokolldateien, die auf Azure Storage mithilfe SQL Server Management Studio Benutzeroberfläche verweisen, die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f5175-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="f5175-122">Klicken Sie in **Objekt-Explorer**auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f5175-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f5175-123">Erweitern Sie **Datenbanken**, und wählen Sie Ihre Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="f5175-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="f5175-124">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="f5175-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="f5175-125">Klicken Sie auf der Seite **Allgemein** im Abschnitt **Wiederherstellungs** Quelle auf **Quell** Gerät.</span><span class="sxs-lookup"><span data-stu-id="f5175-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="f5175-126">Klicken Sie im Textfeld **Quell** Gerät auf die Schaltfläche Durchsuchen, um das Dialogfeld **Sicherungsmedien auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f5175-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="f5175-127">Wählen Sie im Textfeld Sicherungsmedien die Option **Datei**aus, und klicken Sie auf die Schaltfläche **Hinzufügen** , um die Sicherungsdatei (. bak) zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f5175-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="f5175-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5175-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="f5175-129">Klicken Sie auf der ersten Seite auf **Dateien** .</span><span class="sxs-lookup"><span data-stu-id="f5175-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="f5175-130">Geben Sie im Abschnitt **Datenbankdateien wiederherstellen** als im Feld **Wiederherstellen als** den folgenden Wert ein:</span><span class="sxs-lookup"><span data-stu-id="f5175-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="f5175-131">Geben Sie für Datendatei Folgendes ein: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="f5175-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="f5175-132">Geben Sie für Protokolldatei Folgendes ein: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="f5175-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="f5175-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5175-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="f5175-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5175-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="f5175-135">Wenn die Wiederherstellung abgeschlossen ist, melden Sie sich beim Verwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="f5175-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="f5175-136">Sie sollten in der Lage sein, die .mdf- und .ldf-Dateien im Container wie folgt anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="f5175-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="f5175-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="f5175-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="f5175-138">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="f5175-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="f5175-139">Lektion 9. Wiederherstellen einer Datenbank aus Azure Storage</span><span class="sxs-lookup"><span data-stu-id="f5175-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
