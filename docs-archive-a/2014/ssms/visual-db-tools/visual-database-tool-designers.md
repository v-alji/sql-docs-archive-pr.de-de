---
title: Designer in Visual Database Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- data sources [SQL Server]
- View Designer
- Visual Database Tools [SQL Server]
- Database Diagram Designer
- Query Designer [SQL Server]
- design tools [Visual Database Tools]
- Table Designer
- Visual Database Tools [SQL Server], designers
- Properties window [Visual Database Tools]
ms.assetid: bd0ca68e-6f69-42dd-bcb5-ce511673769c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6a307a0a82aa02e7197189ca6cfc9ba70a3fea33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609625"
---
# <a name="visual-database-tool-designers"></a><span data-ttu-id="81fee-102">Designer in Visual Database Tools</span><span class="sxs-lookup"><span data-stu-id="81fee-102">Visual Database Tool Designers</span></span>
  <span data-ttu-id="81fee-103">Visual Database Tools kombiniert eine Reihe von Entwurfstools, die zur Bearbeitung von Datenquellen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="81fee-103">The Visual Database Tools are a combination of design tools you can use to work with a data source.</span></span> <span data-ttu-id="81fee-104">Sie können damit Abfragen erstellen, die Datenbankstruktur entwerfen oder ändern und Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="81fee-104">You can use them to create queries, design or modify a database structure, or update data.</span></span> <span data-ttu-id="81fee-105">Die Tools heißen Datenbankdiagramm-Designer, Tabellen-Designer und Abfrage- und Sicht-Designer.</span><span class="sxs-lookup"><span data-stu-id="81fee-105">The tools are Database Diagram Designer, Table Designer, and Query and View Designer.</span></span>  
  
## <a name="properties-window"></a><span data-ttu-id="81fee-106">Eigenschaftenfenster</span><span class="sxs-lookup"><span data-stu-id="81fee-106">Properties Window</span></span>  
 <span data-ttu-id="81fee-107">Das Eigenschaftenfenster ist keine Eigenheit von Visual Database Tools; an dieser Stelle können Sie jedoch verschiedene Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="81fee-107">The properties window is not specific to Visual Database Tools, but it is where many modifications can be made.</span></span> <span data-ttu-id="81fee-108">Hier werden die Eigenschaften des aktuell ausgewählten Elements (z. B. eine Tabelle) angezeigt. Diese Eigenschaften (vom Namen der Eigenschaften bis zur Sortierung einer Spalte) können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="81fee-108">It shows the properties for the item currently selected (like a table) and allows you to edit those properties (everything from the properties name to the collation of a column).</span></span> <span data-ttu-id="81fee-109">Einige Eigenschaften werden im Eigenschaftenfenster angezeigt, müssen jedoch mit einem anderen Tool geändert werden.</span><span class="sxs-lookup"><span data-stu-id="81fee-109">Some properties can be seen in the properties window but must be modified in a different tool.</span></span>  
  
