---
title: Prüfliste zur Vorbereitung für Data Mining | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615705"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="387b6-102">Prüfliste der Vorbereitung für Data Mining</span><span class="sxs-lookup"><span data-stu-id="387b6-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="387b6-103">Data Mining-Add-Ins stellen eine einfache und unkomplizierte Methode zum Erstellen und Testen von Modellen dar. Wenn es Ihnen jedoch auf wiederholbare und aussagekräftige Ergebnisse ankommt, müssen Sie genügend Zeit einplanen, um grundlegende Geschäftsanforderungen zu formulieren und die erforderlichen Daten zu beschaffen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="387b6-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="387b6-104">Dieser Abschnitt enthält eine Prüfliste, die Sie beim Planen Ihrer Untersuchung unterstützen soll. Darüber hinaus werden häufig auftretende Probleme beschrieben.</span><span class="sxs-lookup"><span data-stu-id="387b6-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="387b6-105">Prüfliste für die Datenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="387b6-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="387b6-106">**Identifikation klar definierter Ausgabedaten**</span><span class="sxs-lookup"><span data-stu-id="387b6-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="387b6-107">Erstellen Sie einen Plan für die Verwendung der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="387b6-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="387b6-108">Verschiedene Modelltypen haben unterschiedliche Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="387b6-108">Different types of models have different outputs.</span></span> <span data-ttu-id="387b6-109">Ein Zeitreihenmodell generiert Werte für eine in der Zukunft liegende Reihe; diese ist leicht verständlich und verwertbar.</span><span class="sxs-lookup"><span data-stu-id="387b6-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="387b6-110">Andere Modelle generieren komplexe Ergebnisse, die von Sachverständigen analysiert werden müssen, um den größtmöglichen Nutzen daraus zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="387b6-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="387b6-111">Welche Ausgabe wünschen Sie?</span><span class="sxs-lookup"><span data-stu-id="387b6-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="387b6-112">Können Sie die Ausgabe als einzelne Spalte oder als einzelnen Wert oder anderweitig als verwertbares Ergebnis definieren?</span><span class="sxs-lookup"><span data-stu-id="387b6-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="387b6-113">Anhand welcher Kriterien können Sie beurteilen, ob das Modell nützlich war?</span><span class="sxs-lookup"><span data-stu-id="387b6-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="387b6-114">Wie nutzen und interpretieren Sie diese Ergebnisse?</span><span class="sxs-lookup"><span data-stu-id="387b6-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="387b6-115">Können Sie den erwarteten Ergebnissen neue Eingabedaten zuordnen?</span><span class="sxs-lookup"><span data-stu-id="387b6-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="387b6-116">**Grundlegendes Verständnis der Bedeutung, Datentypen und Verteilung von Eingabedaten**</span><span class="sxs-lookup"><span data-stu-id="387b6-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="387b6-117">Nehmen Sie sich ausreichend Zeit, um die Quelldaten zu untersuchen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="387b6-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="387b6-118">Die Personen, die mit dem Modell arbeiten, müssen wissen, welche Eingabedaten verwendet wurden und wie die Datentypen und die Variabilität sowie Ausgewogenheit und Qualität zu interpretieren sind.</span><span class="sxs-lookup"><span data-stu-id="387b6-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="387b6-119">Wie viele Daten besitzen Sie?</span><span class="sxs-lookup"><span data-stu-id="387b6-119">How much data do you have?</span></span> <span data-ttu-id="387b6-120">Ist eine ausreichende Menge von Daten für die Modellierung vorhanden?</span><span class="sxs-lookup"><span data-stu-id="387b6-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="387b6-121">Es muss nicht sehr groß sein, und es kann besser werden.</span><span class="sxs-lookup"><span data-stu-id="387b6-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="387b6-122">Stammen die Daten aus mehreren Quellen oder aus einer einzigen Quelle?</span><span class="sxs-lookup"><span data-stu-id="387b6-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="387b6-123">Sind die Daten bereits verarbeitet und bereinigt?</span><span class="sxs-lookup"><span data-stu-id="387b6-123">Is the data already processed and clean?</span></span> <span data-ttu-id="387b6-124">Sind weitere Eingabedaten verfügbar?</span><span class="sxs-lookup"><span data-stu-id="387b6-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="387b6-125">Wissen Sie, wie Sie bearbeitet wurde, bevor Sie Sie erhalten haben. wie können Daten abgeschnitten, zusammengefasst oder konvertiert werden?</span><span class="sxs-lookup"><span data-stu-id="387b6-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="387b6-126">Enthalten die Eingabedaten einige Beispielergebnisse, die für das Training verwendet werden können?</span><span class="sxs-lookup"><span data-stu-id="387b6-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="387b6-127">**Genaue Vorstellungen von der Datenintegrität – wie ist der aktuelle Zustand und welcher Zustand soll erreicht werden?**</span><span class="sxs-lookup"><span data-stu-id="387b6-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="387b6-128">Fehlerhafte Daten können die Qualität des Modells beeinträchtigen oder die Modellerstellung von vornherein verhindern.</span><span class="sxs-lookup"><span data-stu-id="387b6-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="387b6-129">Sie sollten weit reichende Kenntnisse sowohl über die Verteilung als auch über die Bedeutung der Daten haben und wissen, wie der aktuelle Zustand erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="387b6-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="387b6-130">Sie müssen sich darüber im klaren sein, ob es möglich oder sinnvoll ist, die Daten zu vereinfachen, indem Sie die Bezeichnung, die abkürzen numerischer Datentypen oder eine Zusammenfassung durch fassen.</span><span class="sxs-lookup"><span data-stu-id="387b6-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="387b6-131">Sind die Datenbeschriftungen deutlich und richtig?</span><span class="sxs-lookup"><span data-stu-id="387b6-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="387b6-132">Sind die Datentypen geeignet, und wurden sie ggf. geändert?</span><span class="sxs-lookup"><span data-stu-id="387b6-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="387b6-133">Haben Sie falsche Daten aussortiert, bereinigt oder verworfen?</span><span class="sxs-lookup"><span data-stu-id="387b6-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="387b6-134">Haben Sie sich vergewissert, dass keine Duplikate vorhanden sind?</span><span class="sxs-lookup"><span data-stu-id="387b6-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="387b6-135">Wie gehen Sie mit fehlenden Werten um?</span><span class="sxs-lookup"><span data-stu-id="387b6-135">How will you handle missing values?</span></span> <span data-ttu-id="387b6-136">Was bedeuten fehlende Daten?</span><span class="sxs-lookup"><span data-stu-id="387b6-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="387b6-137">Haben Sie die Quellen überprüft, um festzustellen, ob sich während des Importvorgangs eventuell Fehler eingeschlichen haben?</span><span class="sxs-lookup"><span data-stu-id="387b6-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="387b6-138">Wo ist die Eingabe gespeichert?</span><span class="sxs-lookup"><span data-stu-id="387b6-138">Where is the input stored?</span></span> <span data-ttu-id="387b6-139">Wie lange bleibt sie verfügbar?</span><span class="sxs-lookup"><span data-stu-id="387b6-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="387b6-140">Ist ein Datenwörterbuch vorhanden?</span><span class="sxs-lookup"><span data-stu-id="387b6-140">Is there a data dictionary?</span></span> <span data-ttu-id="387b6-141">Können Sie ein solches erstellen?</span><span class="sxs-lookup"><span data-stu-id="387b6-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="387b6-142">Wenn Sie Datasets kombiniert haben: Haben Sie eine Überprüfung auf mehrere Spalten durchgeführt, die dieselben Daten darstellen?</span><span class="sxs-lookup"><span data-stu-id="387b6-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="387b6-143">**Ich weiß, wo Quelldaten gespeichert werden, woher Sie stammen und wie Sie verarbeitet werden. Der Prozess kann bei Bedarf problemlos wiederholt werden.**</span><span class="sxs-lookup"><span data-stu-id="387b6-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="387b6-144">Einmalige Datasets sind für Experimente gut, aber wenn Sie das Modell jemals in die Produktion verschieben möchten, sollten Sie sich im Voraus Gedanken darüber machen, wie der Reinigungsprozess auf operative Daten angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="387b6-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="387b6-145">Wenn Sie über operative Daten verfügen, müssen Sie sich darüber informieren, wie diese möglicherweise geändert wurden, bevor Sie Sie erhalten. Sie müssen wissen, wie Sie gerundet oder zusammengefasst wurden.</span><span class="sxs-lookup"><span data-stu-id="387b6-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="387b6-146">Möchten Sie in der Lage sein, das Experiment zu wiederholen?</span><span class="sxs-lookup"><span data-stu-id="387b6-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="387b6-147">Welche Tools verwenden Sie, um Daten in einem Format vorzubereiten, das Datenanalysen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="387b6-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="387b6-148">Kann der Vorgang automatisiert werden, oder benötigen Sie jemanden, der die Daten in Excel überprüft und bereinigt?</span><span class="sxs-lookup"><span data-stu-id="387b6-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="387b6-149">Sind Sie bei der Datenbeschaffung aus einem anderen System in der Lage, die angewendeten Filter zu erfassen und zu verfolgen?</span><span class="sxs-lookup"><span data-stu-id="387b6-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="387b6-150">Ist Ihr Datenverarbeitungs-Framework in der Lage, Algorithmen für maschinelles Lernen anzuwenden, Tests auszuführen und Ergebnisse zu visualisieren?</span><span class="sxs-lookup"><span data-stu-id="387b6-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="387b6-151">**Festlegen der gewünschten Detailgenauigkeit von Vorhersagen und Anpassung der Daten an die Ausgabeeinheiten**</span><span class="sxs-lookup"><span data-stu-id="387b6-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="387b6-152">Legen Sie vor der Vorbereitung von Daten fest, wie detailliert die Ergebnisse sein sollen. Möchten Sie Umsatzvorhersagen pro Tag oder Quartal erstellen?</span><span class="sxs-lookup"><span data-stu-id="387b6-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="387b6-153">Sie können auch unterschiedliche Datenstrukturen für dieselben Daten einrichten, um verschiedene Zusammenfassungsebenen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="387b6-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="387b6-154">Welche Maßeinheit oder Zeiteinheit wird derzeit verwendet?</span><span class="sxs-lookup"><span data-stu-id="387b6-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="387b6-155">Welche Einheit möchten Sie in den Ergebnissen verwenden?</span><span class="sxs-lookup"><span data-stu-id="387b6-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="387b6-156">Ist es möglich, eine grundlegende Einheit (z. b. Tag/Stunde/Minute/Anweisungs Befehl) für alle Eingabedaten zu definieren?</span><span class="sxs-lookup"><span data-stu-id="387b6-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="387b6-157">Möchten Sie ein Rollup auf übergeordnete Einheiten durchführen?</span><span class="sxs-lookup"><span data-stu-id="387b6-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="387b6-158">Sind Kategorien einheitlich beschriftet?</span><span class="sxs-lookup"><span data-stu-id="387b6-158">Are categories labeled consistently?</span></span> <span data-ttu-id="387b6-159">Können Kategorien einfach hinzugefügt oder entfernt werden?</span><span class="sxs-lookup"><span data-stu-id="387b6-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="387b6-160">**Wiederholbare und reproduzierbare Versuchsanordnung**</span><span class="sxs-lookup"><span data-stu-id="387b6-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="387b6-161">Überdenken Sie Strategien zum Analysieren und Überprüfen der Ergebnisse, und planen Sie das Aufzeichnen einer Momentaufnahme der Daten, um sicherzustellen, dass Sie Auswirkungen zu den Daten zurückverfolgen können.</span><span class="sxs-lookup"><span data-stu-id="387b6-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="387b6-162">Wenn ein zufälliger Ausgangswert verwendet wird, können sich die Ergebnisse leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="387b6-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="387b6-163">Dadurch können sich der Vergleich und die Validierung der Modelle schwierig gestalten.</span><span class="sxs-lookup"><span data-stu-id="387b6-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="387b6-164">Wie wirken sich zahlreiche benutzerdefinierte Änderungen an den Daten auf das nächste Erstellen des Modells aus?</span><span class="sxs-lookup"><span data-stu-id="387b6-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="387b6-165">Wurde bereits ein manuelles Verfahren oder ein genehmigter Prozess definiert, mit dem die Eingabe verarbeitet und die gewünschten Ausgaben abgerufen werden sollen?</span><span class="sxs-lookup"><span data-stu-id="387b6-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="387b6-166">Haben Sie festgelegt, dass ein Ausgangswert für das Modell verwendet werden soll?</span><span class="sxs-lookup"><span data-stu-id="387b6-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="387b6-167">**Fundiertes Fachwissen, um die Ergebnisse überprüfen zu können, oder fachliche Unterstützung von Experten**</span><span class="sxs-lookup"><span data-stu-id="387b6-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="387b6-168">Nehmen Sie sich ausreichend Zeit, um die Variablen, das Modell und die Ergebnisse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="387b6-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="387b6-169">Nehmen Sie beim Bewerten von Interaktionen und Ergebnissen die Unterstützung von Experten in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="387b6-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="387b6-170">Lassen Sie jedoch keine Annahmen über Regel Beweise aus.</span><span class="sxs-lookup"><span data-stu-id="387b6-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="387b6-171">Seien Sie offen für neue und unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="387b6-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="387b6-172">Ist Domänenwissen vorhanden, welches das Filtern von Daten und das Mindern von Eingaberauschen erleichtert?</span><span class="sxs-lookup"><span data-stu-id="387b6-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="387b6-173">Können Domänenexperten dazu beitragen, die Ergebnisse zu verstehen und zu interpretieren, und können sie Verbesserungen vorschlagen?</span><span class="sxs-lookup"><span data-stu-id="387b6-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387b6-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="387b6-174">See Also</span></span>  
 [<span data-ttu-id="387b6-175">Auswählen von Daten für das Data Mining</span><span class="sxs-lookup"><span data-stu-id="387b6-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
