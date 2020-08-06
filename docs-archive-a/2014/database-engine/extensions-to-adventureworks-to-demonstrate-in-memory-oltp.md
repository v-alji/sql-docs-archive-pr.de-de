---
title: Erweiterungen von AdventureWorks zur Veranschaulichung von in-Memory OLTP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724106"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="7927f-102">Erweiterungen von AdventureWorks zur Veranschaulichung von In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="7927f-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="7927f-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7927f-103">Overview</span></span>  
 <span data-ttu-id="7927f-104">Dieses Beispiel veranschaulicht die neue [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Funktion in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7927f-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="7927f-105">sowie die neuen speicheroptimierten Tabellen und systemintern kompilierten gespeicherten Prozeduren. Darüber hinaus kann es verwendet werden, um die Leistungsvorteile von [!INCLUDE[hek_2](../includes/hek-2-md.md)]nachzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7927f-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7927f-106">Informationen zum Anzeigen dieses Themas für SQL Server 2016 finden Sie unter [Erweiterungen von AdventureWorks zur Veranschaulichung von In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span><span class="sxs-lookup"><span data-stu-id="7927f-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="7927f-107">Im Beispiel werden fünf Tabellen aus der AdventureWorks-Datenbank zu speicheroptimierten Tabellen migriert. Zusätzlich enthält es eine exemplarische Arbeitsauslastung zur Abwicklung von Verkaufsaufträgen.</span><span class="sxs-lookup"><span data-stu-id="7927f-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="7927f-108">Die exemplarische Arbeitsauslastung veranschaulicht die Leistungsvorteile von [!INCLUDE[hek_2](../includes/hek-2-md.md)] auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="7927f-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="7927f-109">In der Beschreibung des Beispiels wird erläutert, welche Funktionen bei der Migration der Tabellen zu [!INCLUDE[hek_2](../includes/hek-2-md.md)] nicht ausgeschöpft werden konnten, weil sie für speicheroptimierte Tabellen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]derzeit (noch) nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="7927f-110">Die Dokumentation dieses Beispiels ist wie folgt gegliedert:</span><span class="sxs-lookup"><span data-stu-id="7927f-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="7927f-111">[Erforderliche Komponenten](#Prerequisites) für die Installation des Beispiels und die Ausführung der exemplarischen Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="7927f-112">Anweisungen für [Installieren des auf AdventureWorks basierenden InMemory OLTP-Beispiels](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="7927f-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="7927f-113">[Beschreibung der Beispiel Tabellen und-Prozeduren](#Descriptionofthesampletablesandprocedures) : enthält Beschreibungen der Tabellen und Prozeduren, die AdventureWorks durch das Beispiel hinzugefügt [!INCLUDE[hek_2](../includes/hek-2-md.md)] werden, sowie Überlegungen zum Migrieren einiger der ursprünglichen AdventureWorks-Tabellen zu Speicher optimierten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7927f-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="7927f-114">Anweisungen zur Ausführung von [Leistungsmessungen anhand der exemplarischen Arbeitsauslastung](#PerformanceMeasurementsusingtheDemoWorkload), einschließlich Anweisungen zur Installation und Ausführung von OSTRESS (einem Tool zum Steuern der Arbeitsauslastung) sowie zur Ausführung der exemplarischen Arbeitsauslastung selbst</span><span class="sxs-lookup"><span data-stu-id="7927f-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="7927f-115">Arbeitsspeicher- und Datenträgernutzung im Beispiel</span><span class="sxs-lookup"><span data-stu-id="7927f-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7927f-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7927f-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="7927f-117">RTM-Evaluation, Developer oder Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7927f-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="7927f-118">Für Leistungstests benötigen Sie einen Server, dessen Kapazität ungefähr der eines Servers in Ihrer Produktionsumgebung entspricht.</span><span class="sxs-lookup"><span data-stu-id="7927f-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="7927f-119">Für dieses spezielle Beispiel sollten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]mindestens 16 GB Arbeitsspeicher zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7927f-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7927f-120">Allgemeine Richtlinien zur Hardware für [!INCLUDE[hek_2](../includes/hek-2-md.md)] finden Sie im folgenden Blogbeitrag:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="7927f-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a> <span data-ttu-id="7927f-121">Installieren des auf AdventureWorks basierenden [!INCLUDE[hek_2](../includes/hek-2-md.md)]-Beispiels</span><span class="sxs-lookup"><span data-stu-id="7927f-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="7927f-122">Führen Sie die folgenden Schritte aus, um das Beispiel zu installieren:</span><span class="sxs-lookup"><span data-stu-id="7927f-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="7927f-123">Laden Sie das Archiv für die vollständige Sicherung der AdventureWorks2014-Datenbank herunter:</span><span class="sxs-lookup"><span data-stu-id="7927f-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="7927f-124">Öffnen Sie Folgendes: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="7927f-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="7927f-125">Speichern Sie die Datei, sobald Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="7927f-126">Extrahieren Sie die Datei **AdventureWorks2014.bak** in einen lokalen Ordner, z. B. "c:\temp".</span><span class="sxs-lookup"><span data-stu-id="7927f-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="7927f-127">Stellen Sie die Datenbanksicherung mithilfe von [!INCLUDE[tsql](../includes/tsql-md.md)] oder [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]wieder her:</span><span class="sxs-lookup"><span data-stu-id="7927f-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="7927f-128">Geben Sie den Zielordner und Dateinamen für die Datendatei an, z. B.</span><span class="sxs-lookup"><span data-stu-id="7927f-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="7927f-129">"h:\DATA\AdventureWorks2014_Data.mdf"</span><span class="sxs-lookup"><span data-stu-id="7927f-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="7927f-130">Geben Sie den Zielordner und Dateinamen für die Protokolldatei an, z. B.</span><span class="sxs-lookup"><span data-stu-id="7927f-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="7927f-131">"i:\DATA\AdventureWorks2014_log.ldf"</span><span class="sxs-lookup"><span data-stu-id="7927f-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="7927f-132">Um optimale Leistung zu gewährleisten, sollte die Protokolldatei auf einem anderen Laufwerk als die Datendatei gespeichert werden, idealerweise auf einem Laufwerk mit niedriger Latenz wie einem SSD- oder PCIe-Speichermedium.</span><span class="sxs-lookup"><span data-stu-id="7927f-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="7927f-133">T-SQL-Beispielskript:</span><span class="sxs-lookup"><span data-stu-id="7927f-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="7927f-134">Ändern Sie den Datenbankbesitzer, sodass er einem Anmeldenamen auf Ihrem Server entspricht. Dazu führen Sie den folgenden Befehl im Abfragefenster von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]aus:</span><span class="sxs-lookup"><span data-stu-id="7927f-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="7927f-135">Laden Sie das Beispielskript " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL" aus [SQL Server 2014 RTM-in-Memory-OLTP-Beispiel](https://go.microsoft.com/fwlink/?LinkID=396372) in einen lokalen Ordner herunter.</span><span class="sxs-lookup"><span data-stu-id="7927f-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="7927f-136">Aktualisieren Sie den Wert für die Variable ' checkpoint_files_location ' im Skript ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL ', um auf den Ziel Speicherort für die Prüf Punkt Dateien zu verweisen [!INCLUDE[hek_2](../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7927f-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="7927f-137">Die Prüfpunktdateien sollten auf einem Laufwerk mit ausreichender sequenzieller E/A-Leistung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="7927f-138">Aktualisieren Sie den Wert der Variablen "database_name", sodass sie auf die AdventureWorks2014-Datenbank verweist.</span><span class="sxs-lookup"><span data-stu-id="7927f-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="7927f-139">Stellen Sie sicher, dass Sie den umgekehrten Schrägstrich \' als Teil des Pfadnamens einschließen.</span><span class="sxs-lookup"><span data-stu-id="7927f-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="7927f-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7927f-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="7927f-141">Führen Sie das Beispielskript aus. Sie haben zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="7927f-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="7927f-142">Befehlszeilen-Hilfsprogramm "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="7927f-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="7927f-143">Führen Sie im Ordner mit dem Skript an der Eingabeaufforderung beispielsweise folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7927f-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="7927f-144">Management Studio</span><span class="sxs-lookup"><span data-stu-id="7927f-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="7927f-145">Öffnen Sie das Skript [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL in einem Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="7927f-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="7927f-146">Stellen Sie eine Verbindung mit dem Zielserver her, auf dem die AdventureWorks2014-Datenbank gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="7927f-147">Aktivieren Sie den SQLCMD-Modus, indem Sie auf "Abfrage-> SQLCMD-Modus" klicken.</span><span class="sxs-lookup"><span data-stu-id="7927f-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="7927f-148">Klicken Sie auf die Schaltfläche "ausführen", um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7927f-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="7927f-149">Beschreibung der Beispieltabellen und -prozeduren</span><span class="sxs-lookup"><span data-stu-id="7927f-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="7927f-150">Im Beispiel werden neue Tabellen für Produkte und Verkaufsaufträge auf Grundlage vorhandener AdventureWorks-Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="7927f-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="7927f-151">Das Schema der neuen Tabellen entspricht bis auf die nachfolgend beschriebenen Unterschiede dem der vorhandenen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7927f-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="7927f-152">Die neuen speicheroptimierten Tabellen haben das Suffix „_inmem“.</span><span class="sxs-lookup"><span data-stu-id="7927f-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="7927f-153">Zusätzlich umfasst das Beispiel entsprechende Tabellen mit dem Suffix „_ondisk“. Mithilfe dieser Tabellen können 1:1-Vergleiche zwischen der Leistung speicheroptimierter und datenträgerbasierter Tabellen im System angestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="7927f-154">Beachten Sie, dass die in der Arbeitsauslastung für Leistungsvergleiche verwendeten speicheroptimierten Tabellen vollständig dauerhaft und vollständig protokolliert sind,</span><span class="sxs-lookup"><span data-stu-id="7927f-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="7927f-155">d. h., dass Leistungsvorteile nicht auf Kosten der Dauerhaftigkeit oder Zuverlässigkeit erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="7927f-156">Die Zielarbeitsauslastung in diesem Beispiel dient der Abwicklung von Verkaufsaufträgen. Dabei fließen auch Produkt- und Rabattinformationen</span><span class="sxs-lookup"><span data-stu-id="7927f-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="7927f-157">aus den Tabellen SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer und SpecialOfferProduct ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="7927f-158">Mithilfe der beiden neuen gespeicherten Prozeduren Sales.usp_InsertSalesOrder_inmem und Sales.usp_UpdateSalesOrderShipInfo_inmem werden Verkaufsaufträge eingefügt bzw. Versandinformationen zu bestimmten Verkaufsaufträgen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="7927f-159">Das neue Schema "Demo" enthält Hilfstabellen und gespeicherte Prozeduren zum Ausführen einer exemplarischen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="7927f-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="7927f-160">Durch das [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Beispiel werden AdventureWorks im Einzelnen die folgenden Objekte hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="7927f-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="7927f-161">Tabellen, die durch das Beispiel hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="7927f-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="7927f-162">Neue Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-162">The New Tables</span></span>  
 <span data-ttu-id="7927f-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="7927f-164">Kopfzeileninformationen zu Verkaufsaufträgen.</span><span class="sxs-lookup"><span data-stu-id="7927f-164">Header information about sales orders.</span></span> <span data-ttu-id="7927f-165">Diese Tabelle enthält eine Zeile für jeden Verkaufsauftrag.</span><span class="sxs-lookup"><span data-stu-id="7927f-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="7927f-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="7927f-167">Detailinformationen zu Verkaufsaufträgen.</span><span class="sxs-lookup"><span data-stu-id="7927f-167">Details of sales orders.</span></span> <span data-ttu-id="7927f-168">Diese Tabelle enthält eine Zeile für jeden Einzelposten eines Verkaufsauftrags.</span><span class="sxs-lookup"><span data-stu-id="7927f-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="7927f-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="7927f-170">Informationen zu Sonderangeboten, einschließlich des prozentualen Rabatts, der den einzelnen Sonderangeboten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="7927f-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="7927f-172">Verweistabelle zwischen Sonderangeboten und Produkten.</span><span class="sxs-lookup"><span data-stu-id="7927f-172">Reference table between special offers and products.</span></span> <span data-ttu-id="7927f-173">Jedes Sonderangebot kann für 0 (null) oder mehrere Produkte gelten, und jedes Produkt kann in 0 oder mehreren Sonderangeboten vertreten sein.</span><span class="sxs-lookup"><span data-stu-id="7927f-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="7927f-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="7927f-175">Informationen zu Produkten, einschließlich der Listenpreise.</span><span class="sxs-lookup"><span data-stu-id="7927f-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="7927f-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="7927f-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="7927f-177">Wird in der exemplarischen Arbeitsauslastung zum Erstellen von Beispielverkaufsaufträgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="7927f-178">Datenträgerbasierte Tabellenvarianten:</span><span class="sxs-lookup"><span data-stu-id="7927f-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="7927f-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="7927f-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="7927f-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="7927f-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="7927f-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="7927f-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="7927f-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="7927f-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="7927f-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="7927f-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="7927f-184">Unterschiede zwischen ursprünglichen datenträgerbasierten und neuen speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="7927f-185">Meistens verwenden die neuen, in diesem Beispiel eingeführten Tabellen bis auf wenige Ausnahmen dieselben Spalten und Datentypen</span><span class="sxs-lookup"><span data-stu-id="7927f-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="7927f-186">wie die ursprünglichen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7927f-186">However, there are a few differences.</span></span> <span data-ttu-id="7927f-187">Die Unterschiede und der Grund für die Abweichung sind im Folgenden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7927f-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="7927f-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="7927f-189">Da*Standardeinschränkungen* bei speicheroptimierten Tabellen unterstützt werden, wurden die meisten Standardeinschränkungen unverändert migriert.</span><span class="sxs-lookup"><span data-stu-id="7927f-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="7927f-190">Die ursprüngliche Tabelle Sales.SalesOrderHeader enthält jedoch zwei Standardeinschränkungen, durch die für die Spalten OrderDate und ModifiedDate das aktuelle Datum abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="7927f-191">In einer durchsatzstarken Arbeitsauslastung für die Auftragsverarbeitung, in der zahlreiche Vorgänge parallel ausgeführt werden, können globale Ressourcen zu Konflikten führen.</span><span class="sxs-lookup"><span data-stu-id="7927f-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="7927f-192">Die Systemzeit ist beispielsweise eine solche globale Ressource und kann bei einer [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Arbeitsauslastung, durch die Verkaufsaufträge eingefügt werden, erfahrungsgemäß einen Engpass verursachen. Dies gilt insbesondere, wenn die Systemzeit für mehrere Spalten sowohl in der Auftragskopfzeile als auch in den Auftragsdetails abgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="7927f-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="7927f-193">In diesem Beispiel wird das Problem umgangen, indem die Systemzeit für jeden eingefügten Verkaufsauftrag nur einmal abgerufen und dieser Wert in der gespeicherten Prozedur Sales.usp_InsertSalesOrder_inmem für die datetime-Spalten in SalesOrderHeader_inmem und SalesOrderDetail_inmem verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="7927f-194">*Alias-UDTs* : In der ursprünglichen Tabelle werden die beiden Alias-UDTs (User-defined Data Types, benutzerdefinierte Datentypen) dbo.OrderNumber und dbo.AccountNumber für die Spalten „PurchaseOrderNumber“ bzw. „AccountNumber“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] <span data-ttu-id="7927f-195">unterstützt keine Alias-UDTs für speicheroptimierte Tabellen, daher verwenden die neuen Tabellen die Systemdatentypen nvarchar(25) bzw. nvarchar(15).</span><span class="sxs-lookup"><span data-stu-id="7927f-195">does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="7927f-196">*Spalten mit NULL-Werten in Indexschlüsseln* : In der ursprünglichen Tabelle sind für die Spalte „SalesPersonID“ NULL-Werte zulässig, während die Spalte in den neuen Tabellen keine NULL-Werte zulässt und über eine Standardeinschränkung mit dem Wert (-1) verfügt.</span><span class="sxs-lookup"><span data-stu-id="7927f-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="7927f-197">Dies liegt daran, dass Indizes für speicheroptimierte Tabellen im Indexschlüssel keine Spalten aufweisen dürfen, die NULL-Werte zulassen. Daher dient -1 in diesem Fall als Ersatz für NULL.</span><span class="sxs-lookup"><span data-stu-id="7927f-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="7927f-198">*Berechnete Spalten* : Auf die berechneten Spalten SalesOrderNumber und TotalDue wurde verzichtet, da berechnete Spalten in speicheroptimierten Tabellen von [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="7927f-199">In der neuen Sicht Sales.vSalesOrderHeader_extended_inmem sind die Spalten SalesOrderNumber und TotalDue enthalten.</span><span class="sxs-lookup"><span data-stu-id="7927f-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="7927f-200">Falls diese Spalten benötigt werden, können Sie diese Sicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="7927f-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="7927f-201">*FOREIGN KEY-Einschränkungen* werden für speicheroptimierte Tabellen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7927f-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="7927f-202">SalesOrderHeader_inmem stellt in der exemplarischen Arbeitsauslastung eine aktive Tabelle dar. Darüber hinaus verursachen FOREIGN KEY-Einschränkungen für DML-Vorgänge zusätzlichen Verarbeitungsaufwand, da alle anderen Tabellen, auf die in diesen Einschränkungen verwiesen wird, durchsucht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7927f-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="7927f-203">Daher wird davon ausgegangen, dass die App referenzielle Integrität gewährleistet und dass eingefügte Zeilen nicht auf referenzielle Integrität überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="7927f-204">Die referenzielle Integrität der Daten in dieser Tabelle kann mithilfe der gespeicherten Prozedur dbo.usp_ValidateIntegrity anhand des folgenden Skripts überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="7927f-205">*CHECK-Einschränkungen* werden für speicheroptimierte Tabellen in SQL Server 2014 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7927f-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="7927f-206">Anhand des folgenden Skripts wird die Domänenintegrität zusammen mit der referenziellen Integrität überprüft:</span><span class="sxs-lookup"><span data-stu-id="7927f-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="7927f-207">*Rowguid* : Die rowguid-Spalte wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="7927f-208">Im Gegensatz zu uniqueidentifier wird die ROWGUIDCOL-Option für speicheroptimierte Tabellen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7927f-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="7927f-209">Spalten dieses Typs werden normalerweise für Mergereplikationen oder für Tabellen mit FILESTREAM-Spalten verwendet,</span><span class="sxs-lookup"><span data-stu-id="7927f-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="7927f-210">die in diesem Beispiel beide nicht zum Einsatz kommen.</span><span class="sxs-lookup"><span data-stu-id="7927f-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="7927f-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="7927f-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="7927f-212">*Standardeinschränkungen*: Ähnlich wie SalesOrderHeader wird die Standardeinschränkung, die das Systemdatum bzw. die Systemzeit erfordert, nicht migriert. Stattdessen wird das aktuelle Systemdatum bzw. die aktuelle Systemzeit von der gespeicherten Prozedur, die Verkaufsaufträge einfügt, beim ersten Einfügevorgang hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7927f-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="7927f-213">*Berechnete Spalten*: Die berechnete Spalte „LineTotal“ wurde nicht migriert, weil berechnete Spalten bei speicheroptimierten Tabellen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="7927f-214">Um auf diese Spalte zuzugreifen, verwenden Sie die Sicht Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="7927f-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="7927f-215">*Rowguid* : Die rowguid-Spalte wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="7927f-216">Ausführliche Informationen finden Sie in der Beschreibung zur Tabelle SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="7927f-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="7927f-217">Informationen zu *CHECK* - und *FOREIGN KEY* -Einschränkungen finden Sie in der Beschreibung zu SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="7927f-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="7927f-218">Mit dem folgenden Skript können die Domänenintegrität und die referenzielle Integrität der Tabelle überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="7927f-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="7927f-219">Production.Product</span></span>  
  
-   <span data-ttu-id="7927f-220">*Alias-UDTs*: Die ursprüngliche Tabelle verwendet den benutzerdefinierten Datentyp „dbo.Flag“, der dem Systemdatentyp „bit“ entspricht.</span><span class="sxs-lookup"><span data-stu-id="7927f-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="7927f-221">Die migrierte Tabelle verwendet stattdessen den Datentyp bit.</span><span class="sxs-lookup"><span data-stu-id="7927f-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="7927f-222">*BIN2 Sortierung* -der Spalten Name und ProductNumber sind in Index Schlüsseln enthalten und müssen daher BIN2-Sortierungen in aufweisen [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7927f-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="7927f-223">Hier wird davon ausgegangen, dass die App nicht von Sortiereigenschaften abhängig ist, z. B. nicht nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="7927f-224">*Rowguid* : Die rowguid-Spalte wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="7927f-225">Ausführliche Informationen finden Sie in der Beschreibung zur Tabelle SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="7927f-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="7927f-226">*UNIQUE-*, *CHECK-* und *FOREIGN KEY-Einschränkungen* werden auf zwei Weisen berücksichtigt: Die gespeicherten Prozeduren Product.usp_InsertProduct_inmem und Product.usp_DeleteProduct_inmem können zum Einfügen und Löschen von Produkten verwendet werden. Mithilfe dieser Prozeduren werden Domänenintegrität und referenzielle Integrität überprüft. Bei einer Integritätsverletzung verursachen sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7927f-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="7927f-227">Darüber hinaus können Domänenintegrität und referenzielle Integrität mithilfe des folgenden Skripts direkt überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="7927f-228">Beachten Sie, dass von den gespeicherten Prozeduren usp_InsertProduct_inmem und usp_DeleteProduct_inmem nur Fremdschlüssel zwischen den migrierten Tabellen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="7927f-229">Verweise auf andere Tabellen wie ProductModel, ProductSubcategory und UnitMeasure werden nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="7927f-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="7927f-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="7927f-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="7927f-231">*CHECK-* und *FOREIGN KEY-Einschränkungen* werden auf zwei Weisen berücksichtigt: Die gespeicherten Prozeduren Sales.usp_InsertSpecialOffer_inmem und Sales.usp_DeleteSpecialOffer_inmem können zum Einfügen und Löschen von Sonderangeboten verwendet werden. Mithilfe dieser Prozeduren werden Domänenintegrität und referenzielle Integrität überprüft. Bei einer Integritätsverletzung verursachen sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7927f-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="7927f-232">Darüber hinaus können Domänenintegrität und referenzielle Integrität mithilfe des folgenden Skripts direkt überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="7927f-233">*Rowguid* : Die rowguid-Spalte wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="7927f-234">Ausführliche Informationen finden Sie in der Beschreibung zur Tabelle SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="7927f-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="7927f-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="7927f-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="7927f-236">*FOREIGN KEY-Einschränkungen* werden auf zwei Weisen berücksichtigt: Die gespeicherte Prozedur Sales.usp_InsertSpecialOfferProduct_inmem kann zum Einfügen von Beziehungen zwischen Sonderangeboten und Produkten verwendet werden. Mithilfe dieser Prozedur wird die referenzielle Integrität überprüft. Bei einer Integritätsverletzung verursacht sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7927f-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="7927f-237">Darüber hinaus kann die referenzielle Integrität mithilfe des folgenden Skripts direkt überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="7927f-238">*Rowguid* : Die rowguid-Spalte wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="7927f-239">Ausführliche Informationen finden Sie in der Beschreibung zur Tabelle SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="7927f-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="7927f-240">Überlegungen zu Indizes bei speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="7927f-241">Der Basisindex für speicheroptimierte Tabellen ist der NONCLUSTERED-Index, der Punktsuchen (Indexsuche in Gleichheitsprädikaten), Bereichsscans (Indexsuche in Ungleichheitsprädikaten), vollständige Indexscans und sortierte Scans unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7927f-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="7927f-242">Zusätzlich unterstützen NONCLUSTERED-Indizes Suchen in führenden Indexschlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="7927f-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="7927f-243">Bis auf Rückwärtsscans unterstützen speicheroptimierte NONCLUSTERED-Indizes alle Vorgänge, die auch von datenträgerbasierten NONCLUSTERED-Indizes unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="7927f-244">Daher sind NONCLUSTERED-Indizes eine sichere Wahl für Ihre Indizes.</span><span class="sxs-lookup"><span data-stu-id="7927f-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="7927f-245">Mit HASH-Indizes kann die Arbeitsauslastung weiter optimiert werden,</span><span class="sxs-lookup"><span data-stu-id="7927f-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="7927f-246">da sie speziell für Punktsuchen und Zeileneinfügungen optimiert sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="7927f-247">Allerdings unterstützen sie keine Bereichsscans, sortierte Scans oder Suchen in führenden Indexschlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="7927f-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="7927f-248">Daher sollten diese Indizes mit Vorsicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="7927f-249">Außerdem muss während der Erstellung der bucket_count-Wert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="7927f-250">Die Bucketanzahl sollte normalerweise auf einen Wert zwischen der einfachen und doppelten Anzahl von Indexschlüsselwerten festgelegt werden. Ein zu hoher Wert stellt in der Regel aber auch kein Problem dar.</span><span class="sxs-lookup"><span data-stu-id="7927f-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="7927f-251">Weitere Informationen zu [Indexrichtlinien](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) und Richtlinien zum [Auswählen des geeigneten bucket_count-Werts](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx)finden Sie in der Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7927f-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="7927f-252">Die Indizes der migrierten Tabellen wurden für die exemplarische Arbeitsauslastung, die zur Abwicklung von Verkaufsaufträgen eingesetzt wird, optimiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="7927f-253">Die Arbeitsauslastung basiert auf Einfügungen und Punktsuchen in den Tabellen Sales.SalesOrderHeader_inmem und Sales.SalesOrderDetail_inmem sowie auf Punktsuchen in den Primärschlüsselspalten der Tabellen Production.Product_inmem und Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="7927f-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="7927f-254">Sales.SalesOrderHeader_inmem verfügt über drei Indizes, die aus Leistungsgründen und weil für die Arbeitsauslastung keine sortierten oder Bereichsscans erforderlich sind, alle HASH-Indizes sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="7927f-255">HASH-Index für (SalesOrderID): bucket_count hat einen Wert von 10 Millionen (und wird auf 16 Millionen aufgerundet), da die erwartete Anzahl von Verkaufsaufträgen 10 Millionen beträgt.</span><span class="sxs-lookup"><span data-stu-id="7927f-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="7927f-256">HASH-Index für (SalesPersonID): bucket_count beträgt 1 Million.</span><span class="sxs-lookup"><span data-stu-id="7927f-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="7927f-257">Dem bereitgestellten Dataset sind nur eine geringe Anzahl von Vertriebsmitarbeitern zugeordnet, sodass es zukünftig anwachsen kann. Außerdem tritt bei Punktsuchen keine Leistungsbeeinträchtigung auf, falls eine zu hohe Bucketanzahl ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="7927f-258">HASH-Index für (CustomerID): bucket_count beträgt 1 Million.</span><span class="sxs-lookup"><span data-stu-id="7927f-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="7927f-259">Dem bereitgestellten Dataset ist nur eine geringe Anzahl von Kunden zugeordnet, sodass es zukünftig anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="7927f-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="7927f-260">Sales.SalesOrderDetail_inmem verfügt über drei Indizes, die aus Leistungsgründen und weil für die Arbeitsauslastung keine sortierten oder Bereichsscans erforderlich sind, alle HASH-Indizes sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="7927f-261">HASH-Index für (SalesOrderID, SalesOrderDetailID): Dies ist der Primärschlüsselindex. Obwohl für (SalesOrderID, SalesOrderDetailID) nur selten Suchen ausgeführt werden, lassen sich Zeileneinfügungen beschleunigen, indem ein HASH-Index für den Schlüssel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="7927f-262">bucket_count hat einen Wert von 50 Millionen (und wird auf 67 Millionen aufgerundet): Die erwartete Anzahl von Verkaufsaufträgen beträgt 10 Millionen mit durchschnittlich fünf Einzelposten pro Auftrag.</span><span class="sxs-lookup"><span data-stu-id="7927f-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="7927f-263">HASH-Index für (SalesOrderID): Es werden häufig Suchen nach Verkaufsaufträgen ausgeführt, und Sie möchten alle Einzelposten ermitteln, die sich auf einen einzelnen Auftrag beziehen.</span><span class="sxs-lookup"><span data-stu-id="7927f-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="7927f-264">bucket_count hat einen Wert von 10 Millionen (und wird auf 16 Millionen aufgerundet), da die erwartete Anzahl von Verkaufsaufträgen 10 Millionen beträgt.</span><span class="sxs-lookup"><span data-stu-id="7927f-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="7927f-265">HASH-Index für (ProductID): bucket_count beträgt 1 Million.</span><span class="sxs-lookup"><span data-stu-id="7927f-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="7927f-266">Dem bereitgestellten Dataset ist nur eine geringe Anzahl von Produkten zugeordnet, sodass es zukünftig anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="7927f-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="7927f-267">Production.Product_inmem verfügt über drei Indizes.</span><span class="sxs-lookup"><span data-stu-id="7927f-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="7927f-268">HASH-Index für (ProductID): Da Suchen nach ProductID ein wesentlicher Bestandteil der exemplarischen Arbeitsauslastung sind, wird hier ein HASH-Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="7927f-269">NONCLUSTERED-Index für (Name): ermöglicht sortierte Scans für Produktnamen.</span><span class="sxs-lookup"><span data-stu-id="7927f-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="7927f-270">NONCLUSTERED-Index für (ProductNumber): ermöglicht sortierte Scans für Produktnummern.</span><span class="sxs-lookup"><span data-stu-id="7927f-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="7927f-271">Sales.SpecialOffer_inmem verfügt über einen HASH-Index für (SpecialOfferID): Punktsuchen nach Sonderangeboten sind ein wesentlicher Bestandteil der exemplarischen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="7927f-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="7927f-272">bucket_count beträgt 1 Million und ist auf zukünftiges Wachstum ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="7927f-273">Da in der exemplarischen Arbeitsauslastung nicht auf Sales.SpecialOfferProduct_inmem verwiesen wird, ist es nicht erforderlich, HASH-Indizes für die Tabelle zu verwenden, um die Arbeitsauslastung zu optimieren. Für (SpecialOfferID, ProductID) und (ProductID) werden NONCLUSTERED-Indizes verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="7927f-274">Beachten Sie, dass einige der oben genannten Bucketanzahlen zu hoch angesetzt sind. Auf die Bucketanzahlen für die Indizes von SalesOrderHeader_inmem und SalesOrderDetail_inmem trifft dies jedoch nicht zu, da sie auf eine Anzahl von 10 Millionen Verkaufsaufträgen beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="7927f-275">Auf diese Weise kann das Beispiel auch auf Systemen mit geringerer Arbeitsspeicherkapazität installiert werden. In diesen Fällen verursacht die exemplarische Arbeitsauslastung jedoch einen Fehler vom Typ "Nicht genügend Arbeitsspeicher".</span><span class="sxs-lookup"><span data-stu-id="7927f-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="7927f-276">Wenn Sie einen Wert festlegen möchten, der 10 Millionen Verkaufsaufträge erheblich überschreitet, können Sie die Bucketanzahlen einfach entsprechend erhöhen.</span><span class="sxs-lookup"><span data-stu-id="7927f-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="7927f-277">Überlegungen zur Arbeitsspeichernutzung</span><span class="sxs-lookup"><span data-stu-id="7927f-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="7927f-278">Die Arbeitsspeichernutzung der Beispieldatenbank vor und nach der Ausführung der exemplarischen Arbeitsauslastung wird im Abschnitt [Arbeitsspeichernutzung für speicheroptimierte Tabellen](#Memoryutilizationforthememory-optimizedtables)erörtert.</span><span class="sxs-lookup"><span data-stu-id="7927f-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="7927f-279">Gespeicherte Prozeduren, die durch das Beispiel hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="7927f-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="7927f-280">Die beiden wichtigsten gespeicherten Prozeduren zum Einfügen von Verkaufsaufträgen und Aktualisieren von Versanddetails lauten:</span><span class="sxs-lookup"><span data-stu-id="7927f-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="7927f-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="7927f-282">Fügt einen neuen Verkaufsauftrag in die Datenbank ein und gibt SalesOrderID für den Verkaufsauftrag aus.</span><span class="sxs-lookup"><span data-stu-id="7927f-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="7927f-283">Als Eingabeparameter werden Details zur Auftragskopfzeile sowie die Einzelposten im Auftrag akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="7927f-284">Ausgabeparameter:</span><span class="sxs-lookup"><span data-stu-id="7927f-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="7927f-285">@SalesOrderID int: SalesOrderID für den gerade eingefügten Verkaufsauftrag</span><span class="sxs-lookup"><span data-stu-id="7927f-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="7927f-286">Eingabeparameter (erforderlich):</span><span class="sxs-lookup"><span data-stu-id="7927f-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="7927f-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="7927f-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="7927f-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="7927f-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="7927f-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem: Tabellenwertparameter, der die Einzelposten des Auftrags enthält</span><span class="sxs-lookup"><span data-stu-id="7927f-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="7927f-293">Eingabeparameter (optional):</span><span class="sxs-lookup"><span data-stu-id="7927f-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="7927f-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="7927f-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="7927f-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="7927f-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="7927f-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="7927f-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="7927f-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="7927f-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="7927f-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="7927f-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="7927f-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="7927f-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="7927f-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="7927f-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="7927f-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="7927f-305">Aktualisiert die Versandinformationen für einen bestimmten Verkaufsauftrag.</span><span class="sxs-lookup"><span data-stu-id="7927f-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="7927f-306">Gleichzeitig werden auch die Versandinformationen für alle Einzelposten des Verkaufsauftrags aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="7927f-307">Dies ist eine Wrapperprozedur für die systemintern kompilierte gespeicherte Prozedur Sales.usp_UpdateSalesOrderShipInfo_native. Sie verfügt über eine Wiederholungslogik zur Behandlung (unerwarteter) potenzieller Konflikte mit Transaktionen, die gleichzeitig ausgeführt werden und denselben Auftrag aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7927f-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="7927f-308">Weitere Informationen zur Wiederholungslogik finden Sie in [diesem Thema](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx)in der Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7927f-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="7927f-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="7927f-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="7927f-310">Dies ist die systemintern kompilierte gespeicherte Prozedur, durch die das Update der Versandinformationen tatsächlich verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="7927f-311">Sie sollte normalerweise von der gespeicherten Wrapperprozedur Sales.usp_UpdateSalesOrderShipInfo_inmem aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="7927f-312">Wenn der Client Fehler behandeln kann und eine Wiederholungslogik implementiert wurde, können Sie diese Prozedur direkt aufrufen, anstatt die gespeicherte Wrapperprozedur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7927f-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="7927f-313">Die folgende gespeicherte Prozedur wird für die exemplarische Arbeitsauslastung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7927f-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="7927f-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="7927f-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="7927f-315">Setzt die exemplarische Arbeitsauslastung zurück, indem für die Tabellen SalesOrderHeader und SalesOrderDetail ein erneutes Seeding ausgeführt wird, nachdem sie geleert wurden.</span><span class="sxs-lookup"><span data-stu-id="7927f-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="7927f-316">Mit den folgenden gespeicherten Prozeduren werden Daten in speicheroptimierten Tabellen eingefügt und daraus gelöscht, ohne die Domänenintegrität und referenzielle Integrität zu gefährden.</span><span class="sxs-lookup"><span data-stu-id="7927f-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="7927f-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="7927f-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="7927f-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="7927f-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="7927f-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="7927f-322">Zum Schluss werden Domänenintegrität und referenzielle Integrität mit der folgenden gespeicherten Prozedur überprüft.</span><span class="sxs-lookup"><span data-stu-id="7927f-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="7927f-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="7927f-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="7927f-324">Optionaler Parameter: @object_id: ID des Objekts, dessen Integrität überprüft werden soll</span><span class="sxs-lookup"><span data-stu-id="7927f-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="7927f-325">Diese Prozedur ermittelt anhand der Tabellen dbo.DomainIntegrity, dbo.ReferentialIntegrity und dbo.UniqueIntegrity, welche Integritätsregeln überprüft werden müssen. Im Beispiel werden diese Tabellen auf der Grundlage der CHECK-, FOREIGN KEY- und UNIQUE-Einschränkungen der ursprünglichen Tabellen in der AdventureWorks-Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7927f-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="7927f-326">Die zum Ausführen der Integritätsprüfungen erforderliche T-SQL-Anweisung wird mithilfe der Hilfsprozeduren dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck und dbo.GenerateUQCheck generiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="7927f-327">Leistungsmessungen anhand der exemplarischen Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="7927f-328">OSTRESS ist ein Befehlszeilentool, das vom [!INCLUDE[msCoName](../includes/msconame-md.md)] -Supportteam des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] CSS entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="7927f-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="7927f-329">Mit diesem Tool können Abfragen ausgeführt oder gespeicherte Prozeduren parallel aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="7927f-330">Sie können die Anzahl der Threads zur parallelen Ausführung einer bestimmten T-SQL-Anweisung konfigurieren und angeben, wie oft die Anweisung in diesem Thread ausgeführt werden soll. OSTRESS bündelt die Threads und führt die Anweisung in allen Threads gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="7927f-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="7927f-331">Nachdem die Ausführung aller Threads beendet wurde, meldet OSTRESS die zur Beendigung sämtlicher Threads benötigte Dauer.</span><span class="sxs-lookup"><span data-stu-id="7927f-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="7927f-332">Installieren von OSTRESS</span><span class="sxs-lookup"><span data-stu-id="7927f-332">Installing ostress</span></span>  
 <span data-ttu-id="7927f-333">OSTRESS wird nicht eigenständig, sondern als Teil der RML-Hilfsprogramme installiert.</span><span class="sxs-lookup"><span data-stu-id="7927f-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="7927f-334">Installationsschritte:</span><span class="sxs-lookup"><span data-stu-id="7927f-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="7927f-335">Laden Sie das x64-Installationspaket für die RML-Hilfsprogramme von folgender Seite herunter, und führen Sie es aus:[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="7927f-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="7927f-336">Falls Sie in einem Dialogfeld darauf hingewiesen werden, dass bestimmte Dateien gerade verwendet werden, klicken Sie auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="7927f-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="7927f-337">Ausführen von OSTRESS</span><span class="sxs-lookup"><span data-stu-id="7927f-337">Running ostress</span></span>  
 <span data-ttu-id="7927f-338">OSTRESS wird an der Eingabeaufforderung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7927f-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="7927f-339">Am einfachsten lässt sich das Tool über die RML-Eingabeaufforderung ausführen, die mit den RML-Hilfsprogrammen installiert wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="7927f-340">Führen Sie die folgenden Schritte aus, um die RML-Eingabeaufforderung zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="7927f-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="7927f-341">Öffnen Sie in Windows Server 2012 [R2] sowie in Windows 8 und 8.1 das Startmenü, indem Sie die Windows-Taste drücken, und geben Sie „rml“ ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="7927f-342">Klicken Sie auf die in der Liste der Suchergebnisse angezeigte RML-Eingabeaufforderung (RML Cmd Prompt).</span><span class="sxs-lookup"><span data-stu-id="7927f-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="7927f-343">Vergewissern Sie sich, dass sich die Eingabeaufforderung im Installationsordner für die RML-Hilfsprogramme befindet.</span><span class="sxs-lookup"><span data-stu-id="7927f-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="7927f-344">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7927f-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="7927f-345">Um die Befehlszeilenoptionen für OSTRESS anzuzeigen, führen Sie ostress.exe einfach ohne Angabe von Befehlszeilenoptionen aus.</span><span class="sxs-lookup"><span data-stu-id="7927f-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="7927f-346">Im Folgenden die wichtigsten Optionen, die beim Ausführen von OSTRESS für dieses Beispiel angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="7927f-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="7927f-347">-S: Der Name der [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7927f-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="7927f-348">-E die Windows-Authentifizierung verwenden, um eine Verbindung herzustellen (Standard); Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, verwenden Sie die Optionen-you und-P, um den Benutzernamen bzw. das Kennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7927f-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="7927f-349">-d: Der Name der Datenbank, in diesem Beispiel "AdventureWorks2014".</span><span class="sxs-lookup"><span data-stu-id="7927f-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="7927f-350">-Q: Die auszuführende T-SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7927f-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="7927f-351">-n: Die Anzahl der Verbindungen, über die die einzelnen Eingabedateien/Abfragen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="7927f-352">-r: Die Anzahl der Iterationen für jede Verbindung, über die die einzelnen Eingabedateien/Abfragen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="7927f-353">Exemplarische Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-353">Demo Workload</span></span>  
 <span data-ttu-id="7927f-354">Die wichtigste in der exemplarischen Arbeitsauslastung verwendete gespeicherte Prozedur ist Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="7927f-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="7927f-355">Im folgenden Skript wird ein Tabellenwertparameter (Table-valued Parameter, TVP) mit Beispieldaten erstellt. Anschließend wird die Prozedur aufgerufen, um einen Verkaufsauftrag mit fünf Einzelpositionen einzufügen.</span><span class="sxs-lookup"><span data-stu-id="7927f-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="7927f-356">Das OSTRESS-Tool wird verwendet, um die Aufrufe der gespeicherten Prozedur parallel auszuführen und Clients zu simulieren, die zeitgleich Verkaufsaufträge einfügen.</span><span class="sxs-lookup"><span data-stu-id="7927f-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="7927f-357">Setzen Sie die exemplarische Arbeitsauslastung nach jedem Belastungstest zurück, indem Sie Demo.usp_DemoReset ausführen.</span><span class="sxs-lookup"><span data-stu-id="7927f-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="7927f-358">Durch diese Prozedur werden die Zeilen in den speicheroptimierten Tabellen gelöscht, die datenträgerbasierten Tabellen abgeschnitten und ein Datenbankprüfpunkt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7927f-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="7927f-359">Das folgende Skript wird gleichzeitig ausgeführt, um eine Arbeitsauslastung zur Auftragsabwicklung zu simulieren:</span><span class="sxs-lookup"><span data-stu-id="7927f-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="7927f-360">Mit diesem Skript wird jeder erstellte Beispielauftrag durch 20 in einer WHILE-Schleife ausgeführte gespeicherte Prozeduren 20 Mal eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7927f-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="7927f-361">Die Schleife wird verwendet, weil die Datenbank zum Erstellen des Beispielauftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="7927f-362">In einer typischen Produktionsumgebung wird der einzufügende Verkaufsauftrag durch die Mid-Tier-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7927f-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="7927f-363">Durch das oben angegebene Skript werden Verkaufsaufträge in speicheroptimierte Tabellen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7927f-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="7927f-364">Sie erhalten das Skript zum Einfügen von Verkaufsaufträgen in datenträgerbasierte Tabellen, indem Sie die beiden Suffixe „_inmem in _ondisk“ ändern.</span><span class="sxs-lookup"><span data-stu-id="7927f-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="7927f-365">Wir verwenden das OSTRESS-Tool, um die Skripts unter Verwendung mehrerer gleichzeitiger Verbindungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7927f-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="7927f-366">Dabei wird mit dem Parameter „-n“ gesteuert, wie viele Verbindungen verwendet werden, und mit dem Parameter „-r“, wie oft das Skript für jede Verbindung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="7927f-367">Testen der Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="7927f-368">Um zu überprüfen, ob alles funktioniert, beginnen wir mit einem Beispiel Test, indem 10 gleichzeitige Verbindungen und fünf Iterationen verwendet werden, wobei insgesamt 10 \* 5 \* 20 = 1000 Verkaufsaufträge eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="7927f-369">Beim nachfolgenden Befehl gehen wir davon aus, dass die Standardinstanz auf dem lokalen Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="7927f-370">Wenn Sie eine benannte Instanz oder einen Remoteserver verwenden, ändern Sie den Servernamen mit dem Parameter -S entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7927f-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="7927f-371">Verwenden Sie den folgenden Befehl in der RML-Eingabeaufforderung, um 1.000 Verkaufsaufträge in speicheroptimierte Tabellen einzufügen:</span><span class="sxs-lookup"><span data-stu-id="7927f-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="7927f-372">Klicken Sie auf die Schaltfläche zum Kopieren, um den Befehl zu kopieren, und fügen Sie ihn in die Eingabeaufforderung der RML-Hilfsprogramme ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="7927f-373">Wenn der Befehl erwartungsgemäß funktioniert, sollte das Befehlsfenster etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="7927f-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="7927f-374">Fehlermeldungen sind nicht zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="7927f-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="7927f-375">Überprüfen Sie, ob die Arbeitsauslastung auch bei datenträgerbasierten Tabellen wie erwartet funktioniert, indem Sie den folgenden Befehl an der RML-Eingabeaufforderung ausführen:</span><span class="sxs-lookup"><span data-stu-id="7927f-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="7927f-376">Klicken Sie auf die Schaltfläche zum Kopieren, um den Befehl zu kopieren, und fügen Sie ihn in die Eingabeaufforderung der RML-Hilfsprogramme ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="7927f-377">Ausführen der Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-377">Running the Workload</span></span>  
 <span data-ttu-id="7927f-378">Um das Verhalten in einem größeren Szenario zu testen, fügen wir unter Verwendung von 100 Verbindungen 10 Millionen Verkaufsaufträge ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="7927f-379">Bei einem einfach ausgestatteten Server (z. B. mit 8 physischen und 16 logischen Kernen) und SSD-Basisspeicher für das Protokoll liefert der Test zufriedenstellende Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="7927f-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="7927f-380">Falls der Test mit Ihrer Hardware nicht gut abschneidet, sollten Sie sich im Abschnitt [Problembehandlung bei langsamer Testausführung](#Troubleshootingslow-runningtests) informieren. Wenn Sie das Belastungsniveau für diesen Test verringern möchten, reduzieren Sie die Anzahl der Verbindungen, indem Sie den Parameter „-n“ ändern.</span><span class="sxs-lookup"><span data-stu-id="7927f-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="7927f-381">Um die Anzahl der Verbindungen z. B. auf 40 zu verringern, ändern Sie den Parameter „-n100“ in „-n40“.</span><span class="sxs-lookup"><span data-stu-id="7927f-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="7927f-382">Als Leistungskennzahl für die Arbeitsauslastung wird die Zeitspanne verwendet, die von ostress.exe nach Ausführung der Arbeitsauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="7927f-383">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="7927f-384">Zuerst führen wir die Arbeitsauslastung für speicheroptimierte Tabellen aus.</span><span class="sxs-lookup"><span data-stu-id="7927f-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="7927f-385">Mit dem folgenden Befehl werden 100 Threads geöffnet, die jeweils für 5.000 Iterationen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="7927f-386">Pro Iteration werden 20 Verkaufsaufträge in getrennten Transaktionen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7927f-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="7927f-387">Die 20 Einfügungen pro Iteration sind darauf zurückzuführen, dass die einzufügenden Daten unter Verwendung der Datenbank generiert werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="7927f-388">Daraus ergeben sich insgesamt 20 · 5.000 \* 100 = 10.000.000 eingefügte Verkaufsaufträge.</span><span class="sxs-lookup"><span data-stu-id="7927f-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="7927f-389">Öffnen Sie die RML-Eingabeaufforderung, und führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7927f-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="7927f-390">Klicken Sie auf die Schaltfläche zum Kopieren, um den Befehl zu kopieren, und fügen Sie ihn in die Eingabeaufforderung der RML-Hilfsprogramme ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="7927f-391">Auf einem Testserver mit insgesamt 8 physischen (16 logischen) Kernen betrug die Dauer zwei Minuten und fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7927f-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="7927f-392">Auf einem zweiten Testserver mit 24 physischen (48 logischen) Kernen dauerte der Vorgang eine Minute und 0 (null) Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7927f-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="7927f-393">Beobachten Sie bei der Ausführung der Arbeitsauslastung die CPU-Auslastung, beispielsweise mit dem Task-Manager.</span><span class="sxs-lookup"><span data-stu-id="7927f-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="7927f-394">Sie werden feststellen, dass die CPU-Auslastung bei fast 100 % liegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="7927f-395">Andernfalls verursachen E/A-Protokollvorgänge einen Engpass. Weitere Informationen finden Sie auch unter [Problembehandlung bei langsamer Testausführung](#Troubleshootingslow-runningtests).</span><span class="sxs-lookup"><span data-stu-id="7927f-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="7927f-396">Datenträgerbasierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-396">Disk-based tables</span></span>  
 <span data-ttu-id="7927f-397">Mit dem folgenden Befehl wird die Arbeitsauslastung für datenträgerbasierte Tabellen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7927f-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="7927f-398">Beachten Sie, dass die Ausführung dieser Arbeitsauslastung einige Zeit dauern kann, was hauptsächlich auf Latchkonflikte im System zurückzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="7927f-399">Dieses Problem tritt bei speicheroptimierten Tabellen nicht auf, da sie ohne Latches auskommen.</span><span class="sxs-lookup"><span data-stu-id="7927f-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="7927f-400">Öffnen Sie die RML-Eingabeaufforderung, und führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7927f-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="7927f-401">Klicken Sie auf die Schaltfläche zum Kopieren, um den Befehl zu kopieren, und fügen Sie ihn in die Eingabeaufforderung der RML-Hilfsprogramme ein.</span><span class="sxs-lookup"><span data-stu-id="7927f-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="7927f-402">Auf einem Testserver mit insgesamt 8 physischen (16 logischen) Kernen betrugt die Dauer 41 Minuten und 25 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7927f-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="7927f-403">Auf einem zweiten Testserver mit 24 physischen (48 logischen) Kernen dauerte der Vorgang 52 Minuten und 16 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7927f-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="7927f-404">Der Hauptunterschied zwischen der Leistung speicheroptimierter und datenträgerbasierter Tabellen in diesem Test besteht darin, dass die CPU bei Verwendung datenträgerbasierter Tabellen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nicht voll ausgenutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7927f-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="7927f-405">Die Ursache sind Latchkonflikte: Wenn gleichzeitige Transaktionen versuchen, Daten in dieselbe Datenseite zu schreiben, wird mithilfe von Latches sichergestellt, dass jeweils nur eine Transaktion Schreibzugriff auf eine Seite hat.</span><span class="sxs-lookup"><span data-stu-id="7927f-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="7927f-406">Die [!INCLUDE[hek_2](../includes/hek-2-md.md)]-Engine verwendet keine Latches, und Datenzeilen sind nicht seitenweise angeordnet.</span><span class="sxs-lookup"><span data-stu-id="7927f-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="7927f-407">Folglich blockieren gleichzeitige Transaktionen nicht die Einfügungen der anderen, sodass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die CPU vollständig genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7927f-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="7927f-408">Sie können die CPU-Auslastung bei der Ausführung der Arbeitsauslastung beispielsweise mit dem Task-Manager beobachten.</span><span class="sxs-lookup"><span data-stu-id="7927f-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="7927f-409">Sie werden feststellen, dass die CPU-Auslastung bei Verwendung datenträgerbasierter Tabellen weit von 100 % entfernt ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="7927f-410">In einer Testkonfiguration mit 16 logischen Prozessoren würde sich die Auslastung um 24 % bewegen.</span><span class="sxs-lookup"><span data-stu-id="7927f-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="7927f-411">Optional können Sie den Leistungsindikator „\SQL Server:Latches\Latchwartevorgänge/Sekunde“ im Systemmonitor verwenden, um die Anzahl der Latchwartevorgänge pro Sekunde anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7927f-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="7927f-412">Zurücksetzen der exemplarischen Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-412">Resetting the demo</span></span>  
 <span data-ttu-id="7927f-413">Um die exemplarische Arbeitsauslastung zurückzusetzen, öffnen Sie die RML-Eingabeaufforderung und führen folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7927f-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="7927f-414">Abhängig von der Hardware kann die Ausführung einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="7927f-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="7927f-415">Es wird empfohlen, die Arbeitsauslastung nach jedem Durchgang zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7927f-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="7927f-416">Da bei dieser Arbeitsauslastung nur Einfügungen stattfinden, wird bei jedem Durchgang mehr Arbeitsspeicher belegt. Durch das Zurücksetzen wird verhindert, dass der Arbeitsspeicher knapp wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="7927f-417">Der Abschnitt [Arbeitsspeichernutzung nach dem Ausführen der Arbeitsauslastung](#Memoryutilizationafterrunningtheworkload)enthält Informationen darüber, wie viel Arbeitsspeicher nach einer Ausführung belegt ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="7927f-418">Problembehandlung bei langsamer Testausführung</span><span class="sxs-lookup"><span data-stu-id="7927f-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="7927f-419">Die Testergebnisse variieren normalerweise je nach Hardware und dem im Testlauf verwendeten Parallelitätsgrad.</span><span class="sxs-lookup"><span data-stu-id="7927f-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="7927f-420">Wenn die Ergebnisse nicht wie erwartet ausfallen, sollten Sie folgende Punkte überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7927f-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="7927f-421">Anzahl gleichzeitiger Transaktionen: Wenn die Arbeitsauslastung in einem einzelnen Thread ausgeführt wird, liegt der Leistungsgewinn von [!INCLUDE[hek_2](../includes/hek-2-md.md)] wahrscheinlich unter dem zweifachen Wert.</span><span class="sxs-lookup"><span data-stu-id="7927f-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="7927f-422">Latchkonflikte stellen nur bei einem hohen Parallelitätsgrad ein wirkliches Problem dar.</span><span class="sxs-lookup"><span data-stu-id="7927f-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="7927f-423">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]arbeitet mit einer geringen Anzahl von Kernen: Dies bedeutet, dass das System einen geringen Parallelitätsgrad aufweist, da nur so viele Transaktionen gleichzeitig ausgeführt werden können, wie Kerne für SQL verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="7927f-424">Symptom: Wenn die CPU-Auslastung beim Ausführen der Arbeitsauslastung für datenträgerbasierte Tabellen hoch ist, liegen normalerweise wenig Konflikte vor, was auf eine fehlende Parallelität hinweist.</span><span class="sxs-lookup"><span data-stu-id="7927f-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="7927f-425">Geschwindigkeit des Protokolllaufwerks: Wenn das Protokolllaufwerk für den Transaktionsdurchsatz im System zu langsam ist, verursacht die Arbeitsauslastung bei E/A-Protokollvorgängen einen Engpass.</span><span class="sxs-lookup"><span data-stu-id="7927f-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="7927f-426">Obwohl die Protokollierung mit [!INCLUDE[hek_2](../includes/hek-2-md.md)]effizienter ist, wenn E/A-Protokollvorgänge einen Engpass verursachen, ist der potenzielle Leistungsgewinn begrenzt.</span><span class="sxs-lookup"><span data-stu-id="7927f-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="7927f-427">Symptom: Wenn die CPU-Auslastung beim Ausführen der Arbeitsauslastung für speicheroptimierte Tabellen nicht nahe 100 % liegt oder unregelmäßige Spitzen aufweist, kann ein Engpass bei E/A-Protokollvorgängen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="7927f-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="7927f-428">Sie können die Ursache im Ressourcenmonitor anhand der Warteschlangenlänge für das Protokolllaufwerk ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7927f-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="7927f-429">Arbeitsspeicher- und Datenträgernutzung im Beispiel</span><span class="sxs-lookup"><span data-stu-id="7927f-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="7927f-430">Im Folgenden wird beschrieben, wie viel Arbeitsspeicher und Datenträgerspeicher für die Beispieldatenbank benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="7927f-431">Außerdem sind die Ergebnisse aufgeführt, die auf einem Testserver mit 16 logischen Kernen ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="7927f-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="7927f-432">Arbeitsspeichernutzung für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="7927f-433">Gesamtnutzung der Datenbank</span><span class="sxs-lookup"><span data-stu-id="7927f-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="7927f-434">Mithilfe der folgenden Abfrage kann die gesamte Arbeitsspeichernutzung für [!INCLUDE[hek_2](../includes/hek-2-md.md)] im System ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="7927f-435">Momentaufnahme direkt nach der Erstellung der Datenbank:</span><span class="sxs-lookup"><span data-stu-id="7927f-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-436">**type**</span><span class="sxs-lookup"><span data-stu-id="7927f-436">**type**</span></span>|<span data-ttu-id="7927f-437">**name**</span><span class="sxs-lookup"><span data-stu-id="7927f-437">**name**</span></span>|<span data-ttu-id="7927f-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="7927f-438">**pages_MB**</span></span>|  
|<span data-ttu-id="7927f-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-440">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-440">Default</span></span>|<span data-ttu-id="7927f-441">94</span><span class="sxs-lookup"><span data-stu-id="7927f-441">94</span></span>|  
|<span data-ttu-id="7927f-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="7927f-443">DB_ID_5</span></span>|<span data-ttu-id="7927f-444">877</span><span class="sxs-lookup"><span data-stu-id="7927f-444">877</span></span>|  
|<span data-ttu-id="7927f-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-446">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-446">Default</span></span>|<span data-ttu-id="7927f-447">0</span><span class="sxs-lookup"><span data-stu-id="7927f-447">0</span></span>|  
|<span data-ttu-id="7927f-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-449">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-449">Default</span></span>|<span data-ttu-id="7927f-450">0</span><span class="sxs-lookup"><span data-stu-id="7927f-450">0</span></span>|  
  
 <span data-ttu-id="7927f-451">Die standardmäßigen Arbeitsspeicherclerks basieren auf systemweiten Strukturen und sind relativ klein.</span><span class="sxs-lookup"><span data-stu-id="7927f-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="7927f-452">Der Arbeitsspeicherclerk für die Benutzerdatenbank, d. h. die Datenbank mit der ID 5, umfasst etwa 900 MB.</span><span class="sxs-lookup"><span data-stu-id="7927f-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="7927f-453">Arbeitsspeichernutzung pro Tabelle</span><span class="sxs-lookup"><span data-stu-id="7927f-453">Memory utilization per table</span></span>  
 <span data-ttu-id="7927f-454">Mithilfe der folgenden Abfrage kann ein Drilldown ausgeführt werden, um die Arbeitsspeichernutzung der einzelnen Tabellen und ihrer Indizes zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="7927f-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="7927f-455">Im Folgenden die Ergebnisse, die diese Abfrage bei einer Neuinstallation des Beispiels zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="7927f-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-456">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="7927f-456">**Table Name**</span></span>|<span data-ttu-id="7927f-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="7927f-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="7927f-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="7927f-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="7927f-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="7927f-460">64</span><span class="sxs-lookup"><span data-stu-id="7927f-460">64</span></span>|<span data-ttu-id="7927f-461">3840</span><span class="sxs-lookup"><span data-stu-id="7927f-461">3840</span></span>|  
|<span data-ttu-id="7927f-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="7927f-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="7927f-463">1984</span><span class="sxs-lookup"><span data-stu-id="7927f-463">1984</span></span>|<span data-ttu-id="7927f-464">5504</span><span class="sxs-lookup"><span data-stu-id="7927f-464">5504</span></span>|  
|<span data-ttu-id="7927f-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="7927f-466">15316</span><span class="sxs-lookup"><span data-stu-id="7927f-466">15316</span></span>|<span data-ttu-id="7927f-467">663552</span><span class="sxs-lookup"><span data-stu-id="7927f-467">663552</span></span>|  
|<span data-ttu-id="7927f-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="7927f-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="7927f-469">64</span><span class="sxs-lookup"><span data-stu-id="7927f-469">64</span></span>|<span data-ttu-id="7927f-470">10432</span><span class="sxs-lookup"><span data-stu-id="7927f-470">10432</span></span>|  
|<span data-ttu-id="7927f-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="7927f-472">3</span><span class="sxs-lookup"><span data-stu-id="7927f-472">3</span></span>|<span data-ttu-id="7927f-473">8192</span><span class="sxs-lookup"><span data-stu-id="7927f-473">8192</span></span>|  
|<span data-ttu-id="7927f-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="7927f-475">7168</span><span class="sxs-lookup"><span data-stu-id="7927f-475">7168</span></span>|<span data-ttu-id="7927f-476">147456</span><span class="sxs-lookup"><span data-stu-id="7927f-476">147456</span></span>|  
|<span data-ttu-id="7927f-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-477">Product_inmem</span></span>|<span data-ttu-id="7927f-478">124</span><span class="sxs-lookup"><span data-stu-id="7927f-478">124</span></span>|<span data-ttu-id="7927f-479">12352</span><span class="sxs-lookup"><span data-stu-id="7927f-479">12352</span></span>|  
  
 <span data-ttu-id="7927f-480">Sie erkennen, dass die Tabellen relativ klein sind: SalesOrderHeader_inmem umfasst ca. 7 MB und SalesOrderDetail_inmem ca. 15 MB.</span><span class="sxs-lookup"><span data-stu-id="7927f-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="7927f-481">Hier fällt auf, dass die den Indizes zugeordnete Arbeitsspeicherkapazität deutlich über der Kapazität der Tabellendaten liegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="7927f-482">Dies liegt daran, dass die Datengröße für die Hashindizes im Beispiel vorab auf einen höheren Wert festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="7927f-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="7927f-483">Da Hashindizes über eine feste Größe verfügen, wachsen sie nicht mit der Größe der Daten in der Tabelle mit.</span><span class="sxs-lookup"><span data-stu-id="7927f-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="7927f-484">Arbeitsspeichernutzung nach dem Ausführen der Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="7927f-485">Nach 10 Millionen eingefügten Verkaufsaufträgen stellt sich die Arbeitsspeichernutzung insgesamt wie folgt dar:</span><span class="sxs-lookup"><span data-stu-id="7927f-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-486">**type**</span><span class="sxs-lookup"><span data-stu-id="7927f-486">**type**</span></span>|<span data-ttu-id="7927f-487">**name**</span><span class="sxs-lookup"><span data-stu-id="7927f-487">**name**</span></span>|<span data-ttu-id="7927f-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="7927f-488">**pages_MB**</span></span>|  
|<span data-ttu-id="7927f-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-490">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-490">Default</span></span>|<span data-ttu-id="7927f-491">146</span><span class="sxs-lookup"><span data-stu-id="7927f-491">146</span></span>|  
|<span data-ttu-id="7927f-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="7927f-493">DB_ID_5</span></span>|<span data-ttu-id="7927f-494">7374</span><span class="sxs-lookup"><span data-stu-id="7927f-494">7374</span></span>|  
|<span data-ttu-id="7927f-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-496">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-496">Default</span></span>|<span data-ttu-id="7927f-497">0</span><span class="sxs-lookup"><span data-stu-id="7927f-497">0</span></span>|  
|<span data-ttu-id="7927f-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-499">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-499">Default</span></span>|<span data-ttu-id="7927f-500">0</span><span class="sxs-lookup"><span data-stu-id="7927f-500">0</span></span>|  
  
 <span data-ttu-id="7927f-501">Sie sehen, dass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] etwas weniger als 8 GB für die speicheroptimierten Tabellen und Indizes in der Beispieldatenbank belegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="7927f-502">Nach einem Testlauf ergibt sich die folgende Arbeitsspeichernutzung nach Tabellen:</span><span class="sxs-lookup"><span data-stu-id="7927f-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-503">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="7927f-503">**Table Name**</span></span>|<span data-ttu-id="7927f-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="7927f-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="7927f-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="7927f-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="7927f-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="7927f-507">5113761</span><span class="sxs-lookup"><span data-stu-id="7927f-507">5113761</span></span>|<span data-ttu-id="7927f-508">663552</span><span class="sxs-lookup"><span data-stu-id="7927f-508">663552</span></span>|  
|<span data-ttu-id="7927f-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="7927f-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="7927f-510">64</span><span class="sxs-lookup"><span data-stu-id="7927f-510">64</span></span>|<span data-ttu-id="7927f-511">10368</span><span class="sxs-lookup"><span data-stu-id="7927f-511">10368</span></span>|  
|<span data-ttu-id="7927f-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="7927f-513">2</span><span class="sxs-lookup"><span data-stu-id="7927f-513">2</span></span>|<span data-ttu-id="7927f-514">8192</span><span class="sxs-lookup"><span data-stu-id="7927f-514">8192</span></span>|  
|<span data-ttu-id="7927f-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="7927f-516">1575679</span><span class="sxs-lookup"><span data-stu-id="7927f-516">1575679</span></span>|<span data-ttu-id="7927f-517">147456</span><span class="sxs-lookup"><span data-stu-id="7927f-517">147456</span></span>|  
|<span data-ttu-id="7927f-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-518">Product_inmem</span></span>|<span data-ttu-id="7927f-519">111</span><span class="sxs-lookup"><span data-stu-id="7927f-519">111</span></span>|<span data-ttu-id="7927f-520">12032</span><span class="sxs-lookup"><span data-stu-id="7927f-520">12032</span></span>|  
|<span data-ttu-id="7927f-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="7927f-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="7927f-522">64</span><span class="sxs-lookup"><span data-stu-id="7927f-522">64</span></span>|<span data-ttu-id="7927f-523">3712</span><span class="sxs-lookup"><span data-stu-id="7927f-523">3712</span></span>|  
|<span data-ttu-id="7927f-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="7927f-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="7927f-525">1984</span><span class="sxs-lookup"><span data-stu-id="7927f-525">1984</span></span>|<span data-ttu-id="7927f-526">5504</span><span class="sxs-lookup"><span data-stu-id="7927f-526">5504</span></span>|  
  
 <span data-ttu-id="7927f-527">Es sind insgesamt etwa 6,5 GB Daten angegeben.</span><span class="sxs-lookup"><span data-stu-id="7927f-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="7927f-528">Beachten Sie, dass die Größe der Indizes für die Tabellen SalesOrderHeader_inmem und SalesOrderDetail_inmem der Größe der Indizes vor dem Einfügen der Verkaufsaufträge entspricht.</span><span class="sxs-lookup"><span data-stu-id="7927f-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="7927f-529">Die Indexgröße hat sich nicht geändert, weil beide Tabellen Hashindizes verwenden, die wiederum statisch sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="7927f-530">Nach dem Zurücksetzen der exemplarischen Arbeitauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-530">After demo reset</span></span>  
 <span data-ttu-id="7927f-531">Die gespeicherte Prozedur Demo.usp_DemoReset kann verwendet werden, um die exemplarische Arbeitsauslastung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7927f-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="7927f-532">Durch sie werden die Daten in den Tabellen SalesOrderHeader_inmem und SalesOrderDetail_inmem gelöscht und mit neuen Ausgangsdaten aus den urspünglichen Tabellen SalesOrderHeader und SalesOrderDetail aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7927f-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="7927f-533">Obwohl die Zeilen in den Tabellen gelöscht wurden, bedeutet dies nicht, dass der Arbeitsspeicher sofort freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="7927f-534">gibt den Arbeitsspeicher, der von den aus speicheroptimierten Tabellen gelöschten Zeilen belegt wurde, nach Bedarf im Hintergrund frei.</span><span class="sxs-lookup"><span data-stu-id="7927f-534">reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="7927f-535">Wenn im System keine Transaktionen ausgeführt werden, werden Sie feststellen, dass der von den gelöschten Zeilen belegte Arbeitsspeicher unmittelbar nach dem Zurücksetzen der exemplarischen Arbeitsauslastung noch nicht freigegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="7927f-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-536">**type**</span><span class="sxs-lookup"><span data-stu-id="7927f-536">**type**</span></span>|<span data-ttu-id="7927f-537">**name**</span><span class="sxs-lookup"><span data-stu-id="7927f-537">**name**</span></span>|<span data-ttu-id="7927f-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="7927f-538">**pages_MB**</span></span>|  
|<span data-ttu-id="7927f-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-540">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-540">Default</span></span>|<span data-ttu-id="7927f-541">2261</span><span class="sxs-lookup"><span data-stu-id="7927f-541">2261</span></span>|  
|<span data-ttu-id="7927f-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="7927f-543">DB_ID_5</span></span>|<span data-ttu-id="7927f-544">7396</span><span class="sxs-lookup"><span data-stu-id="7927f-544">7396</span></span>|  
|<span data-ttu-id="7927f-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-546">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-546">Default</span></span>|<span data-ttu-id="7927f-547">0</span><span class="sxs-lookup"><span data-stu-id="7927f-547">0</span></span>|  
|<span data-ttu-id="7927f-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-549">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-549">Default</span></span>|<span data-ttu-id="7927f-550">0</span><span class="sxs-lookup"><span data-stu-id="7927f-550">0</span></span>|  
  
 <span data-ttu-id="7927f-551">Erwartetes Verhalten: Der Arbeitsspeicher wird beim Ausführen der Transaktionsarbeitsauslastung freigegeben.</span><span class="sxs-lookup"><span data-stu-id="7927f-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="7927f-552">Wenn Sie die exemplarische Arbeitsauslastung ein zweites Mal ausführen, werden Sie anfänglich einen Rückgang der Arbeitsspeichernutzung feststellen, da die zuvor gelöschten Zeilen bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="7927f-553">Gleichzeitig nimmt die Arbeitsspeichergröße wieder zu, bis die Arbeitsauslastung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="7927f-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="7927f-554">Nachdem die exemplarische Arbeitsauslastung zurückgesetzt und 10 Millionen Zeilen eingefügt wurden, entspricht die Arbeitsspeichernutzung weitestgehend der Nutzung nach der ersten Ausführung.</span><span class="sxs-lookup"><span data-stu-id="7927f-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="7927f-555">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7927f-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="7927f-556">**type**</span><span class="sxs-lookup"><span data-stu-id="7927f-556">**type**</span></span>|<span data-ttu-id="7927f-557">**name**</span><span class="sxs-lookup"><span data-stu-id="7927f-557">**name**</span></span>|<span data-ttu-id="7927f-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="7927f-558">**pages_MB**</span></span>|  
|<span data-ttu-id="7927f-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-560">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-560">Default</span></span>|<span data-ttu-id="7927f-561">1863</span><span class="sxs-lookup"><span data-stu-id="7927f-561">1863</span></span>|  
|<span data-ttu-id="7927f-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="7927f-563">DB_ID_5</span></span>|<span data-ttu-id="7927f-564">7390</span><span class="sxs-lookup"><span data-stu-id="7927f-564">7390</span></span>|  
|<span data-ttu-id="7927f-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-566">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-566">Default</span></span>|<span data-ttu-id="7927f-567">0</span><span class="sxs-lookup"><span data-stu-id="7927f-567">0</span></span>|  
|<span data-ttu-id="7927f-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="7927f-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="7927f-569">Standard</span><span class="sxs-lookup"><span data-stu-id="7927f-569">Default</span></span>|<span data-ttu-id="7927f-570">0</span><span class="sxs-lookup"><span data-stu-id="7927f-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="7927f-571">Datenträgernutzung für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="7927f-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="7927f-572">Mithilfe der folgenden Abfrage können Sie ermitteln, wie viel Gesamtspeicherplatz die Prüfpunktdateien einer Datenbank zu einem bestimmten Zeitpunkt auf dem Datenträger belegen:</span><span class="sxs-lookup"><span data-stu-id="7927f-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="7927f-573">Anfangszustand</span><span class="sxs-lookup"><span data-stu-id="7927f-573">Initial state</span></span>  
 <span data-ttu-id="7927f-574">Bei der Erstellung der Beispieldateigruppe und der speicheroptimierten Beispieltabellen werden eine Reihe von Prüfpunktdateien vorab erstellt, und das System beginnt, die Dateien mit Daten aufzufüllen. Wie viele Prüfpunktdateien vorab erstellt werden, hängt von der Anzahl der logischen Prozessoren im System ab.</span><span class="sxs-lookup"><span data-stu-id="7927f-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="7927f-575">Da das Beispiel zunächst noch sehr klein ist, sind die vorab erstellten Dateien anfänglich überwiegend leer.</span><span class="sxs-lookup"><span data-stu-id="7927f-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="7927f-576">Im Folgenden wird die anfängliche Größe des Beispiels auf dem Datenträger angezeigt. Der verwendete Computer verfügt über 16 logische Prozessoren:</span><span class="sxs-lookup"><span data-stu-id="7927f-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="7927f-577">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="7927f-578">2312</span><span class="sxs-lookup"><span data-stu-id="7927f-578">2312</span></span>|  
  
 <span data-ttu-id="7927f-579">Wie Sie sehen, besteht eine große Diskrepanz zwischen der Größe der Prüfpunktdateien auf dem Datenträger (2,3 GB) und der tatsächlichen Datengröße, die näher bei 30 MB liegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="7927f-580">Mithilfe der folgenden Abfrage können Sie untersuchen, worauf die Datenträgerbelegung zurückzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="7927f-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="7927f-581">Die Größe auf dem Datenträger, die von dieser Abfrage zurückgegeben wird, stellt bei Dateien mit Status 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE) oder 7 (TOMBSTONE) einen Schätzwert dar.</span><span class="sxs-lookup"><span data-stu-id="7927f-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="7927f-582">Im Anfangszustand erzielt das Beispiel Ergebnisse, die in etwa denen eines Servers mit 16 logischen Prozessoren entsprechen:</span><span class="sxs-lookup"><span data-stu-id="7927f-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="7927f-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-583">**state_desc**</span></span>|<span data-ttu-id="7927f-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-584">**file_type_desc**</span></span>|<span data-ttu-id="7927f-585">**count**</span><span class="sxs-lookup"><span data-stu-id="7927f-585">**count**</span></span>|<span data-ttu-id="7927f-586">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="7927f-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-587">PRECREATED</span></span>|<span data-ttu-id="7927f-588">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-588">DATA</span></span>|<span data-ttu-id="7927f-589">16</span><span class="sxs-lookup"><span data-stu-id="7927f-589">16</span></span>|<span data-ttu-id="7927f-590">2048</span><span class="sxs-lookup"><span data-stu-id="7927f-590">2048</span></span>|  
|<span data-ttu-id="7927f-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-591">PRECREATED</span></span>|<span data-ttu-id="7927f-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-592">DELTA</span></span>|<span data-ttu-id="7927f-593">16</span><span class="sxs-lookup"><span data-stu-id="7927f-593">16</span></span>|<span data-ttu-id="7927f-594">128</span><span class="sxs-lookup"><span data-stu-id="7927f-594">128</span></span>|  
|<span data-ttu-id="7927f-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-596">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-596">DATA</span></span>|<span data-ttu-id="7927f-597">1</span><span class="sxs-lookup"><span data-stu-id="7927f-597">1</span></span>|<span data-ttu-id="7927f-598">128</span><span class="sxs-lookup"><span data-stu-id="7927f-598">128</span></span>|  
|<span data-ttu-id="7927f-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-600">DELTA</span></span>|<span data-ttu-id="7927f-601">1</span><span class="sxs-lookup"><span data-stu-id="7927f-601">1</span></span>|<span data-ttu-id="7927f-602">8</span><span class="sxs-lookup"><span data-stu-id="7927f-602">8</span></span>|  
  
 <span data-ttu-id="7927f-603">Wie Sie sehen, wird der meiste Speicherplatz durch vorab erstellte Daten- und Änderungsdateien belegt.</span><span class="sxs-lookup"><span data-stu-id="7927f-603">As you can see, most of the space is used by precreated data and delta files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="7927f-604">hat vorab ein Dateipaar (bestehend aus Daten- und Änderungsdatei) pro logischem Prozessor erstellt.</span><span class="sxs-lookup"><span data-stu-id="7927f-604">pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="7927f-605">Darüber hinaus wird für Datendateien vorab eine Größe von 128 MB und für Änderungsdateien eine Größe von 8 MB festgelegt. So können Daten effizienter in diese Dateien eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7927f-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="7927f-606">Die tatsächlichen Daten der speicheroptimierten Tabellen sind in einer einzelnen Datendatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7927f-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="7927f-607">Nach dem Ausführen der Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-607">After running the workload</span></span>  
 <span data-ttu-id="7927f-608">Nach einem einzelnen Testlauf, bei dem 10 Millionen Verkaufsaufträge eingefügt wurden, wird in etwa folgender Gesamtspeicherplatz auf dem Datenträger belegt (Testserver mit 16 Kernen):</span><span class="sxs-lookup"><span data-stu-id="7927f-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="7927f-609">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="7927f-610">8828</span><span class="sxs-lookup"><span data-stu-id="7927f-610">8828</span></span>|  
  
 <span data-ttu-id="7927f-611">Die Größe auf dem Datenträger liegt nahe bei 9 GB. Dies entspricht weitestgehend der Größe der Daten im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="7927f-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="7927f-612">Im Folgenden sind die Größen der Prüfpunktdateien in den einzelnen Phasen aufgeschlüsselt:</span><span class="sxs-lookup"><span data-stu-id="7927f-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="7927f-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-613">**state_desc**</span></span>|<span data-ttu-id="7927f-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-614">**file_type_desc**</span></span>|<span data-ttu-id="7927f-615">**count**</span><span class="sxs-lookup"><span data-stu-id="7927f-615">**count**</span></span>|<span data-ttu-id="7927f-616">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="7927f-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-617">PRECREATED</span></span>|<span data-ttu-id="7927f-618">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-618">DATA</span></span>|<span data-ttu-id="7927f-619">16</span><span class="sxs-lookup"><span data-stu-id="7927f-619">16</span></span>|<span data-ttu-id="7927f-620">2048</span><span class="sxs-lookup"><span data-stu-id="7927f-620">2048</span></span>|  
|<span data-ttu-id="7927f-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-621">PRECREATED</span></span>|<span data-ttu-id="7927f-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-622">DELTA</span></span>|<span data-ttu-id="7927f-623">16</span><span class="sxs-lookup"><span data-stu-id="7927f-623">16</span></span>|<span data-ttu-id="7927f-624">128</span><span class="sxs-lookup"><span data-stu-id="7927f-624">128</span></span>|  
|<span data-ttu-id="7927f-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-626">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-626">DATA</span></span>|<span data-ttu-id="7927f-627">1</span><span class="sxs-lookup"><span data-stu-id="7927f-627">1</span></span>|<span data-ttu-id="7927f-628">128</span><span class="sxs-lookup"><span data-stu-id="7927f-628">128</span></span>|  
|<span data-ttu-id="7927f-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-630">DELTA</span></span>|<span data-ttu-id="7927f-631">1</span><span class="sxs-lookup"><span data-stu-id="7927f-631">1</span></span>|<span data-ttu-id="7927f-632">8</span><span class="sxs-lookup"><span data-stu-id="7927f-632">8</span></span>|  
  
 <span data-ttu-id="7927f-633">Es sind weiterhin 16 vorab erstellte Dateipaare verfügbar, die nach dem Schließen der Prüfpunkte sofort einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="7927f-634">Ein Paar wird gerade erstellt, das bis zum Schließen des aktuellen Prüfpunkts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7927f-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="7927f-635">Zusammen mit den aktiven Prüfpunktdateien ergeben 6,5 GB Daten im Arbeitsspeicher eine Datenträgernutzung von ca. 6,5 GB.</span><span class="sxs-lookup"><span data-stu-id="7927f-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="7927f-636">Wie Sie wissen, werden Indizes nicht dauerhaft auf dem Datenträger gespeichert. Folglich ist die Gesamtgröße auf dem Datenträger in diesem Fall kleiner als die Datengröße im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="7927f-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="7927f-637">Nach dem Zurücksetzen der exemplarischen Arbeitauslastung</span><span class="sxs-lookup"><span data-stu-id="7927f-637">After demo reset</span></span>  
 <span data-ttu-id="7927f-638">Nach dem Zurücksetzen der exemplarischen Arbeitsauslastung wird der Speicherplatz auf dem Datenträger nicht sofort freigegeben, wenn das System keine Transaktionen ausführt und keine Datenbank-Prüfpunkte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7927f-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="7927f-639">Damit Prüfpunktdateien die verschiedenen Phasen durchlaufen und schließlich entfernt werden können, müssen eine Reihe von Prüfpunkten sowie Protokollkürzungen vorangegangen sein. Das ist erforderlich, um die Zusammenführung von Prüfpunktdateien sowie die Garbage Collection zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="7927f-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="7927f-640">Wenn das System Transaktionen ausführt (und Sie bei Verwendung des vollständigen Wiederherstellungsmodells regelmäßige Protokollsicherungen vornehmen), erfolgt dieser Schritt automatisch. Befindet sich das System wie im Beispielszenario jedoch im Leerlauf, wird dieser Schritt nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7927f-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="7927f-641">Nach dem Zurücksetzen der exemplarischen Arbeitauslastung sehen Sie in etwa folgende Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="7927f-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="7927f-642">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="7927f-643">11839</span><span class="sxs-lookup"><span data-stu-id="7927f-643">11839</span></span>|  
  
 <span data-ttu-id="7927f-644">Mit fast 12 GB liegen die Ergebnisse deutlich über den 9 GB vor dem Zurücksetzen der exemplarischen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="7927f-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="7927f-645">Dies ist darauf zurückzuführen, dass die Zusammenführung einiger Prüfpunktdateien zwar bereits gestartet, einige der Zusammenführungsziele jedoch noch nicht installiert wurden. Darüber hinaus wurden einige der zusammengeführten Quelldateien noch nicht bereinigt, wie im Folgenden ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="7927f-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="7927f-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-646">**state_desc**</span></span>|<span data-ttu-id="7927f-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-647">**file_type_desc**</span></span>|<span data-ttu-id="7927f-648">**count**</span><span class="sxs-lookup"><span data-stu-id="7927f-648">**count**</span></span>|<span data-ttu-id="7927f-649">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="7927f-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-650">PRECREATED</span></span>|<span data-ttu-id="7927f-651">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-651">DATA</span></span>|<span data-ttu-id="7927f-652">16</span><span class="sxs-lookup"><span data-stu-id="7927f-652">16</span></span>|<span data-ttu-id="7927f-653">2048</span><span class="sxs-lookup"><span data-stu-id="7927f-653">2048</span></span>|  
|<span data-ttu-id="7927f-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-654">PRECREATED</span></span>|<span data-ttu-id="7927f-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-655">DELTA</span></span>|<span data-ttu-id="7927f-656">16</span><span class="sxs-lookup"><span data-stu-id="7927f-656">16</span></span>|<span data-ttu-id="7927f-657">128</span><span class="sxs-lookup"><span data-stu-id="7927f-657">128</span></span>|  
|<span data-ttu-id="7927f-658">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="7927f-658">ACTIVE</span></span>|<span data-ttu-id="7927f-659">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-659">DATA</span></span>|<span data-ttu-id="7927f-660">38</span><span class="sxs-lookup"><span data-stu-id="7927f-660">38</span></span>|<span data-ttu-id="7927f-661">5152</span><span class="sxs-lookup"><span data-stu-id="7927f-661">5152</span></span>|  
|<span data-ttu-id="7927f-662">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="7927f-662">ACTIVE</span></span>|<span data-ttu-id="7927f-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-663">DELTA</span></span>|<span data-ttu-id="7927f-664">38</span><span class="sxs-lookup"><span data-stu-id="7927f-664">38</span></span>|<span data-ttu-id="7927f-665">1331</span><span class="sxs-lookup"><span data-stu-id="7927f-665">1331</span></span>|  
|<span data-ttu-id="7927f-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="7927f-666">MERGE TARGET</span></span>|<span data-ttu-id="7927f-667">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-667">DATA</span></span>|<span data-ttu-id="7927f-668">7</span><span class="sxs-lookup"><span data-stu-id="7927f-668">7</span></span>|<span data-ttu-id="7927f-669">896</span><span class="sxs-lookup"><span data-stu-id="7927f-669">896</span></span>|  
|<span data-ttu-id="7927f-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="7927f-670">MERGE TARGET</span></span>|<span data-ttu-id="7927f-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-671">DELTA</span></span>|<span data-ttu-id="7927f-672">7</span><span class="sxs-lookup"><span data-stu-id="7927f-672">7</span></span>|<span data-ttu-id="7927f-673">56</span><span class="sxs-lookup"><span data-stu-id="7927f-673">56</span></span>|  
|<span data-ttu-id="7927f-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="7927f-674">MERGED SOURCE</span></span>|<span data-ttu-id="7927f-675">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-675">DATA</span></span>|<span data-ttu-id="7927f-676">13</span><span class="sxs-lookup"><span data-stu-id="7927f-676">13</span></span>|<span data-ttu-id="7927f-677">1772</span><span class="sxs-lookup"><span data-stu-id="7927f-677">1772</span></span>|  
|<span data-ttu-id="7927f-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="7927f-678">MERGED SOURCE</span></span>|<span data-ttu-id="7927f-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-679">DELTA</span></span>|<span data-ttu-id="7927f-680">13</span><span class="sxs-lookup"><span data-stu-id="7927f-680">13</span></span>|<span data-ttu-id="7927f-681">455</span><span class="sxs-lookup"><span data-stu-id="7927f-681">455</span></span>|  
  
 <span data-ttu-id="7927f-682">Sobald Transaktionsaktivitäten im System auftreten, werden Zusammenführungsziele installiert und zusammengeführte Quelldateien bereinigt.</span><span class="sxs-lookup"><span data-stu-id="7927f-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="7927f-683">Nachdem die exemplarische Arbeitsauslastung ein zweites Mal ausgeführt, zurückgesetzt und 10 Millionen Verkaufsaufträge eingefügt wurden, werden Sie feststellen, dass die während der ersten Ausführung der Arbeitsauslastung erstellten Dateien bereinigt wurden.</span><span class="sxs-lookup"><span data-stu-id="7927f-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="7927f-684">Wenn Sie die vorangehende Abfrage bei aktiver Arbeitsauslastung mehrere Male ausführen, können Sie beobachten, wie die Prüfpunktdateien die verschiedenen Phasen durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="7927f-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="7927f-685">Nachdem die Arbeitsauslastung zum zweiten Mal ausgeführt und 10 Millionen Verkaufsaufträge eingefügt wurden, ist die Datenträgernutzung ähnlich (wenn auch nicht identisch) mit der Nutzung nach der ersten Ausführung. Dies liegt an der Dynamik des Systems.</span><span class="sxs-lookup"><span data-stu-id="7927f-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="7927f-686">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7927f-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="7927f-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-687">**state_desc**</span></span>|<span data-ttu-id="7927f-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="7927f-688">**file_type_desc**</span></span>|<span data-ttu-id="7927f-689">**count**</span><span class="sxs-lookup"><span data-stu-id="7927f-689">**count**</span></span>|<span data-ttu-id="7927f-690">**Größe auf dem Datenträger (MB)**</span><span class="sxs-lookup"><span data-stu-id="7927f-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="7927f-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-691">PRECREATED</span></span>|<span data-ttu-id="7927f-692">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-692">DATA</span></span>|<span data-ttu-id="7927f-693">16</span><span class="sxs-lookup"><span data-stu-id="7927f-693">16</span></span>|<span data-ttu-id="7927f-694">2048</span><span class="sxs-lookup"><span data-stu-id="7927f-694">2048</span></span>|  
|<span data-ttu-id="7927f-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="7927f-695">PRECREATED</span></span>|<span data-ttu-id="7927f-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-696">DELTA</span></span>|<span data-ttu-id="7927f-697">16</span><span class="sxs-lookup"><span data-stu-id="7927f-697">16</span></span>|<span data-ttu-id="7927f-698">128</span><span class="sxs-lookup"><span data-stu-id="7927f-698">128</span></span>|  
|<span data-ttu-id="7927f-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-700">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-700">DATA</span></span>|<span data-ttu-id="7927f-701">2</span><span class="sxs-lookup"><span data-stu-id="7927f-701">2</span></span>|<span data-ttu-id="7927f-702">268</span><span class="sxs-lookup"><span data-stu-id="7927f-702">268</span></span>|  
|<span data-ttu-id="7927f-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="7927f-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="7927f-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-704">DELTA</span></span>|<span data-ttu-id="7927f-705">2</span><span class="sxs-lookup"><span data-stu-id="7927f-705">2</span></span>|<span data-ttu-id="7927f-706">16</span><span class="sxs-lookup"><span data-stu-id="7927f-706">16</span></span>|  
|<span data-ttu-id="7927f-707">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="7927f-707">ACTIVE</span></span>|<span data-ttu-id="7927f-708">DATA</span><span class="sxs-lookup"><span data-stu-id="7927f-708">DATA</span></span>|<span data-ttu-id="7927f-709">41</span><span class="sxs-lookup"><span data-stu-id="7927f-709">41</span></span>|<span data-ttu-id="7927f-710">5608</span><span class="sxs-lookup"><span data-stu-id="7927f-710">5608</span></span>|  
|<span data-ttu-id="7927f-711">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="7927f-711">ACTIVE</span></span>|<span data-ttu-id="7927f-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="7927f-712">DELTA</span></span>|<span data-ttu-id="7927f-713">41</span><span class="sxs-lookup"><span data-stu-id="7927f-713">41</span></span>|<span data-ttu-id="7927f-714">328</span><span class="sxs-lookup"><span data-stu-id="7927f-714">328</span></span>|  
  
 <span data-ttu-id="7927f-715">In diesem Fall gibt es zwei Prüfpunktdateipaare mit dem Status „under construction“. Das legt die Vermutung nahe, dass aufgrund des hohen Parallelitätsgrads der Arbeitsauslastung mehrere Dateipaare in den Status „under construction“ versetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="7927f-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="7927f-716">Mehrere gleichzeitige Threads erforderten also zur selben Zeit ein neues Dateipaar, wodurch sich der Status eines Paares von „precreated“ in „under construction“ geändert hat.</span><span class="sxs-lookup"><span data-stu-id="7927f-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7927f-717">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7927f-717">See Also</span></span>  
 [<span data-ttu-id="7927f-718">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="7927f-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
