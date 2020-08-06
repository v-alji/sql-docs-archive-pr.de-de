---
title: Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723430"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="95db9-102">Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="95db9-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="95db9-103">Sie können Spalten zu einem Tablix-Datenbereich hinzufügen bzw. daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="95db9-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="95db9-104">Der Tablix-Datenbereich kann eine Tabelle, eine Matrix oder eine Liste sein.</span><span class="sxs-lookup"><span data-stu-id="95db9-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="95db9-105">Die folgenden Vorgehensweisen gelten nicht für Diagramm- und Messgerätdatenbereiche.</span><span class="sxs-lookup"><span data-stu-id="95db9-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="95db9-106">In Tablix-Datenbereichen können Spalten hinzugefügt werden, die mit einer Gruppe verknüpft sind (innerhalb einer Gruppe) oder die nicht mit einer Gruppe verknüpft sind (außerhalb einer Gruppe).</span><span class="sxs-lookup"><span data-stu-id="95db9-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="95db9-107">Eine Spalte in einer Gruppe wiederholt sich einmal pro eindeutigem Gruppenwert.</span><span class="sxs-lookup"><span data-stu-id="95db9-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="95db9-108">So wiederholt sich zum Beispiel eine Spalte in einer Gruppe, die auf dem Wert in einer Datenspalte mit Farbnamen basiert, einmal pro eindeutigem Farbnamen.</span><span class="sxs-lookup"><span data-stu-id="95db9-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="95db9-109">Bei geschachtelten Gruppen kann sich die Spalte außerhalb der untergeordneten Gruppe, aber innerhalb der übergeordneten Gruppe befinden.</span><span class="sxs-lookup"><span data-stu-id="95db9-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="95db9-110">In diesem Fall wiederholt sich die Zeile einmal für jeden eindeutigen Wert in der übergeordneten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="95db9-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="95db9-111">So wählen Sie einen Datenbereich aus und zeigen die Zeilen- und Spaltenziehpunkte an</span><span class="sxs-lookup"><span data-stu-id="95db9-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="95db9-112">Klicken Sie in der Entwurfsansicht auf die obere linke Ecke des Tablix-Datenbereichs, sodass die Spalten- und Zeilenziehpunkte über und neben dem Datenbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="95db9-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="95db9-113">Weitere Informationen zu Datenbereichs Bereichen finden Sie unter [Listen &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="95db9-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="95db9-114">So fügen Sie eine Spalte in einen ausgewählten Datenbereich ein</span><span class="sxs-lookup"><span data-stu-id="95db9-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="95db9-115">Klicken Sie mit der rechten Maustaste auf einen Spaltenziehpunkt an der Stelle, an der Sie eine Spalte einfügen möchten. Klicken Sie auf **Spalte einfügen**und dann auf **Links** bzw. **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="95db9-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="95db9-116">– oder –</span><span class="sxs-lookup"><span data-stu-id="95db9-116">-- or --</span></span>  
  
-   <span data-ttu-id="95db9-117">Klicken Sie mit der rechten Maustaste auf eine Zelle in dem Datenbereich, in dem Sie eine Spalte einfügen möchten. Klicken Sie auf **Spalte einfügen**und dann auf **Links** bzw. **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="95db9-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="95db9-118">So löschen Sie eine Spalte aus einem ausgewählten Datenbereich</span><span class="sxs-lookup"><span data-stu-id="95db9-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="95db9-119">Wählen Sie die Spalten aus, die Sie löschen möchten, klicken Sie mit der rechten Maustaste auf den Ziehpunkt für eine der ausgewählten Spalten, und klicken Sie dann auf **Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="95db9-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="95db9-120">– oder –</span><span class="sxs-lookup"><span data-stu-id="95db9-120">-- or --</span></span>  
  
-   <span data-ttu-id="95db9-121">Klicken Sie mit der rechten Maustaste auf eine Zelle in dem Datenbereich, in dem Sie eine Spalte löschen möchten, und klicken Sie dann auf **Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="95db9-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="95db9-122">So fügen Sie eine Spalte in eine Gruppe in einem ausgewählten Datenbereich ein</span><span class="sxs-lookup"><span data-stu-id="95db9-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="95db9-123">Klicken Sie mit der rechten Maustaste auf eine Spaltengruppenzelle im Spaltengruppenbereich eines Tablix-Datenbereichs, in dem Sie eine Spalte einfügen möchten, klicken Sie auf **Spalte einfügen**, und klicken Sie dann auf **Links - Außerhalb von Gruppe**, **Links - Innerhalb von Gruppe**, **Rechts - Innerhalb von Gruppe**oder **Rechts - Außerhalb von Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="95db9-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="95db9-124">Die Spalte wird entweder innerhalb oder außerhalb der Gruppe eingefügt, die durch die Spaltengruppenzelle, auf die Sie geklickt haben, repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="95db9-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="95db9-125">So löschen Sie eine Spalte aus einer Gruppe in einem ausgewählten Datenbereich</span><span class="sxs-lookup"><span data-stu-id="95db9-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="95db9-126">Klicken Sie mit der rechten Maustaste auf eine Spaltengruppenzelle im Spaltengruppenbereich eines Tablix-Datenbereichs, aus dem Sie eine Spalte löschen möchten, und klicken Sie dann auf **Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="95db9-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95db9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95db9-127">See Also</span></span>  
 <span data-ttu-id="95db9-128">[Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95db9-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95db9-129">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95db9-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95db9-130">[Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95db9-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95db9-131">[Matrizen (Berichts-Generator und SSRS)](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95db9-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95db9-132">[Listen (Berichts-Generator und SSRS)](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95db9-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="95db9-133">Listen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="95db9-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
