---
title: Erstellen einer rekursiven Hierarchiegruppe (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616431"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="5b2fc-102">Erstellen einer rekursiven Hierarchiegruppe (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="5b2fc-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5b2fc-103">Eine rekursive Hierarchiegruppe organisiert Daten aus einem Berichtsdataset, das mehrere hierarchische Ebenen aufweist, zum Beispiel eine Berichtsstruktur für die Beziehung zwischen Managern und Mitarbeitern in der Hierarchie einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="5b2fc-104">Bevor Sie Daten in einer Tabelle als rekursive Hierarchiegruppe organisieren können, müssen Sie ein Dataset erstellen, das alle hierarchischen Daten enthält. Sie benötigen separate Felder für das zu gruppierende Element und das Element, nach dem gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="5b2fc-105">Ein Dataset, in dem Sie Mitarbeiter rekursiv unter dem Manager gruppieren möchten, kann z. B. einen Namen, einen Mitarbeiternamen, eine Mitarbeiter-ID und eine Manager-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="5b2fc-106">So erstellen Sie eine rekursive Hierarchiegruppe</span><span class="sxs-lookup"><span data-stu-id="5b2fc-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="5b2fc-107">Fügen Sie in der Entwurfsansicht eine Tabelle hinzu, und ziehen Sie die anzuzeigenden Datasetfelder in die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="5b2fc-108">Normalerweise ist das Feld, das Sie als Hierarchie anzeigen möchten, in der ersten Spalte angeordnet.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="5b2fc-109">Klicken Sie mit der rechten Maustaste in der Tabelle an einer beliebigen Stelle, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="5b2fc-110">Im Bereich Gruppierung wird die Detailgruppe für die gewählte Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="5b2fc-111">Klicken Sie im Bereich „Zeilengruppen“ mit der rechten Maustaste auf **Details**, und klicken Sie anschließend auf **Gruppe bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="5b2fc-112">Das Dialogfeld **Gruppeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5b2fc-113">Klicken Sie unter **Gruppierungsausdrücke**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="5b2fc-114">Im Raster wird eine neue Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="5b2fc-115">Wählen Sie in der Liste **Gruppieren nach** das zu gruppierende Feld aus, oder geben Sie es ein.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="5b2fc-116">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="5b2fc-117">Wählen Sie in der Liste **Rekursives übergeordnetes Element** das Feld aus, nach dem gruppiert werden soll, oder geben Sie es ein.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="5b2fc-118">Führen Sie den Bericht aus.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-118">Run the report.</span></span> <span data-ttu-id="5b2fc-119">Im Bericht wird die rekursive Hierarchiegruppe angezeigt. Die Anzeige erfolgt jedoch ohne einen Einzug, der die Hierarchie verdeutlichen würde.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="5b2fc-120">So formatieren Sie eine rekursive Hierarchiegruppe mit Einzugsebenen</span><span class="sxs-lookup"><span data-stu-id="5b2fc-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="5b2fc-121">Klicken Sie auf das Textfeld mit dem Feld, dem Sie Einzugsebenen hinzufügen möchten, um ein Hierarchieformat anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="5b2fc-122">Die Eigenschaften für das Textfeld werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b2fc-123">Wenn der Bereich Eigenschaften geschlossen ist, klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="5b2fc-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="5b2fc-124">Erweitern Sie im Bereich Eigenschaften den `Padding` Knoten, klicken Sie auf **Links**, und wählen Sie in der Dropdown Liste den Eintrag aus **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="5b2fc-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="5b2fc-125">Geben Sie im Ausdruckfenster den folgenden Ausdruck ein:</span><span class="sxs-lookup"><span data-stu-id="5b2fc-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="5b2fc-126">Die Auffüllung-Eigenschaften erfordern alle eine Zeichenfolge im Format *nnyy*. Dabei steht *nn* für eine Zahl und *yy* für die Maßeinheit.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="5b2fc-127">Im obigen Beispielausdruck wird eine Zeichenfolge generiert, bei der die Auffüllung mithilfe der `Level`-Funktion basierend auf der Rekursionsebene vergrößert wird.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="5b2fc-128">Eine Zeile mit der Ebene 1 hätte z.B. die Auffüllung (2 + (1\*10))=12pt, und eine Zeile mit der Ebene 3 hätte die Auffüllung (2 + (3\*10))=32pt.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="5b2fc-129">Weitere Informationen zur- `Level` Funktion finden Sie unter [Ebene](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="5b2fc-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="5b2fc-130">Führen Sie den Bericht aus.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-130">Run the report.</span></span> <span data-ttu-id="5b2fc-131">Der Bericht zeigt eine hierarchische Ansicht der gruppierten Daten an.</span><span class="sxs-lookup"><span data-stu-id="5b2fc-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b2fc-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b2fc-132">See Also</span></span>  
 <span data-ttu-id="5b2fc-133">[Erstellen von rekursiven Hierarchiegruppen &#40;Berichts-Generator und SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5b2fc-134">[Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5b2fc-135">[Aggregatfunktionsreferenz &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="5b2fc-136">[Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5b2fc-137">[Matrizen (Berichts-Generator und SSRS)](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5b2fc-138">[Listen (Berichts-Generator und SSRS)](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b2fc-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5b2fc-139">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5b2fc-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
