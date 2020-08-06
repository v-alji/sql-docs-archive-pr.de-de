---
title: Erstellen und Verwalten von Perspektiven (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609499"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="f413f-102">Erstellen und Verwalten von Perspektiven (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="f413f-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="f413f-103">Eine Perspektive definiert sichtbare Teilmengen eines Modells, die fokussierte, unternehmensspezifische oder anwendungsspezifische Blickpunkte des Modells bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f413f-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="f413f-104">In den Tasks in diesem Thema wird beschrieben, wie Perspektiven mithilfe des Dialogfelds **Perspektiven** im Modell-Designer erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f413f-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="f413f-105">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="f413f-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="f413f-106">So fügen Sie eine Perspektive hinzu</span><span class="sxs-lookup"><span data-stu-id="f413f-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="f413f-107">So bearbeiten Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="f413f-108">So benennen Sie eine Perspektive um</span><span class="sxs-lookup"><span data-stu-id="f413f-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="f413f-109">So löschen Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="f413f-110">So kopieren Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="f413f-111">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f413f-111">Tasks</span></span>  
 <span data-ttu-id="f413f-112">Zum Erstellen von Perspektiven verwenden Sie das Dialogfeld **Perspektiven** , in dem Sie Perspektiven hinzufügen, bearbeiten, löschen, kopieren und anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="f413f-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="f413f-113">Um das Dialogfeld **Perspektiven** anzuzeigen, klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf das Menü **Modell** und dann auf **Perspektiven**.</span><span class="sxs-lookup"><span data-stu-id="f413f-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="f413f-114">So fügen Sie eine Perspektive hinzu</span><span class="sxs-lookup"><span data-stu-id="f413f-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="f413f-115">Zum Hinzufügen einer neuen Perspektive klicken Sie auf **Neue Perspektive**.</span><span class="sxs-lookup"><span data-stu-id="f413f-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="f413f-116">Anschließend können Sie die einzufügenden Feldobjekte aktivieren und deaktivieren und einen Namen für die neue Perspektive angeben.</span><span class="sxs-lookup"><span data-stu-id="f413f-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="f413f-117">Wenn Sie eine leere Perspektive erstellen, die alle Felder mit Feldobjekten enthält, wird dem Benutzer, der diese Perspektive verwendet, eine leere Feldliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f413f-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="f413f-118">Perspektiven sollten mindestens eine Tabelle und eine Spalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="f413f-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a><span data-ttu-id="f413f-119">So bearbeiten Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="f413f-120">Zum Ändern einer Perspektive aktivieren und deaktivieren Sie Felder in der Spalte der Perspektive, wodurch Feld Objekte der Perspektive hinzugefügt bzw. daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f413f-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="f413f-121">So benennen Sie eine Perspektive um</span><span class="sxs-lookup"><span data-stu-id="f413f-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="f413f-122">Wenn Sie mit dem Mauszeiger auf die Spaltenüberschrift einer Perspektive (den Namen der Perspektive) zeigen, wird die Schaltfläche **Umbenennen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f413f-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="f413f-123">Klicken Sie auf **Umbenennen**, um die Perspektive umzubenennen. Geben Sie dann einen neuen Namen ein, oder bearbeiten Sie den vorhandenen Namen.</span><span class="sxs-lookup"><span data-stu-id="f413f-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="f413f-124">So löschen Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="f413f-125">Wenn Sie mit dem Mauszeiger auf die Spaltenüberschrift einer Perspektive (den Namen der Perspektive) zeigen, wird die Schaltfläche **Löschen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f413f-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="f413f-126">Klicken Sie zum Löschen der Perspektive auf die Schaltfläche **Löschen** , und klicken Sie im Bestätigungsfenster auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="f413f-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a><span data-ttu-id="f413f-127">So kopieren Sie eine Perspektive</span><span class="sxs-lookup"><span data-stu-id="f413f-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="f413f-128">Wenn Sie mit dem Mauszeiger auf die Spaltenüberschrift einer Perspektive zeigen, wird die Schaltfläche **Kopieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f413f-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="f413f-129">Klicken Sie auf die Schaltfläche **Kopieren** , um eine Kopie dieser Perspektive zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f413f-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="f413f-130">Rechts neben den vorhandenen Perspektiven wird eine Kopie der ausgewählten Perspektive als neue Perspektive hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f413f-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="f413f-131">Die neue Perspektive erbt den Namen der kopierten Perspektive, und an das Ende des Namens wird die Anmerkung *-Kopieren* angefügt.</span><span class="sxs-lookup"><span data-stu-id="f413f-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="f413f-132">Wenn beispielsweise eine Kopie der *Sales* -Perspektive erstellt wird, wird die neue Perspektive als *Sales-Copy*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f413f-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f413f-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f413f-133">See Also</span></span>  
 <span data-ttu-id="f413f-134">[Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f413f-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f413f-135">Hierarchien &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="f413f-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
