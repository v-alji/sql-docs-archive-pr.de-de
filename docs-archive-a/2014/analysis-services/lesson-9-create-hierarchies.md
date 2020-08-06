---
title: 'Lektion 10: Erstellen von Hierarchien | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700449"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="aa055-102">Lektion 10: Erstellen von Hierarchien</span><span class="sxs-lookup"><span data-stu-id="aa055-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="aa055-103">In dieser Lektion erstellen Sie Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="aa055-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="aa055-104">Hierarchien sind Gruppen von Spalten, die in Ebenen angeordnet werden. Beispielsweise könnte eine Geografiehierarchie Unterebenen für Land, Status, Landkreis und Stadt beinhalten.</span><span class="sxs-lookup"><span data-stu-id="aa055-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="aa055-105">Hierarchien können in einer Feldliste einer Berichterstellungsclientanwendung getrennt von anderen Spalten auftreten. So können Clientbenutzer leichter durch diese navigieren und sie in Berichte einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="aa055-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="aa055-106">Weitere Informationen finden Sie unter [Hierarchien &#40;SSAS – tabellarisch&#41;](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="aa055-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="aa055-107">Verwenden Sie zum Erstellen von Hierarchien den Modell-Designer in der *Diagrammsicht*.</span><span class="sxs-lookup"><span data-stu-id="aa055-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="aa055-108">Das Erstellen und Verwalten von Hierarchien in der Datensicht des Modell-Designers wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aa055-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="aa055-109">Geschätzte Zeit zum Bearbeiten dieser Lektion: **20 Minuten**</span><span class="sxs-lookup"><span data-stu-id="aa055-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa055-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aa055-110">Prerequisites</span></span>  
 <span data-ttu-id="aa055-111">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="aa055-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="aa055-112">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige, [Lektion 9: Erstellen von Perspektiven](lesson-8-create-perspectives.md), abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="aa055-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="aa055-113">Erstellen von Hierarchien</span><span class="sxs-lookup"><span data-stu-id="aa055-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="aa055-114">So erstellen Sie in der Product-Tabelle eine Kategoriehierarchie</span><span class="sxs-lookup"><span data-stu-id="aa055-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="aa055-115">Klicken Sie im Modell-Designer auf das `Model` Menü, zeigen Sie auf **Modell Ansicht**, und klicken Sie dann auf **Diagramm Sicht**.</span><span class="sxs-lookup"><span data-stu-id="aa055-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="aa055-116">Verwenden Sie die Steuerelemente der Miniaturkarte oben rechts im Modell-Designer, um die Sicht der Objekte in der Diagrammsicht je nach Bedarf zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aa055-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="aa055-117">Ordnen Sie Objekte in der Diagrammsicht neu an, wird diese Sicht beim Speichern des Projekts beibehalten.</span><span class="sxs-lookup"><span data-stu-id="aa055-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="aa055-118">Klicken Sie im Modell-Designer mit der rechten Maustaste auf die `Product` Tabelle, und klicken Sie dann auf **Hierarchie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="aa055-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="aa055-119">Eine neue Hierarchie wird am unteren Rand des Tabellenfensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa055-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="aa055-120">Benennen Sie im Hierarchienamen die Hierarchie um `Category` , indem Sie eingeben, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="aa055-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="aa055-121">`Product`Klicken Sie in der Tabelle auf die Spalte **Product Category Name** , ziehen Sie Sie in die `Category` Hierarchie, und geben Sie dann oberhalb des `Category` namens frei.</span><span class="sxs-lookup"><span data-stu-id="aa055-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="aa055-122">`Category`Klicken Sie in der Hierarchie mit der rechten Maustaste auf die Spalte **Product Category Name** , klicken Sie dann auf **Umbenennen**, und geben Sie ein `Category` .</span><span class="sxs-lookup"><span data-stu-id="aa055-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa055-123">Durch das Umbenennen einer Spalte in einer Hierarchie wird die betreffende Spalte in der Tabelle nicht umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa055-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="aa055-124">Eine Spalte in einer Hierarchie ist nur eine Darstellung der Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="aa055-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="aa055-125">`Product`Klicken Sie in der Tabelle mit der rechten Maustaste auf die Spalte **Product Subcategory Name** , zeigen Sie im Kontextmenü auf **zur Hierarchie hinzufügen**, und klicken Sie dann auf `Category` .</span><span class="sxs-lookup"><span data-stu-id="aa055-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="aa055-126">Benennen Sie **Product Subcategory Name** in um `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="aa055-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="aa055-127">Fügen Sie mithilfe von klicken und ziehen oder mithilfe des Befehls **zur Hierarchie hinzufügen** im Kontextmenü die Spalten **Model Name** und **Product Name** (in der angegebenen Reihenfolge) hinzu, und platzieren Sie Sie unterhalb der Spalte **Product Subcategory Name** .</span><span class="sxs-lookup"><span data-stu-id="aa055-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="aa055-128">Benennen Sie diese Spalten um `Model` `Product` bzw. um.</span><span class="sxs-lookup"><span data-stu-id="aa055-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="aa055-129">So erstellen Sie Hierarchien in der Date-Tabelle</span><span class="sxs-lookup"><span data-stu-id="aa055-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="aa055-130">Klicken Sie im Modell-Designer mit der rechten Maustaste auf die Tabelle **Date** und anschließend auf **Hierarchie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="aa055-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="aa055-131">Benennen Sie die Hierarchie in **Calendar**(Kalender) um.</span><span class="sxs-lookup"><span data-stu-id="aa055-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="aa055-132">Fügen Sie die folgenden Spalten in der entsprechenden Reihenfolge hinzu, und benennen Sie sie dann um:</span><span class="sxs-lookup"><span data-stu-id="aa055-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="aa055-133">Spalte</span><span class="sxs-lookup"><span data-stu-id="aa055-133">Column</span></span>|<span data-ttu-id="aa055-134">Umbenennen in:</span><span class="sxs-lookup"><span data-stu-id="aa055-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="aa055-135">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="aa055-135">Calendar Year</span></span>|<span data-ttu-id="aa055-136">Jahr</span><span class="sxs-lookup"><span data-stu-id="aa055-136">Year</span></span>|  
    |<span data-ttu-id="aa055-137">Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="aa055-137">Calendar Semester</span></span>|<span data-ttu-id="aa055-138">Semester</span><span class="sxs-lookup"><span data-stu-id="aa055-138">Semester</span></span>|  
    |<span data-ttu-id="aa055-139">Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="aa055-139">Calendar Quarter</span></span>|<span data-ttu-id="aa055-140">Quarter</span><span class="sxs-lookup"><span data-stu-id="aa055-140">Quarter</span></span>|  
    |<span data-ttu-id="aa055-141">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="aa055-141">Month Calendar</span></span>|<span data-ttu-id="aa055-142">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="aa055-142">Month</span></span>|  
    |<span data-ttu-id="aa055-143">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="aa055-143">Day Of Month</span></span>|<span data-ttu-id="aa055-144">Tag</span><span class="sxs-lookup"><span data-stu-id="aa055-144">Day</span></span>|  
  
