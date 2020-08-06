---
title: Manuelles Verknüpfen von Tabellen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695122"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="bfe1a-102">Manuelles Verknüpfen von Tabellen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bfe1a-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="bfe1a-103">Wenn Sie einer Abfrage mindestens zwei Tabellen hinzufügen, versucht der [Abfrage- und Sicht-Designer](visual-database-tools.md) diese auf der Grundlage häufig auftretender Daten oder der in der Datenbank gespeicherten Informationen zu Tabellenjoins zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="bfe1a-104">Ausführliche Informationen finden Sie unter [Automatisches Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfe1a-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="bfe1a-105">Wenn der Abfrage- und Sicht-Designer die Tabellen jedoch nicht automatisch verknüpft hat oder wenn Sie weitere Joinbedingungen zwischen Tabellen erstellen möchten, können Sie Tabellen manuell verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="bfe1a-106">Sie können Joins auf der Grundlage von Vergleichen zwischen zwei beliebigen Spalten erstellen, die aber nicht dieselben Informationen enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="bfe1a-107">Wenn z. B. die Datenbank die zwei Tabellen `titles` und `roysched`enthält, können Sie die Werte in der Spalte `ytd_sales` der Tabelle `titles` mit den Spalten `lorange` und `hirange` in der Tabelle `roysched` vergleichen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="bfe1a-108">Das Erstellen dieses Joins ermöglicht Ihnen das Suchen nach Titeln, für die die Verkäufe des aktuellen Jahres zwischen dem unteren und dem oberen Bereich der Tantiemenzahlungen liegen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="bfe1a-109">Joins funktionieren am schnellsten, wenn die Spalten in der Joinbedingung indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="bfe1a-110">In einigen Fällen kann der Join über nicht indizierte Spalten zu einer langsamen Abfrage führen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="bfe1a-111">So verknüpfen Sie Tabellen oder Objekte mit Tabellenstruktur manuell</span><span class="sxs-lookup"><span data-stu-id="bfe1a-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="bfe1a-112">Fügen Sie dem [Diagrammbereich](diagram-pane-visual-database-tools.md) die zu verknüpfenden Objekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="bfe1a-113">Ziehen Sie den Namen der Joinspalte aus der ersten Tabelle bzw. aus dem ersten Objekt mit Tabellenstruktur, und legen Sie diesen auf der entsprechenden Spalte in der zweiten Tabelle bzw. im zweiten Objekt mit Tabellenstruktur ab.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="bfe1a-114">Ein Join kann nicht auf der Grundlage der Spalten `text`, `ntext` oder i`mage` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfe1a-115">Die Joinspalten müssen denselben (oder einen kompatiblen) Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="bfe1a-116">Wenn z. B. die Joinspalte in der ersten Tabelle eine Datenspalte ist, müssen Sie diese mit einer Datenspalte in der zweiten Tabelle verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="bfe1a-117">Wenn es sich jedoch bei der ersten Joinspalte um eine Integer-Spalte handelt, muss die zu verknüpfende Spalte ebenfalls vom Integer-Datentyp sein, kann jedoch eine andere Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="bfe1a-118">Der Abfrage- und Sicht-Designer überprüft die Datentypen der für einen Join verwendeten Spalten nicht. Wenn Sie jedoch die Abfrage ausführen, zeigt die Datenbank bei nicht kompatiblen Datentypen einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="bfe1a-119">Ändern Sie ggf. den Joinoperator; in der Standardeinstellung ist der Operator ein Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="bfe1a-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="bfe1a-120">Weitere Informationen finden Sie unter [Ändern von Joinoperatoren &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfe1a-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="bfe1a-121">Der Abfrage- und Sicht-Designer fügt der SQL-Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md) eine INNER JOIN-Klausel hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="bfe1a-122">Sie können den Typ in einen äußeren Join ändern.</span><span class="sxs-lookup"><span data-stu-id="bfe1a-122">You can change the type to an outer join.</span></span> <span data-ttu-id="bfe1a-123">Weitere Informationen finden Sie unter [Erstellen von äußeren Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfe1a-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe1a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfe1a-124">See Also</span></span>  
 [<span data-ttu-id="bfe1a-125">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe1a-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
