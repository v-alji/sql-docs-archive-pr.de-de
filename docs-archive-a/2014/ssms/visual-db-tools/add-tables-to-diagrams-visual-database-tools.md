---
title: Hinzufügen von Tabellen zu Diagrammen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618435"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="63a5a-102">Hinzufügen von Tabellen zu Diagrammen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="63a5a-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="63a5a-103">Sie können dem Datenbankdiagramm eine Tabelle hinzufügen, um die Diagrammstruktur zu bearbeiten oder Beziehungen zu anderen Tabellen im Diagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63a5a-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="63a5a-104">Sie können der Datenbank entweder bereits vorhandene Datenbanktabellen oder eine neue Tabelle hinzufügen, die noch nicht in der Datenbank definiert ist.</span><span class="sxs-lookup"><span data-stu-id="63a5a-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="63a5a-105">So fügen Sie eine neue Tabelle in ein Diagramm ein</span><span class="sxs-lookup"><span data-stu-id="63a5a-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="63a5a-106">Vergewissern Sie sich, dass Sie mit der Datenbank verbunden sind, in der die Tabelle erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63a5a-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="63a5a-107">Zum Erstellen einer Tabelle im aktuellen Diagramm klicken Sie auf der Symbolleiste auf die Schaltfläche **Neue Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="63a5a-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="63a5a-108">Oder</span><span class="sxs-lookup"><span data-stu-id="63a5a-108">-or-</span></span>  
  
     <span data-ttu-id="63a5a-109">Klicken Sie mit der rechten Maustaste auf das Diagramm, und wählen Sie **Neue Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="63a5a-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="63a5a-110">Übernehmen oder ändern Sie den vom System zugewiesenen Namen der Tabelle im Dialogfeld **Namen auswählen** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="63a5a-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="63a5a-111">In der Standardansicht des Diagramms wird nun eine neue Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63a5a-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="63a5a-112">Geben Sie in der ersten Zelle der neuen Tabelle einen Spaltennamen ein.</span><span class="sxs-lookup"><span data-stu-id="63a5a-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="63a5a-113">Drücken Sie dann die TAB-TASTE, um zur nächsten Zelle zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="63a5a-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="63a5a-114">Wählen Sie unter **Datentyp**einen Datentyp für die Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="63a5a-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="63a5a-115">Jeder Spalte muss ein Name und ein Datentyp zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="63a5a-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="63a5a-116">Sie können die anderen Eigenschaften der Spalte im Tabellen-Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="63a5a-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="63a5a-117">Wiederholen Sie die Schritte 3 und 4 für jede Spalte, die Sie der Tabelle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="63a5a-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63a5a-118">Wenn Sie das Datenbankdiagramm speichern, wird die neue Tabelle der Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63a5a-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="63a5a-119">So fügen Sie einem Diagramm eine vorhandene Tabelle zu</span><span class="sxs-lookup"><span data-stu-id="63a5a-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="63a5a-120">Vergewissern Sie sich, dass Sie mit der Datenbank verbunden sind, deren Tabellen Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="63a5a-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="63a5a-121">Markieren Sie eine Tabelle im Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="63a5a-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="63a5a-122">Ziehen Sie die Tabelle in das Datenbankdiagramm.</span><span class="sxs-lookup"><span data-stu-id="63a5a-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="63a5a-123">Lassen Sie die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="63a5a-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63a5a-124">Wenn Beziehungen zwischen der ausgewählten Tabelle und anderen Tabellen im Diagramm bestehen, werden automatisch Beziehungslinien gezogen.</span><span class="sxs-lookup"><span data-stu-id="63a5a-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="63a5a-125">So fügen Sie einem Diagramm verknüpfte Tabellen hinzu</span><span class="sxs-lookup"><span data-stu-id="63a5a-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="63a5a-126">Wählen Sie eine oder mehrere Tabellen mit Fremdschlüsseleinschränkungen im Datenbankdiagramm aus.</span><span class="sxs-lookup"><span data-stu-id="63a5a-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="63a5a-127">Klicken Sie mit der rechten Maustaste auf eine der ausgewählten Tabellen, und wählen Sie **Verknüpfte Tabellen hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="63a5a-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63a5a-128">Daraufhin werden dem Diagramm sowohl die Tabellen hinzugefügt, auf die die ausgewählten Tabellen mit einer Fremdschlüsseleinschränkung verweisen, als auch die Tabellen, die mit einer Fremdschlüsseleinschränkung auf die ausgewählten Tabellen verweisen.</span><span class="sxs-lookup"><span data-stu-id="63a5a-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a5a-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63a5a-129">See Also</span></span>  
 <span data-ttu-id="63a5a-130">[Arbeiten mit Daten Bank Diagrammen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="63a5a-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="63a5a-131">Verwenden von Tabellen in Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="63a5a-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
