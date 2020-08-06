---
title: Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630443"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="128fe-102">Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer</span><span class="sxs-lookup"><span data-stu-id="128fe-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="128fe-103">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes-Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zeigt Mining Modelle an, die mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes-Algorithmus erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="128fe-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="128fe-104">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Algorithmus für das naive Bayes-Verfahren ist ein Klassifizierungsalgorithmus, der sehr gut an Modellierungsaufgaben für Vorhersagen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="128fe-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="128fe-105">Weitere Informationen zu diesem Algorithmus finden Sie unter [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="128fe-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="128fe-106">Da der Hauptverwendungszweck eines naiven Bayes-Modells darin besteht, eine Möglichkeit zum schnellen Durchsuchen von Daten in einem Dataset bereitzustellen, verfügt der [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Viewer für naives Bayes-Verfahren über verschiedene Methoden, die Interaktion zwischen vorhersagbaren Attributen und Eingabeattributen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="128fe-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="128fe-107">Wenn Sie detaillierte Informationen über die im Modell verwendeten Formeln und die entdeckten Muster anzeigen möchten, können Sie zum [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree-Viewer wechseln.</span><span class="sxs-lookup"><span data-stu-id="128fe-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="128fe-108">Weitere Informationen finden Sie unter [Durchsuchen eines Modells mit dem Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) oder [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="128fe-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="128fe-109">Viewer-Registerkarten</span><span class="sxs-lookup"><span data-stu-id="128fe-109">Viewer Tabs</span></span>  
 <span data-ttu-id="128fe-110">Wenn Sie ein Miningmodell in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]durchsuchen, wird das Modell im Data Mining-Designer auf der Registerkarte **Miningmodell-Viewer** mit dem jeweils geeigneten Viewer für das Modell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="128fe-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="128fe-111">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Viewer für naives Bayes-Verfahren stellt zum Durchsuchen der Daten folgende Registerkarten bereit:</span><span class="sxs-lookup"><span data-stu-id="128fe-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="128fe-112">Abhängigkeitsnetzwerk</span><span class="sxs-lookup"><span data-stu-id="128fe-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="128fe-113">Attribut profile</span><span class="sxs-lookup"><span data-stu-id="128fe-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="128fe-114">Attributmerkmale</span><span class="sxs-lookup"><span data-stu-id="128fe-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="128fe-115">Attributunterscheidung</span><span class="sxs-lookup"><span data-stu-id="128fe-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="128fe-116">Abhängigkeits Netzwerk</span><span class="sxs-lookup"><span data-stu-id="128fe-116">Dependency Network</span></span>  
 <span data-ttu-id="128fe-117">Die Registerkarte **Abhängigkeitsnetzwerk** zeigt die Abhängigkeiten zwischen den Eingabeattributen und den vorhersagbaren Attributen in einem Modell an.</span><span class="sxs-lookup"><span data-stu-id="128fe-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="128fe-118">Der Schieberegler auf der linken Seite des Viewers fungiert als Filter, der an die Stärken der Abhängigkeiten gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="128fe-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="128fe-119">Wenn Sie den Schieberegler nach unten ziehen, werden nur die stärksten Links angezeigt.</span><span class="sxs-lookup"><span data-stu-id="128fe-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="128fe-120">Wenn Sie einen Knoten auswählen, hebt der Viewer die Abhängigkeiten hervor, die knotenspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="128fe-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="128fe-121">Wenn Sie beispielsweise einen vorhersagbaren Knoten auswählen, wird vom Viewer auch jeder Knoten hervorgehoben, der beim Vorhersagen des vorhersagbaren Knotens hilft.</span><span class="sxs-lookup"><span data-stu-id="128fe-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="128fe-122">Die Legende im unteren Bereich des Viewers verknüpft Farbcodes mit dem Abhängigkeitstyp im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="128fe-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="128fe-123">Wenn Sie einen vorhersagbaren Knoten auswählen, wird dieser z. B. türkis schattiert, und die Knoten, die den ausgewählten Knoten vorhersagen, orange.</span><span class="sxs-lookup"><span data-stu-id="128fe-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="128fe-124">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="128fe-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a> <span data-ttu-id="128fe-125">Attributprofile</span><span class="sxs-lookup"><span data-stu-id="128fe-125">Attribute Profiles</span></span>  
 <span data-ttu-id="128fe-126">Die Registerkarte **Attributprofile** zeigt Histogramme in einem Raster an.</span><span class="sxs-lookup"><span data-stu-id="128fe-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="128fe-127">Sie können dieses Raster verwenden, um die vorhersagbaren Attribute, die Sie im Feld **Vorhersagbar** auswählen, mit den anderen Attributen zu vergleichen, die im Modell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="128fe-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="128fe-128">Jede Spalte in der Tabelle stellt einen Status des vorhersagbaren Attributs dar.</span><span class="sxs-lookup"><span data-stu-id="128fe-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="128fe-129">Wenn das vorhersagbare Attribut viele Status hat, können Sie die Anzahl der Status verändern, die im Histogramm angezeigt werden, indem Sie die Option **Histogrammbalken**anpassen.</span><span class="sxs-lookup"><span data-stu-id="128fe-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="128fe-130">Wenn die Anzahl, die Sie auswählen, kleiner ist als die Gesamtzahl von Status im Attribut, werden die Status nach Unterstützung sortiert, wobei die restlichen Status in einem einzigen grauen Bucket gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="128fe-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="128fe-131">Um eine Mininglegende anzuzeigen, die die Farben des Histogramms den Statuswerten eines Attributs zuordnet, aktivieren Sie das Kontrollkästchen **Legende anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="128fe-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="128fe-132">Die Mininglegende zeigt auch die Verteilung von Fällen für jedes Attribut/Wert-Paar an, das Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="128fe-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="128fe-133">Klicken Sie mit der rechten Maustaste auf die Registerkarte **Attributprofile** , und wählen Sie **Kopieren**aus, um die Inhalte des Rasters als HTML-Tabelle in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="128fe-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="128fe-134">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="128fe-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a><span data-ttu-id="128fe-135">Attribut Merkmale</span><span class="sxs-lookup"><span data-stu-id="128fe-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="128fe-136">Um die Registerkarte **Attributmerkmale** zu verwenden, wählen Sie aus der Liste **Attribut** ein vorhersagbares Attribut aus, und wählen Sie anschließend aus der Liste **Wert** einen Status des ausgewählten Attributs aus.</span><span class="sxs-lookup"><span data-stu-id="128fe-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="128fe-137">Wenn Sie diese Variablen festlegen, zeigt die Registerkarte **Attributmerkmale** die Status der Attribute an, die mit dem ausgewählten Fall des ausgewählten Attributs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="128fe-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="128fe-138">Die Attribute sind nach ihrer Wichtigkeit sortiert.</span><span class="sxs-lookup"><span data-stu-id="128fe-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="128fe-139">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="128fe-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a><span data-ttu-id="128fe-140">Attribut Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="128fe-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="128fe-141">Wählen Sie zum Verwenden der Registerkarte **Attributunterscheidung** ein vorhersagbares Attribut und zwei ihrer Status aus den Listen **Attribut**, **Wert 1**und **Wert 2** aus.</span><span class="sxs-lookup"><span data-stu-id="128fe-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="128fe-142">Das Raster auf der Registerkarte **Attributunterscheidung** zeigt daraufhin die folgenden Informationen in Spalten an:</span><span class="sxs-lookup"><span data-stu-id="128fe-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="128fe-143">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="128fe-143">**Attribute**</span></span>  
 <span data-ttu-id="128fe-144">Listet weitere Attribute im Dataset auf, die einen Status enthalten, der den Status eines vorhersagbaren Attributs stark bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="128fe-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="128fe-145">**Werte**</span><span class="sxs-lookup"><span data-stu-id="128fe-145">**Values**</span></span>  
 <span data-ttu-id="128fe-146">Zeigt den Wert des Attributs in der Spalte **Attribute** an.</span><span class="sxs-lookup"><span data-stu-id="128fe-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="128fe-147">**Günstige\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="128fe-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="128fe-148">Zeigt eine farbige Leiste an, die kennzeichnet, wie stark der Attributwert den in **Wert 1**dargestellten vorhersagbaren Attributwert bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="128fe-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="128fe-149">**Günstige\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="128fe-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="128fe-150">Zeigt eine farbige Leiste an, die kennzeichnet, wie stark der Attributwert den in **Wert 2** dargestellten vorhersagbaren Attributwert bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="128fe-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="128fe-151">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="128fe-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="128fe-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="128fe-152">See Also</span></span>  
 <span data-ttu-id="128fe-153">[Microsoft Naive Bayes-Algorithmus](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="128fe-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="128fe-154">[Tasks und Anleitungen des Mining Modell-Viewers](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="128fe-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="128fe-155">[Data Mining-Tools](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="128fe-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="128fe-156">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="128fe-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
