---
title: Microsoft Generic Content Tree Viewer (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724277"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="088f4-102">Microsoft Generic Content Tree Viewer (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="088f4-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="088f4-103">Der **Microsoft Generic Content Tree Viewer** zeigt ausführliche Informationen über den Inhalt eines Data Mining-Modells in einem standardisierten HTML-Tabellenformat an.</span><span class="sxs-lookup"><span data-stu-id="088f4-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="088f4-104">Diese Sicht ist hilfreich, da sie die zugrunde liegende Struktur des Modells zeigt sowie Details zu Koeffizienten, die Verteilung von Werten und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="088f4-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="088f4-105">Die tatsächlich in der Tabelle angezeigten Inhalte variieren je nach verwendetem Algorithmus und können Spalten, Regeln, Eigenschaften, Attribute, Knoten und Formeln umfassen.</span><span class="sxs-lookup"><span data-stu-id="088f4-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="088f4-106">Weitere Informationen zu Modellinhalten und zur Interpretation der Informationen eines jeden Modelltyps finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="088f4-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="088f4-107">Für die im Viewer angezeigten Informationen wird eine gemeinsame Struktur verwendet, die auf dem Schemarowset für Miningmodelle basiert.</span><span class="sxs-lookup"><span data-stu-id="088f4-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="088f4-108">Das Schemarowset für den Inhalt ist ein allgemeines Framework zum Speichern von Mustern, Statistiken und weiteren Inhalten eines Data Mining-Modells.</span><span class="sxs-lookup"><span data-stu-id="088f4-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="088f4-109">Eine Liste der Spalten im Data Mining-Schemarowset für Miningmodelle finden Sie unter [DMSCHEMA_MINING_MODEL_CONTENT-Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="088f4-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="088f4-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="088f4-110">Options</span></span>  
 <span data-ttu-id="088f4-111">**Knotenbeschriftung (Eindeutige ID)**</span><span class="sxs-lookup"><span data-stu-id="088f4-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="088f4-112">In diesem Bereich wird eine Liste aller Knoten im ausgewählten Miningmodell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="088f4-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="088f4-113">Die Knoten werden abhängig vom angezeigten Modelltyp unterschiedlich in der Struktur angeordnet.</span><span class="sxs-lookup"><span data-stu-id="088f4-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="088f4-114">Sie können auf die einzelnen Knoten klicken, um Details über den Knoten im Bereich **Knotendetails** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="088f4-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="088f4-115">**Knotendetails**</span><span class="sxs-lookup"><span data-stu-id="088f4-115">**Node details**</span></span>  
 <span data-ttu-id="088f4-116">Zeigt ausführliche Informationen über den Inhalt des ausgewählten Knotens an.</span><span class="sxs-lookup"><span data-stu-id="088f4-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="088f4-117">In jedem Knoten werden die dazugehörigen Informationen in einem standardisierten Format gespeichert, der Inhalt und die Bedeutung der Tabellenzeilen sind jedoch abhängig vom Typ des angezeigten Modells oder Knotens.</span><span class="sxs-lookup"><span data-stu-id="088f4-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="088f4-118">Die Informationen für einen Knoten, der eine Regel in einem Zuordnungsmodell darstellt, unterscheiden sich z. B. von den Informationen bei einem Knoten, der eine Struktur in einem Entscheidungsstrukturmodell darstellt.</span><span class="sxs-lookup"><span data-stu-id="088f4-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="088f4-119">Informationen zur Interpretation der Knoteninformationen eines bestimmten Modelltyps finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="088f4-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088f4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="088f4-120">See Also</span></span>  
 <span data-ttu-id="088f4-121">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="088f4-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="088f4-122">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="088f4-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="088f4-123">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="088f4-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
