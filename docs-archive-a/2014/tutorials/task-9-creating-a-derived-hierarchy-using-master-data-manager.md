---
title: 'Aufgabe 9: Erstellen einer abgeleiteten Hierarchie mit Master Data Manager | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726358"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="d0e4f-102">Aufgabe 9: Erstellen einer abgeleiteten Hierarchie mithilfe des Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="d0e4f-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="d0e4f-103">In dieser Aufgabe erstellen Sie eine abgeleitete Hierarchie mit Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="d0e4f-104">Diese abgeleitete Hierarchie wird von den domänenbasierten Attribut Beziehungen zwischen den Entitäten " **Supplier** " und " **State** " abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="d0e4f-105">Wechseln Sie zur Hauptseite **Master Data Manager** , indem Sie oben auf der Seite auf **SQL Server 2012 Master Data Services** klicken.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="d0e4f-106">Klicken Sie im Abschnitt **administrative Aufgaben** auf **System Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="d0e4f-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="d0e4f-107">Zeigen Sie mit der Maus auf **Verwalten** in der Menüleiste, und klicken Sie auf **abgeleitete Hierarchien**.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="d0e4f-108">![Menü "Verwalten" – "Abgeleitete Hierarchien" ausgewählt](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Menü "Verwalten" – "Abgeleitete Hierarchien" ausgewählt")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="d0e4f-109">Klicken Sie auf der Symbolleiste auf **abgeleitete Hierarchie hinzufügen (+)** .</span><span class="sxs-lookup"><span data-stu-id="d0e4f-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="d0e4f-110">![Abgeleitete Hierarchie hinzufügen (Schaltfläche)](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Abgeleitete Hierarchie hinzufügen (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="d0e4f-111">Geben Sie **suppliersinstate** als **Namen der abgeleiteten Hierarchie**ein.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="d0e4f-112">Klicken Sie in der Symbolleiste auf die Schaltfläche **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="d0e4f-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="d0e4f-113">![Abgeleitete Hierarchie speichern (Schaltfläche)](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Abgeleitete Hierarchie speichern (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="d0e4f-114">Ziehen Sie **Supplier** von **Verfügbare Ebenen: suppliersinstate** auf **Current Levels: suppliersinstate**.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="d0e4f-115">![Auf aktueller Ebene verfügbare Entitäten und Hierarchien](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Auf aktueller Ebene verfügbare Entitäten und Hierarchien")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="d0e4f-116">Ziehen Sie den **Zustand** von **Verfügbare Ebenen: suppliersinstate** in **aktuelle Ebenen: suppliersinstate**.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="d0e4f-117">Der Bildschirm sollte die **aktuellen Ebenen** aufweisen, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="d0e4f-118">![Aktuelle Ebenen und Vorschau der abgeleiteten Hierarchie](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Aktuelle Ebenen und Vorschau der abgeleiteten Hierarchie")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="d0e4f-119">Erweitern Sie im **Vorschaufenster** den Eintrag **NY {New York}** , und Sie sollten einen Lieferanten in diesem Zustand sehen, wie in der obigen Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="d0e4f-120">Wechseln Sie zur Hauptseite **Master Data Manager** , indem Sie oben auf der Seite auf **SQL Server 2012 Master Data Services** klicken.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="d0e4f-121">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="d0e4f-122">Zeigen Sie mit der Maus auf **Hierarchien** , und klicken Sie auf **abgeleitet: suppliersinstate**.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="d0e4f-123">![Hierarchien – Abgeleitet: SuppliersInState (Menü)](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchien – Abgeleitet: SuppliersInState (Menü)")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="d0e4f-124">Klicken Sie in der Struktur **Ansicht** auf einen beliebigen **Status** Knoten, und die Lieferanten in diesem Zustand werden im rechten Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e4f-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="d0e4f-125">![Abgeleitete Hierarchie im Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Abgeleitete Hierarchie im Explorer")</span><span class="sxs-lookup"><span data-stu-id="d0e4f-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d0e4f-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d0e4f-126">Next Step</span></span>  
 [<span data-ttu-id="d0e4f-127">Lektion 5: Automatisierung der Bereinigung und des Abgleich mit SSIS</span><span class="sxs-lookup"><span data-stu-id="d0e4f-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
