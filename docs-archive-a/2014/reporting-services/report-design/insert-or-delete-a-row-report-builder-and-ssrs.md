---
title: Einfügen oder Löschen einer Zeile (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723425"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="18585-102">Einfügen oder Löschen einer Zeile (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="18585-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="18585-103">Sie können Zeilen zu einem Tablix-Datenbereich hinzufügen bzw. daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="18585-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="18585-104">Der Tablix-Datenbereich kann eine Tabelle, eine Matrix oder eine Liste sein.</span><span class="sxs-lookup"><span data-stu-id="18585-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="18585-105">Die folgenden Vorgehensweisen gelten nicht für Diagramm- und Messgerätdatenbereiche.</span><span class="sxs-lookup"><span data-stu-id="18585-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="18585-106">In Tablix-Datenbereichen können Zeilen hinzugefügt werden, die mit einer Gruppe verknüpft sind (innerhalb einer Gruppe) oder die nicht mit einer Gruppe verknüpft sind (außerhalb einer Gruppe).</span><span class="sxs-lookup"><span data-stu-id="18585-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="18585-107">Eine Zeile in einer Gruppe wiederholt sich einmal pro eindeutigem Gruppenwert.</span><span class="sxs-lookup"><span data-stu-id="18585-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="18585-108">So wiederholt sich zum Beispiel eine Zeile in einer Gruppe, die auf dem Wert in einer Datenspalte mit Farbnamen basiert, einmal pro eindeutigem Farbnamen.</span><span class="sxs-lookup"><span data-stu-id="18585-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="18585-109">Bei geschachtelten Gruppen kann sich die Zeile außerhalb der untergeordneten Gruppe, aber innerhalb der übergeordneten Gruppe befinden.</span><span class="sxs-lookup"><span data-stu-id="18585-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="18585-110">In diesem Fall wiederholt sich die Zeile einmal für jeden eindeutigen Wert in der übergeordneten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="18585-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="18585-111">So wählen Sie einen Datenbereich aus und zeigen die Zeilen- und Spaltenziehpunkte an</span><span class="sxs-lookup"><span data-stu-id="18585-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="18585-112">Klicken Sie in der Entwurfsansicht auf die obere linke Ecke des Tablix-Datenbereichs, sodass die Spalten- und Zeilenziehpunkte über und neben dem Datenbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="18585-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="18585-113">Weitere Informationen zu Datenbereichs Bereichen finden Sie unter [Listen &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="18585-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="18585-114">So fügen Sie eine Zeile in einen ausgewählten Datenbereich ein</span><span class="sxs-lookup"><span data-stu-id="18585-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="18585-115">Klicken Sie mit der rechten Maustaste an der Stelle, an der Sie eine Zeile einfügen möchten, auf einen Zeilenziehpunkt, klicken Sie auf **Zeile einfügen**und dann auf **Oberhalb** bzw. **Unterhalb**.</span><span class="sxs-lookup"><span data-stu-id="18585-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="18585-116">\- oder –</span><span class="sxs-lookup"><span data-stu-id="18585-116">\- or -</span></span>  
  
-   <span data-ttu-id="18585-117">Klicken Sie mit der rechten Maustaste auf eine Zelle in dem Datenbereich, in dem Sie eine Zeile einfügen möchten, klicken Sie auf **Zeile einfügen**und dann auf **Oberhalb** bzw. **Unterhalb**.</span><span class="sxs-lookup"><span data-stu-id="18585-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="18585-118">So löschen Sie eine Zeile aus einem ausgewählten Datenbereich</span><span class="sxs-lookup"><span data-stu-id="18585-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="18585-119">Wählen Sie die Zeile oder Zeilen aus, die Sie löschen möchten, klicken Sie mit der rechten Maustaste auf den Ziehpunkt einer der ausgewählten Zeilen, und klicken Sie dann auf **Zeilen löschen**.</span><span class="sxs-lookup"><span data-stu-id="18585-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="18585-120">\- oder –</span><span class="sxs-lookup"><span data-stu-id="18585-120">\- or -</span></span>  
  
-   <span data-ttu-id="18585-121">Klicken Sie mit der rechten Maustaste auf eine Zelle in dem Datenbereich, in dem Sie eine Zeile löschen möchten, und klicken Sie dann auf **Zeilen löschen**.</span><span class="sxs-lookup"><span data-stu-id="18585-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="18585-122">So fügen Sie eine Zeile in eine Gruppe in einem ausgewählten Datenbereich ein</span><span class="sxs-lookup"><span data-stu-id="18585-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="18585-123">Klicken Sie mit der rechten Maustaste auf eine Zeilengruppenzelle im Zeilengruppenbereich eines Tablix-Datenbereichs, in dem Sie eine Zeile einfügen möchten, klicken Sie auf **Zeile einfügen**und dann auf **Oberhalb - Außerhalb von Gruppe**, **Oberhalb - Innerhalb von Gruppe**, **Unterhalb - Innerhalb von Gruppe**oder **Unterhalb - Außerhalb von Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="18585-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="18585-124">Die Zeile wird entweder innerhalb oder außerhalb der Gruppe eingefügt, die durch die Zeilengruppenzelle, auf die Sie geklickt haben, repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="18585-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="18585-125">So löschen Sie eine Zeile aus einer Gruppe in einem ausgewählten Datenbereich</span><span class="sxs-lookup"><span data-stu-id="18585-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="18585-126">Klicken Sie mit der rechten Maustaste auf eine Zeilengruppenzelle im Zeilengruppenbereich eines Tablix-Datenbereichs, aus dem Sie eine Zeile löschen möchten, und klicken Sie dann auf **Zeilen löschen**.</span><span class="sxs-lookup"><span data-stu-id="18585-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18585-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18585-127">See Also</span></span>  
 <span data-ttu-id="18585-128">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18585-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18585-129">[Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18585-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18585-130">[Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18585-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18585-131">[Matrizen (Berichts-Generator und SSRS)](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18585-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18585-132">[Listen (Berichts-Generator und SSRS)](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18585-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="18585-133">Listen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="18585-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
