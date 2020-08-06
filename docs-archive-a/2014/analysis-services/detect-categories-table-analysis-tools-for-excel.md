---
title: Kategorien erkennen (Tabellenanalyse Tools für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722017"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="b2e11-102">Kategorien erkennen (Tabellenanalysetool für Excel)</span><span class="sxs-lookup"><span data-stu-id="b2e11-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="b2e11-103">![Kategorien erkennen (Schaltfläche auf Menüband)](media/tat-detectcat.gif "Kategorien erkennen (Schaltfläche auf Menüband)")</span><span class="sxs-lookup"><span data-stu-id="b2e11-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="b2e11-104">Das Tool **Kategorien erkennen** ermittelt automatisch Zeilen in einer Tabelle, die ähnliche Merkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="b2e11-105">Bei Abschluss des Tools wird ein Bericht erstellt, in dem die gefundenen Kategorien zusammen mit ihren charakteristischen Merkmalen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="b2e11-106">Standardmäßig wird der Datentabelle, die die vorgeschlagene Kategorie enthält, für jede Zeile Ihrer Daten eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2e11-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="b2e11-107">Sie können die Kategorien dann überprüfen und umbenennen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="b2e11-108">Verwenden des Tools Kategorien erkennen</span><span class="sxs-lookup"><span data-stu-id="b2e11-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="b2e11-109">Öffnen Sie eine Excel-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b2e11-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="b2e11-110">Klicken Sie auf **Kategorien erkennen**.</span><span class="sxs-lookup"><span data-stu-id="b2e11-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="b2e11-111">Geben Sie die in der Analyse zu verwendenden Spalten an.</span><span class="sxs-lookup"><span data-stu-id="b2e11-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="b2e11-112">Sie können die Auswahl von Spalten, die andere Werte aufweisen, wie Personennamen oder Datensatz-IDs, aufheben, wenn diese Spalten für die Analyse nicht nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2e11-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="b2e11-113">Geben Sie optional die maximale Anzahl der zu erstellenden Kategorien an.</span><span class="sxs-lookup"><span data-stu-id="b2e11-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="b2e11-114">Standardmäßig werden vom Tool so viele Kategorien automatisch erstellt, wie von ihm gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="b2e11-115">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b2e11-115">Click **Run**.</span></span>

6.  <span data-ttu-id="b2e11-116">Es wird ein neues Arbeitsblatt mit dem Namen Kategoriebericht vom Tool erstellt, in dem die Kategorien und deren Merkmale aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="b2e11-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="b2e11-117">Weitere Informationen zum Angeben von Optionen für das Tool finden Sie unter [Dialog Feld "Kategorien erkennen" (Tabellenanalyse Tools für Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b2e11-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="b2e11-118">Grundlegendes zum Kategoriebericht</span><span class="sxs-lookup"><span data-stu-id="b2e11-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="b2e11-119">Der **Kategoriebericht** enthält zwei Tabellen: **Kategorie** -und **Kategoriemerkmale**und ein Diagramm für **Kategorieprofile** .</span><span class="sxs-lookup"><span data-stu-id="b2e11-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="b2e11-120">Kategorieliste</span><span class="sxs-lookup"><span data-stu-id="b2e11-120">Category List</span></span>
 <span data-ttu-id="b2e11-121">In der ersten Tabelle sind die Kategorien aufgeführt, die gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="b2e11-122">Die Spalte **Zeilen Anzahl** gibt an, wie viele Daten Zeilen jeder Kategorie zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="b2e11-123">Im Modell werden temporäre Namen für jede Kategorie erstellt, die Kategorien können aber nach Bedarf umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="b2e11-124">Im folgenden Beispiel wurde die erste Kategorie als **niedriges Einkommen**umbenannt, da dies das oberste Attribut des Clusters war.</span><span class="sxs-lookup"><span data-stu-id="b2e11-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="b2e11-125">![Mit dem Tool "Kategorien erkennen" erstellter Bericht](media/dm13-tat-detectcat-report1.gif "Mit dem Tool "Kategorien erkennen" erstellter Bericht")</span><span class="sxs-lookup"><span data-stu-id="b2e11-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b2e11-126">Sobald Sie die neue Bezeichnung eingeben, wird die Änderung an alle anderen Diagramme sowie an die Kategorieliste weitergegeben, die im Quelldatenarbeitsblatt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b2e11-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="b2e11-127">Kategoriemerkmale</span><span class="sxs-lookup"><span data-stu-id="b2e11-127">Category Characteristics</span></span>
 <span data-ttu-id="b2e11-128">In der zweiten Tabelle, **Kategorieeigenschaften**, werden Details über die Zusammensetzung der einzelnen Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2e11-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="b2e11-129">Klicken Sie oben in der Spalte **Kategorie** auf die Schaltfläche **Filter** , um den Fokus auf ein oder nur einige Kategorien zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="b2e11-130">![Mit dem Tool "Kategorien erkennen" erstellter Bericht](media/dm13-tat-detectcat-report2.gif "Mit dem Tool "Kategorien erkennen" erstellter Bericht")</span><span class="sxs-lookup"><span data-stu-id="b2e11-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b2e11-131">Die Schattierung in der Spalte, **relative Wichtigkeit**, gibt an, wie wichtig diese Kombination von Attribut und Wert ist.</span><span class="sxs-lookup"><span data-stu-id="b2e11-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="b2e11-132">Je länger der Balken, desto wahrscheinlicher ist es, dass das Attribut für seine Kategorie stark repräsentativ ist.</span><span class="sxs-lookup"><span data-stu-id="b2e11-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="b2e11-133">Kategorieprofildiagramm</span><span class="sxs-lookup"><span data-stu-id="b2e11-133">Categories Profile Chart</span></span>
 <span data-ttu-id="b2e11-134">Das abschließende Diagramm im Arbeits **Categories Report** Blatt " **kategorieberichte", "Kategorieprofile**", ist ein interaktives **PivotChart** , das Sie verwenden können, um Felder neu anzuordnen und auszublenden, nach Werten zu filtern und die Diagramm Darstellung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="b2e11-135">Excel 2013 bietet jetzt **Diagramm Stile** und **Diagramm Elemente** -Steuerelemente direkt in der Entwurfs Oberfläche, die das verbessern des Diagramm Entwurfs erleichtern.</span><span class="sxs-lookup"><span data-stu-id="b2e11-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="b2e11-136">![Mit dem Tool "Kategorien erkennen" erstellter Bericht](media/dm13-tat-detectcat-report3.gif "Mit dem Tool "Kategorien erkennen" erstellter Bericht")</span><span class="sxs-lookup"><span data-stu-id="b2e11-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="b2e11-137">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2e11-137">Requirements</span></span>
 <span data-ttu-id="b2e11-138">Das Tool **Kategorien erkennen** hat keine Anforderungen hinsichtlich der Menge oder des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="b2e11-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="b2e11-139">Wenn Sie das Tool **Kategorien erkennen** verwenden, wird in der ursprünglichen Datentabelle eine neue Spalte (Kategorie) erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2e11-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="b2e11-140">Wenn Sie diese Spalte in der Datentabelle belassen, beeinflusst sie möglicherweise die Ergebnisse von anschließend durchgeführten Data Mining-Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="b2e11-141">Erstellen Sie daher eine Kopie der Datentabelle ohne die Spalte Kategorie, um sicherzustellen, dass diese Spalte sich nicht auf andere Vorgänge auswirkt, bevor Sie andere Data Mining-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2e11-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="b2e11-142">Verwandte Tools</span><span class="sxs-lookup"><span data-stu-id="b2e11-142">Related Tools</span></span>
 <span data-ttu-id="b2e11-143">Wenn das Tool **Kategorien erkennen** Ihre Daten analysiert, erstellt es mithilfe des Clustering-Algorithmus eine Data Mining Struktur und Data Mining Modell [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2e11-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="b2e11-144">Nachdem Sie mit dem Tool **wichtige Einflussfaktoren analysieren** ein Data Mining Modell erstellt haben, können Sie den Data Mining-Client für Excel verwenden, um das Modell zu durchsuchen und die Beziehungen ausführlicher zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b2e11-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="b2e11-145">Der Data Mining-Client für Excel stellt ein separates Add-In mit erweiterter Data Mining-Funktionalität dar.</span><span class="sxs-lookup"><span data-stu-id="b2e11-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="b2e11-146">Weitere Informationen finden Sie unter durch [Suchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="b2e11-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="b2e11-147">Weitere Informationen zur Verwendung der Daten Modellierungsfunktionen im Data Mining-Client für Excel finden Sie unter [Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="b2e11-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="b2e11-148">Weitere Informationen zum Algorithmus, der vom Tool **Kategorien erkennen** verwendet wird, finden Sie im Thema "Microsoft Clustering-Algorithmus" in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2e11-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2e11-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2e11-149">See Also</span></span>
 [<span data-ttu-id="b2e11-150">Tabellenanalysetools für Excel</span><span class="sxs-lookup"><span data-stu-id="b2e11-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


