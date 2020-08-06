---
title: 'Lektion 4: Erstellen einer Datenbank in Azure Storage | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622084"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="0e602-102">Lektion 4: Erstellen einer Datenbank in Azure Storage</span><span class="sxs-lookup"><span data-stu-id="0e602-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="0e602-103">In dieser Lektion erfahren Sie, wie Sie eine Datenbank mithilfe des Features SQL Server Datendateien in Azure erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e602-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="0e602-104">Vor dieser Lektion müssen Sie Lektion 1, 2 und 3 abschließen.</span><span class="sxs-lookup"><span data-stu-id="0e602-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="0e602-105">Lektion 3 ist ein sehr wichtiger Schritt, da Sie die Informationen über Ihren Azure-Speicher Container und den zugehörigen Richtlinien Namen und SAS-Schlüssel vor Lektion 4 im SQL Server Anmelde Informationsspeicher speichern müssen.</span><span class="sxs-lookup"><span data-stu-id="0e602-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="0e602-106">Für jeden Speichercontainer, der von einer Daten- oder Protokolldatei verwendet wird, müssen Sie SQL Server-Anmeldeinformationen erstellen, deren Namen mit dem Containerpfad übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0e602-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="0e602-107">Anschließend können Sie eine neue Datenbank in erstellen Azure Storage</span><span class="sxs-lookup"><span data-stu-id="0e602-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="0e602-108">In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="0e602-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="0e602-109">Sie verfügen über ein Azure Storage Konto.</span><span class="sxs-lookup"><span data-stu-id="0e602-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0e602-110">Sie haben unter Ihrem Azure Storage Konto einen Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e602-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0e602-111">Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e602-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="0e602-112">Sie haben auch einen SAS-Schlüssel generiert.</span><span class="sxs-lookup"><span data-stu-id="0e602-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="0e602-113">Sie haben die SQL Server-Anmeldeinformationen auf dem Quellcomputer erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e602-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="0e602-114">Führen Sie die folgenden Schritte aus, um eine Datenbank in Azure mithilfe der SQL Server Datendateien in Azure Storage zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0e602-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0e602-115">Stellen Sie eine Verbindung mit SQL Server Management Studio her.</span><span class="sxs-lookup"><span data-stu-id="0e602-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="0e602-116">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz der installierten Datenbank-Engine her.</span><span class="sxs-lookup"><span data-stu-id="0e602-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="0e602-117">Klicken Sie auf der Standardsymbolleiste auf "Neue Abfrage".</span><span class="sxs-lookup"><span data-stu-id="0e602-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="0e602-118">Kopieren Sie das folgende Beispiel in das Abfragefenster, und ändern Sie es nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="0e602-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="0e602-119">Beachten Sie, dass das FILENAME-Feld auf den URI-Pfad der Datenbankdatei im Speichercontainer verweist und mit https beginnen muss.</span><span class="sxs-lookup"><span data-stu-id="0e602-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="0e602-120">Fügen Sie einige Daten zur Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e602-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="0e602-121">Um die neue Datenbank "TestDB1" auf einem lokalen SQL Server zu sehen, aktualisieren Sie die Datenbanken im Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="0e602-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="0e602-122">Um die neu erstellte Datenbank im Speicherkonto anzuzeigen, stellen Sie eine Verbindung mit dem Speicherkonto über SQL Server Management Studio (SSMS) her.</span><span class="sxs-lookup"><span data-stu-id="0e602-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="0e602-123">Weitere Informationen zum Herstellen einer Verbindung mit einem Azure-Speicher mithilfe SQL Server Management Studio finden Sie in den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="0e602-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="0e602-124">Rufen Sie zunächst die Speicherkontoinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="0e602-124">First, get the storage account information.</span></span> <span data-ttu-id="0e602-125">Melden Sie sich beim Verwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="0e602-125">Log in to the Management Portal.</span></span> <span data-ttu-id="0e602-126">Klicken Sie anschließend auf **Speicher** , und wählen Sie Ihr Speicherkonto aus.</span><span class="sxs-lookup"><span data-stu-id="0e602-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="0e602-127">Wenn ein Speicherkonto ausgewählt ist, klicken Sie unten auf der Seite auf **Zugriffsschlüssel verwalten** .</span><span class="sxs-lookup"><span data-stu-id="0e602-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="0e602-128">Dadurch wird ein ähnliches Dialogfeld geöffnet:</span><span class="sxs-lookup"><span data-stu-id="0e602-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="0e602-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0e602-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="0e602-130">Kopieren Sie die Werte für **Speicherkonto Name** und **primärer Zugriffsschlüssel** in das Dialogfeld **mit Azure Storage verbinden** in SSMS.</span><span class="sxs-lookup"><span data-stu-id="0e602-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="0e602-131">Klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="0e602-131">Then, click **Connect**.</span></span> <span data-ttu-id="0e602-132">Die Informationen zu Speicherkontocontainern werden in SSMS angezeigt, wie im folgenden Bildschirmfoto veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0e602-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="0e602-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0e602-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="0e602-134">Der folgende Screenshot zeigt die neu erstellte Datenbank sowohl in der lokalen Umgebung als auch in Azure Storage Umgebung.</span><span class="sxs-lookup"><span data-stu-id="0e602-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="0e602-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0e602-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="0e602-136">**Hinweis:** Wenn aktive Verweise auf Datendateien in einem Container vorhanden sind, führen alle Versuche, die zugeordneten SQL Server-Anmeldeinformationen zu löschen, zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0e602-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="0e602-137">Wenn bereits eine Lease für eine bestimmte Datenbankdatei in einem BLOB vorhanden ist und Sie sie löschen möchten, müssen Sie die Lease auf dem BLOB unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="0e602-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="0e602-138">Um die Lease zu unterbrechen, können Sie [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx)verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e602-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="0e602-139">Mit dieser neuen Funktion können Sie SQL Server so konfigurieren, dass jede CREATE DATABASE-Anweisung standardmäßig eine Cloud-fähige Datenbank generiert.</span><span class="sxs-lookup"><span data-stu-id="0e602-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="0e602-140">Anders ausgedrückt: Sie können Standarddaten und Protokoll Speicherorte in SQL Server Management Studio serverinstanzeigenschaften festlegen, sodass alle Datenbankdateien (MDF-, LDF-Dateien) in Azure Storage als seitenblobs erstellt werden, wenn Sie eine Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e602-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="0e602-141">Führen Sie die folgenden Schritte aus, um eine Datenbank in Azure Storage mithilfe SQL Server Management Studio Benutzeroberfläche zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0e602-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="0e602-142">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz der SQL Server-Datenbank-Engine her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e602-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0e602-143">Klicken Sie mit der rechten Maustaste auf "Datenbanken", und klicken Sie dann auf "Neue Datenbank".</span><span class="sxs-lookup"><span data-stu-id="0e602-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="0e602-144">Geben Sie im Dialogfeld "Neue Datenbank" einen Datenbanknamen ein.</span><span class="sxs-lookup"><span data-stu-id="0e602-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="0e602-145">Zum Ändern der Standardwerte der Primärdaten- und Transaktionsprotokolldateien klicken Sie im Bereich "Datenbankdateien" auf die entsprechende Zelle und geben den neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="0e602-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="0e602-146">Geben Sie auch den Pfad für den Dateispeicherort an.</span><span class="sxs-lookup"><span data-stu-id="0e602-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="0e602-147">Geben Sie für "Pfad" den URL-Pfad des Speichercontainers ein, wie `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="0e602-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="0e602-148">Geben Sie für "Dateiname" die physischen Dateinamen der Datenbankdateien (.mdf, .ldf) ein.</span><span class="sxs-lookup"><span data-stu-id="0e602-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="0e602-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0e602-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="0e602-150">Weitere Informationen finden Sie unter [Hinzufügen von Daten oder Protokolldateien mit einer Datenbank](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="0e602-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="0e602-151">Behalten Sie alle anderen Standardwerte bei.</span><span class="sxs-lookup"><span data-stu-id="0e602-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="0e602-152">Klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="0e602-152">Click OK.</span></span>  
  
 <span data-ttu-id="0e602-153">Um die neue Datenbank "TestDB1" auf einem lokalen SQL Server zu sehen, aktualisieren Sie die Datenbanken im Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="0e602-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="0e602-154">Um die neu erstellte Datenbank im Speicherkonto anzuzeigen, stellen Sie über SQL Server Management Studio (SSMS) eine Verbindung mit dem Speicherkonto her, wie weiter oben in dieser Lektion beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e602-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="0e602-155">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="0e602-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="0e602-156">Lektion 5. &#40;optional,&#41; Ihre Datenbank mithilfe von TDE zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="0e602-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
