---
title: Assistent für Verwendungs basierte Optimierung (F1-Hilfe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.f1
helpviewer_keywords:
- Usage-Based Optimization Wizard
ms.assetid: e5f5a938-ae7c-4f4e-9416-a7f94ac82763
author: minewiskan
ms.author: owend
ms.openlocfilehash: 517c122f79421294e1dfa562665948c4dc7bf95f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720353"
---
# <a name="usage-based-optimization-wizard-f1-help"></a><span data-ttu-id="5ffdf-102">Assistent für verwendungsbasierte Optimierung (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="5ffdf-102">Usage-Based Optimization Wizard F1 Help</span></span>
  <span data-ttu-id="5ffdf-103">Der Assistent für verwendungsbasierte Optimierung ist hinsichtlich der Ausgabe dem Aggregationsentwurfs-Assistenten ähnlich und wird zum Entwerfen von Aggregationen für eine Partition verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-103">The Usage-Based Optimization Wizard is similar in output to the Aggregation Design Wizard, and is used to design aggregations for a partition.</span></span> <span data-ttu-id="5ffdf-104">Die vom Assistenten für verwendungsbasierte Optimierung entworfenen Aggregationen basieren jedoch auf bestimmten Verwendungsmustern, die in dem Abfrageprotokoll einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-104">However, the Usage-Based Optimization Wizard designs aggregations based on the specific usage patterns of queries recorded in the query log of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="5ffdf-105">Aggregationen bieten Leistungsverbesserungen, indem Sie zulassen [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , dass vorab berechnete Summen direkt aus dem Cube-Speicher abgerufen werden, anstatt Daten aus einer zugrunde liegenden Datenquelle für jede Abfrage neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-105">Aggregations provide performance improvements by allowing [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to retrieve pre-calculated totals directly from cube storage instead of having to recalculate data from an underlying data source for each query.</span></span>  
  
 <span data-ttu-id="5ffdf-106">Öffnen Sie den [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Cube-Designer für ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt, und klicken Sie dann auf die Registerkarte **Aggregationen** , um den Assistenten für Verwendungs basierte Optimierung in zu öffnen. Klicken Sie auf der Symbolleiste auf die Schaltfläche **Verwendungs basierte Optimierung** .</span><span class="sxs-lookup"><span data-stu-id="5ffdf-106">To open the Usage-Based Optimization Wizard from within [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the cube designer for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click the **Aggregations** tab. Click the **Usage Based Optimization** button in the toolbar.</span></span>  
  
 <span data-ttu-id="5ffdf-107">Stellen Sie eine Verbindung mit einer [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Datenbank her, und öffnen Sie anschließend den Ordner [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Cubes **, um den Assistenten für verwendungsbasierte Optimierung in** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-107">To open the Usage-Based Optimization Wizard from within [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and then open the **Cubes** folder.</span></span> <span data-ttu-id="5ffdf-108">Wählen Sie einen Cube aus, öffnen Sie anschließend den Ordner **Measuregruppen** , und erweitern Sie die Measuregruppe, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-108">Select a cube and then open the **Measure Groups** folder and expand the measure group that you want to modify.</span></span> <span data-ttu-id="5ffdf-109">Klicken Sie mit der rechten Maustaste auf den Ordner **Partitionen** , und wählen Sie dann die Option **Verwendungsbasierte Optimierung**aus.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-109">Right-click the **Partitions** folder and then select **Usage Based Optimization**.</span></span>  
  
 <span data-ttu-id="5ffdf-110">Sie können den Aggregationsentwurfs-Assistenten verwenden, um diese Aggregationen zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-110">To design these aggregations, you can use the Aggregation Design Wizard.</span></span> <span data-ttu-id="5ffdf-111">Dieser Assistent führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="5ffdf-111">This wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="5ffdf-112">Auswählen von Standard- oder benutzerdefinierten Einstellungen für die Speicherungs- und Zwischenspeicherungsoptionen einer Partition, einer Measuregruppe oder eines Cubes.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-112">Selecting standard or custom settings for the storage and caching options of a partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="5ffdf-113">Bereitstellen von geschätzten oder tatsächlichen Werten für Objekte, auf die die Partition, die Measuregruppe oder der Cube verweist.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-113">Providing estimated or actual counts for objects referenced by the partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="5ffdf-114">Abgeben von Aggregationsoptionen und Grenzwerten, um den Speicher und die Abfrageleistung der entworfenen Aggregationen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-114">Specifying aggregation options and limits to optimize the storage and query performance delivered by designed aggregations.</span></span>  
  
-   <span data-ttu-id="5ffdf-115">Speichern und optionales Verarbeiten der Partition, der Measuregruppe oder des Cubes, um die definierten Aggregationen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-115">Saving and optionally processing the partition, measure group, or cube to generate the defined aggregations.</span></span>  
  
 <span data-ttu-id="5ffdf-116">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] wird der Aggregationsentwurfs-Assistent zum Entwerfen von Aggregationen bereitgestellt, die auf statistischen Analysen der Struktur der Partition basieren, um einen Aggregationsentwurf zu erstellen, der durch die Speicherplatzgröße oder den geschätzten Leistungsgewinn begrenzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-116">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides the Aggregation Design Wizard to design aggregations based on statistical analysis of the structure of the partition to deliver an aggregation design that can be limited by storage size or estimated performance gain.</span></span> <span data-ttu-id="5ffdf-117">Sie können den Aggregationsentwurfs-Assistenten dazu verwenden, die Gesamtleistung einer Partition zu steigern, aber der Aggregationsentwurf ist dann nicht auf die speziellen Bedürfnisse Ihrer gewerblichen Benutzer ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-117">You can use the Aggregation Design Wizard to improve the overall performance of a partition, but the aggregation design is not targeted to the specific needs of your business users.</span></span> <span data-ttu-id="5ffdf-118">Mit dem Assistenten für verwendungsbasierte Optimierung können Sie einen Aggregationsentwurf bereitstellen, der auf diese speziellen Bedürfnisse ausgerichtet ist. Das ist aber nur möglich, wenn das Abfrageprotokoll der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz genügend Informationen zum Erstellen solcher Abfragen enthält.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-118">The Usage-Based Optimization Wizard can provide an aggregation design targeted to these specific needs, but the wizard can do so only if the query log for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance contains enough information to construct such queries.</span></span>  
  
 <span data-ttu-id="5ffdf-119">Normalerweise werden beide Assistenten zusammen verwendet, um die Leistung sowohl in Bezug auf die Bereitstellung als auch in Bezug auf den Zeitverlauf zu steigern.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-119">Typically, both wizards are used together to improve performance both upon deployment and over time.</span></span> <span data-ttu-id="5ffdf-120">Der Aggregationsentwurfs-Assistent sollte zuerst verwendet werden, wenn die Partition (bzw. der Cube oder die Measuregruppe, die die Partition enthält) erstmalig bereitgestellt wird, um von einer besseren Gesamtleistung zu profitieren.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-120">The Aggregation Design Wizard should be used first, when the partition (or the cube or measure group containing the partition) is initially deployed, to provide an overall performance benefit.</span></span> <span data-ttu-id="5ffdf-121">Nach einem bestimmten Zeitraum, in dem die Abfragen der gewerblichen Benutzer für die Partition im Abfrageprotokoll aufgezeichnet wurden, können Sie den Assistenten für verwendungsbasierte Optimierung verwenden, um den Aggregationsentwurf stärker auf die bessere Erfüllung der Leistungs- und Abfrageanforderungen Ihrer gewerblichen Benutzer zu fokussieren.</span><span class="sxs-lookup"><span data-stu-id="5ffdf-121">After a period of time during which you have recorded the queries of business users for the partition in the query log, you can then use the Usage-Based Optimization Wizard to further focus the aggregation design to better serve the performance and query requirements of your business users.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ffdf-122">Informationen zum Konfigurieren des Abfrageprotokolls finden Sie unter [Konfigurieren des Abfrageprotokolls von Analysis Services](instances/log-operations-in-analysis-services.md?view=sql-server-2014#bkmk_querylog).</span><span class="sxs-lookup"><span data-stu-id="5ffdf-122">For information about configuring the query log, see [Configuring the Analysis Services Query Log](instances/log-operations-in-analysis-services.md?view=sql-server-2014#bkmk_querylog).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ffdf-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5ffdf-123">In This Section</span></span>  
  
-   [<span data-ttu-id="5ffdf-124">Wählen Sie Partitionen aus, um den Assistenten für Verwendungs basierte Optimierung zu &#40;ändern&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-124">Select Partitions to Modify &#40;Usage-Based Optimization Wizard&#41;</span></span>](select-partitions-to-modify-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-125">Geben Sie die Abfrage Kriterien &#40;Assistenten für Verwendungs basierte Optimierung an&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-125">Specify Query Criteria &#40;Usage-Based Optimization Wizard&#41;</span></span>](specify-query-criteria-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-126">Überprüfen Sie die Abfragen, die &#40;Assistenten für die Verwendungs basierte Optimierung optimiert werden&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-126">Review the Queries that will be Optimized &#40;Usage-Based Optimization Wizard&#41;</span></span>](review-the-queries-that-will-be-optimized-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-127">Überprüfen Sie die Aggregations Verwendung &#40;Verwendungs basierten Optimierungs-Assistenten&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-127">Review Aggregation Usage &#40;Usage-Based Optimiation Wizard&#41;</span></span>](review-aggregation-usage-usage-based-optimiation-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-128">Objekt Anzahl &#40;Verwendungs basierten Optimierungs Assistenten angeben&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-128">Specify Object Counts &#40;Usage-Based Optimization Wizard&#41;</span></span>](specify-object-counts-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-129">Festlegen der Aggregations Optionen &#40;Verwendungs basierte Optimierung-Assistent&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-129">Set Aggregation Options &#40;Usage-Based Optimization Wizard&#41;</span></span>](set-aggregation-options-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="5ffdf-130">Der Assistent &#40;Assistenten für Verwendungs basierte Optimierung abgeschlossen&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-130">Completing the Wizard &#40;Usage-Based Optimization Wizard&#41;</span></span>](completing-the-wizard-usage-based-optimization-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ffdf-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ffdf-131">See Also</span></span>  
 <span data-ttu-id="5ffdf-132">[Aggregationen und Aggregations Entwürfe](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span><span class="sxs-lookup"><span data-stu-id="5ffdf-132">[Aggregations and Aggregation Designs](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span></span>  
 <span data-ttu-id="5ffdf-133">[Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="5ffdf-133">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="5ffdf-134">[Aggregations Entwurfs-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5ffdf-134">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="5ffdf-135">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="5ffdf-135">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  