---
title: Durchsuchen eines Modells mit dem Microsoft Generic Content Tree Viewer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622324"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="64da1-102">Durchsuchen eines Modells mit dem Microsoft Generic Content Tree Viewer</span><span class="sxs-lookup"><span data-stu-id="64da1-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="64da1-103">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Viewer für generische Miningmodellinhalte enthält ausführliche Informationen über die vom Miningalgorithmus erfassten Muster und bietet zudem Zugang zu verschiedenen Statistiken, die während des Analysevorgangs generiert werden.</span><span class="sxs-lookup"><span data-stu-id="64da1-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="64da1-104">Die Menge und Art der Informationen hängen von dem verwendeten Algorithmus ab und können folgende Kategorien umfassen:</span><span class="sxs-lookup"><span data-stu-id="64da1-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="64da1-105">Segmente der Daten und ihre Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="64da1-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="64da1-106">Beschreibende Statistik zu jeder Gruppe oder zum gesamten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="64da1-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="64da1-107">Die Anzahl von Verzweigungen oder untergeordnete Knoten in einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="64da1-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="64da1-108">Berechnungen, z. B. Varianz und Mitte, für einen Cluster oder einen Datensatz.</span><span class="sxs-lookup"><span data-stu-id="64da1-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="64da1-109">Durch Anzeigen dieser Informationen können Sie die Ergebnisse der Analyse besser verstehen.</span><span class="sxs-lookup"><span data-stu-id="64da1-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="64da1-110">Sie können auch Möglichkeiten identifizieren, Ihr Modell zu optimieren und anschließend erneut mit Daten zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="64da1-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="64da1-111">Oder Sie können sich dazu entschließen, Ihr Modell mit einem anderen Algorithmus erneut zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="64da1-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="64da1-112">Anzeigen von Miningmodellinhalten</span><span class="sxs-lookup"><span data-stu-id="64da1-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="64da1-113">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer zeigt die im *Schemarowset für den Inhalt* des Miningmodells enthaltenen Spalten, Regeln, Eigenschaften, Attribute, Knoten sowie andere Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="64da1-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="64da1-114">Das Schemarowset für den Inhalt ist ein allgemeines Framework zum Darstellen detaillierter Informationen über den Inhalt eines Data Mining-Modells.</span><span class="sxs-lookup"><span data-stu-id="64da1-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="64da1-115">Diese ausführlichen Informationen sind in einer HTML-Tabelle enthalten, in der die Muster, Cluster oder Strukturen im Modell als Knoten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="64da1-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="64da1-116">Sie können auf jeden Knoten klicken und ihn erweitern, um weitere Details anzuzeigen, z.B. die Formeln oder die Anzahl der unterschiedlichen Werte für ein numerisches Attribut.</span><span class="sxs-lookup"><span data-stu-id="64da1-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="64da1-117">Sie können auch die Beziehungen zwischen unter- und übergeordneten Elementen unter den Knoten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="64da1-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="64da1-118">Weitere Informationen zur allgemeinen Bedeutung der in den Miningmodellinhalten verwendeten Begriffe finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="64da1-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="64da1-119">Das Thema enthält außerdem Links zu Informationen über Miningmodellinhalte für bestimmte Modelltypen.</span><span class="sxs-lookup"><span data-stu-id="64da1-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="64da1-120">Jeder Miningmodelltyp enthält Informationen, die eng mit dem Algorithmus und den in den Daten gefundenen Mustern zusammenhängen. Daher wird empfohlen, die technische Referenz für den jeweiligen Modelltyp zu lesen, um jeden Modelltyp genau zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="64da1-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="64da1-121">Abfragen von Miningmodellinhalten</span><span class="sxs-lookup"><span data-stu-id="64da1-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="64da1-122">Die im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer enthaltenen Informationen können auch durch Abfragen des Miningmodells abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="64da1-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="64da1-123">Abfragen für Miningmodellinhalt können Sie mithilfe von DMX-Anweisungen (Data Mining-Erweiterungen) erstellen.</span><span class="sxs-lookup"><span data-stu-id="64da1-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="64da1-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]können Sie beispielsweise durch das Ausführen der folgenden DMX-Anweisung eine Inhaltsabfrage ausführen:</span><span class="sxs-lookup"><span data-stu-id="64da1-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="64da1-125">Weitere Informationen finden Sie unter [Data Mining-Abfragen](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64da1-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64da1-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64da1-126">See Also</span></span>  
 <span data-ttu-id="64da1-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining-&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="64da1-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="64da1-128">Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="64da1-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
