---
title: Ausreißer (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727214"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="37a97-102">Ausreißer (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="37a97-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="37a97-103">![Ausreißer-Assistent (Data Mining-Menüband)](media/dmc-outliers.gif "Ausreißer-Assistent (Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="37a97-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="37a97-104">Ein *Ausreißer* bedeutet einen Datenwert, der aus einem der folgenden Gründe problematisch ist:</span><span class="sxs-lookup"><span data-stu-id="37a97-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="37a97-105">Der Wert liegt außerhalb des erwarteten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="37a97-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="37a97-106">Daten wurden möglicherweise falsch eingegeben.</span><span class="sxs-lookup"><span data-stu-id="37a97-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="37a97-107">Der Wert fehlt.</span><span class="sxs-lookup"><span data-stu-id="37a97-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="37a97-108">Daten enthalten ein Leerzeichen oder eine andere NULL-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="37a97-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="37a97-109">Der Wert ist genau, liegt aber so weit außerhalb der Verteilung, dass er das Modell erheblich beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="37a97-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="37a97-110">Mit dem Data Mining-Client für Excel können Sie diese Daten ermitteln und dann die Werte aktualisieren oder unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="37a97-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="37a97-111">Sie können z. B. Ausreißer durch ein arithmetisches Mittel ersetzen oder die Zeilen löschen, die potentiell falsche Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="37a97-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="37a97-112">Ausreißerbehandlung</span><span class="sxs-lookup"><span data-stu-id="37a97-112">Handling Outliers</span></span>  
 <span data-ttu-id="37a97-113">Der **ausreißerentfernungs** -Assistent bietet mehrere Tools, mit denen Ausreißer entsprechend behandelt werden können:</span><span class="sxs-lookup"><span data-stu-id="37a97-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="37a97-114">Zunächst können Sie die Daten untersuchen, um die Verteilung von Werten und die Beziehung zwischen Ausreißern und anderen Daten besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="37a97-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="37a97-115">Beispielsweise können Sie den Task " **Daten durchsuchen** " verwenden, um die Werte zu überprüfen und zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="37a97-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="37a97-116">Der **ausreißerentfernungs** -Assistent zeigt außerdem ein Diagramm an, entweder ein Linien-oder Balkendiagramm, um Ihnen das Verständnis der Verteilung aller Werte zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="37a97-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="37a97-117">Als nächstes können Sie mit dem **ausreißerausreißerassistenten** Ausreißer entfernen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="37a97-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="37a97-118">Die zu verwendende Methode hängt davon ab, ob die Werte diskret oder kontinuierlich sind.</span><span class="sxs-lookup"><span data-stu-id="37a97-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="37a97-119">Der Assistent stellt diskrete Werte in einem Balkendiagramm dar, wobei jeder Balken für einen bestimmten Wert und die Höhe des Balkens für die Anzahl der Fälle für jeden Wert steht.</span><span class="sxs-lookup"><span data-stu-id="37a97-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="37a97-120">Durch Bewegen des Schwellenwert-Schiebereglers im Diagramm können Sie die Balken verkürzen, die Gruppen mit ungewöhnlichen oder potentiell schlechten Werten darstellen.</span><span class="sxs-lookup"><span data-stu-id="37a97-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="37a97-121">Der Assistent zeigt kontinuierliche Werte entweder in einem Balkendiagramm oder in einem Liniendiagramm an.</span><span class="sxs-lookup"><span data-stu-id="37a97-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="37a97-122">Im Liniendiagramm wird der Wert auf der X-Achse und die Anzahl der Werte auf der Y-Achse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="37a97-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="37a97-123">Sie können steuern, ob die Werte am unteren und am Ende des Diagramms entfernt oder beibehalten werden sollen, indem Sie die **minimalen** und **maximalen** Werte ändern oder die Balken verschieben.</span><span class="sxs-lookup"><span data-stu-id="37a97-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="37a97-124">Beim Ändern der Minimum- und Maximumwerte werden die unterdrückten Daten im Diagramm schattiert dargestellt.</span><span class="sxs-lookup"><span data-stu-id="37a97-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="37a97-125">Nachdem Sie ausgewählt haben, mit welchen Ausreißern Sie arbeiten möchten, können Sie im Assistenten festlegen, wie die Ausreißer verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="37a97-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="37a97-126">Sie können die Zeilen mit den Ausreißerwerten löschen oder einen Ersatzwert angeben, wie z. B. einen Mittelwert, eine Null oder einen anderen Wert Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="37a97-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="37a97-127">Schließlich bietet der Assistent einige Optionen zum Anzeigen der neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="37a97-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="37a97-128">Sie können die ursprünglichen Daten durch die neuen Werte ersetzen, der Tabelle eine neue Spalte mit den neuen Werten hinzufügen oder ein neues Arbeitsblatt erstellen, das die aktualisierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="37a97-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="37a97-129">Verwenden des Ausreißerentfernungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="37a97-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="37a97-130">Klicken Sie im **Data Mining** -Menüband auf **Daten bereinigen**, und wählen Sie **Ausreißer**aus.</span><span class="sxs-lookup"><span data-stu-id="37a97-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="37a97-131">Wählen Sie im Dialogfeld **Quelldaten auswählen** eine Excel-Datentabelle oder einen Zellbereich aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="37a97-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="37a97-132">Sie können den **Ausreißer** -Assistenten nicht für externe Daten verwenden, es sei denn, Sie kopieren ihn zuerst in Excel.</span><span class="sxs-lookup"><span data-stu-id="37a97-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="37a97-133">Wählen Sie im Dialogfeld **Spalte auswählen** eine **einzelne** Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="37a97-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="37a97-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37a97-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="37a97-135">Überprüfen Sie im Dialogfeld **Schwellenwerte angeben** die Verteilung der Daten.</span><span class="sxs-lookup"><span data-stu-id="37a97-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="37a97-136">Wenn die Spalte diskrete Werte enthält, zeigt der Assistent ein Histogramm an, das die Anzahl für jeden diskreten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="37a97-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="37a97-137">Wenn es sich bei Ausreißern um seltene Werte handelt, können Sie diese filtern, indem Sie den **Minimal** Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="37a97-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="37a97-138">Wenn die Spalte numerische Daten enthält, können Sie auf die Schaltfläche **als diskret anzeigen** oder auf die Schaltfläche **als numerisch anzeigen** klicken, um zwischen dem Anzeigen der Werte in einem Balkendiagramm oder einem Liniendiagramm zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="37a97-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="37a97-139">Wählen Sie im Dialogfeld **Schwellenwerte angeben** den Datenbereich aus, den Sie aufbewahren möchten, indem Sie einen minimal-und Höchstwert eingeben, oder indem Sie die Schieberegler ziehen.</span><span class="sxs-lookup"><span data-stu-id="37a97-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="37a97-140">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37a97-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="37a97-141">Geben Sie im Dialogfeld **ausreißerbehandlung** an, ob die Werte gelöscht oder ersetzt werden sollen, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="37a97-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="37a97-142">Geben Sie im Dialogfeld **Ziel auswählen** an, wo die neuen Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="37a97-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="37a97-143">Zugehörige Optionen</span><span class="sxs-lookup"><span data-stu-id="37a97-143">Related Options</span></span>  
 <span data-ttu-id="37a97-144">Der Assistent bietet folgende Optionen:</span><span class="sxs-lookup"><span data-stu-id="37a97-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="37a97-145">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="37a97-145">**Options**</span></span>|<span data-ttu-id="37a97-146">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="37a97-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="37a97-147">**Spalte auswählen**</span><span class="sxs-lookup"><span data-stu-id="37a97-147">**Select Column**</span></span>|<span data-ttu-id="37a97-148">Sie können nur mit jeweils einer Spalte arbeiten.</span><span class="sxs-lookup"><span data-stu-id="37a97-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="37a97-149">**Umgang mit Schwellenwerten angeben**</span><span class="sxs-lookup"><span data-stu-id="37a97-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="37a97-150">Legen Sie einen Schwellenwert mithilfe von **Minimal** fest, um Werte auszuschließen, die in weniger Zeilen als der Schwellenwert gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="37a97-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="37a97-151">Anfänglich ist der Wert **Minimal** gleich dem Wert mit den wenigsten Zeilen, und Sie können den Minimalwert nicht unterschreiten.</span><span class="sxs-lookup"><span data-stu-id="37a97-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="37a97-152">**Ausreißerbehandlung**</span><span class="sxs-lookup"><span data-stu-id="37a97-152">**Outlier Handling**</span></span>|<span data-ttu-id="37a97-153">Wenn Sie Ausreißer löschen möchten, können Sie die Daten im aktuellen Arbeitsblatt ändern oder eine Kopie der Daten in einem neuen Arbeitsblatt erstellen.</span><span class="sxs-lookup"><span data-stu-id="37a97-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37a97-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37a97-154">See Also</span></span>  
 [<span data-ttu-id="37a97-155">Durchsuchen von Daten &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="37a97-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
