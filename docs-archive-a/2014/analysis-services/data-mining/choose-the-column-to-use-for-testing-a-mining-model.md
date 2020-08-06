---
title: Wählen Sie die Spalte aus, die zum Testen eines Mining Modells verwendet werden soll. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619458"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="aab13-102">Auswählen der zum Testen eines Miningmodells zu verwendenden Spalte</span><span class="sxs-lookup"><span data-stu-id="aab13-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="aab13-103">Bevor Sie die Genauigkeit eines Miningmodells messen können, müssen Sie sich entscheiden, welches Ergebnis Sie bewerten möchten.</span><span class="sxs-lookup"><span data-stu-id="aab13-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="aab13-104">Bei den meisten Data Mining-Modellen müssen Sie mindestens eine Spalte auswählen, die als vorhersagbares Attribut verwendet werden soll, wenn Sie das Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="aab13-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="aab13-105">Wenn Sie die Genauigkeit des Modells testen, müssen Sie daher im Allgemeinen dieses Attribut zum Testen auswählen.</span><span class="sxs-lookup"><span data-stu-id="aab13-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="aab13-106">In der folgenden Liste werden einige weitere Überlegungen zum Auswählen des vorhersagbaren Attributs, das in Tests verwendet werden soll, beschrieben:</span><span class="sxs-lookup"><span data-stu-id="aab13-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="aab13-107">Einige Typen von Data Mining Modellen können mehrere Attribute vorhersagen, wie z. b. neuronale Netzwerke, die die Beziehungen zwischen vielen Attributen untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="aab13-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="aab13-108">Andere Typen von Mining Modellen, z. b. Clustering-Modelle, verfügen nicht unbedingt über ein vorhersagbares Attribut.</span><span class="sxs-lookup"><span data-stu-id="aab13-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="aab13-109">Clustermodelle können nicht getestet werden, außer wenn sie über ein vorhersagbares Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="aab13-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="aab13-110">Sie müssen als Ergebnis ein kontinuierliches vorhersagbares Attribut auswählen, um ein Punktdiagramm zu erstellen oder die Genauigkeit eines Regressionsmodells zu messen.</span><span class="sxs-lookup"><span data-stu-id="aab13-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="aab13-111">In diesem Fall können Sie keinen Zielwert angeben.</span><span class="sxs-lookup"><span data-stu-id="aab13-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="aab13-112">Wenn Sie etwas anderes als ein Punktdiagramm erstellen, muss die zugrunde liegende Miningstrukturspalte auch einen Inhaltstyp von **Diskret** oder **Diskretisiert**haben.</span><span class="sxs-lookup"><span data-stu-id="aab13-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="aab13-113">Wenn Sie ein diskretes Attribut als vorhersagbares Ergebnis auswählen, können Sie auch einen Zielwert angeben, oder Sie können das Feld **Wert vorhersagen** leer lassen.</span><span class="sxs-lookup"><span data-stu-id="aab13-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="aab13-114">Wenn Sie einen **Vorhersagewert**einschließen, misst das Diagramm nur die Effektivität des Modells bei der Vorhersage des Zielwerts.</span><span class="sxs-lookup"><span data-stu-id="aab13-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="aab13-115">Wenn Sie kein Zielergebnis angeben, wird das Modell in Bezug auf seine Genauigkeit gemessen, alle Ergebnisse vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="aab13-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="aab13-116">Wenn Sie mehrere Modelle einschließen und sie in einem einzelnen Genauigkeitsdiagramm vergleichen möchten, müssen alle Modelle die gleiche vorhersagbare Spalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="aab13-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="aab13-117">Beim Erstellen eines Kreuzvalidierungsberichts werden alle Modelle von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatisch analysiert, die dasselbe vorhersagbare Attribut haben.</span><span class="sxs-lookup"><span data-stu-id="aab13-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="aab13-118">Wenn die Option **Vorhersagespalten und -werte synchronisieren**ausgewählt wird, werden von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatisch vorhersagbare Spalten ausgewählt, die über die gleichen Namen und übereinstimmenden Datentypen verfügen.</span><span class="sxs-lookup"><span data-stu-id="aab13-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="aab13-119">Wenn die Spalten diese Kriterien nicht erfüllen, können Sie diese Option deaktivieren und manuell eine vorhersagbare Spalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="aab13-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="aab13-120">Dies ist möglicherweise erforderlich, wenn Sie das Modell mit einem externen Dataset testen, das andere Spalten enthält als das Modell.</span><span class="sxs-lookup"><span data-stu-id="aab13-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="aab13-121">Wenn Sie jedoch eine Spalte mit dem falschen Datentyp auswählen, werden entweder ein Fehler bzw. falsche Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aab13-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="aab13-122">Bestimmen des vorhersagbaren Ergebnisses</span><span class="sxs-lookup"><span data-stu-id="aab13-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="aab13-123">Doppelklicken Sie auf die Miningstruktur, um sie in Data Mining-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aab13-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="aab13-124">Klicken Sie auf die Registerkarte **Mininggenauigkeitsdiagramm** .</span><span class="sxs-lookup"><span data-stu-id="aab13-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="aab13-125">Klicken Sie auf die Registerkarte **Eingabeauswahl** .</span><span class="sxs-lookup"><span data-stu-id="aab13-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="aab13-126">Klicken Sie auf der Registerkarte **Eingabeauswahl** unter **Name der vorhersagbaren Spalte**auf eine vorhersagbare Spalte für jedes Modell, das Sie im Diagramm einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="aab13-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="aab13-127">Im Feld **Name der vorhersagbaren Spalte** werden nur die Miningmodellspalten aufgelistet, für die als Verwendungstyp **Vorhersagen** oder **Nur vorhersagen**festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="aab13-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="aab13-128">Wenn Sie den Liftwert für ein Modell bestimmen möchten, müssen Sie einen bestimmten zu messenden Ergebniswert auswählen, indem Sie ihn aus der Liste **Wert vorhersagen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="aab13-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab13-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aab13-129">See Also</span></span>  
 <span data-ttu-id="aab13-130">[Auswählen und Zuordnen von Modell Test Daten](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="aab13-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="aab13-131">Auswählen eines Genauigkeitsdiagrammtyps Festlegen von Diagrammoptionen</span><span class="sxs-lookup"><span data-stu-id="aab13-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
