---
title: Durchsuchen und Bereinigen von Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608065"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="0dc01-102">Durchsuchen und Bereinigen von Daten</span><span class="sxs-lookup"><span data-stu-id="0dc01-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="0dc01-103">Die Datenvorbereitung umfasst viel mehr als die Datenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="0dc01-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="0dc01-104">Die Art und Weise der Datenvorbereitung wirkt sich auch darauf aus, wie Ergebnisse am Ende interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="0dc01-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="0dc01-105">Die Datenvorbereitung umfasst folgende Tasks:</span><span class="sxs-lookup"><span data-stu-id="0dc01-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="0dc01-106">Untersuchen und Überprüfen der Verteilung von Daten</span><span class="sxs-lookup"><span data-stu-id="0dc01-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="0dc01-107">Bereinigen ungültiger Datensätze und Auswählen von Spalten für Data Mining</span><span class="sxs-lookup"><span data-stu-id="0dc01-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="0dc01-108">Korrekte Handhabung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="0dc01-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="0dc01-109">Klassifizieren von Werten oder Aggregieren von Werten nach unterschiedlichen Zeitblöcken</span><span class="sxs-lookup"><span data-stu-id="0dc01-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="0dc01-110">Hinzufügen von Bezeichnungen, um die Nutzbarkeit der Ergebnisse zu verbessern</span><span class="sxs-lookup"><span data-stu-id="0dc01-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="0dc01-111">Konvertieren von Datentypen oder Kategorisieren von Werten für die Analyse (wo erforderlich)</span><span class="sxs-lookup"><span data-stu-id="0dc01-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="0dc01-112">Wenn Sie mit der Datenmodellierung noch nicht vertraut sind, empfiehlt es sich, dass Sie das verwandte Thema, [Checkliste zur Vorbereitung für das Data Mining](checklist-of-preparation-for-data-mining.md), lesen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="0dc01-113">Datenvorbereitungstools</span><span class="sxs-lookup"><span data-stu-id="0dc01-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="0dc01-114">Die Data Mining-Add-Ins für Office enthalten die folgenden Tools für die Datenbereinigung und-Vorbereitung:</span><span class="sxs-lookup"><span data-stu-id="0dc01-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="0dc01-115">Daten durchsuchen</span><span class="sxs-lookup"><span data-stu-id="0dc01-115">Explore Data</span></span>  
 <span data-ttu-id="0dc01-116">Verwenden Sie den Assistenten zum durch **Suchen von Daten** für diese Daten Vorbereitungs Tasks:</span><span class="sxs-lookup"><span data-stu-id="0dc01-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="0dc01-117">Anzeigen der Daten in der Vorschau und Ermitteln von Fehlern, die vor der Analyse korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="0dc01-118">Sammeln statistischer Informationen, um das Gleichgewicht der Daten und die erforderlichen Cleanuptasks zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="0dc01-119">Identifizieren hilfreicher Spalten für die Analyse und Planen der Datenmodellierungsphase.</span><span class="sxs-lookup"><span data-stu-id="0dc01-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="0dc01-120">[Erkunden Sie die Daten &#40;SQL Server Data Mining-Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="0dc01-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="0dc01-121">Erkennen und Behandeln von Ausreißern</span><span class="sxs-lookup"><span data-stu-id="0dc01-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="0dc01-122">Der **ausreißerausreißerassistent** gibt eine Grafik zur Verteilung der Werte in Ihren Daten und hilft Ihnen, extreme Werte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="0dc01-123">Verwenden Sie das **ausreißertool** für die folgenden Daten Vorbereitungs Tasks:</span><span class="sxs-lookup"><span data-stu-id="0dc01-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="0dc01-124">Bestimmen der Zuverlässigkeit einzelner Werte anhand von Mustern, die in den Daten festgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0dc01-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="0dc01-125">Überprüfen ungewöhnlicher Werte und Ergreifen von Maßnahmen (Löschen oder Ersetzen dieser Werte).</span><span class="sxs-lookup"><span data-stu-id="0dc01-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="0dc01-126">Beschränken eines Modells auf einen bestimmten Bereich von Werten.</span><span class="sxs-lookup"><span data-stu-id="0dc01-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="0dc01-127">Wenn Ihnen beispielsweise bekannt ist, dass für eine bestimmte Filiale Ausreißer vorliegen, können Sie den betreffenden Wert eliminieren und damit ein Modell erhalten, mit dem bessere Vorhersagen für die anderen Filialen getroffen werden.</span><span class="sxs-lookup"><span data-stu-id="0dc01-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="0dc01-128">[Ausreißer &#40;SQL Server Data Mining-Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="0dc01-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="0dc01-129">Neubezeichnen und Klassifizieren von Daten</span><span class="sxs-lookup"><span data-stu-id="0dc01-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="0dc01-130">Der **Assistent zum** neubezeichnen gruppiert Daten nach Werten, damit Sie die Bezeichnungen für die Daten ändern können.</span><span class="sxs-lookup"><span data-stu-id="0dc01-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="0dc01-131">Verwenden Sie das Tool Neu bezeichnen für die folgenden Datenvorbereitungstasks:</span><span class="sxs-lookup"><span data-stu-id="0dc01-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="0dc01-132">Ändern von in Umfrageergebnissen enthaltenen numerischen Codes in Textbeschreibungen, die den jeweiligen numerischen Code erläutern.</span><span class="sxs-lookup"><span data-stu-id="0dc01-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="0dc01-133">Beispielsweise können Sie Dateneinträge wie Geschlecht = 1 durch Geschlecht = Weiblich ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="0dc01-134">Klassifizieren von Daten, indem Gruppen erstellt werden, die Zahlenbereiche darstellen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="0dc01-135">Angenommen, Sie möchten eine Einkommens Spalte von Zahlen durch Bezeichnungen wie **Income-** Mittel und **Income-High**ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="0dc01-136">Reduzieren diskreter Werte auf Kategorien.</span><span class="sxs-lookup"><span data-stu-id="0dc01-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="0dc01-137">Wenn Sie beispielsweise ein Kaufmuster ermitteln möchten, Ihre Ausgangsbasis aber zu viele Einzelprodukte umfasst, könnten Sie Produkte allgemeineren Kategorien zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="0dc01-138">&#40;SQL Server Data Mining-Add-ins neu bezeichnen&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc01-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="0dc01-139">Bereinigen von Daten</span><span class="sxs-lookup"><span data-stu-id="0dc01-139">Cleanse Data</span></span>  
 <span data-ttu-id="0dc01-140">Die Datenbereinigung umfasst zahlreiche Aktivitäten, die größtenteils durch die Add-Ins unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0dc01-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="0dc01-141">Identifizieren von NULL-Werten und bestimmen, ob sie in einen reellen Wert geändert oder als `Missing`-Werte behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="0dc01-142">Erkennen von fehlenden Werten und Entfernen dieser Werte oder Berechnen eines geeigneten Werts (z. B. eines Mittelwerts, NULL-Werts oder sonstigen Werts).</span><span class="sxs-lookup"><span data-stu-id="0dc01-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="0dc01-143">Durchsuchen von Daten &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc01-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="0dc01-144">&#40;SQL Server Data Mining-Add-ins neu bezeichnen&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc01-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="0dc01-145">Aus Beispiel füllen</span><span class="sxs-lookup"><span data-stu-id="0dc01-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="0dc01-146">Beispieldaten</span><span class="sxs-lookup"><span data-stu-id="0dc01-146">Sample Data</span></span>  
 <span data-ttu-id="0dc01-147">Der Assistent für Beispieldaten stellt zwei Methoden zum Erstellen von ausgeglichenen Datasets zum Trainieren und Testen von Modellen bereit.</span><span class="sxs-lookup"><span data-stu-id="0dc01-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="0dc01-148">**Zufällige Stichprobenentnahme.**</span><span class="sxs-lookup"><span data-stu-id="0dc01-148">**Random sampling.**</span></span> <span data-ttu-id="0dc01-149">Verwenden Sie diese Option, um eine repräsentative Menge von Daten aus einem größeren Dataset zu extrahieren und zu Trainings- oder Testzwecken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0dc01-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="0dc01-150">Die Data Mining-Add-Ins verwenden eine *stratifilierte Stichprobe* , um sicherzustellen, dass für jede Stichprobe mit Stichproben eine ausgeglichene Menge von Werten abgerufen wird</span><span class="sxs-lookup"><span data-stu-id="0dc01-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="0dc01-151">**Über Quotierung.**</span><span class="sxs-lookup"><span data-stu-id="0dc01-151">**Oversampling.**</span></span> <span data-ttu-id="0dc01-152">Verwenden Sie diese Option, wenn Sie über weniger Daten verfügen als für das Zielergebnis gewünscht und diese Daten stärker gewichten müssen.</span><span class="sxs-lookup"><span data-stu-id="0dc01-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="0dc01-153">Beispiel: Obwohl Betrugsdelikte u. U. relativ selten vorkommen, können Sie Betrugsfälle überquotieren, um geeignete Daten für die Modellierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0dc01-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="0dc01-154">[Beispiel Daten &#40;SQL Server Data Mining-Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="0dc01-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc01-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dc01-155">See Also</span></span>  
 <span data-ttu-id="0dc01-156">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="0dc01-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="0dc01-157">[Validieren von Modellen und Verwenden von Modellen für Vorhersage &#40;Data Mining-Add-Ins für Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0dc01-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="0dc01-158">Bereitstellen und Skalieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc01-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
