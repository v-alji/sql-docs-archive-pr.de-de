---
title: Durchsuchen des bereitgestellten Cubes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619430"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="2e9b4-102">Durchsuchen des bereitgestellten Cubes</span><span class="sxs-lookup"><span data-stu-id="2e9b4-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="2e9b4-103">In der folgenden Aufgabe durchsuchen Sie den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="2e9b4-104">Da Measures in der Analyse dimensionsübergreifend verglichen werden, verwenden Sie zum Durchsuchen von Daten eine Excel-PivotTable.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="2e9b4-105">Mithilfe einer PivotTable lassen sich Kunden-, Datums- und Produktinformationen auf verschiedenen Achsen platzieren. So können Sie verfolgen, wie sich die Internetverkäufe ändern, wenn sie für bestimmte Zeiträume, Kundendemografien und Produktlinien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="2e9b4-106">So durchsuchen Sie den bereitgestellten Cube</span><span class="sxs-lookup"><span data-stu-id="2e9b4-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="2e9b4-107">Um zum Cube-Designer in zu wechseln [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , doppelklicken Sie im Ordner **Cubes** der Projektmappen-Explorer auf den \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial\*\* -Cube.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="2e9b4-108">Öffnen Sie die Registerkarte **Browser** , und klicken Sie dann auf der Symbolleiste des Designers auf die Schaltfläche **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="2e9b4-109">Klicken Sie auf das Excel-Symbol, um Excel zu starten, wobei die Arbeitsbereichsdatenbank als Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="2e9b4-110">Sobald Sie aufgefordert werden, Verbindungen zu aktivieren, klicken Sie auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="2e9b4-111">Erweitern Sie in der PivotTable-Feldliste **Internet Sales**, und ziehen Sie dann das **Sales Amount** -Measure in den Bereich **Werte** .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="2e9b4-112">Erweitern Sie in der PivotTable-Feldliste den Eintrag **Product**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="2e9b4-113">Ziehen Sie die **Product Model Lines** -Benutzerhierarchie in den Bereich **Spalten** .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="2e9b4-114">Erweitern Sie in der PivotTable-Feldliste die Option **Customer**, erweitern Sie **Location**, und ziehen Sie die **Customer Geography** -Hierarchie aus dem Anzeigeordner **Location** in der Customer-Dimension in den Bereich Zeilen.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="2e9b4-115">Erweitern Sie in der PivotTable-Feldliste den Eintrag **Order Date**, und ziehen Sie dann die **Order Date.Calendar Date** -Hierarchie in den Bereich **Berichtsfilter** .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="2e9b4-116">Klicken Sie auf den Filter rechts vom Filter **Order Date.Calendar Date** im Datenbereich, deaktivieren Sie das Kontrollkästchen für die Ebene **(Alle)** , erweitern Sie **2006**&gt; **H1 CY 2006**&gt; **Q1 CY 2006**, aktivieren Sie das Kontrollkästchen für **Februar 2006**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2e9b4-117">Internetverkäufe nach Region und Produktgruppe für den Monat Februar 2006 werden wie im folgenden Bild angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="2e9b4-118">![Internet Sales nach Land/Region und Produktlinie](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet Sales nach Land/Region und Produktlinie")</span><span class="sxs-lookup"><span data-stu-id="2e9b4-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2e9b4-119">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="2e9b4-119">Next Lesson</span></span>  
 [<span data-ttu-id="2e9b4-120">Lektion 4: Definieren von erweiterten Attributen und Dimensionseigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e9b4-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
