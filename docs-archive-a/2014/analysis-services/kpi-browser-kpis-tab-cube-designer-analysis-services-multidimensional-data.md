---
title: KPI-Browser (Registerkarte ' KPIs ', Cube-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610154"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="98bc3-102">KPI-Browser (Registerkarte 'KPIs', Cube-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="98bc3-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="98bc3-103">Mithilfe des Bereichs **KPI-Browser** der Registerkarte **KPIs** des Cube-Designers können Sie die KPI-Ergebnisse (Key Performance Indicators) anzeigen und testen.</span><span class="sxs-lookup"><span data-stu-id="98bc3-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="98bc3-104">KPIs müssen vor dem Durchsuchen zuerst auf einer-Instanz bereitgestellt werden [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98bc3-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98bc3-105">Der Bereich wird nur in der Browseransicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98bc3-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98bc3-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="98bc3-106">Options</span></span>  
 <span data-ttu-id="98bc3-107">**Teilcuberaster**</span><span class="sxs-lookup"><span data-stu-id="98bc3-107">**Subcube grid**</span></span>  
 <span data-ttu-id="98bc3-108">Definieren Sie mithilfe dieser Option einen Teilcube, und schränken Sie die im Bereich **Ergebnisse** angezeigten Ergebnisse der KPIs ein.</span><span class="sxs-lookup"><span data-stu-id="98bc3-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="98bc3-109">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="98bc3-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="98bc3-110">**Dimension**</span><span class="sxs-lookup"><span data-stu-id="98bc3-110">**Dimension**</span></span>  
 <span data-ttu-id="98bc3-111">Wählen Sie die Dimension aus, auf die dieser Filter angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="98bc3-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="98bc3-112">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="98bc3-112">**Hierarchy**</span></span>  
 <span data-ttu-id="98bc3-113">Wählen Sie die Hierarchie aus, auf die dieser Filter angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="98bc3-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="98bc3-114">**Operator**</span><span class="sxs-lookup"><span data-stu-id="98bc3-114">**Operator**</span></span>  
 <span data-ttu-id="98bc3-115">Wählen Sie den Operator aus, der definiert, wie der Ausdruck in **Filterausdruck** auf die ausgewählte Hierarchie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="98bc3-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="98bc3-116">Die folgende Tabelle beschreibt die verfügbaren Operatoren.</span><span class="sxs-lookup"><span data-stu-id="98bc3-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="98bc3-117">Wert</span><span class="sxs-lookup"><span data-stu-id="98bc3-117">Value</span></span>|<span data-ttu-id="98bc3-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98bc3-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98bc3-119">**Gleich**</span><span class="sxs-lookup"><span data-stu-id="98bc3-119">**Equal**</span></span>|<span data-ttu-id="98bc3-120">Die Ergebnisse sind auf die in **Filterausdruck**definierte Menge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="98bc3-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-121">**Ungleich**</span><span class="sxs-lookup"><span data-stu-id="98bc3-121">**Not Equal**</span></span>|<span data-ttu-id="98bc3-122">Die Ergebnisse sind auf die Elemente beschränkt, die durch die in **Filterausdruck**definierte Menge ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="98bc3-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-123">**Geben Sie in**</span><span class="sxs-lookup"><span data-stu-id="98bc3-123">**In**</span></span>|<span data-ttu-id="98bc3-124">Die Ergebnisse sind auf die in **Filterausdruck**gewählte benannte Menge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="98bc3-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-125">**Not In**</span><span class="sxs-lookup"><span data-stu-id="98bc3-125">**Not In**</span></span>|<span data-ttu-id="98bc3-126">Die Ergebnisse sind auf die Elemente beschränkt, die durch die in **Filterausdruck**gewählte benannte Menge ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="98bc3-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-127">**Contains**</span><span class="sxs-lookup"><span data-stu-id="98bc3-127">**Contains**</span></span>|<span data-ttu-id="98bc3-128">Die Ergebnisse sind auf die Elemente beschränkt, deren Elementnamen die in **Filterausdruck**angegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="98bc3-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-129">**Beginnt mit**</span><span class="sxs-lookup"><span data-stu-id="98bc3-129">**Begins With**</span></span>|<span data-ttu-id="98bc3-130">Die Ergebnisse sind auf die Elemente beschränkt, deren Elementnamen mit der in **Filterausdruck**angegebenen Zeichenfolge beginnen.</span><span class="sxs-lookup"><span data-stu-id="98bc3-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-131">**Bereich (inklusiv)**</span><span class="sxs-lookup"><span data-stu-id="98bc3-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="98bc3-132">Die Ergebnisse sind auf den in **Filterausdruck**ausgewählten Bereich beschränkt.</span><span class="sxs-lookup"><span data-stu-id="98bc3-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-133">**Bereich (exklusiv)**</span><span class="sxs-lookup"><span data-stu-id="98bc3-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="98bc3-134">Die Ergebnisse sind auf die Elemente beschränkt, die durch den in **Filterausdruck**ausgewählten Bereich ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="98bc3-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98bc3-135">**MDX**</span><span class="sxs-lookup"><span data-stu-id="98bc3-135">**MDX**</span></span>|<span data-ttu-id="98bc3-136">Die Ergebnisse sind auf den in **Filterausdruck**festgelegten MDX-Ausdruck (Multidimensional Expressions) beschränkt.</span><span class="sxs-lookup"><span data-stu-id="98bc3-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="98bc3-137">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="98bc3-137">**Filter Expression**</span></span>  
 <span data-ttu-id="98bc3-138">Geben Sie den Ausdruck ein, der durch **Operator**ausgewertet werden soll, um die zu durchsuchenden KPI-Ergebnisse einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="98bc3-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98bc3-139">Bei dem Feld handelt es sich um ein dynamisches Dateneingabeelement, dessen Anzeigemodus sich je nach dem vom ausgewählten Operator benötigten Datentyp ändert.</span><span class="sxs-lookup"><span data-stu-id="98bc3-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="98bc3-140">**Ergebnis Raster**</span><span class="sxs-lookup"><span data-stu-id="98bc3-140">**Results grid**</span></span>  
 <span data-ttu-id="98bc3-141">Zeigt basierend auf einem unter **Filterraster**definierten Filter den ausgewerteten Wert, das Ziel, den Status und den Trend der KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="98bc3-142">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="98bc3-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="98bc3-143">**Struktur anzeigen**</span><span class="sxs-lookup"><span data-stu-id="98bc3-143">**Display Structure**</span></span>  
 <span data-ttu-id="98bc3-144">Zeigt die im Cube enthaltenen KPIs hierarchisch nach den Werten **Anzeigeordner** oder **Übergeordneter KPI** für jeden KPI organisiert an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="98bc3-145">**Wert**</span><span class="sxs-lookup"><span data-stu-id="98bc3-145">**Value**</span></span>  
 <span data-ttu-id="98bc3-146">Zeigt den Wert des KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="98bc3-147">**Zielsetzung**</span><span class="sxs-lookup"><span data-stu-id="98bc3-147">**Goal**</span></span>  
 <span data-ttu-id="98bc3-148">Zeigt den Zielwert des KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="98bc3-149">**Status**</span><span class="sxs-lookup"><span data-stu-id="98bc3-149">**Status**</span></span>  
 <span data-ttu-id="98bc3-150">Zeigt die Statusgrafik des KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="98bc3-151">**Trend**</span><span class="sxs-lookup"><span data-stu-id="98bc3-151">**Trend**</span></span>  
 <span data-ttu-id="98bc3-152">Zeigt die Trendgrafik des KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="98bc3-153">**Weight**</span><span class="sxs-lookup"><span data-stu-id="98bc3-153">**Weight**</span></span>  
 <span data-ttu-id="98bc3-154">Zeigt den Gewichtungungsfaktor des KPIs an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="98bc3-155">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="98bc3-155">**(Description)**</span></span>  
 <span data-ttu-id="98bc3-156">Zeigt ein Informationssymbol an, wenn für einen KPI eine Beschreibung bereit steht.</span><span class="sxs-lookup"><span data-stu-id="98bc3-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="98bc3-157">Zeigen Sie mit dem Cursor auf das Informationssymbol, um eine QuickInfo mit einer Beschreibung für den KPI anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98bc3-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98bc3-158">Wenn während der Berechnung eines KPIs auf der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz ein Fehler auftritt, zeigt diese Option mit dem Fehler verknüpfte Informationen an.</span><span class="sxs-lookup"><span data-stu-id="98bc3-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bc3-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98bc3-159">See Also</span></span>  
 [<span data-ttu-id="98bc3-160">KPIs &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="98bc3-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
