---
title: Ändern der Eigenschaften eines Mining Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608931"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="8c6e6-102">Ändern der Eigenschaften eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="8c6e6-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="8c6e6-103">Einige Miningmodelleigenschaften gelten für das gesamte Modell, wohingegen andere Modelleigenschaften für einzelne Spalten gelten.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="8c6e6-104">Beispiele von Eigenschaften, die für das gesamte Modell gelten, sind die `Drillthrough`-Eigenschaft, die angibt, ob die Falldaten für Abfragen verfügbar sein sollen, und die `Description`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="8c6e6-105">Eigenschaften, die für die Spalte gültig sind, schließen `Usage` und `ModelingFlags` ein, die steuern, wie Daten in der Spalte im Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="8c6e6-106">Die folgenden Modelleigenschaften besitzen erweiterte Editor-Programme, mit denen Ausdrücke erstellt oder komplexe Modelleigenschaften konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="8c6e6-107">Funktionen der folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8c6e6-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="8c6e6-108">`Filter`Property: öffnet das [Dialog Feld Datasetfilter oder Modell Filter](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="8c6e6-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="8c6e6-109">`AlgorithmParameters`Property: öffnet das [Dialog Feld Algorithmusparameter, &#40;Mining Modell Ansicht&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="8c6e6-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="8c6e6-110">Informationen zum Festlegen der Eigenschaften eines Miningmodells finden Sie unter [Miningmodellspalten](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8c6e6-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="8c6e6-111">So ändern Sie die Eigenschaften eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="8c6e6-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="8c6e6-112">Klicken Sie im Data Mining-Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste entweder auf den Spaltenheader, der den Namen des Miningmodells enthält, oder auf die Zeile des Rasters mit dem Namen des Miningalgorithmus. Wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8c6e6-113">Wählen Sie im Fenster **Eigenschaften** auf der rechten Seite des Bildschirms den Wert aus, der der Eigenschaft entspricht, die Sie ändern möchten, und geben Sie dann den neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="8c6e6-114">Der neue Wert wird wirksam, wenn Sie ein anderes Element im Designer auswählen.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="8c6e6-115">So ändern Sie die Eigenschaften einer Miningmodellspalte</span><span class="sxs-lookup"><span data-stu-id="8c6e6-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="8c6e6-116">Klicken Sie im Data Mining-Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste auf die Zelle des Rasters im Schnittpunkt zwischen Miningstrukturspalte und Miningmodell. Wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8c6e6-117">Wählen Sie im Fenster **Eigenschaften** auf der rechten Seite des Bildschirms den Wert aus, der der Eigenschaft entspricht, die Sie ändern möchten, und geben Sie dann den neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c6e6-118">Wenn die Spalten Verwendung auf festgelegt ist `Ignore` , ist das Fenster **Eigenschaften** für die Spalte leer.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="8c6e6-119">Der neue Wert wird wirksam, wenn Sie ein anderes Element im Designer auswählen.</span><span class="sxs-lookup"><span data-stu-id="8c6e6-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6e6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c6e6-120">See Also</span></span>  
 [<span data-ttu-id="8c6e6-121">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8c6e6-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
