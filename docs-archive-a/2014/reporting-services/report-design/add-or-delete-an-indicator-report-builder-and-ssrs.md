---
title: Hinzufügen oder Löschen eines Indikators (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719600"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="3a704-102">Hinzufügen oder Löschen eines Indikators (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="3a704-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3a704-103">Indikatoren sind minimale Messgeräte, die den Zustand eines einzelnen Datenwerts auf einen Blick wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="3a704-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="3a704-104">Weitere Informationen dazu finden Sie unter [Indikatoren &#40;Berichts-Generator und SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a704-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="3a704-105">Indikatoren werden im Allgemeinen in einer Tabelle oder einer Matrix in Zellen eingefügt, aber Sie können Indikatoren auch parallel mit Messgeräten, eingebettet in Messgeräte oder eigenständig verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a704-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="3a704-106">Beim ersten Hinzufügen eines Indikators wird er standardmäßig so konfiguriert, dass Prozentsätze als Maßeinheiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a704-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="3a704-107">Die Prozentbereiche sind gleichmäßig über die Elemente des Indikatorsatzes verteilt, und der vom Indikator angezeigte Wertebereich entspricht dem übergeordneten Element des Indikators, z. B. einer Tabelle oder Matrix.</span><span class="sxs-lookup"><span data-stu-id="3a704-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="3a704-108">Sie können die Werte und die Status von Indikatoren aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3a704-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="3a704-109">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3a704-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="3a704-110">Ändern von Indikatorsymbolen und Indikatorsätzen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a704-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="3a704-111">Festlegen und Konfigurieren von Maßeinheiten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a704-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="3a704-112">Festlegen des Synchronisierungsbereichs &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a704-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="3a704-113">Da ein Indikator im Messgerätebereich positioniert wird, müssen Sie den Indikator statt des Bereichs auswählen, wenn Sie den Indikator mit dem Dialogfeld **Indikatoreigenschaften** oder dem Bereich **Eigenschaften** konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3a704-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="3a704-114">Die folgende Abbildung enthält einen ausgewählten Indikator in dessen Messgerätbereich.</span><span class="sxs-lookup"><span data-stu-id="3a704-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="3a704-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="3a704-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a704-116">Abhängig von der Spaltenbreite und Länge der Datenwerte kann der Text in Tabellen- oder Matrixzellen umbrochen und in mehreren Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a704-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="3a704-117">In diesem Fall kann das Indikatorsymbol gestreckt und in der Form verändert werden,</span><span class="sxs-lookup"><span data-stu-id="3a704-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="3a704-118">wodurch u. U. seine Lesbarkeit beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="3a704-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="3a704-119">Platzieren Sie den Indikator in einem Rechteck, um sicherzustellen, dass das Symbol nicht verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="3a704-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="3a704-120">So fügen Sie einer Tabelle oder einer Matrix einen Indikator hinzu</span><span class="sxs-lookup"><span data-stu-id="3a704-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="3a704-121">Öffnen Sie einen vorhandenen Bericht, oder erstellen Sie einen neuen Bericht, der eine Tabelle und eine Matrix mit den anzuzeigenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="3a704-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="3a704-122">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) oder [Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a704-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="3a704-123">Fügen Sie eine Spalte in die Tabelle oder Matrix ein.</span><span class="sxs-lookup"><span data-stu-id="3a704-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="3a704-124">Weitere Informationen finden Sie unter [Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a704-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="3a704-125">Klicken Sie optional auf der Registerkarte **Einfügen** auf **Rechteck**, und klicken Sie dann in der neuen Spalte auf eine Zelle.</span><span class="sxs-lookup"><span data-stu-id="3a704-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="3a704-126">Klicken Sie auf der Registerkarte **Einfügen** auf **Indikator**, und klicken Sie dann in der neuen Spalte auf eine Zelle.</span><span class="sxs-lookup"><span data-stu-id="3a704-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="3a704-127">Falls Sie einer Zelle ein Rechteck hinzugefügt haben, klicken Sie auf diese Zelle.</span><span class="sxs-lookup"><span data-stu-id="3a704-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="3a704-128">Klicken Sie im linken Bereich des Dialogfelds **Indikatorart auswählen** auf den gewünschten Indikatortyp und dann auf den Indikatorsatz.</span><span class="sxs-lookup"><span data-stu-id="3a704-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="3a704-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a704-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3a704-130">Klicken Sie auf den Indikator.</span><span class="sxs-lookup"><span data-stu-id="3a704-130">Click the indicator.</span></span> <span data-ttu-id="3a704-131">Der Bereich **Messgerätdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3a704-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="3a704-132">Klicken Sie im Bereich **Werte** in der Dropdownliste **(Keine Angabe)** auf das Feld, dessen Werte Sie als Indikator anzeigen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a704-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="3a704-133">Der Indikator ist so konfiguriert, dass Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a704-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="3a704-134">Standardmäßig sind Indikatoren so konfiguriert, dass Prozentsätze als Maßeinheiten verwendet werden, und die Prozentbereiche werden über die Elemente des Indikators gleichmäßig verteilt. Der vom Indikator gelieferte Wert verwendet den Bereich der nächsten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="3a704-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="3a704-135">So löschen Sie einen Indikator für eine Tabelle oder eine Matrix</span><span class="sxs-lookup"><span data-stu-id="3a704-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="3a704-136">Klicken Sie mit der rechten Maustaste auf den Indikator, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3a704-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3a704-137">Ein Indikator kann in einem Messgerätbereich positioniert sein, der andere Indikatoren oder Messgeräte enthält.</span><span class="sxs-lookup"><span data-stu-id="3a704-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="3a704-138">Wenn die Messgerätbereiche mehrere Elemente enthalten, stellen Sie sicher, dass Sie zum Löschen auf den Indikator klicken und nicht auf den Messgerätbereich.</span><span class="sxs-lookup"><span data-stu-id="3a704-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="3a704-139">Wenn Sie klicken und den Messgerätbereich entfernen, werden die Messgerätbereiche und alle Elemente darin gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3a704-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="3a704-140">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3a704-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a704-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a704-141">See Also</span></span>  
 [<span data-ttu-id="3a704-142">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a704-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
