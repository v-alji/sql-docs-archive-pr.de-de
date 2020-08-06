---
title: Aktivieren der Komprimierung für eine Tabelle oder einen Index | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.compwiz.selectaction.f1
- sql12.swb.compwiz.welcome.f1
- sql12.swb.compwiz.scriptfileoption.f1
- sql12.swb.compwiz.createjob.f1
- sql12.swb.compwiz.progress.f1
- sql12.swb.compwiz.outputoptions.f1
- sql12.swb.compwiz.compressiontype.f1
- sql12.swb.compwiz.summary.f1
helpviewer_keywords:
- data compression wizard
- compression [SQL Server], enable
ms.assetid: b7442cff-e616-475a-9c5a-5a765089e5f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a51c3b5e0c4e9b5624911310ce20db5a8e060a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621002"
---
# <a name="enable-compression-on-a-table-or-index"></a><span data-ttu-id="7ad0a-102">Aktivieren der Komprimierung für eine Tabelle oder einen Index</span><span class="sxs-lookup"><span data-stu-id="7ad0a-102">Enable Compression on a Table or Index</span></span>
  <span data-ttu-id="7ad0a-103">In diesem Thema wird beschrieben, wie die Komprimierung für eine Tabelle oder einen Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-103">This topic describes how to enable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7ad0a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7ad0a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7ad0a-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7ad0a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7ad0a-107">Security</span><span class="sxs-lookup"><span data-stu-id="7ad0a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7ad0a-108">**So aktivieren Sie die Komprimierung für eine Tabelle oder einen Index mit:**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-108">**To enable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="7ad0a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ad0a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7ad0a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ad0a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ad0a-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7ad0a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7ad0a-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7ad0a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7ad0a-113">Für Systemtabellen ist die Komprimierung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-113">System tables cannot be enabled for compression.</span></span>  
  