4.  <span data-ttu-id="aa055-145">Wiederholen Sie in der Tabelle **Date** die oben genannten Schritte, und erstellen Sie die Hierarchie **Fiscal** , einschließlich der folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="aa055-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="aa055-146">Spalte</span><span class="sxs-lookup"><span data-stu-id="aa055-146">Column</span></span>|<span data-ttu-id="aa055-147">Umbenennen in:</span><span class="sxs-lookup"><span data-stu-id="aa055-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="aa055-148">Fiscal Year</span><span class="sxs-lookup"><span data-stu-id="aa055-148">Fiscal Year</span></span>|<span data-ttu-id="aa055-149">Jahr</span><span class="sxs-lookup"><span data-stu-id="aa055-149">Year</span></span>|  
    |<span data-ttu-id="aa055-150">Fiscal Semester</span><span class="sxs-lookup"><span data-stu-id="aa055-150">Fiscal Semester</span></span>|<span data-ttu-id="aa055-151">Semester</span><span class="sxs-lookup"><span data-stu-id="aa055-151">Semester</span></span>|  
    |<span data-ttu-id="aa055-152">Fiscal Quarter</span><span class="sxs-lookup"><span data-stu-id="aa055-152">Fiscal Quarter</span></span>|<span data-ttu-id="aa055-153">Quarter</span><span class="sxs-lookup"><span data-stu-id="aa055-153">Quarter</span></span>|  
    |<span data-ttu-id="aa055-154">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="aa055-154">Month Calendar</span></span>|<span data-ttu-id="aa055-155">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="aa055-155">Month</span></span>|  
    |<span data-ttu-id="aa055-156">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="aa055-156">Day Of Month</span></span>|<span data-ttu-id="aa055-157">Tag</span><span class="sxs-lookup"><span data-stu-id="aa055-157">Day</span></span>|  
  
5.  <span data-ttu-id="aa055-158">Wiederholen Sie abschließend in der Tabelle **Date** die oben genannten Schritte, und erstellen Sie die Hierarchie **Production Calendar** (Produktionskalender), einschließlich der folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="aa055-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="aa055-159">Spalte</span><span class="sxs-lookup"><span data-stu-id="aa055-159">Column</span></span>|<span data-ttu-id="aa055-160">Umbenennen in:</span><span class="sxs-lookup"><span data-stu-id="aa055-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="aa055-161">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="aa055-161">Calendar Year</span></span>|<span data-ttu-id="aa055-162">Jahr</span><span class="sxs-lookup"><span data-stu-id="aa055-162">Year</span></span>|  
    |<span data-ttu-id="aa055-163">Week Number Of Year</span><span class="sxs-lookup"><span data-stu-id="aa055-163">Week Number Of Year</span></span>|<span data-ttu-id="aa055-164">Woche</span><span class="sxs-lookup"><span data-stu-id="aa055-164">Week</span></span>|  
    |<span data-ttu-id="aa055-165">Day Of Week</span><span class="sxs-lookup"><span data-stu-id="aa055-165">Day Of Week</span></span>|<span data-ttu-id="aa055-166">Tag</span><span class="sxs-lookup"><span data-stu-id="aa055-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="aa055-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="aa055-167">Next Steps</span></span>  
 <span data-ttu-id="aa055-168">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 11: Erstellen von Partitionen](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="aa055-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
