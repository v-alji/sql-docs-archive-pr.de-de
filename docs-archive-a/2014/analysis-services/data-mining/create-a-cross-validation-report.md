---
title: Erstellen eines Kreuz Validierungs Berichts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694838"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="3010d-102">Erstellen von Berichten für Kreuzvalidierung</span><span class="sxs-lookup"><span data-stu-id="3010d-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="3010d-103">In diesem Thema wird die Erstellung eines Kreuzvalidierungsberichts auf der Registerkarte "Genauigkeitsdiagramm" im Data Mining-Designer erläutert.</span><span class="sxs-lookup"><span data-stu-id="3010d-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="3010d-104">Allgemeine Informationen zum Aussehen eines Kreuzvalidierungsberichts und zu den statistischen Measures, die er enthält, finden Sie unter [Kreuzvalidierung &#40;Analysis Services – Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3010d-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="3010d-105">Ein Kreuzvalidierungsbericht unterscheidet sich grundlegend von einem Genauigkeitsdiagramm, z. B. ein Prognosegütediagramm oder eine Klassifikationsmatrix.</span><span class="sxs-lookup"><span data-stu-id="3010d-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="3010d-106">Bei der Kreuzvalidierung wird die Gesamtverteilung von Daten bewertet, die in einem Modell oder einer Struktur verwendet werden. Daher wird auch kein Testdataset angegeben.</span><span class="sxs-lookup"><span data-stu-id="3010d-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="3010d-107">Bei der Kreuzvalidierung werden immer nur die ursprünglichen Daten verwendet, mit denen das Modell oder die Miningstruktur trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3010d-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="3010d-108">Kreuzvalidierung kann nur hinsichtlich eines einzelnen vorhersagbaren Ergebnisses ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3010d-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="3010d-109">Wenn die Struktur Modelle unterstützt, die über andere vorhersagbare Attribute verfügen, müssen Sie separate Berichte für jede vorhersagbare Ausgabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="3010d-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="3010d-110">Nur Modelle, die mit der gerade ausgewählten Struktur verknüpft werden, sind für die Kreuzvalidierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3010d-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="3010d-111">Wenn die derzeit ausgewählte Struktur eine Kombination aus Clustering- und Nicht-Clusteringmodellen unterstützt, lädt die gespeicherte Kreuzvalidierungsprozedur nach einem Klick auf **Ergebnisse abrufen**automatisch Modelle, die über die gleiche vorhergesagte Spalte verfügen. Clusteringmodelle, die nicht das gleiche vorhersagbare Attribut verwenden, werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3010d-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="3010d-112">Sie können einen Kreuzvalidierungsbericht für ein Clusteringmodell erstellen, das nur dann nicht über ein vorhersagbares Attribut verfügt, wenn die Miningstruktur keine anderen vorhersagbaren Attribute unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3010d-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="3010d-113">Auswählen einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="3010d-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="3010d-114">Öffnen Sie den Data Mining-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3010d-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="3010d-115">Öffnen Sie in Projektmappen-Explorer die Datenbank, die die Struktur oder das Modell enthält, für das Sie einen Bericht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3010d-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="3010d-116">Doppelklicken Sie im Data Mining-Designer auf die Miningstruktur, um die Struktur und die zugehörigen Modelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3010d-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="3010d-117">Klicken Sie auf die Registerkarte **Mininggenauigkeitsdiagramm** .</span><span class="sxs-lookup"><span data-stu-id="3010d-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="3010d-118">Klicken Sie auf die Registerkarte **Kreuzvalidierung** .</span><span class="sxs-lookup"><span data-stu-id="3010d-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="3010d-119">Festlegen von Kreuzvalidierungsoptionen</span><span class="sxs-lookup"><span data-stu-id="3010d-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="3010d-120">Klicken Sie auf der Registerkarte **Kreuzvalidierung** für **Foldanzahl**auf den Pfeil nach unten, um eine Zahl zwischen 1 und 10 auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3010d-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="3010d-121">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="3010d-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="3010d-122">Die **Foldanzahl** stellt die Anzahl von Partitionen dar, die innerhalb des ursprünglichen Datasets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3010d-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="3010d-123">Wenn Sie die Foldanzahl auf 1 festgelegt haben, wird der Trainingssatz ohne Partitionierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3010d-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="3010d-124">Klicken Sie für **Zielattribut**auf den Pfeil nach unten, und wählen Sie eine Spalte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="3010d-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="3010d-125">Wenn das Modell ein Clustermodell ist, wählen Sie **#Cluster** , um anzugeben, dass das Modell nicht über ein vorhersagbares Attribut verfügt.</span><span class="sxs-lookup"><span data-stu-id="3010d-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="3010d-126">Beachten Sie, dass der Wert **#Cluster**nur verfügbar ist, wenn die Miningstruktur keine anderen vorhersagbaren Attributtypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3010d-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="3010d-127">Sie können nur ein vorhersagbares Attribut pro Bericht auswählen.</span><span class="sxs-lookup"><span data-stu-id="3010d-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="3010d-128">Standardmäßig sind alle zugehörigen Modelle, die über das gleiche vorhersagbare Attribut verfügen, im Bericht enthalten.</span><span class="sxs-lookup"><span data-stu-id="3010d-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="3010d-129">Geben Sie für **Maximale Anzahl von Fällen**eine Zahl ein, die groß genug ist, um eine repräsentative Stichprobe von Daten bereitzustellen, wenn die Daten auf die angegebene Anzahl von Aufteilungen aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="3010d-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="3010d-130">Wenn Sie eine Zahl angeben, die größer ist als die Anzahl der tatsächlichen Fälle im Trainingssatz des Modells, werden alle Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="3010d-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="3010d-131">Wenn der Trainingsdatensatz sehr groß ist, können Sie über den unter **Maximale Anzahl von Fällen** eingegebenen Wert die Gesamtzahl der verarbeiteten Fälle einschränken. Der Bericht kann so schneller beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3010d-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="3010d-132">Sie sollten jedoch keinen zu kleinen Wert für **Maximale Anzahl von Fällen** eingeben, da ansonsten möglicherweise nicht genügend Daten zur Kreuzvalidierung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3010d-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="3010d-133">Geben Sie optional für **Zielstatus**den Wert des vorhersagbaren Attributs ein, das Sie modellieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3010d-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="3010d-134">Wenn zum Beispiel die Spalte [Fahrradkäufer] zwei mögliche Werte enthält, nämlich 1 (Ja) und 2 (Nein), können Sie den Wert 1 eingeben, um die Genauigkeit des Modells nur für das gewünschte Ergebnis zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="3010d-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3010d-135">Wenn Sie keinen Wert eingeben, ist die Option **Zielschwellenwert** nicht verfügbar, und das Modell wird für alle möglichen Werte des vorhersagbaren Attributs bewertet.</span><span class="sxs-lookup"><span data-stu-id="3010d-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="3010d-136">Geben Sie optional für **Zielschwellenwert**eine Dezimalzahl zwischen 0 und 1 ein, um anzugeben, welche Mindestwahrscheinlichkeit eine Vorhersage erreichen muss, damit sie als genau gelten kann.</span><span class="sxs-lookup"><span data-stu-id="3010d-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="3010d-137">Zusätzliche Tipps zur Festlegung von Wahrscheinlichkeitsschwellenwerten finden Sie unter [Measures im Kreuzvalidierungsbericht](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="3010d-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="3010d-138">Klicken Sie auf **Ergebnisse abrufen**.</span><span class="sxs-lookup"><span data-stu-id="3010d-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="3010d-139">Drucken des Kreuzvalidierungsberichts</span><span class="sxs-lookup"><span data-stu-id="3010d-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="3010d-140">Klicken Sie auf der Registerkarte **Kreuzvalidierung** mit der rechten Maustaste auf den abgeschlossenen Bericht.</span><span class="sxs-lookup"><span data-stu-id="3010d-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="3010d-141">Wählen Sie aus dem Kontextmenü die Option **Drucken** oder **Seitenansicht** , um zunächst den Bericht zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3010d-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="3010d-142">Erstellen einer Kopie des Berichts in Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="3010d-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="3010d-143">Klicken Sie auf der Registerkarte **Kreuzvalidierung** mit der rechten Maustaste auf den abgeschlossenen Bericht.</span><span class="sxs-lookup"><span data-stu-id="3010d-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="3010d-144">Wählen Sie im Kontextmenü die Option **Alles auswählen**.</span><span class="sxs-lookup"><span data-stu-id="3010d-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="3010d-145">Klicken Sie mit der rechten Maustaste auf den ausgewählten Text, und wählen Sie **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="3010d-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="3010d-146">Fügen Sie die Auswahl in eine geöffnete Excel-Arbeitsmappe ein.</span><span class="sxs-lookup"><span data-stu-id="3010d-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="3010d-147">Wenn Sie die Option **Einfügen** verwenden, wird der Bericht als HTML in Excel eingefügt. Auf diese Weise werden Zeilen- und Spaltenformatierung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3010d-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="3010d-148">Wenn Sie den Bericht mit den Optionen für **Inhalte einfügen** für Text oder Unicode-Text einfügen, wird der Bericht im nach Zeilen getrennten Format eingefügt.</span><span class="sxs-lookup"><span data-stu-id="3010d-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3010d-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3010d-149">See Also</span></span>  
 [<span data-ttu-id="3010d-150">Measures im Kreuzvalidierungsbericht</span><span class="sxs-lookup"><span data-stu-id="3010d-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
