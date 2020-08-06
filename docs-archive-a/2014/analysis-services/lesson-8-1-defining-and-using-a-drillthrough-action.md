---
title: Definieren und Verwenden von Drillthrough-Aktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698726"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="ef553-102">Definieren und Verwenden einer Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ef553-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="ef553-103">Das Dimensionieren von Faktendaten mit einer Faktendimension, ohne die von der Abfrage zurückgegebenen Daten richtig zu filtern, kann bei Abfragen zu einer verminderten Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="ef553-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="ef553-104">Um dies zu vermeiden, können Sie eine Drillthroughaktion definieren, mit der die Gesamtanzahl der Zeilen, die zurückgegeben werden, reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="ef553-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="ef553-105">Dadurch wird die Abfrageleistung erheblich verbessert.</span><span class="sxs-lookup"><span data-stu-id="ef553-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="ef553-106">Im Rahmen der Tasks in diesem Thema definieren Sie eine Drillthroughaktion, die Bestelldetailinformationen für Verkäufe an Kunden über das Internet zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ef553-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="ef553-107">Definieren der Eigenschaften einer Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ef553-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="ef553-108">Klicken Sie im Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube auf die Registerkarte **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="ef553-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="ef553-109">Die Registerkarte **Aktionen** umfasst mehrere Bereiche.</span><span class="sxs-lookup"><span data-stu-id="ef553-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="ef553-110">Auf der linken Seite der Registerkarte werden die Bereiche **Aktionsplaner** und **Berechnungstools** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef553-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="ef553-111">Rechts neben diesen beiden Bereichen befindet sich der **Anzeigebereich** , der die Details der im Bereich **Aktionsplaner** ausgewählten Aktion enthält.</span><span class="sxs-lookup"><span data-stu-id="ef553-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="ef553-112">In der folgenden Abbildung ist die Registerkarte **Aktionen** des Cube-Designers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef553-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="ef553-113">![Aktionen (Registerkarte) des Cube-Designers](../../2014/tutorials/media/l8-action1.gif "Aktionen (Registerkarte) des Cube-Designers")</span><span class="sxs-lookup"><span data-stu-id="ef553-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="ef553-114">Klicken Sie auf der Symbolleiste der Registerkarte **Aktionen** auf **Neue Drillthroughaktion** .</span><span class="sxs-lookup"><span data-stu-id="ef553-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="ef553-115">Es wird eine leere Aktionsvorlage im Anzeigebereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef553-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="ef553-116">![Leere Aktionsvorlage im Anzeigebereich](../../2014/tutorials/media/l8-action2.gif "Leere Aktionsvorlage im Anzeigebereich")</span><span class="sxs-lookup"><span data-stu-id="ef553-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="ef553-117">Ändern Sie im Feld **Name** den Namen dieser Aktion in `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="ef553-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="ef553-118">Wählen Sie in der Liste **Measuregruppenelemente** die Option **Internet Sales**aus.</span><span class="sxs-lookup"><span data-stu-id="ef553-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="ef553-119">Wählen Sie im Feld **Drillthroughspalten** in der Liste **Dimensionen** die Option **Internet Sales Order Details** aus.</span><span class="sxs-lookup"><span data-stu-id="ef553-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="ef553-120">Aktivieren Sie in der Liste **Rückgabespalten** die Kontrollkästchen für **Elementbeschreibung** und **Bestellnummer** , und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef553-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="ef553-121">In der folgenden Abbildung ist die Aktionsvorlage zu sehen, wie sie zum jetzigen Zeitpunkt in dieser Prozedur aussehen sollte.</span><span class="sxs-lookup"><span data-stu-id="ef553-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="ef553-122">![Drillthroughspalten (Feld)](../../2014/tutorials/media/l8-action3.gif "Drillthroughspalten (Feld)")</span><span class="sxs-lookup"><span data-stu-id="ef553-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="ef553-123">Erweitern Sie das Feld **Weitere Eigenschaften** , wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef553-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="ef553-124">![Weitere Eigenschaften (Feld)](../../2014/tutorials/media/l8-action4.gif "Weitere Eigenschaften (Feld)")</span><span class="sxs-lookup"><span data-stu-id="ef553-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="ef553-125">Geben Sie im Feld **Maximale Zeilen** Anzahl ein `10` .</span><span class="sxs-lookup"><span data-stu-id="ef553-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="ef553-126">Geben Sie im Feld **Beschriftung** den Text ein `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="ef553-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="ef553-127">Durch diese Einstellungen wird die Anzahl der zurückgegebenen Zeilen beschränkt und die Beschriftung angegeben, die im Clientanwendungsmenü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ef553-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="ef553-128">In der folgenden Abbildung werden diese Einstellungen im Feld **Weitere Eigenschaften** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef553-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="ef553-129">![Weitere Eigenschaften (Feld)](../../2014/tutorials/media/l8-action5.gif "Weitere Eigenschaften (Feld)")</span><span class="sxs-lookup"><span data-stu-id="ef553-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="ef553-130">Verwenden der Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ef553-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="ef553-131">Klicken Sie im Menü **Erstellen** auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="ef553-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="ef553-132">Klicken Sie nach erfolgreichem Abschluss der Bereitstellung im Cube-Designer für den **Tutorial-Cube auf die Registerkarte** Browser [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] und anschließend auf die Schaltfläche **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="ef553-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="ef553-133">Starten Sie Excel.</span><span class="sxs-lookup"><span data-stu-id="ef553-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="ef553-134">Fügen Sie dem Bereich „Werte“ das **Internet Sales-Sales Amount** -Measure hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef553-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="ef553-135">Fügen Sie dem Bereich **Berichtsfilter** die benutzerdefinierte **Customer Geography** -Hierarchie aus dem Ordner **Location** in der **Customer** -Dimension hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef553-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="ef553-136">Fügen Sie in der PivotTable in **Customer Geography**einen Filter hinzu, durch den ein einzelner Kunde ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ef553-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="ef553-137">Erweitern Sie die Optionen **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, aktivieren Sie das Kontrollkästchen für **Adam Powell**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef553-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ef553-138">Im Bereich Daten werden die gesamten Produktverkäufe von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] an Adam Powell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef553-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="ef553-139">Klicken Sie mit der rechten Maustaste auf den Umsatz, zeigen Sie auf **Zusätzliche Aktionen**, und klicken Sie anschließend auf **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="ef553-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="ef553-140">Die Details der an Adam Powell gelieferten Bestellungen werden im **Datenstichproben-Viewer**angezeigt, wie in der folgenden Abbildung zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="ef553-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="ef553-141">Einige zusätzliche Details wären jedoch hilfreich, wie z. B. Bestelldatum, Fälligkeitsdatum und Lieferdatum.</span><span class="sxs-lookup"><span data-stu-id="ef553-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="ef553-142">Sie fügen diese zusätzlichen Details in der nächsten Prozedur hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef553-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="ef553-143">![An Adam Powell versendete Bestellungen](../../2014/tutorials/media/l8-action6.gif "An Adam Powell versendete Bestellungen")</span><span class="sxs-lookup"><span data-stu-id="ef553-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="ef553-144">Schließen von Excel/</span><span class="sxs-lookup"><span data-stu-id="ef553-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="ef553-145">Ändern der Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ef553-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="ef553-146">Öffnen Sie den Dimensions-Designer für die **Internet Sales Order Details** -Dimension.</span><span class="sxs-lookup"><span data-stu-id="ef553-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="ef553-147">Für diese Dimension wurden nur drei Attribute definiert.</span><span class="sxs-lookup"><span data-stu-id="ef553-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="ef553-148">Klicken Sie im Bereich **Datenquellensicht** mit der rechten Maustaste auf einen leeren Bereich und anschließend auf **Alle Tabellen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ef553-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="ef553-149">Zeigen Sie im Menü **Format** auf **AutoLayout** , und klicken Sie anschließend auf **Diagramm**.</span><span class="sxs-lookup"><span data-stu-id="ef553-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="ef553-150">Suchen Sie die Tabelle **InternetSales (dbo.FactInternetSales)** , indem Sie mit der rechten Maustaste in einem offenen Bereich des Bereichs **Datenquellensicht** klicken.</span><span class="sxs-lookup"><span data-stu-id="ef553-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="ef553-151">Klicken Sie auf **Tabelle suchen** und auf **InternetSales,** und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef553-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="ef553-152">Erstellen Sie neue Attribute anhand der folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="ef553-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="ef553-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="ef553-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="ef553-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="ef553-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="ef553-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="ef553-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="ef553-156">Ändern Sie die **Name** -Eigenschaft für das **Order Date Key** -Attribut in `Order Date` , und klicken Sie dann auf die Schaltfläche zum Durchsuchen für die **Name Column** -Eigenschaft, und wählen Sie im Dialogfeld **Namensspalte** den Wert **Date** als Quell Tabelle und SimpleDate als Quell Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="ef553-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="ef553-157">Ändern Sie die **Name** -Eigenschaft für das **Due Date Key** -Attribut in `Due Date` , und ändern Sie dann mithilfe derselben Methode wie das **Order Date Key** -Attribut die **Name Column** -Eigenschaft für dieses Attribut in **Date. SimpleDate (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="ef553-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="ef553-158">Ändern Sie die **Name** -Eigenschaft für das **Ship Date Key** -Attribut in `Ship Date` , und ändern Sie dann die **Name Column** -Eigenschaft für dieses Attribut in **Date. SimpleDate (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="ef553-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="ef553-159">Wechseln Sie zur Registerkarte **Aktionen** des Cube-Designers für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube.</span><span class="sxs-lookup"><span data-stu-id="ef553-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="ef553-160">Fügen Sie im Feld **Drillthroughspalten** der Liste **Rückgabespalten** die folgenden Spalten durch Aktivieren der entsprechenden Kontrollkästchen hinzu, und klicken Sie anschließend auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="ef553-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="ef553-161">Order Date</span><span class="sxs-lookup"><span data-stu-id="ef553-161">Order Date</span></span>  
  
    -   <span data-ttu-id="ef553-162">Due Date</span><span class="sxs-lookup"><span data-stu-id="ef553-162">Due Date</span></span>  
  
    -   <span data-ttu-id="ef553-163">Ship Date</span><span class="sxs-lookup"><span data-stu-id="ef553-163">Ship Date</span></span>  
  
     <span data-ttu-id="ef553-164">In der folgenden Abbildung sind diese Spalten markiert.</span><span class="sxs-lookup"><span data-stu-id="ef553-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="ef553-165">![Drillthroughspalten (Feld)](../../2014/tutorials/media/l8-action7.gif "Drillthroughspalten (Feld)")</span><span class="sxs-lookup"><span data-stu-id="ef553-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="ef553-166">Überprüfen der geänderten Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ef553-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="ef553-167">Klicken Sie im Menü **Erstellen** auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="ef553-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="ef553-168">Wechseln Sie nach erfolgreichem Abschluss der Bereitstellung im Cube-Designer für den **Tutorial-Cube zur Registerkarte** Browser [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , und klicken Sie anschließend auf die Schaltfläche **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="ef553-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="ef553-169">Starten Sie Excel.</span><span class="sxs-lookup"><span data-stu-id="ef553-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="ef553-170">Erstellen Sie die PivotTable mit **Internet Sales-Sales Amount** im Bereich „Werte“ und **Customer Geography** im Berichtsfilter neu.</span><span class="sxs-lookup"><span data-stu-id="ef553-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="ef553-171">Fügen Sie einen Filter hinzu, durch den **Adam Powell**aus **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ef553-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="ef553-172">Klicken Sie auf die Datenzelle **Internet Sales-Sales Amount** , zeigen Sie auf **Zusätzliche Aktionen**, und klicken Sie anschließend auf **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="ef553-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="ef553-173">Die Details dieser an Adam Powell gelieferten Bestellungen werden in einem temporären Arbeitsblatt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef553-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="ef553-174">Dies umfasst Artikelbeschreibung, Bestellnummer, Bestelldatum, Fälligkeitsdatum und Versanddatum, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef553-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="ef553-175">![An Adam Powell versendete Bestellungen](../../2014/tutorials/media/l8-action8.gif "An Adam Powell versendete Bestellungen")</span><span class="sxs-lookup"><span data-stu-id="ef553-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ef553-176">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="ef553-176">Next Lesson</span></span>  
 [<span data-ttu-id="ef553-177">Lektion 9: Definieren von Perspektiven und Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="ef553-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef553-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef553-178">See Also</span></span>  
 <span data-ttu-id="ef553-179">[Aktionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ef553-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ef553-180">[Aktionen in mehrdimensionalen Modellen](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="ef553-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="ef553-181">[Dimensions Beziehungen](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="ef553-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="ef553-182">[Definieren einer Fakten Beziehung](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="ef553-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="ef553-183">Definieren von Faktenbeziehungen und Faktenbeziehungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="ef553-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
