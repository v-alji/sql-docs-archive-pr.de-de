---
title: Verknüpfen von Tabellen über mehrere Spalten (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618422"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="de496-102">Verknüpfen von Tabellen über mehrere Spalten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="de496-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="de496-103">Sie können Tabellen über mehrere Spalten verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="de496-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="de496-104">Dies bedeutet, dass Sie eine Abfrage erstellen können, die Übereinstimmungen von Zeilen aus den zwei Tabellen nur herstellt, wenn diese mehrere Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="de496-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="de496-105">Wenn die Datenbank eine Beziehung enthält, in der mehrere Fremdschlüsselspalten einer Tabelle einem mehrspaltigen Primärschlüssel in der anderen Tabelle entsprechen, können Sie mit dieser Beziehung ein Join über mehrere Spalten erstellen.</span><span class="sxs-lookup"><span data-stu-id="de496-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="de496-106">Ausführliche Informationen finden Sie unter [Automatisches Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="de496-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="de496-107">Sie können den Join auch dann manuell erstellen, wenn die Datenbank keine mehrspaltige Fremdschlüsselbeziehung enthält.</span><span class="sxs-lookup"><span data-stu-id="de496-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="de496-108">So erstellen Sie manuell einen Join über mehrere Spalten</span><span class="sxs-lookup"><span data-stu-id="de496-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="de496-109">Fügen Sie dem [Diagrammbereich](diagram-pane-visual-database-tools.md) die zu verknüpfenden Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="de496-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="de496-110">Ziehen Sie den Namen der ersten Joinspalte aus dem Fenster der ersten Tabelle, und legen Sie diesen auf der entsprechenden Spalte im Fenster der zweiten Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="de496-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="de496-111">Einen Join kann nicht auf der Grundlage von text-, ntext- oder image-Spalten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="de496-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de496-112">Im Allgemeinen müssen die Joinspalten denselben (oder einen kompatiblen) Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="de496-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="de496-113">Wenn z. B. die Joinspalte in der ersten Tabelle eine Datenspalte ist, müssen Sie diese mit einer Datenspalte in der zweiten Tabelle verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="de496-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="de496-114">Wenn es sich jedoch bei der ersten Joinspalte um eine Integer-Spalte handelt, muss die zu verknüpfende Spalte ebenfalls vom Integer-Datentyp sein, kann jedoch eine andere Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="de496-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="de496-115">In einzelnen Fällen ist ein Join scheinbar inkompatibler Spalten dank impliziter Datentypkonvertierungen jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="de496-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="de496-116">Der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) überprüft die Datentypen der für einen Join verwendeten Spalten nicht. Wenn Sie jedoch die Abfrage ausführen, zeigt die Datenbank bei nicht kompatiblen Datentypen einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="de496-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="de496-117">Ziehen Sie den Namen der zweiten Joinspalte aus dem Fenster der ersten Tabelle, und legen Sie diesen auf der entsprechenden Spalte im Fenster der zweiten Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="de496-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="de496-118">Wiederholen Sie Schritt drei für jedes weitere Paar von Joinspalten in den beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="de496-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="de496-119">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="de496-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de496-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de496-120">See Also</span></span>  
 [<span data-ttu-id="de496-121">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="de496-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
