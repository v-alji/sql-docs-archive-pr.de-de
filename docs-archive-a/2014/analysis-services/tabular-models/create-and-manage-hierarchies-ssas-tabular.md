---
title: Erstellen und Verwalten von Hierarchien (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616212"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="ae62f-102">Erstellen und Verwalten von Hierarchien (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="ae62f-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="ae62f-103">Hierarchien können in der Diagrammsicht des Modell-Designers erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ae62f-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="ae62f-104">Um den Modell-Designer in der Diagrammsicht in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]anzuzeigen, klicken Sie auf das Menü **Modell** , zeigen Sie dann auf **Modellansicht**, und klicken Sie dann auf **Diagrammsicht**.</span><span class="sxs-lookup"><span data-stu-id="ae62f-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="ae62f-105">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="ae62f-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="ae62f-106">Erstellen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="ae62f-107">Bearbeiten einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="ae62f-108">Löschen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="ae62f-109">Erstellen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="ae62f-110">Sie können eine Hierarchie mithilfe der Kontextmenüs für Spalten und Tabellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae62f-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="ae62f-111">Wenn Sie eine Hierarchie erstellen, wird eine neue übergeordnete Ebene mit den ausgewählten Spalten als untergeordnete Ebenen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae62f-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="ae62f-112">So erstellen Sie eine Hierarchie über das Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="ae62f-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="ae62f-113">Klicken Sie im Modell-Designer (Diagrammsicht) in einem Tabellenfenster mit der rechten Maustaste auf eine Spalte, und klicken Sie dann auf **Hierarchie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ae62f-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="ae62f-114">Um mehrere Spalten auszuwählen, klicken Sie auf jede Spalte, klicken Sie dann mit der rechten Maustaste, um das Kontextmenü zu öffnen, und klicken Sie dann auf **Hierarchie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ae62f-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="ae62f-115">Im unteren Bereich des Tabellenfensters wird eine übergeordnete Hierarchieebene erstellt, und die ausgewählten Spalten werden als untergeordnete Ebenen unter die Hierarchie kopiert.</span><span class="sxs-lookup"><span data-stu-id="ae62f-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="ae62f-116">Geben Sie einen Namen für die Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="ae62f-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="ae62f-117">Sie können zusätzliche Spalten in die übergeordnete Ebene der Hierarchie ziehen, wodurch die Spalten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="ae62f-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="ae62f-118">Legen Sie die untergeordnete Ebene an der Stelle ab, an der sie in der Hierarchie angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae62f-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae62f-119">Wenn Sie ein Measure zusammen mit mindestens einer Spalte auswählen oder Spalten aus mehreren Tabellen auswählen, ist der Befehl Hierarchie erstellen im Kontextmenü deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae62f-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="ae62f-120">Bearbeiten einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="ae62f-121">Sie können eine Hierarchie und eine untergeordnete Ebene umbenennen, die Reihenfolge der untergeordneten Ebenen ändern, zusätzliche Spalten als untergeordnete Ebenen hinzufügen, eine untergeordnete Ebene aus einer Hierarchie entfernen, den Quellnamen einer untergeordneten Ebene (Spaltennamen) anzeigen und eine untergeordnete Ebene ausblenden, wenn sie über den gleichen Namen verfügt wie die übergeordnete Hierarchieebene.</span><span class="sxs-lookup"><span data-stu-id="ae62f-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="ae62f-122">So ändern Sie den Namen einer Hierarchie oder untergeordneten Ebene</span><span class="sxs-lookup"><span data-stu-id="ae62f-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="ae62f-123">Klicken Sie mit der rechten Maustaste auf die übergeordnete Hierarchieebene oder eine untergeordnete Ebene, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="ae62f-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="ae62f-124">Geben Sie einen neuen Namen ein, oder bearbeiten Sie den vorhandenen Namen.</span><span class="sxs-lookup"><span data-stu-id="ae62f-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="ae62f-125">So ändern Sie die Reihenfolge einer untergeordneten Ebene in einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="ae62f-126">Klicken Sie auf eine untergeordnete Ebene, und ziehen Sie sie auf eine neue Position in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="ae62f-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="ae62f-127">Alternativ können Sie mit der rechten Maustaste auf eine untergeordnete Ebene der Hierarchie klicken und dann auf Nach oben klicken, um die Ebene in der Liste nach oben zu verschieben, oder klicken Sie auf Nach unten, um die Ebene in der Liste nach unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ae62f-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="ae62f-128">Oder klicken Sie auf eine untergeordnete Ebene, um sie auszuwählen, und drücken Sie dann ALT+NACH-OBEN, um die Ebene nach oben zu verschieben, oder drücken Sie ALT+NACH-UNTEN, um die Ebene in der Liste nach unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ae62f-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="ae62f-129">So fügen Sie einer Hierarchie eine weitere untergeordnete Ebene hinzu</span><span class="sxs-lookup"><span data-stu-id="ae62f-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="ae62f-130">Klicken Sie auf eine Spalte, und ziehen Sie sie auf die übergeordnete Ebene oder auf eine bestimmte Position in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="ae62f-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="ae62f-131">Die Spalte wird als untergeordnete Ebene der Hierarchie kopiert.</span><span class="sxs-lookup"><span data-stu-id="ae62f-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="ae62f-132">Oder klicken Sie mit der rechten Maustaste auf eine Spalte, zeigen Sie auf **Zur Hierarchie hinzufügen**, und klicken Sie dann auf die Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="ae62f-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae62f-133">Sie können der Hierarchie eine (in Berichten ausgeblendete) Spalte als untergeordnete Ebene hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae62f-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="ae62f-134">Die untergeordnete Ebene wird nicht ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="ae62f-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="ae62f-135">So entfernen Sie eine untergeordnete Ebene aus einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="ae62f-136">Klicken Sie mit der rechten Maustaste auf eine untergeordnete Ebene, und klicken Sie dann auf **Aus Hierarchie entfernen**.</span><span class="sxs-lookup"><span data-stu-id="ae62f-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="ae62f-137">Sie können auch auf eine untergeordnete Ebene klicken und dann **ENTF**drücken.</span><span class="sxs-lookup"><span data-stu-id="ae62f-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae62f-138">Wenn Sie eine untergeordnete Hierarchieebene umbenennen, hat sie nicht mehr den gleichen Namen wie die Spalte, von der sie kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae62f-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="ae62f-139">Verwenden Sie den Befehl **Quellspaltennamen einblenden** , um die Spalte anzuzeigen, von der sie kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae62f-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="ae62f-140">So zeigen Sie einen Quellnamen an</span><span class="sxs-lookup"><span data-stu-id="ae62f-140">To show a source name</span></span>  
  
