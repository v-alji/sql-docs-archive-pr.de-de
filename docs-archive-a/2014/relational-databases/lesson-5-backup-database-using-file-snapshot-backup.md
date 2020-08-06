---
title: 'Lektion 6: Migrieren einer Datenbank von einem lokalen Quellcomputer zu einem Zielcomputer in Azure | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620369"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="bfc0c-102">Lektion 6: Migrieren einer Datenbank von einem lokalen Quellcomputer zu einem Zielcomputer in Azure</span><span class="sxs-lookup"><span data-stu-id="bfc0c-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="bfc0c-103">In dieser Lektion wird davon ausgegangen, dass Sie bereits über eine andere SQL Server verfügen, die sich möglicherweise auf einem anderen lokalen Computer oder auf einem virtuellen Computer in Azure befindet.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="bfc0c-104">Informationen zum Erstellen eines virtuellen SQL Server virtuellen Computers in Azure finden Sie unter Bereitstellen [eines virtuellen SQL Server](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/)Computers in Azure.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="bfc0c-105">Stellen Sie nach der Bereitstellung einer SQL Server virtuellen Maschine in Azure sicher, dass Sie über SQL Server Management Studio auf einem anderen Computer eine Verbindung mit einer Instanz von SQL Server auf diesem virtuellen Computer herstellen können.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="bfc0c-106">In dieser Lektion wird auch davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="bfc0c-107">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="bfc0c-108">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="bfc0c-109">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="bfc0c-110">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="bfc0c-111">Sie haben die SQL Server-Anmeldeinformationen auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="bfc0c-112">Sie haben bereits einen Ziel SQL Server virtuellen Computer in Azure erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="bfc0c-113">Es wird empfohlen, dass Sie diesen erstellen, indem Sie ein Plattformimage mit SQL Server 2014 auswählen.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="bfc0c-114">Führen Sie die folgenden Schritte aus, um eine Datenbank von SQL Server lokal zu einem anderen virtuellen Computer in Azure zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="bfc0c-115">Öffnen Sie auf dem Quellcomputer (in diesem Lernprogramm ein lokaler Computer) ein Abfragefenster in SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="bfc0c-116">Trennen Sie die Datenbank, um sie auf einen anderen Computer zu verschieben, indem Sie folgende Anweisungen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="bfc0c-117">Wenn Sie eine Datenbank auf einen Zielcomputer übertragen müssen, müssen Sie ihn zunächst vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="bfc0c-118">Um den Zielcomputer vorzubereiten, müssen Sie zunächst SQL Server-Anmeldeinformationen auf dem Zielcomputer erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="bfc0c-119">Wenn es sich um eine verschlüsselte Datenbank handelt, müssen Sie auch das Zertifikat vom Quellcomputer auf den Zielcomputer importieren.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="bfc0c-120">Um SQL Server-Anmeldeinformationen auf dem Zielcomputer zu erstellen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="bfc0c-121">Stellen Sie eine Verbindung zum Zielcomputer über SQL Server Management Studio auf dem Quellcomputer her.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="bfc0c-122">Oder starten Sie SQL Server Management Studio direkt auf dem Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="bfc0c-123">Klicken Sie auf der  Standardsymbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="bfc0c-124">Kopieren Sie das folgende Beispiel in das Abfragefenster, und ändern Sie es nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="bfc0c-125">Mit der folgenden-Anweisung wird eine SQL Server Anmelde Informationen erstellt, um das Shared Access Certificate Ihres Speicher Containers zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="bfc0c-126">Um alle verfügbaren Anmeldeinformationen anzuzeigen, können Sie im Abfragefenster die folgende Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="bfc0c-127">Wenn Sie mit dem Zielserver verbunden sind, öffnen Sie das Abfragefenster, und führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="bfc0c-128">Am Ende dieses Schritts wird das vom Quellcomputer kopierte Verschlüsselungszertifikat vom Zielcomputer importiert.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="bfc0c-129">Anschließend können Sie die Datendateien auf dem Zielcomputer anfügen.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="bfc0c-130">Erstellen Sie dann eine Datenbank mit Daten-und Protokolldateien, die auf die vorhandenen Dateien in Azure Storage verweisen, indem Sie die Option zum Anfügen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="bfc0c-131">Führen Sie die folgende Anweisung im Abfragefenster aus:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="bfc0c-132">Klicken Sie im Objekt-Explorer auf "Datenbanken" und mit der rechten Maustaste auf "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="bfc0c-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="bfc0c-133">Sie sollten die neu erstellte Datenbank "TestDB1onDest" anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="bfc0c-134">Führen Sie als Nächstes die folgende Anweisung im Abfragefenster aus:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="bfc0c-135">Es sollten alle Daten aufgelistet werden, die Sie in Lektion 4 eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="bfc0c-136">Beachten Sie, dass die verschlüsselte Datenbank ohne Datenverschiebung auf eine andere Berechnungsinstanz übertragen wurde.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="bfc0c-137">Führen Sie die folgenden Schritte aus, um eine Datenbank mit Daten-und Protokolldateien zu erstellen, die auf die vorhandenen Dateien in Azure Storage mithilfe SQL Server Management Studio Benutzeroberfläche verweisen:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="bfc0c-138">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer Instanz der SQL Server-Datenbank-Engine her, und erweitern Sie anschließend diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="bfc0c-139">Klicken Sie mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Neue Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="bfc0c-140">Klicken Sie anschließend mit der rechten Maustaste auf "TestDB".</span><span class="sxs-lookup"><span data-stu-id="bfc0c-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="bfc0c-141">Klicken Sie auf "Tasks" und dann auf "Trennen".</span><span class="sxs-lookup"><span data-stu-id="bfc0c-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="bfc0c-142">Prüfen Sie "Verbindungen löschen" im Dialogfeld "Trennen".</span><span class="sxs-lookup"><span data-stu-id="bfc0c-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="bfc0c-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="bfc0c-144">Stellen Sie eine Verbindung mit einem Zielcomputer her, der SQL Server 2014 CTP2 oder höher aufweist.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="bfc0c-145">Um den Zielcomputer vorzubereiten, müssen Sie SQL Server-Anmeldeinformationen auf dem Zielcomputer erstellen, um auf den gleichen Container zu verweisen, in dem sich TestDB1 befindet.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="bfc0c-146">Wenn Sie den erneuten Anfügevorgang auf dem gleichen Computer durchführen, ist es nicht erforderlich, andere Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="bfc0c-147">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf **Datenbanken** und dann auf **Anfügen**</span><span class="sxs-lookup"><span data-stu-id="bfc0c-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="bfc0c-148">Klicken Sie im Dialogfeld **Datenbanken** anfügen auf **Hinzufügen**, um die anzufügende Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="bfc0c-149">Im Dialogfeld **Datenbankdateien suchen** :</span><span class="sxs-lookup"><span data-stu-id="bfc0c-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="bfc0c-150">Geben Sie für den Speicherort der Datenbank-Datendatei Folgendes `https://teststorageaccnt.blob.core.windows.net/testcontainer/` ein:</span><span class="sxs-lookup"><span data-stu-id="bfc0c-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="bfc0c-151">Geben Sie als Dateiname Folgendes ein: `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="bfc0c-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="bfc0c-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfc0c-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="bfc0c-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="bfc0c-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="bfc0c-154">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="bfc0c-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="bfc0c-155">Lektion 7: Verschieben von Datendateien nach Azure Storage</span><span class="sxs-lookup"><span data-stu-id="bfc0c-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
