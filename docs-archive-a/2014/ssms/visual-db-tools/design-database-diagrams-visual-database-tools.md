---
title: Entwerfen von Datenbankdiagrammen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65536
- vdt.DatabaseDesigner
helpviewer_keywords:
- Database Diagram Designer
- Visual Database Tools [SQL Server], database diagrams
- database diagrams [SQL Server], designing
- diagrams [SQL Server], designing
ms.assetid: 6d2c14e1-3d73-4d10-ae5b-7f2b5d6c4ea8
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb4cbc518b6878ed8fb6e9f7d5d2d00803ab4d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697374"
---
# <a name="design-database-diagrams-visual-database-tools"></a><span data-ttu-id="af7b6-102">Entwerfen von Datenbankdiagrammen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="af7b6-102">Design Database Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="af7b6-103">Der Datenbank-Designer ist ein visuelles Tool, mit dem Sie eine Datenbank, mit der eine Verbindung besteht, entwerfen und anzeigen lassen können.</span><span class="sxs-lookup"><span data-stu-id="af7b6-103">The Database Designer is a visual tool that allows you to design and visualize a database to which you are connected.</span></span> <span data-ttu-id="af7b6-104">Beim Entwerfen einer Datenbank können Sie mithilfe des Datenbank-Designers Tabellen, Spalten, Schlüssel, Indizes, Beziehungen und Einschränkungen erstellen, bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="af7b6-104">When designing a database, you can use Database Designer to create, edit, or delete tables, columns, keys, indexes, relationships, and constraints.</span></span> <span data-ttu-id="af7b6-105">Zur Darstellung einer Datenbank können Sie ein oder mehrere Diagramme erstellen, die die Tabellen, Spalten, Schlüssel oder Beziehungen innerhalb der Datenbank teilweise oder ganz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="af7b6-105">To visualize a database, you can create one or more diagrams illustrating some or all of the tables, columns, keys, and relationships in it.</span></span>  
  
 <span data-ttu-id="af7b6-106">![Datenbankdiagramm zur Illustration von Tabellenbeziehungen](../../database-engine/media//dv3w7c1.gif "Datenbankdiagramm zur Illustration von Tabellenbeziehungen")</span><span class="sxs-lookup"><span data-stu-id="af7b6-106">![Database diagram illustrating table relationships](../../database-engine/media//dv3w7c1.gif "Database diagram illustrating table relationships")</span></span>  
  
 <span data-ttu-id="af7b6-107">Sie können für jede Datenbank beliebig viele Datenbankdiagramme erstellen, und jede Datenbanktabelle kann in einer beliebigen Anzahl von Diagrammen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="af7b6-107">For any database, you can create as many database diagrams as you like; each database table can appear on any number of diagrams.</span></span> <span data-ttu-id="af7b6-108">Daher können Sie verschiedene Diagramme erstellen, um unterschiedliche Bereiche der Datenbank darzustellen oder unterschiedliche Aspekte des Entwurfs hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="af7b6-108">Thus, you can create different diagrams to visualize different portions of the database, or to accentuate different aspects of the design.</span></span> <span data-ttu-id="af7b6-109">Sie können z. B. ein umfangreiches Diagramm erstellen, in dem alle Tabellen und Spalten angezeigt werden, und ein kleineres Diagramm, in dem die Tabellen ohne ihre Spalten dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="af7b6-109">For example, you can create a large diagram showing all tables and columns, and you can create a smaller diagram showing all tables without showing the columns.</span></span>  
  
 <span data-ttu-id="af7b6-110">Jedes erstellte Diagramm wird in der zugehörigen Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="af7b6-110">Each database diagram you create is stored in the associated database.</span></span>  
  
## <a name="tables-and-columns-in-a-database-diagram"></a><span data-ttu-id="af7b6-111">Tabellen und Spalten in einem Datenbankdiagramm</span><span class="sxs-lookup"><span data-stu-id="af7b6-111">Tables and Columns in a Database Diagram</span></span>  
 <span data-ttu-id="af7b6-112">Innerhalb eines Datenbankdiagramms können Tabellen mit drei unterschiedlichen Merkmalen angezeigt werden: einer Titelleiste, einem Zeilenselektor und einer Reihe von Eigenschaftenspalten.</span><span class="sxs-lookup"><span data-stu-id="af7b6-112">Within a database diagram, each table can appear with three distinct features: a title bar, a row selector, and a set of property columns.</span></span>  
  
 <span data-ttu-id="af7b6-113">**Titelleiste** In der Titelleiste wird der Name der Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af7b6-113">**Title Bar** The title bar shows the name of the table</span></span>  
  
 <span data-ttu-id="af7b6-114">Wenn Sie in einer Tabelle Änderungen vorgenommen und diese noch nicht gespeichert haben, wird am Ende des Tabellennamens ein Sternchen (\*) angezeigt, um so auf ungespeicherte Änderungen hinzuweisen.</span><span class="sxs-lookup"><span data-stu-id="af7b6-114">If you have modified a table and have not yet saved it, an asterisk (\*) appears at the end of the table name to indicate unsaved changes.</span></span> <span data-ttu-id="af7b6-115">Informationen zum Speichern von geänderten Tabellen und Diagrammen finden Sie unter [Verwenden von Datenbankdiagrammen &#40;Visual Database Tools&#41;](visual-database-tools.md)</span><span class="sxs-lookup"><span data-stu-id="af7b6-115">For information about saving modified tables and diagrams, see [Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md)</span></span>  
  
 <span data-ttu-id="af7b6-116">**Zeilenselektor** Klicken Sie auf den Zeilenselektor, um eine Spalte in einer Datenbank auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="af7b6-116">**Row Selector** You can click the row selector to select a database column in the table.</span></span> <span data-ttu-id="af7b6-117">Der Zeilenselektor zeigt ein Symbol in Form eines Schlüssels an, wenn sich die Spalte im Primärschlüssel der Tabelle befindet.</span><span class="sxs-lookup"><span data-stu-id="af7b6-117">The row selector displays a key symbol if the column is in the table's primary key.</span></span> <span data-ttu-id="af7b6-118">Informationen zu primär Schlüsseln finden Sie unter [Primary-und FOREIGN KEY-Einschränkungen](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="af7b6-118">For information about primary keys, see [Primary and Foreign Key Constraints](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="af7b6-119">**Eigenschaftenspalten** Die Eigenschaftenspalten werden nur in bestimmten Sichten der Tabellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af7b6-119">**Property Columns** The set of property columns is visible only in the certain views of your table.</span></span> <span data-ttu-id="af7b6-120">Sie können sich eine Tabelle in fünf verschiedenen Sichten anzeigen lassen, um dann die Größe und das Layout des betreffenden Diagramms verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="af7b6-120">You can view a table in any of five different views to help you manage the size and layout of your diagram.</span></span>  
  
 <span data-ttu-id="af7b6-121">Weitere Informationen zu Tabellensichten finden Sie unter [Anpassen des Umfangs der in Diagrammen angezeigten Informationen &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af7b6-121">For more information about table views, see [Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span></span>  
  
## <a name="relationships-in-a-database-diagram"></a><span data-ttu-id="af7b6-122">Beziehungen in einem Datenbankdiagramm</span><span class="sxs-lookup"><span data-stu-id="af7b6-122">Relationships in a Database Diagram</span></span>  
 <span data-ttu-id="af7b6-123">Innerhalb eines Datenbankdiagramms können Eigenschaften mit drei unterschiedlichen Merkmalen angezeigt werden: Endpunkte, eine bestimmte Linienart und verknüpfte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="af7b6-123">Within a database diagram, each relationship can appear with three distinct features: endpoints, a line style, and related tables.</span></span>  
  
 <span data-ttu-id="af7b6-124">**Endpunkte** Die Endpunkte der Linie geben an, ob es sich um eine 1:1-Beziehung oder um eine 1:n-Beziehung handelt.</span><span class="sxs-lookup"><span data-stu-id="af7b6-124">**Endpoints** The endpoints of the line indicate whether the relationship is one-to-one or one-to-many.</span></span> <span data-ttu-id="af7b6-125">Wenn eine Beziehung einen Schlüssel an einem Endpunkt und ein Unendlichkeitszeichen am anderen Endpunkt aufweist, handelt es sich um eine 1:n-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="af7b6-125">If a relationship has a key at one endpoint and a figure-eight at the other, it is a one-to-many relationship.</span></span> <span data-ttu-id="af7b6-126">Wenn eine Beziehung an jedem Endpunkt einen Schlüssel aufweist, handelt es sich um eine 1:1-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="af7b6-126">If a relationship has a key at each endpoint, it is a one-to-one relationship.</span></span>  
  
 <span data-ttu-id="af7b6-127">**Linienart** Die Linie selbst (ohne die Endpunkte) gibt an, ob das Datenbank-Managementsystem (DBMS) die referenzielle Integrität für die Beziehung erzwingt, wenn der Fremdschlüsseltabelle neue Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="af7b6-127">**Line Style** The line itself (not its endpoints) indicates whether the Database Management System (DBMS) enforces referential integrity for the relationship when new data is added to the foreign-key table.</span></span> <span data-ttu-id="af7b6-128">Bei einer durchgezogenen Linie erzwingt das DBMS die referenzielle Integrität für die Beziehung, wenn Zeilen in der Fremdschlüsseltabelle hinzugefügt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af7b6-128">If the line appears solid, the DBMS enforces referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span> <span data-ttu-id="af7b6-129">Bei einer gepunkteten Linie erzwingt das DBMS keine referenzielle Integrität für die Beziehung, wenn Zeilen in der Fremdschlüsseltabelle hinzugefügt oder bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="af7b6-129">If the line appears dotted, the DBMS does not enforce referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span>  
  
 <span data-ttu-id="af7b6-130">**Verknüpfte Tabellen** Die Beziehungslinie gibt an, das zwischen zwei Tabellen eine Fremdschlüsselbeziehung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="af7b6-130">**Related Tables** The relationship line indicates that a foreign-key relationship exists between one table and another.</span></span> <span data-ttu-id="af7b6-131">Bei einer 1:n-Beziehung ist die Fremdschlüsseltabelle die Tabelle neben dem Unendlichkeitszeichen der Linie.</span><span class="sxs-lookup"><span data-stu-id="af7b6-131">For a one-to-many relationship, the foreign-key table is the table near the line's figure-eight symbol.</span></span> <span data-ttu-id="af7b6-132">Wenn beide Endpunkte der Linie mit derselben Tabelle verbunden sind, handelt es sich um eine reflexive Beziehung.</span><span class="sxs-lookup"><span data-stu-id="af7b6-132">If both endpoints of the line attach to the same table, the relationship is a reflexive relationship.</span></span> <span data-ttu-id="af7b6-133">Weitere Informationen finden Sie unter [Zeichnen reflexiver Beziehungen &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af7b6-133">For more information, see [Draw Reflexive Relationships &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af7b6-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="af7b6-134">In this Section</span></span>  
 [<span data-ttu-id="af7b6-135">Grundlagen des Besitzes von Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-135">Understand Database Diagram Ownership &#40;Visual Database Tools&#41;</span></span>](understand-database-diagram-ownership-visual-database-tools.md)  
  
 [<span data-ttu-id="af7b6-136">Navigieren im Datenbankdiagramm-Designer &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-136">Navigate in Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](navigate-in-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="af7b6-137">Einrichten im Datenbankdiagramm-Designer &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-137">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](set-up-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="af7b6-138">Aktualisieren von Datenbankdiagrammen aus älteren Versionen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-138">Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;</span></span>](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md)  
  
 [<span data-ttu-id="af7b6-139">Öffnen des Datenbankdiagramm-Designers &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-139">Open Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](open-database-diagram-designer-visual-database-tools.md)  
  
## <a name="see-also"></a><span data-ttu-id="af7b6-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af7b6-140">See Also</span></span>  
 <span data-ttu-id="af7b6-141">[Arbeiten mit Daten Bank Diagrammen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="af7b6-141">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="af7b6-142">[Arbeiten mit Tabellen im Daten Bank Diagramm &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="af7b6-142">[Work with Tables in Database Diagram &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="af7b6-143">Verwenden von Diagrammlayout &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="af7b6-143">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  