-   <span data-ttu-id="ae62f-141">Klicken Sie mit der rechten Maustaste auf eine untergeordnete Ebene in der Hierarchie, und klicken Sie dann auf **Quellspaltennamen**einblenden.</span><span class="sxs-lookup"><span data-stu-id="ae62f-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="ae62f-142">Der Name der Spalte, von der die Spalte kopiert wurde, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae62f-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a><span data-ttu-id="ae62f-143">Löschen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="ae62f-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="ae62f-144">So löschen Sie eine Hierarchie und entfernen deren untergeordnete Ebenen</span><span class="sxs-lookup"><span data-stu-id="ae62f-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="ae62f-145">Klicken Sie mit der rechten Maustaste auf die übergeordnete Hierarchieebene, und klicken Sie dann auf Hierarchie löschen.</span><span class="sxs-lookup"><span data-stu-id="ae62f-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="ae62f-146">Klicken Sie auf die übergeordnete Hierarchieebene, und drücken Sie dann ENTF.</span><span class="sxs-lookup"><span data-stu-id="ae62f-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="ae62f-147">Dadurch werden auch alle untergeordneten Ebenen entfernt.</span><span class="sxs-lookup"><span data-stu-id="ae62f-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae62f-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae62f-148">See Also</span></span>  
 <span data-ttu-id="ae62f-149">[Tabellen Modell-Designer &#40;tabellarischen SSAS-&#41;](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ae62f-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="ae62f-150">[Hierarchien &#40;tabellarischen SSAS-&#41;](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ae62f-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ae62f-151">Measures &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="ae62f-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
