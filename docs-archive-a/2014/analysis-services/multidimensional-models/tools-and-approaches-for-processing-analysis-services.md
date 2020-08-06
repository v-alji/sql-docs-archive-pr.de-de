---
title: Tools und Ansätze für die Verarbeitung (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618351"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="76a00-102">Tools und Ansätze zum Verarbeiten (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="76a00-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="76a00-103">Die Verarbeitung ist ein Vorgang, bei dem Analysis Services Daten aus einer relationalen Datenquelle abfragt und Analysis Services-Objekte mit diesen Daten auffüllt.</span><span class="sxs-lookup"><span data-stu-id="76a00-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="76a00-104">Als Analysis Services-Systemadministrator können Sie die Verarbeitung der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte mithilfe der folgenden Ansätze ausführen und überwachen:</span><span class="sxs-lookup"><span data-stu-id="76a00-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="76a00-105">Ausführen der Auswirkungsanalyse, um Objektabhängigkeiten und den Umfang von Vorgängen zu verstehen</span><span class="sxs-lookup"><span data-stu-id="76a00-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="76a00-106">Verarbeiten von einzelnen Objekten in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a00-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="76a00-107">Verarbeiten von einzelnen oder mehreren Objekten in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a00-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="76a00-108">Führen Sie die Auswirkungsanalyse aus, um eine Liste von verbundenen Objekten zu überprüfen, die als Ergebnis der aktuellen Aktion nicht verarbeitet sind.</span><span class="sxs-lookup"><span data-stu-id="76a00-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="76a00-109">Generieren und Ausführen eines Skripts in einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -XMLA-Abfragefenster in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , um einzelne oder mehrere Objekte zu verarbeiten</span><span class="sxs-lookup"><span data-stu-id="76a00-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="76a00-110">Verwenden von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="76a00-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="76a00-111">Verwenden von Ablaufsteuerungen und Tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketen</span><span class="sxs-lookup"><span data-stu-id="76a00-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="76a00-112">Überwachen von Verarbeitung mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="76a00-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="76a00-113">Programmieren Sie mit AMO eine benutzerdefinierte Lösung.</span><span class="sxs-lookup"><span data-stu-id="76a00-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="76a00-114">Weitere Informationen finden Sie unter [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="76a00-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="76a00-115">Die Verarbeitung ist ein stark konfigurierbarer Vorgang. Selbiger wird von einem Satz von Verarbeitungsoptionen gesteuert, die bestimmen, ob vollständige oder inkrementelle Verarbeitung auf Objektebene auftritt.</span><span class="sxs-lookup"><span data-stu-id="76a00-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="76a00-116">Weitere Informationen zu Verarbeitungsoptionen und -objekten finden Sie unter [Verarbeiten von Optionen und Einstellungen &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) und [Verarbeiten von Analysis Services-Objekten](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76a00-117">In diesem Thema werden die Tools und die Ansätze zum Verarbeiten von mehrdimensionalen Modellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76a00-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="76a00-118">Weitere Informationen zum Verarbeiten von tabellarischen Modellen finden Sie unter Verarbeiten von Daten [Banken, Tabellen oder Partitionen](../tabular-models/process-database-table-or-partition-analysis-services.md) und [Verarbeiten von Daten &#40;SSAS-Tabellen&#41;](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="76a00-119">Verarbeiten von Objekten in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76a00-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="76a00-120">Starten Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , und stellen Sie eine Verbindung mit Analysis Services her.</span><span class="sxs-lookup"><span data-stu-id="76a00-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="76a00-121">Klicken Sie mit der rechten Maustaste auf das Analysis Services-Objekt, das Sie verarbeiten möchten, und klicken Sie auf **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="76a00-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="76a00-122">Sie können Daten auf einer dieser Ebenen verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="76a00-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="76a00-123">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="76a00-123">Databases</span></span>  
  
    -   <span data-ttu-id="76a00-124">Cubes</span><span class="sxs-lookup"><span data-stu-id="76a00-124">Cubes</span></span>  
  
    -   <span data-ttu-id="76a00-125">Measuregruppen oder einzelne Partitionen in der Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="76a00-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="76a00-126">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="76a00-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="76a00-127">Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="76a00-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="76a00-128">Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="76a00-128">Mining Structures</span></span>  
  
     <span data-ttu-id="76a00-129">Analysis Services-Objekte sind hierarchisch.</span><span class="sxs-lookup"><span data-stu-id="76a00-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="76a00-130">Wenn Sie die Datenbank wählen, kann die Verarbeitung für alle in der Datenbank enthaltenen Objekte durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76a00-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="76a00-131">Ob die Verarbeitung tatsächlich durchgeführt wird, hängt von der ausgewählten Verarbeitungsoption und vom Status des Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="76a00-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="76a00-132">Insbesondere gilt: Wenn ein Objekt noch nicht verarbeitet wurde, führt die Verarbeitung seines übergeordneten Elements dazu, dass das Objekt selbst auch verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="76a00-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="76a00-133">Weitere Informationen zu Objektabhängigkeiten finden Sie unter [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="76a00-134">Verwenden Sie im Dialogfeld **Verarbeiten** unter **Verarbeitungsoptionen**den bereitgestellten Standardwert, oder wählen Sie in der Liste eine andere Option aus.</span><span class="sxs-lookup"><span data-stu-id="76a00-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="76a00-135">Weitere Informationen finden Sie unter [Verarbeiten von Optionen und Einstellungen &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="76a00-136">Klicken Sie auf **Auswirkungsanalyse** , um abhängige Objekte zu identifizieren und optional zu verarbeiten, die betroffen sind, wenn die im Dialogfeld Verarbeiten aufgeführten Objekte verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="76a00-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="76a00-137">Klicken Sie optional auf **Einstellungen ändern** , um die Verarbeitungsreihenfolge, das Verarbeitungsverhalten relativ zu bestimmten Typen von Fehlern und andere Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="76a00-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="76a00-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76a00-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="76a00-139">Im Dialogfeld Verarbeitungsstatus wird für jeden Befehl fortlaufend der Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76a00-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="76a00-140">Wenn eine Statusmeldung abgeschnitten ist, können Sie auf **Details anzeigen** klicken, um die ganze Meldung zu lesen.</span><span class="sxs-lookup"><span data-stu-id="76a00-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="76a00-141">Verarbeiten von Objekten in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="76a00-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="76a00-142">Starten Sie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , und öffnen Sie ein Projekt, das bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="76a00-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="76a00-143">Erweitern Sie im Projektmappen-Explorer den Ordner **Dimensionen** unter dem bereitgestellten Projekt.</span><span class="sxs-lookup"><span data-stu-id="76a00-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="76a00-144">Klicken Sie mit der rechten Maustaste auf eine Dimension, und klicken Sie dann auf **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="76a00-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="76a00-145">Sie können mit der rechten Maustaste auf mehrere Dimensionen klicken, um mehrere Objekte auf einmal zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="76a00-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="76a00-146">Weitere Informationen finden Sie unter [Batchverarbeitung &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="76a00-147">Überprüfen Sie im Dialogfeld **Dimension aufbereiten** in der Spalte **Verarbeitungsoptionen** unter **Objektliste**, ob die Option für diese Spalte **Vollständig verarbeiten**lautet.</span><span class="sxs-lookup"><span data-stu-id="76a00-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="76a00-148">Sollte dies nicht der Fall sein, klicken Sie unter **Verarbeitungsoptionen**auf die Option, und wählen Sie aus der Dropdownliste **Vollständig verarbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="76a00-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="76a00-149">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="76a00-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="76a00-150">Klicken Sie nach Abschluss der Verarbeitung auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="76a00-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="76a00-151">Ausführen der Auswirkungs Analyse, um Objektabhängigkeiten und den Umfang der Vorgänge zu identifizieren</span><span class="sxs-lookup"><span data-stu-id="76a00-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="76a00-152">Bevor Sie ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekt in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] oder [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]verarbeiten, können Sie die Auswirkung auf die verbundenen Objekte analysieren, indem Sie auf **Auswirkungsanalyse** in einem der **Objekte verarbeiten** -Dialogfelder klicken.</span><span class="sxs-lookup"><span data-stu-id="76a00-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="76a00-153">Klicken Sie mit der rechten Maustaste auf eine Dimension, einen Cube, eine Measuregruppe oder eine Partition, um ein Dialogfeld **Objekte verarbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="76a00-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="76a00-154">Klicken Sie auf **Auswirkungsanalyse**.</span><span class="sxs-lookup"><span data-stu-id="76a00-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="76a00-155">scannt das Modell und berichtet über Neuverarbeitungsanforderungen für Objekte, die auf das für die Verarbeitung ausgewählte verweisen.</span><span class="sxs-lookup"><span data-stu-id="76a00-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="76a00-156">Verarbeiten von Objekten mit XMLA</span><span class="sxs-lookup"><span data-stu-id="76a00-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="76a00-157">Starten Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , und stellen Sie eine Verbindung mit Analysis Services her.</span><span class="sxs-lookup"><span data-stu-id="76a00-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="76a00-158">Klicken Sie mit der rechten Maustaste auf das Objekt, und klicken Sie dann auf **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="76a00-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="76a00-159">Wählen Sie im Dialogfeld **Verarbeiten** die Verarbeitungsoption aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="76a00-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="76a00-160">Ändern Sie beliebige andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="76a00-160">Modify any other settings.</span></span> <span data-ttu-id="76a00-161">Führen Sie die Auswirkungsanalyse aus, um die Änderungen zu identifizieren, die ggf. vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="76a00-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="76a00-162">Klicken Sie im Bildschirm zum Verarbeiten von Objekten \*\*\*\* auf **Skript** .</span><span class="sxs-lookup"><span data-stu-id="76a00-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="76a00-163">Mit diesem Schritt wird ein XMLA-Skript generiert und ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -XMLA-Abfragefenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="76a00-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="76a00-164">Schließen Sie das Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="76a00-164">Close the dialog box.</span></span> <span data-ttu-id="76a00-165">Das Skript enthält den Verarbeitungsbefehl und die Optionen, die im Dialogfeld angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="76a00-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="76a00-166">Sie können optional dem Skript weiterhin Elemente hinzufügen, wenn Sie zusätzliche Objekte im gleichen Batch verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="76a00-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="76a00-167">Wiederholen Sie zum Fortfahren die vorherigen Schritte, und fügen Sie das generierte Skript an, damit Sie über ein einzelnes Skript für alle Verarbeitungsvorgänge verfügen.</span><span class="sxs-lookup"><span data-stu-id="76a00-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="76a00-168">Ein Beispiel finden Sie unter [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="76a00-169">Klicken Sie in der Menüleiste auf **Abfrage**, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="76a00-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="76a00-170">Verarbeiten von Objekten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="76a00-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="76a00-171">Ab dieser Version von SQL Server können Sie Analysis Services PowerShell-Cmdlets zum Verarbeiten von Objekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="76a00-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="76a00-172">Die folgenden Cmdlets können interaktiv oder per Skript ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="76a00-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="76a00-173">Invoke-ProcessCube-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="76a00-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="76a00-174">Invoke-ProcessDimension-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="76a00-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="76a00-175">Invoke-ProcessPartition-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="76a00-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="76a00-176">[Invoke-ASCmd-Cmdlet](/powershell/module/sqlserver/invoke-ascmd), das verwendet werden kann, um ein XMLA-, MDX- oder DMX-Skript mit Verarbeitungsbefehlen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="76a00-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="76a00-177">Überwachungsobjektverarbeitung mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="76a00-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="76a00-178">Stellen Sie in SQL Server Profiler eine Verbindung zu einer Analysis Services-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="76a00-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="76a00-179">Klicken Sie unter **Ereignisauswahl** aufAlle Ereignisse anzeigen, um der Liste alle Ereignisse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76a00-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="76a00-180">Wählen Sie eines der folgenden Ereignisse aus:</span><span class="sxs-lookup"><span data-stu-id="76a00-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="76a00-181">**Command Begin** und **Command End** , um anzuzeigen, wenn die Verarbeitung gestartet und angehalten wird</span><span class="sxs-lookup"><span data-stu-id="76a00-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="76a00-182">**Error** , um sämtliche Fehler aufzuzeichnen</span><span class="sxs-lookup"><span data-stu-id="76a00-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="76a00-183">**Progress Report Begin**, **Progress Report Current**und **Progress Report End** , um über den Verarbeitungsstatus zu berichten und die SQL-Abfragen anzuzeigen, die verwendet wurden, um die Daten abzurufen</span><span class="sxs-lookup"><span data-stu-id="76a00-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="76a00-184">**Execute MDX Script Begin** und **Execute MDX Script End** , um die Cubeberechnungen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="76a00-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="76a00-185">Fügen Sie alternativ Sperrereignisse hinzu, wenn Sie auf Verarbeitung bezogene Leistungsprobleme diagnostizieren</span><span class="sxs-lookup"><span data-stu-id="76a00-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="76a00-186">Verarbeiten von Analysis Services-Objekten mit Integration Services</span><span class="sxs-lookup"><span data-stu-id="76a00-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="76a00-187">Erstellen Sie in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]ein Paket, das den Analysis Services-Verarbeitungstask verwendet, um Objekte automatisch mit neuen Daten aufzufüllen wenn Sie regelmäßige Updates an der relationalen Quelldatenbank vornehmen.</span><span class="sxs-lookup"><span data-stu-id="76a00-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="76a00-188">Doppelklicken Sie in der **SSIS-Toolbox**auf **Analysis Services-Verarbeitung** , um den Task zum Paket hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76a00-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="76a00-189">Bearbeiten Sie den Task, um eine Verbindung zur Datenbank anzugeben und um zu bestimmen, welche Objekte verarbeitet werden sollen und um die Verarbeitungsoption zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="76a00-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="76a00-190">Weitere Informationen zum Implementieren dieses Tasks finden Sie unter [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="76a00-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a00-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76a00-191">See Also</span></span>  
 [<span data-ttu-id="76a00-192">Verarbeitung von mehrdimensionalen Modellobjekten</span><span class="sxs-lookup"><span data-stu-id="76a00-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
