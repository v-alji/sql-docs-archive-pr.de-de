---
title: Hinzufügen von Sparklines und Datenbalken (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609655"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="89a7f-102">Hinzufügen von Sparklines und Datenbalken (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="89a7f-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="89a7f-103">Sparklines und Datenbalken sind kleine, zusätzliche Diagramme, die viele Information mit wenig relevanten Details vermitteln.</span><span class="sxs-lookup"><span data-stu-id="89a7f-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="89a7f-104">Weitere Informationen dazu finden Sie unter [Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89a7f-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="89a7f-105">Sparklines und Datenbalken werden meist in die Zellen einer Tabelle oder Matrix eingefügt.</span><span class="sxs-lookup"><span data-stu-id="89a7f-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="89a7f-106">Sparklines zeigen normalerweise jeweils nur eine Reihe an.</span><span class="sxs-lookup"><span data-stu-id="89a7f-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="89a7f-107">Datenbalken können einen oder mehrere Datenpunkte enthalten.</span><span class="sxs-lookup"><span data-stu-id="89a7f-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="89a7f-108">Sowohl Sparklines als auch Datenbalken gewinnen dadurch an Bedeutung, dass sie die Reiheninformationen für jede Zeile in der Tabelle oder der Matrix wiederholen.</span><span class="sxs-lookup"><span data-stu-id="89a7f-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="89a7f-109">So fügen Sie einer Sparkline oder einem Datenbalken eine Tabelle oder Matrix hinzu</span><span class="sxs-lookup"><span data-stu-id="89a7f-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="89a7f-110">Erstellen Sie eine Tabelle oder eine Matrix mit den Daten, die angezeigt werden sollen, falls Sie dies nicht bereits getan haben.</span><span class="sxs-lookup"><span data-stu-id="89a7f-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="89a7f-111">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) oder [Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89a7f-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="89a7f-112">Fügen Sie eine Spalte in die Tabelle oder Matrix ein.</span><span class="sxs-lookup"><span data-stu-id="89a7f-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="89a7f-113">Weitere Informationen finden Sie unter [Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89a7f-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="89a7f-114">Klicken Sie auf der Registerkarte **Einfügen** auf **Sparkline** oder **Datenbalken**, und klicken Sie dann in eine Zelle in der neuen Spalte.</span><span class="sxs-lookup"><span data-stu-id="89a7f-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89a7f-115">Sie können Sparklines nicht in die Detailgruppe in einer Tabelle einfügen.</span><span class="sxs-lookup"><span data-stu-id="89a7f-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="89a7f-116">Sie müssen in eine Zelle eingefügt werden, die einer Gruppe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="89a7f-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="89a7f-117">Klicken Sie im Dialogfeld **Sparkline-/Datenleistentyp ändern** auf die gewünschte Sparkline- oder Datenbalkenart und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="89a7f-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="89a7f-118">Klicken Sie auf die Sparkline oder den Datenbalken.</span><span class="sxs-lookup"><span data-stu-id="89a7f-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="89a7f-119">Der Bereich **Diagrammdaten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="89a7f-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="89a7f-120">Klicken Sie im Bereich **Werte** auf das Pluszeichen ( **) bei** Felder hinzufügen**+** und anschließend auf das Feld, dessen Werte Sie als Diagramm darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="89a7f-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="89a7f-121">Klicken Sie im Bereich **Kategoriegruppen** auf das Pluszeichen ( **) bei** Felder hinzufügen**+** und anschließend auf das Feld, nach dessen Werten Sie gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="89a7f-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="89a7f-122">In der Regel fügen Sie bei Sparklines und Datenbalken dem Bereich **Reihengruppe** kein Feld hinzu, da Sie nur eine Reihe für jede Zeile möchten.</span><span class="sxs-lookup"><span data-stu-id="89a7f-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a7f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89a7f-123">See Also</span></span>  
 <span data-ttu-id="89a7f-124">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89a7f-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="89a7f-125">Ausrichten von Diagrammdaten in einer Tabelle oder einer Matrix &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="89a7f-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
