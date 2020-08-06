---
title: Ändern der Diskretisierung einer Spalte in einem Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621275"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="58b0e-102">Ändern der Diskretisierung von Spalten in Miningmodellen</span><span class="sxs-lookup"><span data-stu-id="58b0e-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="58b0e-103">diskretisiert automatisch Werte, d. h., in bestimmten Szenarien werden Daten in numerischen Spalten als Container formatiert.</span><span class="sxs-lookup"><span data-stu-id="58b0e-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="58b0e-104">Wenn die Daten zum Beispiel fortlaufende numerische Daten enthalten und Sie ein Entscheidungsstrukturmodell erstellen, wird jede Spalte mit fortlaufenden Daten abhängig von der Verteilung der Daten automatisch klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="58b0e-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="58b0e-105">Wenn Sie steuern möchten, wie die Daten diskretisiert werden, müssen Sie die Eigenschaften der Spalte "Miningstruktur" ändern, die steuern, wie die Daten im Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58b0e-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="58b0e-106">Allgemeine Informationen zum Festlegen der Eigenschaften eines Miningmodells finden Sie unter [Miningmodellspalten](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="58b0e-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="58b0e-107">So zeigen Sie die Eigenschaften einer Miningmodellspalte an</span><span class="sxs-lookup"><span data-stu-id="58b0e-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="58b0e-108">Klicken Sie im Data Mining-Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste entweder auf den Spaltenheader, der den Namen des Miningmodells enthält, oder auf die Zeile des Rasters mit dem Namen des Miningalgorithmus. Wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="58b0e-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="58b0e-109">Das Fenster **Eigenschaften** zeigt die Eigenschaften an, die dem Miningmodell insgesamt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58b0e-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="58b0e-110">Klicken Sie in der Spalte **Struktur** an der linken Seite des Bildschirms auf die Spalte, die die fortlaufenden numerischen Daten enthält, die Sie diskretisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="58b0e-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="58b0e-111">Das Fenster **Eigenschaften** zeigt die Eigenschaften an, die dieser Spalte zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58b0e-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="58b0e-112">So ändern Sie die Diskretisierungsmethode</span><span class="sxs-lookup"><span data-stu-id="58b0e-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="58b0e-113">Klicken Sie im Fenster **Mining Eigenschaften** auf das Textfeld neben **Inhalt**, und wählen Sie `Discretized` aus der Dropdown Liste aus.</span><span class="sxs-lookup"><span data-stu-id="58b0e-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="58b0e-114">Das Fenster <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> und <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> sind nun aktiviert.</span><span class="sxs-lookup"><span data-stu-id="58b0e-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="58b0e-115">Klicken Sie im Fenster **Eigenschaften** auf das Textfeld neben, <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> und wählen Sie einen der folgenden Werte aus: `Automatic` , `EqualAreas` oder `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="58b0e-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58b0e-116">Wenn die Spalten Verwendung auf festgelegt ist `Ignore` , ist das Fenster **Eigenschaften** für die Spalte leer.</span><span class="sxs-lookup"><span data-stu-id="58b0e-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="58b0e-117">Der neue Wert wird wirksam, wenn Sie ein anderes Element im Designer auswählen.</span><span class="sxs-lookup"><span data-stu-id="58b0e-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="58b0e-118">Klicken Sie im Data Mining-Designer auf der Registerkarte **Eigenschaften** neben <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> , und geben Sie einen numerischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="58b0e-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58b0e-119">Wenn Sie diese Eigenschaften ändern, muss die Struktur zusammen mit allen Modellen, in denen Sie die neue Einstellung verwenden möchten, neu verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="58b0e-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b0e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58b0e-120">See Also</span></span>  
 [<span data-ttu-id="58b0e-121">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="58b0e-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
