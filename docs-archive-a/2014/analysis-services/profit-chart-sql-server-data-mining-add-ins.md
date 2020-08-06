---
title: Gewinn Diagramm (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618297"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="c3735-102">Gewinndiagramm (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="c3735-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="c3735-103">![Gewinndiagramm (Schaltfläche auf Data Mining-Menüband)](media/dmc-profitchart.gif "Gewinndiagramm (Schaltfläche auf Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="c3735-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="c3735-104">Ein Gewinndiagramm zeigt den geschätzten Gewinnanstieg an, der einem Miningmodell zugeordnet ist, um so zu ermitteln, welche Kunden in einem Geschäftsszenario angesprochen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c3735-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="c3735-105">Auf der Y-Achse des Diagramms ist der Gewinn dargestellt, während auf der X-Achse der Prozentwert der vom Unternehmen angesprochenen Personen dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c3735-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="c3735-106">Ein typisches Gewinndiagramm zeigt einen Anstieg der Gewinne bis zu einem Wendepunkt an, nach dem die Gewinne abnehmen, wenn mehr Personen angesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="c3735-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="c3735-107">Konfigurieren des Gewinndiagramms</span><span class="sxs-lookup"><span data-stu-id="c3735-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="c3735-108">Während im Genauigkeitsdiagramm nur die Wahrscheinlichkeit bewertet wird, mit der Vorhersagen falsch oder richtig sind, werden im Gewinndiagramm Erfahrungswerte aus der realen Welt über die Konsequenzen von Aktionen infolge einer bestimmten Vorhersage mit einbezogen.</span><span class="sxs-lookup"><span data-stu-id="c3735-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="c3735-109">Dazu werden folgende Faktoren berücksichtigt, die Sie beim Ausführen des Assistenten angeben:</span><span class="sxs-lookup"><span data-stu-id="c3735-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="c3735-110">**Bevölkerungs**</span><span class="sxs-lookup"><span data-stu-id="c3735-110">**Population**</span></span>  
  
     <span data-ttu-id="c3735-111">Die Anzahl von Fällen im Dataset, die zum Erstellen des Liftdiagramms verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3735-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="c3735-112">Dies ist z. B. die Anzahl von potenziellen Kunden.</span><span class="sxs-lookup"><span data-stu-id="c3735-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="c3735-113">**Festes Kosten**</span><span class="sxs-lookup"><span data-stu-id="c3735-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="c3735-114">Die festen Kosten, die mit dem Geschäftsproblem verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="c3735-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="c3735-115">Wenn es sich hier z. B. um eine gezielte Mailingaktion handelt, hängen die Kosten nicht von variablen Werten (z. B. der Anzahl von getätigten Telefonanrufen oder der Anzahl von verschickten Werbesendungen) ab.</span><span class="sxs-lookup"><span data-stu-id="c3735-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="c3735-116">**Einzelkosten**</span><span class="sxs-lookup"><span data-stu-id="c3735-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="c3735-117">Kosten, die zusätzlich zu den festen Kosten entstehen und den einzelnen Kundenkontakten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="c3735-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="c3735-118">Dies wären z. B. Werbesendungen oder Telefonanrufe.</span><span class="sxs-lookup"><span data-stu-id="c3735-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="c3735-119">**Einzelumsatz**</span><span class="sxs-lookup"><span data-stu-id="c3735-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="c3735-120">Die Höhe des mit einem erfolgreichen Verkauf verbundenen Umsatzes.</span><span class="sxs-lookup"><span data-stu-id="c3735-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="c3735-121">Verwenden des Gewinndiagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c3735-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="c3735-122">Beim Erstellen eines Gewinndiagramms müssen Sie auf ein bereits vorhandenes Data Mining-Modell verweisen.</span><span class="sxs-lookup"><span data-stu-id="c3735-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="c3735-123">Sie können Modelle durchsuchen, um nach einem Modell zu suchen, das Ihren Daten entspricht, indem Sie auf **Modelle verwalten** oder auf **Durchsuchen** klicken, um Details zu dem verwendeten Algorithmus und den Spalten im Mining Modell anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3735-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="c3735-124">Weitere Informationen finden Sie unter durch [Suchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) und [Verwalten von Modellen &#40;SQL Server Data Mining-Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c3735-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="c3735-125">So erstellen Sie ein Gewinndiagramm</span><span class="sxs-lookup"><span data-stu-id="c3735-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="c3735-126">Wählen Sie ein bereits vorhandenes Modell aus.</span><span class="sxs-lookup"><span data-stu-id="c3735-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="c3735-127">Geben Sie die Spalte an, die vorhergesagt werden soll, sowie ggf. den Zielwert.</span><span class="sxs-lookup"><span data-stu-id="c3735-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="c3735-128">Wählen Sie die Quelldaten aus. Dies sind die Daten, die Sie in das Modell eingeben, um eine Vorhersage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3735-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="c3735-129">Es sollte sich dabei nicht um die gleichen Daten handeln, mit denen Sie das Modell erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c3735-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="c3735-130">Ordnen Sie die Spalten in den neuen (Quell-)Daten den Spalten im Data Mining-Modell zu.</span><span class="sxs-lookup"><span data-stu-id="c3735-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="c3735-131">Wenn sich die Spaltennamen ähneln, werden sie automatisch vom Assistenten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c3735-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="c3735-132">Geben Sie die für den Assistenten erforderlichen Kosteninformationen ein: feste Kosten, Einzelkosten, Auffüllung und erwartete Einnahmen.</span><span class="sxs-lookup"><span data-stu-id="c3735-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="c3735-133">Optional können Sie eine gestaffelte Reihe von Kosten eingeben (Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="c3735-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="c3735-134">Beispielsweise fallen die Kosten für ein Mailing möglicherweise geringer aus, je größer die Anzahl der gesendeten Elemente ist. In diesem Fall können Sie abhängig von der Anzahl der Sendungen unterschiedliche Kosten eingeben. Die Kosten werden dann vom Assistenten für jede Stichprobengröße automatisch angepasst.</span><span class="sxs-lookup"><span data-stu-id="c3735-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="c3735-135">Vom Assistenten wird ein Diagramm erstellt, in dem die Kosten-Nutzen-Analyse für das Modell dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c3735-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="c3735-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3735-136">Requirements</span></span>  
 <span data-ttu-id="c3735-137">Wenn Sie Vorhersagen für diskrete numerische Werte treffen möchten, müssen Sie den genauen vorherzusagenden Zielwert auswählen.</span><span class="sxs-lookup"><span data-stu-id="c3735-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="c3735-138">Grundlegendes zum Gewinndiagramm</span><span class="sxs-lookup"><span data-stu-id="c3735-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="c3735-139">Das Gewinndiagramm enthält eine graue vertikale Linie, die Sie durch Klicken auf eine Stelle des Diagramms verschieben können.</span><span class="sxs-lookup"><span data-stu-id="c3735-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="c3735-140">In der **Mining Legende** werden eine Bewertung, die richtige Auffüllung und die Vorhersage Wahrscheinlichkeit angezeigt, die mit der Position der grauen Linie im Diagramm verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c3735-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="c3735-141">Wenn Sie mit der grauen Linie im Diagramm den Punkt des höchsten Gewinns auswählen, können Sie über den Wert Vorhersagewahrscheinlichkeit einen Wahrscheinlichkeitsschwellenwert festlegen, ab dem ein Kunde angesprochen wird.</span><span class="sxs-lookup"><span data-stu-id="c3735-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="c3735-142">Wenn beispielsweise die Gewinnkurve ihren höchsten Punkt bei 55 Prozent der Auffüllung erreicht und die zugeordnete Vorhersagewahrscheinlichkeit bei 20 Prozent liegt, bedeutet dies, dass zur Erzielung des Gewinnmaximums nur diejenigen Kunden angesprochen werden sollten, von denen mit einer Wahrscheinlichkeit von 20 Prozent oder mehr eine Antwort erwartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3735-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3735-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3735-143">See Also</span></span>  
 [<span data-ttu-id="c3735-144">Validieren von Modellen und Verwenden von Modellen für Vorhersage &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c3735-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
