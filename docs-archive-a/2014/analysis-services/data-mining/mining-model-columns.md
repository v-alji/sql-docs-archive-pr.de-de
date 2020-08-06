---
title: Mining Modell Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700497"
---
# <a name="mining-model-columns"></a><span data-ttu-id="585b3-102">Miningmodellspalten</span><span class="sxs-lookup"><span data-stu-id="585b3-102">Mining Model Columns</span></span>
  <span data-ttu-id="585b3-103">Ein Data Mining-Modell wendet einen Miningmodellalgorithmus für die Daten an, welcher durch eine Miningstruktur dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="585b3-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="585b3-104">Wie die Miningstruktur enthält das Miningmodell Spalten.</span><span class="sxs-lookup"><span data-stu-id="585b3-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="585b3-105">Ein Miningmodell ist in der Miningstruktur enthalten und erbt alle Werte der Eigenschaften, die von der Miningstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="585b3-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="585b3-106">Das Modell kann alle Spalten aus der Miningstruktur oder nur eine Teilmenge der Spalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="585b3-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="585b3-107">Sie können für eine Miningmodellspalte zwei weitere Informationen definieren: Verwendung und Modellierungsflags.</span><span class="sxs-lookup"><span data-stu-id="585b3-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="585b3-108">Bei der**Verwendung** handelt es sich um eine Eigenschaft, die definiert, wie das Modell die Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="585b3-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="585b3-109">Spalten können als Eingabespalten, Schlüsselspalten oder vorhersagbare Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="585b3-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="585b3-110">**Modellierungsflags** stellen weitere Informationen zu den in der Falltabelle definierten Daten für den Algorithmus bereit, sodass der Algorithmus ein genaueres Modell erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="585b3-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="585b3-111">Modellierungsflags können programmgesteuert in der Sprache Data Mining-Erweiterungen (DMX) oder in **mit dem** Data Mining-Designer [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]definiert werden.</span><span class="sxs-lookup"><span data-stu-id="585b3-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="585b3-112">In der folgenden Liste werden die Modellierungsflags beschrieben, die Sie für eine Miningmodellspalte definieren können.</span><span class="sxs-lookup"><span data-stu-id="585b3-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="585b3-113">Gibt an, dass das Vorhandensein der Attributs wichtiger ist als die Werte in der Attributspalte.</span><span class="sxs-lookup"><span data-stu-id="585b3-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="585b3-114">Stellen Sie sich z. B. eine Falltabelle mit einer Bestellelementenliste vor, die einem bestimmten Kunden zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="585b3-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="585b3-115">Die Tabellendaten enthalten für jedes Element Produkttyp, Bezeichner und Kosten.</span><span class="sxs-lookup"><span data-stu-id="585b3-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="585b3-116">Für die Modellierung kann die Tatsache, dass der Kunde einen bestimmtes Bestellelement erworben hat, wichtiger sein als die Kosten des Bestellelements selbst.</span><span class="sxs-lookup"><span data-stu-id="585b3-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="585b3-117">In diesem Fall sollte die Cost-Spalte mit `MODEL_EXISTENCE_ONLY` gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="585b3-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="585b3-118">Zeigt an, dass der Algorithmus die angegebene Spalte in der Regressionsformel von Regressionsalgorithmen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="585b3-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="585b3-119">Dieses Flag wird von den Algorithmen [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees und [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series unterstützt.</span><span class="sxs-lookup"><span data-stu-id="585b3-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="585b3-120">Weitere Informationen zum Festlegen der Verwendungseigenschaft und zum programmgesteuerten Definieren des Modellierungsflags mit DMX finden Sie unter [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="585b3-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="585b3-121">Weitere Informationen zum Festlegen der Verwendungseigenschaft und zum Definieren des Modellierungsflags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]finden Sie unter [Verschieben von Data Mining-Objekten](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="585b3-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585b3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="585b3-122">See Also</span></span>  
 <span data-ttu-id="585b3-123">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="585b3-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="585b3-124">[Mining Strukturen &#40;Analysis Services Data Mining-&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="585b3-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="585b3-125">[Ändern der Eigenschaften eines Mining Modells](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="585b3-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="585b3-126">[Ausschließen einer Spalte aus einem Mining Modell](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="585b3-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="585b3-127">Miningstrukturspalten</span><span class="sxs-lookup"><span data-stu-id="585b3-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
