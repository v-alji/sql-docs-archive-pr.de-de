---
title: Löschen von Beziehungen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696205"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="443b2-102">Löschen von Beziehungen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="443b2-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="443b2-103">Sie können vorhandene Beziehungen in der Diagrammsicht des Modell-Designers oder über das Dialogfeld Beziehungen verwalten löschen.</span><span class="sxs-lookup"><span data-stu-id="443b2-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="443b2-104">Weitere Informationen darüber, wie Beziehungen in tabellarischen Modellen verwendet werden, finden Sie unter [Beziehungen &#40;SSAS – tabellarisch&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="443b2-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="443b2-105">Überlegungen für das Löschen von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="443b2-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="443b2-106">Berücksichtigen Sie vor dem Löschen einer Beziehung die folgenden Aspekte:</span><span class="sxs-lookup"><span data-stu-id="443b2-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="443b2-107">Es gibt keine Möglichkeit, das Löschen einer Beziehung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="443b2-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="443b2-108">Sie können die Beziehung neu erstellen, diese Aktion erfordert jedoch eine vollständige Neuberechnung der Formeln im Modell.</span><span class="sxs-lookup"><span data-stu-id="443b2-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="443b2-109">Führen Sie daher immer zuerst eine Überprüfung durch, bevor Sie eine Beziehung löschen, die in Formeln verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="443b2-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="443b2-110">Wenn Sie eine Beziehung zwischen zwei Tabellen löschen, kann dies Fehler in Formeln verursachen, die auf diese Tabellen verweisen.</span><span class="sxs-lookup"><span data-stu-id="443b2-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="443b2-111">Die Data Analysis Expression (DAX)-Funktion RELATED sucht anhand der Beziehungen zwischen Tabellen nach verknüpften Werten in anderen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="443b2-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="443b2-112">Die Funktion gibt andere Ergebnisse zurück, nachdem die Beziehung gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="443b2-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="443b2-113">Weitere Informationen finden Sie im Thema zur RELATED-Funktion (DAX).</span><span class="sxs-lookup"><span data-stu-id="443b2-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="443b2-114">Das Erstellen und Löschen von Beziehungen ändert nicht nur die PivotTable und die Formelergebnisse, sondern führt auch dazu, dass die Arbeitsmappe neu berechnet wird. Dies kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="443b2-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="443b2-115">Löschen von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="443b2-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="443b2-116">So löschen Sie eine Beziehung mithilfe der Diagrammsicht</span><span class="sxs-lookup"><span data-stu-id="443b2-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="443b2-117">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf das Menü **Modell** , zeigen Sie auf **Modellansicht**, und klicken Sie dann auf **Diagrammsicht**.</span><span class="sxs-lookup"><span data-stu-id="443b2-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="443b2-118">Klicken Sie mit der rechten Maustaste zwischen zwei Tabellen auf eine Beziehungslinie, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="443b2-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="443b2-119">So löschen Sie eine Beziehung über das Dialogfeld "Beziehungen verwalten"</span><span class="sxs-lookup"><span data-stu-id="443b2-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="443b2-120">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]im Menü **Tabelle** auf **Beziehungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="443b2-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="443b2-121">Wählen Sie im Dialogfeld **Beziehungen verwalten** mindestens eine Beziehung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="443b2-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="443b2-122">Um mehrere Beziehungen auszuwählen, halten Sie die STRG-TASTE gedrückt, während Sie auf die einzelnen Beziehungen klicken.</span><span class="sxs-lookup"><span data-stu-id="443b2-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="443b2-123">Klicken Sie auf **Beziehung löschen**.</span><span class="sxs-lookup"><span data-stu-id="443b2-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="443b2-124">Klicken Sie im Dialogfeld **Beziehungen verwalten** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="443b2-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="443b2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="443b2-125">See Also</span></span>  
 <span data-ttu-id="443b2-126">[Beziehungen &#40;tabellarischen SSAS-&#41;](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="443b2-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="443b2-127">Erstellen einer Beziehung zwischen zwei Tabellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="443b2-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