-   <span data-ttu-id="7ad0a-114">Wenn die Tabelle ein Heap ist, erfolgt der Neuerstellungsvorgang für den ONLINE-Modus mit einem einzelnen Thread.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-114">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="7ad0a-115">Verwenden Sie den OFFLINE-Modus für einen Multithreaded-Neuerstellungsvorgang von Heaps.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-115">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="7ad0a-116">Weitere Informationen zur Datenkomprimierung finden Sie unter [Datenkomprimierung](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-116">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="7ad0a-117">Sie können die Komprimierungseinstellung einer einzelnen Partition nicht ändern, wenn die Tabelle nicht ausgerichtete Indizes aufweist.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7ad0a-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7ad0a-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ad0a-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ad0a-119">Permissions</span></span>  
 <span data-ttu-id="7ad0a-120">Erfordert die ALTER-Berechtigung für die Tabelle oder den Index.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ad0a-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ad0a-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-compression-on-a-table-or-index"></a><span data-ttu-id="7ad0a-122">So aktivieren Sie die Komprimierung für eine Tabelle oder einen Index</span><span class="sxs-lookup"><span data-stu-id="7ad0a-122">To enable compression on a table or index</span></span>  
  
1.  <span data-ttu-id="7ad0a-123">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, die Sie komprimieren möchten, und erweitern Sie dann den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="7ad0a-123">In Object Explorer, expand the database that contains the table that you want to compress and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="7ad0a-124">Um einen Index zu komprimieren, erweitern Sie die Tabelle mit dem Index, den Sie komprimieren möchten, und erweitern Sie dann den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="7ad0a-124">To compress an index, expand the table that contains the index that you want to compress and then expand the **Indexes** folder.</span></span>  
  
3.  <span data-ttu-id="7ad0a-125">Klicken Sie mit der rechten Maustaste auf die Tabelle oder den Index, die bzw. den Sie komprimieren möchten, zeigen Sie auf **Speicher**, und wählen Sie dann **Komprimierung verwalten…** aus.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-125">Right-click the table or index to compress, point to **Storage** and select **Manage Compression...**.</span></span>  
  
4.  <span data-ttu-id="7ad0a-126">Klicken Sie auf der Seite **Willkommen** des Datenkomprimierungs-Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7ad0a-127">Wählen Sie auf der Seite **Komprimierungstyp auswählen** für Komprimierungstyp aus, der auf alle Partitionen der Tabelle oder des Index angewendet werden soll, die Sie komprimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-127">On the **Select Compression Type** page, select the compression type to apply to each partition in the table or index you want to compress.</span></span> <span data-ttu-id="7ad0a-128">Klicken Sie abschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="7ad0a-129">Die folgenden Optionen sind auf der Seite **Komprimierungstyp auswählen** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="7ad0a-130">**Gleichen Komprimierungstyp für alle Partitionen verwenden** (Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="7ad0a-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="7ad0a-131">Wählen Sie diese Option aus, um für alle Partitionen die gleiche Komprimierungseinstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="7ad0a-132">Damit werden das Auswahlfeld aktiviert und die Spalte **Komprimierungstyp** im Raster deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="7ad0a-133">Wenn das Kontrollkästchen aktiviert ist, enthält die nebenstehende Liste die Optionen **Keiner**, **Zeile**und **Seite**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="7ad0a-134">**Partitionsnummer**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-134">**Partition Number**</span></span>  
     <span data-ttu-id="7ad0a-135">Listet jede Partition in der Tabelle bzw. im Index auf.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="7ad0a-136">Diese Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="7ad0a-137">**Komprimierungstyp**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-137">**Compression Type**</span></span>  
     <span data-ttu-id="7ad0a-138">Wählen Sie die Komprimierungsoption für jede Partition aus.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-138">Select the compression option for each partition.</span></span> <span data-ttu-id="7ad0a-139">Nicht verfügbar, wenn **Gleichen Komprimierungstyp für alle Partitionen verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="7ad0a-140">Listenoptionen sind **Keiner**, **Zeile**und **Seite**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="7ad0a-141">**Grenze**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-141">**Boundary**</span></span>  
     <span data-ttu-id="7ad0a-142">Zeigt die Partitionsbegrenzung an.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-142">Displays the partition boundary.</span></span> <span data-ttu-id="7ad0a-143">Diese Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="7ad0a-144">**Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-144">**Row Count**</span></span>  
     <span data-ttu-id="7ad0a-145">Zeigt die Anzahl von Zeilen in dieser Partition an.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="7ad0a-146">Diese Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="7ad0a-147">**Aktueller Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-147">**Current Space**</span></span>  
     <span data-ttu-id="7ad0a-148">Zeigt den aktuell von dieser Partition belegten Speicherplatz in Megabytes (MB) an.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="7ad0a-149">Diese Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="7ad0a-150">**Angeforderter komprimierter Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="7ad0a-151">Nachdem Sie auf **Berechnen**geklickt haben, wird in dieser Spalte die geschätzte Größe der einzelnen Partitionen nach der Komprimierung angezeigt. Dabei wird die in der Spalte **Komprimierungstyp** angegebene Einstellung zugrunde gelegt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="7ad0a-152">Diese Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="7ad0a-153">**Berechnen**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-153">**Calculate**</span></span>  
     <span data-ttu-id="7ad0a-154">Klicken Sie auf diese Option, um die Größe der einzelnen Partitionen nach der Komprimierung auf Grundlage der in der Spalte **Komprimierungstyp** angegebenen Einstellung zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="7ad0a-155">Geben Sie auf der Seite **Ausgabeoption auswählen** an, wie Sie die Komprimierung fertig stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-155">In the **Select an Output Option** page, specify how you want to complete your compression.</span></span> <span data-ttu-id="7ad0a-156">Wählen Sie **Skript erstellen** aus, um ein auf den vorherigen Seiten im Assistenten basierendes SQL-Skript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="7ad0a-157">Wählen Sie **Sofort ausführen** aus, um die neue partitionierte Tabelle zu erstellen, nachdem Sie alle verbleibenden Seiten im Assistenten vervollständigt haben.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="7ad0a-158">Wählen Sie **Zeitplan** aus, um die neue partitionierte Tabelle zu einer vorher bestimmten Zeit für die Zukunft zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="7ad0a-159">Wenn Sie **Skript erstellen**auswählen, sind die folgenden Optionen unter **Skriptoptionen**verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="7ad0a-160">**Skript in Datei schreiben**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-160">**Script to file**</span></span>  
     <span data-ttu-id="7ad0a-161">Generiert das Skript als SQL-Datei.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="7ad0a-162">Geben Sie in das Dialogfeld **Dateiname** einen Dateinamen und einen Speicherort ein, oder klicken Sie auf **Durchsuchen** , um das Dialogfeld **Speicherort der Skriptdatei** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="7ad0a-163">Wählen Sie in **Speichern unter** **Unicode-Text** oder **ANSI-Text**aus.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="7ad0a-164">**Skript in Zwischenablage schreiben**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="7ad0a-165">Speichert das Skript in der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="7ad0a-166">**Skript in Fenster "Neue Abfrage" schreiben**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="7ad0a-167">Generiert das Skript in einem neuen Abfrage-Editor-Fenster.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="7ad0a-168">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="7ad0a-169">Wenn Sie **Zeitplan**auswählen, klicken Sie auf **Zeitplan ändern**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="7ad0a-170">Geben Sie im Dialogfeld **Neuer Auftragszeitplan** im Feld **Name** den Namen des Auftragszeitplans ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="7ad0a-171">Wählen Sie in der Liste **Zeitplantyp** den Zeitplantyp aus:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="7ad0a-172">**Automatisch starten, wenn der SQL Server-Agent startet**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="7ad0a-173">**Starten, wenn sich die CPUs im Leerlauf befinden**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="7ad0a-174">**Wiederholt**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-174">**Recurring**.</span></span> <span data-ttu-id="7ad0a-175">Aktivieren Sie diese Option, wenn die neue partitionierte Tabellen regelmäßig mit neuen Informationen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="7ad0a-176">**Einmalige Ausführung**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-176">**One time**.</span></span> <span data-ttu-id="7ad0a-177">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="7ad0a-178">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Aktiviert** , um den Zeitplan zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="7ad0a-179">Wenn Sie **Wiederholt**auswählen:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="7ad0a-180">Geben Sie unter **Häufigkeit**in der Liste **Tritt auf** die Häufigkeit des Vorkommens an:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="7ad0a-181">Wenn Sie im Dialogfeld **Wiederholen alle**die Option **Täglich** auswählen, geben Sie ein, wie oft der Auftragszeitplan wiederholt wird (in Tagen).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="7ad0a-182">Wenn Sie im Dialogfeld **Wiederholen alle**die Option **Wöchentlich** auswählen, geben Sie ein, wie oft der Auftragszeitplan wiederholt wird (in Wochen).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="7ad0a-183">Wählen Sie den Tag oder die Tage der Woche aus, an denen der Auftragszeitplan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="7ad0a-184">Wenn Sie **Monatlich**auswählen, wählen Sie **Tag** oder **Am**aus.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="7ad0a-185">Wenn Sie **Tag**auswählen, geben Sie das Datum ein, an dem der Auftragszeitplan ausgeführt wird, und wie oft der Auftragszeitplan wiederholt werden soll (in Monaten).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="7ad0a-186">Wenn Sie beispielsweise möchten, dass der Auftragszeitplan jeden zweiten Monat am 15. ausgeführt wird, wählen Sie **Tag** aus, und geben Sie in das erste Feld „15“ und in das zweite Feld „2“ ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="7ad0a-187">Beachten Sie, dass die größte im zweiten Feld zulässige Zahl „99“ ist.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="7ad0a-188">Wenn Sie **Am**auswählen, geben Sie den spezifischen Tag der Woche im Monat an, an dem der Auftragszeitplan ausgeführt wird, und wie oft der Auftragszeitplan wiederholt werden soll (in Monaten).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="7ad0a-189">Wenn Sie beispielsweise möchten, dass der Auftragszeitplan jeden zweiten Monat am letzten Wochentag ausgeführt werden soll, wählen Sie **Tag** und in der ersten Liste **Letzter** und in der zweiten Liste **Wochentag** aus, und geben Sie in das letzte Feld „2“ ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="7ad0a-190">Sie können auch **ersten**, **zweiten**, **dritten**oder **vierten**sowie bestimmte Wochentage z. B. Sonntag oder Mittwoch) aus den ersten beiden Listen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="7ad0a-191">Beachten Sie, dass die größte im letzten Feld zulässige Zahl „99“ ist.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="7ad0a-192">Geben Sie unter **Häufigkeit pro Tag**an, wie oft der Auftragszeitplan an dem Tag wiederholt werden soll, an dem der Auftragszeitplan ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="7ad0a-193">Wenn Sie **Einmalig um**auswählen, geben Sie im Feld **Einmalig um** die spezifische Tageszeit ein, zu der der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="7ad0a-194">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="7ad0a-195">Wenn Sie **Alle**auswählen, geben Sie an, wie oft der Auftragszeitplan an dem unter **Häufigkeit**ausgewählten Tag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="7ad0a-196">Wenn Sie z.B. möchten, dass der Auftragszeitplan am Tag seiner Ausführung alle 2 Stunden wiederholt wird, wählen Sie **Alle** aus, geben in das erste Feld „2“ ein und wählen dann in der Liste **Stunde(n)** aus.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="7ad0a-197">Aus dieser Liste können Sie auch **Minute(n)** und **Sekunde(n)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="7ad0a-198">Beachten Sie, dass die größte im ersten Feld zulässige Zahl „100“ ist.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="7ad0a-199">Geben Sie im Feld **Start** die Zeit ein, zu der die Ausführung des Auftragszeitplans beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="7ad0a-200">Geben Sie im Feld **Ende** die Zeit ein, zu der die Ausführung des Auftragszeitplans enden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="7ad0a-201">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="7ad0a-202">Geben Sie unter **Dauer**in **Startdatum**das Datum ein, an dem die Ausführung des Auftragszeitplans beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="7ad0a-203">Wählen Sie **Enddatum** oder **Kein Enddatum** aus, um anzugeben, wann die Ausführung des Auftragszeitplans beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="7ad0a-204">Wenn Sie **Enddatum**auswählen, geben Sie das Datum ein, an dem die Ausführung des Auftragszeitplans beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="7ad0a-205">Wenn Sie **Einmal**auswählen, geben Sie unter **Einmalig**in das Feld **Datum** das Datum ein, an dem der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="7ad0a-206">Geben Sie im Feld **Uhrzeit** die Zeit ein, zu der der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="7ad0a-207">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="7ad0a-208">Überprüfen Sie unter **Zusammenfassung**im Feld **Beschreibung**, ob alle Auftragszeitplaneinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="7ad0a-209">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="7ad0a-210">Nach Fertigstellen dieser Seite klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="7ad0a-211">Erweitern Sie auf der Seite **Zusammenfassung der Überprüfung** unter **Überprüfen Sie Ihre Auswahl**alle verfügbaren Optionen, um zu überprüfen, ob alle Komprimierungseinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all compression settings are correct.</span></span> <span data-ttu-id="7ad0a-212">Klicken Sie auf **Fertig stellen**, wenn alle Einstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="7ad0a-213">Auf der Seite **Status des Komprimierungsassistenten** können Sie Statusinformationen zu den Aktionen des Assistenten zum Erstellen von Partitionen überwachen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="7ad0a-214">Je nach den im Assistenten ausgewählten Optionen enthält diese Seite eine oder mehrere Aktionen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="7ad0a-215">Im oberen Feld werden der Gesamtstatus des Assistenten und die Anzahl der empfangenen Status-, Fehler- und Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="7ad0a-216">Die folgenden Optionen sind auf der Seite **Status des Komprimierungsassistenten** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7ad0a-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="7ad0a-217">**Details**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-217">**Details**</span></span>  
     <span data-ttu-id="7ad0a-218">Stellt für jede vom Assistenten ausgeführte Aktion Informationen zur Aktion, zum Status und zu den zurückgegebenen Meldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="7ad0a-219">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-219">**Action**</span></span>  
     <span data-ttu-id="7ad0a-220">Gibt den Typ und den Namen jeder Aktion an.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="7ad0a-221">**Status**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-221">**Status**</span></span>  
     <span data-ttu-id="7ad0a-222">Gibt an, ob für die Aktion des Assistenten insgesamt der Wert **Erfolg** oder der Wert **Fehler**zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="7ad0a-223">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-223">**Message**</span></span>  
     <span data-ttu-id="7ad0a-224">Stellt alle vom Prozess zurückgegebenen Fehler- oder Warnmeldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="7ad0a-225">**Report**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-225">**Report**</span></span>  
     <span data-ttu-id="7ad0a-226">Erstellt einen Bericht mit den Ergebnissen des Assistenten zum Erstellen von Partitionen.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="7ad0a-227">Die Optionen sind **Bericht anzeigen**, **Bericht in Datei speichern**, **Bericht in Zwischenablage kopieren**und **Bericht als E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="7ad0a-228">**Bericht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-228">**View Report**</span></span>  
     <span data-ttu-id="7ad0a-229">Öffnet das Dialogfeld **Bericht anzeigen** , das einen Textbericht zum Fortschritt des Assistenten zum Erstellen von Partitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="7ad0a-230">**Bericht in Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-230">**Save Report to File**</span></span>  
     <span data-ttu-id="7ad0a-231">Öffnet das Dialogfeld **Bericht speichern unter** .</span><span class="sxs-lookup"><span data-stu-id="7ad0a-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="7ad0a-232">**Bericht in Zwischenablage kopieren**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="7ad0a-233">Kopiert die Ergebnisse aus dem Statusbericht des Assistenten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="7ad0a-234">**Bericht als E-Mail senden**</span><span class="sxs-lookup"><span data-stu-id="7ad0a-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="7ad0a-235">Kopiert die Ergebnisse aus dem Statusbericht des Assistenten in eine E-Mail.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="7ad0a-236">Nach Abschluss dieser Schritte klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7ad0a-237">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ad0a-237">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-compression-on-a-table"></a><span data-ttu-id="7ad0a-238">So aktivieren Sie die Komprimierung für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="7ad0a-238">To enable compression on a table</span></span>  
  
1.  <span data-ttu-id="7ad0a-239">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ad0a-240">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7ad0a-241">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-241">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7ad0a-242">Im Beispiel wird zuerst die gespeicherte Prozedur `sp_estimate_data_compression_savings` ausgeführt, um die geschätzte Größe des Objekts zurückzugeben, wenn die ROW-Komprimierungseinstellung verwendet würde.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-242">The example first executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the object if it were to use the ROW compression setting.</span></span> <span data-ttu-id="7ad0a-243">Im Beispiel wird dann die ROW-Komprimierung für alle Partitionen der angegebenen Tabelle aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-243">The example then enables ROW compression on all partitions in the specified table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_estimate_data_compression_savings 'Production', 'TransactionHistory', NULL, NULL, 'ROW' ;  
  
    ALTER TABLE Production.TransactionHistory REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = ROW);   
    GO  
    ```  
  
#### <a name="to-enable-compression-on-an-index"></a><span data-ttu-id="7ad0a-244">So aktivieren Sie die Komprimierung für einen Index</span><span class="sxs-lookup"><span data-stu-id="7ad0a-244">To enable compression on an index</span></span>  
  
1.  <span data-ttu-id="7ad0a-245">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-245">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ad0a-246">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-246">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7ad0a-247">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-247">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7ad0a-248">Im Beispiel wird zuerst die `sys.indexes` -Katalogsicht abgefragt, um den Namen und `index_id` für jeden Index der Tabelle `Production.TransactionHistory` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-248">The example first queries the `sys.indexes` catalog view to return the name and `index_id` for each index on the `Production.TransactionHistory` table.</span></span> <span data-ttu-id="7ad0a-249">Dann wird die gespeicherte Prozedur `sp_estimate_data_compression_savings` ausgeführt, um die geschätzte Größe der angegebenen Index-ID zurückzugeben, wenn die PAGE-Komprimierungseinstellung verwendet würde.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-249">It then executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the specified index ID if it were to use the PAGE compression setting.</span></span> <span data-ttu-id="7ad0a-250">Schließlich wird im Beispiel Index-ID 2 (`IX_TransactionHistory_ProductID`) neu erstellt, wobei die PAGE-Komprimierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ad0a-250">Finally, the example rebuilds index ID 2 (`IX_TransactionHistory_ProductID`), specifying PAGE compression.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT name, index_id  
    FROM sys.indexes  
    WHERE OBJECT_NAME (object_id) = N'TransactionHistory';  
  
    EXEC sp_estimate_data_compression_savings   
        @schema_name = 'Production',   
        @object_name = 'TransactionHistory',  
        @index_id = 2,   
        @partition_number = NULL,   
        @data_compression = 'PAGE' ;   
  
    ALTER INDEX IX_TransactionHistory_ProductID ON Production.TransactionHistory REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = PAGE);  
    GO  
    ```  
  
 <span data-ttu-id="7ad0a-251">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) und [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ad0a-251">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad0a-252">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ad0a-252">See Also</span></span>  
 <span data-ttu-id="7ad0a-253">[Datenkomprimierung](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="7ad0a-253">[Data Compression](data-compression.md) </span></span>  
 [<span data-ttu-id="7ad0a-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ad0a-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql)  
  
  
