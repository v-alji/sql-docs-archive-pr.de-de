---
title: Aggregations Entwurfs-Assistent F1-Hilfe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregation Design Wizard
ms.assetid: 39e23cf1-6405-4fb6-bc14-ba103314362d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace30a07970b1871d037ebe6f31b2079f1895ffa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615232"
---
# <a name="aggregation-design-wizard-f1-help"></a><span data-ttu-id="5119f-102">Aggregationsentwurfs-Assistent (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="5119f-102">Aggregation Design Wizard F1 Help</span></span>
  <span data-ttu-id="5119f-103">Aggregationen bieten Leistungsverbesserungen, indem Sie zulassen [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , dass vorab berechnete Summen direkt aus dem Cube-Speicher abgerufen werden, anstatt Daten aus einer zugrunde liegenden Datenquelle für jede Abfrage neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="5119f-103">Aggregations provide performance improvements by allowing [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to retrieve pre-calculated totals directly from cube storage instead of having to recalculate data from an underlying data source for each query.</span></span>  
  
 <span data-ttu-id="5119f-104">Sie können den Aggregationsentwurfs-Assistenten verwenden, um diese Aggregationen zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="5119f-104">To design these aggregations, you can use the Aggregation Design Wizard.</span></span> <span data-ttu-id="5119f-105">Dieser Assistent führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="5119f-105">This wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="5119f-106">Auswählen von Standard- oder benutzerdefinierten Einstellungen für die Speicherungs- und Zwischenspeicherungsoptionen einer Partition, einer Measuregruppe oder eines Cubes.</span><span class="sxs-lookup"><span data-stu-id="5119f-106">Selecting standard or custom settings for the storage and caching options of a partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="5119f-107">Bereitstellen von geschätzten oder tatsächlichen Werten für Objekte, auf die die Partition, die Measuregruppe oder der Cube verweist.</span><span class="sxs-lookup"><span data-stu-id="5119f-107">Providing estimated or actual counts for objects referenced by the partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="5119f-108">Abgeben von Aggregationsoptionen und Grenzwerten, um den Speicher und die Abfrageleistung der entworfenen Aggregationen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="5119f-108">Specifying aggregation options and limits to optimize the storage and query performance delivered by designed aggregations.</span></span>  
  
-   <span data-ttu-id="5119f-109">Speichern und optionales Verarbeiten der Partition, der Measuregruppe oder des Cubes, um die definierten Aggregationen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5119f-109">Saving and optionally processing the partition, measure group, or cube to generate the defined aggregations.</span></span>  
  
 <span data-ttu-id="5119f-110">Nach Verwendung des Aggregationsentwurfs-Assistenten können Sie mithilfe des Assistenten für verwendungsbasierte Optimierung Aggregationen entwerfen, die auf den Verwendungsmustern gewerblicher Benutzer und den den Cube abfragenden Clientanwendungen basieren.</span><span class="sxs-lookup"><span data-stu-id="5119f-110">After you use the Aggregation Design Wizard, you can use the Usage-Based Optimization Wizard to design aggregations based on the usage patterns of the business users and client applications that query the cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5119f-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5119f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5119f-112">Wählen Sie Partitionen zum Ändern &#40;Aggregations Entwurfs-Assistenten aus&#41;</span><span class="sxs-lookup"><span data-stu-id="5119f-112">Select Partitions to Modify &#40;Aggregation Design Wizard&#41;</span></span>](select-partitions-to-modify-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="5119f-113">Überprüfen der Aggregations Verwendung &#40;Aggregations Entwurfs-&#41;Assistenten</span><span class="sxs-lookup"><span data-stu-id="5119f-113">Review Aggregation Usage &#40;Aggregation Design Wizard&#41;</span></span>](review-aggregation-usage-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="5119f-114">Objekt Anzahl &#40;Aggregations Entwurfs-Assistenten angeben&#41;</span><span class="sxs-lookup"><span data-stu-id="5119f-114">Specify Object Counts &#40;Aggregation Design Wizard&#41;</span></span>](specify-object-counts-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="5119f-115">Aggregations Optionen &#40;Aggregations Entwurfs-Assistenten festlegen&#41;</span><span class="sxs-lookup"><span data-stu-id="5119f-115">Set Aggregation Options &#40;Aggregation Design Wizard&#41;</span></span>](set-aggregation-options-aggregation-design-wizard.md)  
  
-   [<span data-ttu-id="5119f-116">Der Assistent &#40;Aggregations Entwurfs-Assistenten wird abgeschlossen&#41;</span><span class="sxs-lookup"><span data-stu-id="5119f-116">Completing the Wizard &#40;Aggregation Design Wizard&#41;</span></span>](completing-the-wizard-aggregation-design-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="5119f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5119f-117">See Also</span></span>  
 <span data-ttu-id="5119f-118">[Aggregationen und Aggregations Entwürfe](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span><span class="sxs-lookup"><span data-stu-id="5119f-118">[Aggregations and Aggregation Designs](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span></span>  
 <span data-ttu-id="5119f-119">[Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="5119f-119">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="5119f-120">[Assistent für Verwendungs basierte Optimierung (F1-Hilfe)](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5119f-120">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="5119f-121">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="5119f-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
