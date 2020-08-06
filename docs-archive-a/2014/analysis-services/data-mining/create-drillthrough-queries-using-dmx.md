---
title: Erstellen von Drillthrough-Abfragen mit DMX | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620059"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="d3a5a-102">Erstellen von Drillthroughabfragen mit DMX</span><span class="sxs-lookup"><span data-stu-id="d3a5a-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="d3a5a-103">Für alle Modelle, die Drillthrough unterstützen, können Fall- und Strukturdaten durch Erstellen einer DMX-Abfrage in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder einem beliebigen anderen Client abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d3a5a-104">Zum Anzeigen der Daten muss Drillthrough aktiviert werden, wofür Sie die entsprechenden Berechtigungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="d3a5a-105">Angeben von Drillthroughoptionen</span><span class="sxs-lookup"><span data-stu-id="d3a5a-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="d3a5a-106">Die allgemeine Syntax zum Abrufen von Modell- und Strukturfällen sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="d3a5a-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="d3a5a-107">Weitere Informationen zur Verwendung von DMX-Abfragen zum Zurückgeben von Falldaten finden Sie unter [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) und [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="d3a5a-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d3a5a-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d3a5a-108">Examples</span></span>  
 <span data-ttu-id="d3a5a-109">Bei der folgenden DMX-Abfrage werden die Falldaten für eine bestimmte Produktreihe von einem Zeitreihenmodell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="d3a5a-110">Die Abfrage gibt außerdem die Spalte `Amount` zurück, die zwar nicht im Modell verwendet wurde, jedoch in der Miningstruktur verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="d3a5a-111">In diesem Beispiel wird ein Alias verwendet, um die Strukturspalte umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="d3a5a-112">Wenn Sie der Strukturspalte keinen Alias zuordnen, wird die Spalte mit dem Namen "Expression" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="d3a5a-113">Dies ist das Standardverhalten für alle unbenannten Spalten.</span><span class="sxs-lookup"><span data-stu-id="d3a5a-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a5a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3a5a-114">See Also</span></span>  
 <span data-ttu-id="d3a5a-115">[Drillthrough-Abfragen &#40;Data Mining-&#41;](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d3a5a-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="d3a5a-116">Drillthrough in Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="d3a5a-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
