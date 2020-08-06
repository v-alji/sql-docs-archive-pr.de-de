---
title: Hinzufügen einer Detailgruppe (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617771"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="2900f-102">Hinzufügen einer Detailgruppe (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="2900f-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2900f-103">Die Detaildaten aus einem Berichtsdataset werden als Gruppe ohne Gruppierungsausdruck angegeben.</span><span class="sxs-lookup"><span data-stu-id="2900f-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="2900f-104">Fügen Sie einem Tablix-Datenbereich eine Detailgruppe hinzu, wenn die Detaildaten für eine Matrix angezeigt, wenn aus einer Tabelle bzw. Liste gelöschte Detaildaten wieder hinzugefügt oder wenn zusätzliche Detailgruppen hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2900f-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="2900f-105">Weitere Informationen zu Gruppen finden Sie unter [Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2900f-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="2900f-106">So fügen Sie einem Tablix-Datenbereich eine Detailgruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="2900f-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="2900f-107">Klicken Sie auf der Entwurfsoberfläche auf eine beliebige Stelle im Tablix-Datenbereich, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2900f-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="2900f-108">Im Bereich Gruppierung werden die Zeilengruppen und Spaltengruppen für den derzeit ausgewählten Tablix-Datenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2900f-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="2900f-109">Klicken Sie im Bereich „Gruppierung“ mit der rechten Maustaste auf eine Gruppe, die die innerste untergeordnete Gruppe darstellt.</span><span class="sxs-lookup"><span data-stu-id="2900f-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="2900f-110">Klicken Sie auf **Gruppe hinzufügen**und dann auf **Untergeordnete Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="2900f-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="2900f-111">Das Dialogfeld **Tablix-Gruppe** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2900f-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2900f-112">Geben Sie in **Gruppierungsausdruck**keinen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="2900f-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="2900f-113">Eine Detailgruppe verfügt über keinen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2900f-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="2900f-114">Wählen Sie **Detaildaten anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="2900f-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="2900f-115">Im Bereich Gruppierung wird eine neue Detailgruppe als untergeordnete Gruppe hinzugefügt, und vom Zeilenhandle für die in Schritt 1 ausgewählte Gruppe wird das Symbol für die Detailgruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2900f-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="2900f-116">Weitere Informationen zu Handles finden Sie unter [Zellen, Zeilen und Spalten des Tablix-Datenbereichs (Berichts-Generator und SSRS)](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2900f-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2900f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2900f-117">See Also</span></span>  
 <span data-ttu-id="2900f-118">[Hinzufügen oder Löschen einer Gruppe in einem Datenbereich &#40;Berichts-Generator und SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2900f-119">[Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2900f-120">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2900f-121">[Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2900f-122">[Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2900f-123">[Listet &#40;Berichts-Generator und SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2900f-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2900f-124">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2900f-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
