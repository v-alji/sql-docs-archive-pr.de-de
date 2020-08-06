---
title: Abfragen von nächsten Nachbarn aus räumlichen Daten | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621955"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="66a4a-102">Abfragen von nächsten Nachbarn aus räumlichen Daten</span><span class="sxs-lookup"><span data-stu-id="66a4a-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="66a4a-103">Eine häufig für räumliche Daten verwendete Abfrage ist die Nächster Nachbar-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="66a4a-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="66a4a-104">Mithilfe von Nächster Nachbar-Abfragen werden die räumlichen Objekte gesucht, die einem bestimmten räumlichen Objekt am nächsten liegen.</span><span class="sxs-lookup"><span data-stu-id="66a4a-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="66a4a-105">Beispielsweise muss von einer Filialsuche auf einer Website häufig die Filiale bestimmt werden, die dem Standort des Kunden am nächsten liegt.</span><span class="sxs-lookup"><span data-stu-id="66a4a-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="66a4a-106">Eine Nächster Nachbar-Abfrage kann in einer Vielzahl von gültigen Abfrageformaten geschrieben werden. Damit jedoch für die Nächster Nachbar-Abfrage ein räumlicher Index verwendet wird, muss die folgende Syntax angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a4a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="66a4a-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="66a4a-108">Nächster Nachbar-Abfrage und räumliche Indizes</span><span class="sxs-lookup"><span data-stu-id="66a4a-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="66a4a-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden `TOP`-Klauseln und `ORDER BY`-Klauseln verwendet, um eine Nächster Nachbar-Abfrage für Spalten mit räumlichen Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="66a4a-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="66a4a-110">Die `ORDER BY`-Klausel enthält einen Aufruf der `STDistance()`-Methode für den Typ der Spalte mit räumlichen Daten.</span><span class="sxs-lookup"><span data-stu-id="66a4a-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="66a4a-111">Die `TOP`-Klausel gibt die für die Abfrage zurückzugebende Anzahl von Objekten an.</span><span class="sxs-lookup"><span data-stu-id="66a4a-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="66a4a-112">Die folgenden Anforderungen müssen erfüllt sein, damit eine Nächster Nachbar-Abfrage einen räumlichen Index verwendet:</span><span class="sxs-lookup"><span data-stu-id="66a4a-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="66a4a-113">Ein räumlicher Index muss in einer der räumlichen Spalten vorhanden sein, und die `STDistance()`-Methode muss diese Spalte in der `WHERE`-Klausel und der `ORDER BY`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="66a4a-114">Die `TOP`-Klausel darf keine `PERCENT`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="66a4a-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="66a4a-115">Die `WHERE`-Klausel muss eine `STDistance()`-Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="66a4a-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="66a4a-116">Wenn in der `WHERE`-Klausel mehrere Prädikate vorhanden sind, muss das Prädikat mit der `STDistance()`-Methode über eine `AND`-Konjunktion mit den anderen Prädikaten verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="66a4a-117">Die `STDistance()`-Methode darf sich nicht in einem optionalen Teil der `WHERE`-Klausel befinden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="66a4a-118">Der erste Ausdruck in der `ORDER BY`-Klausel muss die `STDistance()`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="66a4a-119">Die Sortierreihenfolge für den ersten `STDistance()`-Ausdruck in der `ORDER BY`-Klausel muss auf `ASC` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="66a4a-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="66a4a-120">Alle Zeilen, für die `STDistance` den Wert `NULL` zurückgibt, müssen herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="66a4a-121">Methoden, die den Datentyp `geography` oder `geometry` als Argument annehmen, geben `NULL` zurück, wenn die SRIDs für die Typen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="66a4a-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="66a4a-122">Es wird empfohlen, dass für Indizes in Nächster Nachbar-Abfragen die neuen Mosaiken für räumliche Indizes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66a4a-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="66a4a-123">Weitere Informationen zu Mosaiken für räumliche Indizes finden Sie unter [Räumliche Daten &#40;SQL Server&#41;](spatial-data-sql-server.md)festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="66a4a-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66a4a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66a4a-124">Example</span></span>  
 <span data-ttu-id="66a4a-125">Im folgenden Codebeispiel wird eine Nächster Nachbar-Abfrage veranschaulicht, die einen räumlichen Index verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="66a4a-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="66a4a-126">Im Beispiel wird die Tabelle `Person.Address` in der `AdventureWorks2012` -Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="66a4a-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="66a4a-127">Erstellen Sie einen räumlichen Index in der SpatialLocation-Spalte, um zu veranschaulichen, wie eine Nächster Nachbar-Abfrage einen räumlichen Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="66a4a-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="66a4a-128">Weitere Informationen zum Erstellen von räumlichen Indizes finden Sie unter [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="66a4a-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66a4a-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66a4a-129">Example</span></span>  
 <span data-ttu-id="66a4a-130">Im folgenden Codebeispiel wird eine Nächster Nachbar-Abfrage veranschaulicht, die keine räumlichen Indizes verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="66a4a-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="66a4a-131">In der Abfrage fehlt eine `WHERE`-Klausel, die `STDistance()` in einem im Syntaxabschnitt angegebenen Format verwendet, sodass die Abfrage keine räumlichen Indizes verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="66a4a-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a4a-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66a4a-132">See Also</span></span>  
 [<span data-ttu-id="66a4a-133">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66a4a-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