## <a name="database-diagram-designer"></a><span data-ttu-id="81fee-110">Datenbankdiagramm-Designer</span><span class="sxs-lookup"><span data-stu-id="81fee-110">Database Diagram Designer</span></span>  
 <span data-ttu-id="81fee-111">Im Datenbankdiagramm-Designer können Sie über ein Fenster Tabellen und Beziehungen einer Datenbank erstellen, bearbeiten und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="81fee-111">Database Diagram Designer provides a window where you can visually create, edit, and show the tables and relationships in a database.</span></span>  
  
 <span data-ttu-id="81fee-112">Wenn Sie den Datenbankdiagramm-Designer anzeigen möchten, öffnen Sie ein vorhandenes Diagramm, oder klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Datenbankknoten, und wählen Sie **Neues Datenbankdiagramm** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="81fee-112">To display Database Diagram Designer, open an existing diagram or right-click the Database node in Object Explorer and choose **New Database Diagram** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="81fee-113">Sobald der Designer geöffnet ist, wird das Menü **Datenbankdiagramm** im Hauptmenü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="81fee-113">Once the designer is open, the **Database Diagram** menu appears in the main menu.</span></span> <span data-ttu-id="81fee-114">Dieses Menü bildet den Zugriffspunkt zu den speziellen Funktionen des Designers.</span><span class="sxs-lookup"><span data-stu-id="81fee-114">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81fee-115">Dieser Designer ist mit Microsoft SQL Server-Datenbanken verwendbar.</span><span class="sxs-lookup"><span data-stu-id="81fee-115">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="81fee-116">Diese Version von Visual Database Tools unterstützt Microsoft SQL Server Version 7 und ältere Versionen nicht.</span><span class="sxs-lookup"><span data-stu-id="81fee-116">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="table-designer"></a><span data-ttu-id="81fee-117">Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="81fee-117">Table Designer</span></span>  
 <span data-ttu-id="81fee-118">Der Tabellen-Designer ist ein visuelles Tool, mit dem Sie eine einzelne Tabelle einer Microsoft SQL Server-Datenbank, mit der Sie eine Verbindung hergestellt haben, entwerfen und anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="81fee-118">Table Designer is a visual tool allowing you to design and visualize a single table in a Microsoft SQL Server database to which you are connected.</span></span>  
  
 <span data-ttu-id="81fee-119">Der Tabellen-Designer umfasst zwei Bereiche.</span><span class="sxs-lookup"><span data-stu-id="81fee-119">Table Designer has two panes.</span></span> <span data-ttu-id="81fee-120">Im oberen Bereich wird ein Datenblatt angezeigt, wobei jede Zeile des Datenblatts eine Spalte in der Datenbank wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="81fee-120">The upper area shows a grid; each row of the grid describes one database column.</span></span> <span data-ttu-id="81fee-121">Das Datenblatt zeigt die wichtigsten Attribute der einzelnen Datenbankspalten an: Spaltenname, Datentyp und Einstellung für die Zulassung von NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="81fee-121">For each database column, the grid displays its fundamental attributes: column name, data type, and nulls-allowed setting.</span></span>  
  
 <span data-ttu-id="81fee-122">Im unteren Bereich des Tabellen-Designers werden auf der Registerkarte Spalteneigenschaften weitere Attribute derjenigen Spalte angezeigt, die im oberen Bereich ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="81fee-122">The lower area of Table Designer, the Column Properties tab, shows additional attributes for whichever column is highlighted in the upper area.</span></span>  
  
 <span data-ttu-id="81fee-123">Im Tabellen-Designer können Sie zudem mit der rechten Maustaste auf den Datenblattabschnitt klicken, um auf Dialogfelder zuzugreifen, über die Sie Beziehungen, Einschränkungen, Indizes und Schlüssel für die Tabelle erstellen oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="81fee-123">From Table Designer, you can also right-click in the grid section to access dialog boxes through which you can create and modify relationships, constraints, indexes, and keys for the table.</span></span>  
  
 <span data-ttu-id="81fee-124">Öffnen Sie eine vorhandene Tabelle, oder klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Knoten **Tabelle** , und wählen Sie im Dropdownmenü **Neue Tabelle hinzufügen** aus, um den Tabellen-Designer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="81fee-124">To display Table Designer, open an existing table, or right-click the **Tables** node in Object Explorer, and choose **Add New Table** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="81fee-125">Sobald der Designer geöffnet ist, wird das Menü Tabellen-Designer im Hauptmenü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="81fee-125">Once the designer is open, the Table Designer menu appears in the main menu.</span></span> <span data-ttu-id="81fee-126">Dieses Menü bildet den Zugriffspunkt zu den speziellen Funktionen des Designers.</span><span class="sxs-lookup"><span data-stu-id="81fee-126">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81fee-127">Dieser Designer ist mit Microsoft SQL Server-Datenbanken verwendbar.</span><span class="sxs-lookup"><span data-stu-id="81fee-127">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="81fee-128">Diese Version von Visual Database Tools unterstützt Microsoft SQL Server Version 7 und ältere Versionen nicht.</span><span class="sxs-lookup"><span data-stu-id="81fee-128">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="query-and-view-designer"></a><span data-ttu-id="81fee-129">Abfrage- und Sicht-Designer</span><span class="sxs-lookup"><span data-stu-id="81fee-129">Query and View Designer</span></span>  
 <span data-ttu-id="81fee-130">Beim Abfrage- und Sicht-Designer handelt es sich eigentlich um zwei Tools, die auf sehr ähnliche Weise funktionieren.</span><span class="sxs-lookup"><span data-stu-id="81fee-130">Query and View designer is actually two tools that work in very similar ways.</span></span> <span data-ttu-id="81fee-131">Einige der Hauptunterschiede sind:</span><span class="sxs-lookup"><span data-stu-id="81fee-131">Some of the major differences are:</span></span>  
  
