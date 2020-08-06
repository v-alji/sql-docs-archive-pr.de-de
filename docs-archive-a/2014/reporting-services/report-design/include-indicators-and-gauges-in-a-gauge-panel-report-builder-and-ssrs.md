---
title: Aufnehmen von Indikatoren und Messgeräten in einen Messgerätbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723474"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="8345a-102">Aufnehmen von Indikatoren und Messgeräten in einen Messgerätbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8345a-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8345a-103">Der Messgerätbereich ist der Container der obersten Ebene, der mindestens ein Messgerät und/oder einen Indikator enthält.</span><span class="sxs-lookup"><span data-stu-id="8345a-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="8345a-104">Indikatoren können in Messgeräte eingebettet werden oder neben ihnen im Messgerätbereich eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8345a-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="8345a-105">Wenn der Indikator und das Messgerät im Messgerätbereich angrenzen und Daten aus anderen Feldern anzeigen, empfiehlt es sich, Bezeichnungen hinzufügen, um unmissverständlich anzuzeigen, welche Daten das Messgerät und der Indikator übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8345a-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="8345a-106">Messgerät- und Indikatoroptionen können mit Ausdrücken festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8345a-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="8345a-107">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8345a-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="8345a-108">So betten Sie einen Indikator in einem Messgerät ein</span><span class="sxs-lookup"><span data-stu-id="8345a-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="8345a-109">Öffnen Sie einen vorhandenen Bericht, oder erstellen Sie einen neuen Bericht, der eine Tabelle und eine Matrix mit den anzuzeigenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="8345a-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="8345a-110">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) oder [Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8345a-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="8345a-111">Fügen Sie eine Spalte in die Tabelle oder Matrix ein.</span><span class="sxs-lookup"><span data-stu-id="8345a-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="8345a-112">Weitere Informationen finden Sie unter [Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8345a-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="8345a-113">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Messgerät**, und klicken Sie danach auf eine Zelle in der neuen Spalte.</span><span class="sxs-lookup"><span data-stu-id="8345a-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="8345a-114">Das Dialogfeld **Messgerättyp auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8345a-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="8345a-115">Klicken Sie auf **Radial**.</span><span class="sxs-lookup"><span data-stu-id="8345a-115">Click **Radial**.</span></span> <span data-ttu-id="8345a-116">Das erste radiale Messgerät wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8345a-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8345a-117">Klicken Sie auf das Messgerät.</span><span class="sxs-lookup"><span data-stu-id="8345a-117">Click the gauge.</span></span> <span data-ttu-id="8345a-118">Der Bereich **Messgerätdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="8345a-119">Klicken Sie im Bereich **Werte** im Listenfeld **(Keine Angabe)** auf das Feld, dessen Werte im Messgerät angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8345a-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="8345a-120">Sie können auch das Feld, das verwendet werden soll, aus dem Berichtsdataset ziehen.</span><span class="sxs-lookup"><span data-stu-id="8345a-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="8345a-121">Klicken Sie mit der rechten Maustaste auf das Messgerät, klicken Sie auf **Indikator hinzufügen**und anschließend auf **Untergeordnet**.</span><span class="sxs-lookup"><span data-stu-id="8345a-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="8345a-122">Das Dialogfeld **Indikatorart auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="8345a-123">Klicken Sie im linken Bereich des Dialogfelds **Indikatorart auswählen** auf den gewünschten Indikatortyp und dann auf den Indikatorsatz.</span><span class="sxs-lookup"><span data-stu-id="8345a-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="8345a-124">Klicken Sie auf den Indikator.</span><span class="sxs-lookup"><span data-stu-id="8345a-124">Click the indicator.</span></span> <span data-ttu-id="8345a-125">Der Bereich **Messgerätdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="8345a-126">Klicken Sie im Bereich **Werte** im Listenfeld **(Keine Angabe)** auf das Feld, dessen Werte Sie als Indikator anzeigen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="8345a-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="8345a-127">Sie können auch das Feld, das verwendet werden soll, aus dem Berichtsdataset ziehen.</span><span class="sxs-lookup"><span data-stu-id="8345a-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="8345a-128">Das Feld kann sowohl das gleiche als auch ein anderes Feld als das sein, das Sie im Messgerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="8345a-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="8345a-129">So zeigen Sie einen Indikator und ein Messgerät nebeneinander an</span><span class="sxs-lookup"><span data-stu-id="8345a-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="8345a-130">Öffnen Sie einen vorhandenen Bericht, oder erstellen Sie einen neuen Bericht, der eine Tabelle und eine Matrix mit den anzuzeigenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="8345a-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="8345a-131">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) oder [Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8345a-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="8345a-132">Fügen Sie eine Spalte in die Tabelle oder Matrix ein.</span><span class="sxs-lookup"><span data-stu-id="8345a-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="8345a-133">Weitere Informationen finden Sie unter [Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8345a-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="8345a-134">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Messgerät**, und klicken Sie danach auf eine Zelle in der eingefügten Spalte.</span><span class="sxs-lookup"><span data-stu-id="8345a-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="8345a-135">Das Dialogfeld **Messgerättyp auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8345a-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="8345a-136">Klicken Sie auf **Radial**.</span><span class="sxs-lookup"><span data-stu-id="8345a-136">Click **Radial**.</span></span> <span data-ttu-id="8345a-137">Das erste radiale Messgerät wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8345a-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8345a-138">Klicken Sie auf das Messgerät.</span><span class="sxs-lookup"><span data-stu-id="8345a-138">Click the gauge.</span></span> <span data-ttu-id="8345a-139">Der Bereich **Messgerätdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="8345a-140">Klicken Sie im Bereich **Werte** im Listenfeld **(Keine Angabe)** auf das Feld, dessen Werte im Messgerät angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8345a-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="8345a-141">Sie können auch das Feld, das verwendet werden soll, aus dem Berichtsdataset ziehen.</span><span class="sxs-lookup"><span data-stu-id="8345a-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="8345a-142">Klicken Sie mit der rechten Maustaste auf das Messgerät, klicken Sie auf **Indikator hinzufügen**und anschließend auf **Angrenzend**.</span><span class="sxs-lookup"><span data-stu-id="8345a-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="8345a-143">Das Dialogfeld **Indikatorart auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="8345a-144">Klicken Sie im linken Bereich des Dialogfelds **Indikatorart auswählen** auf den gewünschten Indikatortyp und dann auf den Indikatorsatz.</span><span class="sxs-lookup"><span data-stu-id="8345a-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="8345a-145">Klicken Sie auf den Indikator.</span><span class="sxs-lookup"><span data-stu-id="8345a-145">Click the indicator.</span></span> <span data-ttu-id="8345a-146">Der Bereich **Messgerätdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8345a-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="8345a-147">Klicken Sie im Bereich **Werte** im Listenfeld **(Keine Angabe)** auf das Feld, dessen Werte Sie als Indikator anzeigen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="8345a-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="8345a-148">Sie können auch das Feld, das verwendet werden soll, aus dem Berichtsdataset ziehen.</span><span class="sxs-lookup"><span data-stu-id="8345a-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="8345a-149">Das Feld kann sowohl das gleiche als auch ein anderes Feld als das sein, das Sie im Messgerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="8345a-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="8345a-150">Klicken Sie mit der rechten Maustaste auf den Bereich „Messgerät“, und klicken Sie anschließend auf **Bezeichnung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8345a-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="8345a-151">Dem Messgerät wird eine Bezeichnung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8345a-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="8345a-152">Wiederholen Sie diesen Schritt noch einmal.</span><span class="sxs-lookup"><span data-stu-id="8345a-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="8345a-153">Der Messgerätbereich verfügt über zwei Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="8345a-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="8345a-154">Ziehen Sie jede Bezeichnung an eine Stelle in der Nähe des Messgeräts oder Indikators.</span><span class="sxs-lookup"><span data-stu-id="8345a-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="8345a-155">Klicken Sie mit der rechten Maustaste auf die Bezeichnung in der Nähe des Messgeräts, klicken Sie auf **Bezeichnungseigenschaften**, und geben Sie den Text ein, der im Feld **Text** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8345a-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="8345a-156">Klicken Sie mit der rechten Maustaste auf den Indikator in der Nähe des Messgeräts, klicken Sie auf **Bezeichnungseigenschaften**, und geben Sie den Text ein, der im Feld **Text** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8345a-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8345a-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8345a-157">See Also</span></span>  
 [<span data-ttu-id="8345a-158">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8345a-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