-   <span data-ttu-id="81fee-132">Sichten werden zusammen mit der Datenbank gespeichert, während Abfragen in einem Visual Studio-Datenbankprojekt gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="81fee-132">Views are saved with the database while a query is saved with a Visual Studio database project.</span></span>  
  
-   <span data-ttu-id="81fee-133">Der Abfrage-Designer kann mit fast jeder beliebigen Datenquelle verwendet werden, während der Sicht-Designer nur SQL Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81fee-133">Query Designer works with nearly any data source, where View Designer works only with SQL Server.</span></span>  
  
-   <span data-ttu-id="81fee-134">Mit dem Abfrage-Designer können Sie SELECT-, INSERT-, UPDATE- und DELETE DML-Anweisungen entwerfen; dagegen können Sichten nur SELECT-Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="81fee-134">Query Designer allows you to design SELECT, INSERT, UPDATE and DELETE DML statements, while views can only contain SELECT statements.</span></span>  
  
### <a name="view-designer"></a><span data-ttu-id="81fee-135">Sicht-Designer</span><span class="sxs-lookup"><span data-stu-id="81fee-135">View Designer</span></span>  
 <span data-ttu-id="81fee-136">Mit dem Sicht-Designer können Sie eine vorhandene Sicht entwerfen und darstellen oder in einer Microsoft SQL Server-Datenbank, mit der eine Verbindung besteht, eine neue Sicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="81fee-136">View Designer allows you to design and visualize an existing view or create a new one in a Microsoft SQL Server database to which you are connected.</span></span>  
  
 <span data-ttu-id="81fee-137">Der Sicht-Designer umfasst vier Bereiche: den Diagrammbereich, den Kriterienbereich, den SQL-Bereich und den Ergebnisbereich.</span><span class="sxs-lookup"><span data-stu-id="81fee-137">View Designer has four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span> <span data-ttu-id="81fee-138">Ausführlichere Informationen zu den einzelnen Bereichen finden Sie unter [Tools im Abfrage- und Sicht-Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="81fee-138">For more detailed information on each of these panes, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="81fee-139">Öffnen Sie eine vorhandene Sicht, oder klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Knoten **Sicht**, und wählen Sie im Dropdownmenü **Neue Sicht hinzufügen** aus, um den Sicht-Designer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="81fee-139">To display View Designer, open an existing view or right-click the **View** node in Object Explorer and choose **Add New View** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="81fee-140">Sobald der Designer geöffnet ist, wird das Menü **Abfrage-Designer** im Hauptmenü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="81fee-140">Once the designer is open, the **Query Designer** menu appears in the main menu.</span></span> <span data-ttu-id="81fee-141">Dieses Menü bildet den Zugriffspunkt zu den speziellen Funktionen des Designers.</span><span class="sxs-lookup"><span data-stu-id="81fee-141">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81fee-142">Dieser Designer ist mit Microsoft SQL Server-Datenbanken verwendbar.</span><span class="sxs-lookup"><span data-stu-id="81fee-142">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="81fee-143">Diese Version von Visual Database Tools unterstützt Microsoft SQL Server Version 7 und ältere Versionen nicht.</span><span class="sxs-lookup"><span data-stu-id="81fee-143">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fee-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81fee-144">See Also</span></span>  
 <span data-ttu-id="81fee-145">[Entwerfen von Daten Bank Diagrammen &#40;Visual Database Tools&#41;](design-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="81fee-145">[Design Database Diagrams &#40;Visual Database Tools&#41;](design-database-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="81fee-146">[Entwerfen von Tabellen &#40;Visual Database Tools&#41;](design-tables-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="81fee-146">[Design Tables &#40;Visual Database Tools&#41;](design-tables-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="81fee-147">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="81fee-147">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
