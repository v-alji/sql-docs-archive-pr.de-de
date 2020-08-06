---
title: Verwenden der Rowsetbindung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607726"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="87ed4-102">Verwenden der Rowsetbindung (ODBC)</span><span class="sxs-lookup"><span data-stu-id="87ed4-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="87ed4-103">So verwenden Sie spaltenbezogene Bindungen</span><span class="sxs-lookup"><span data-stu-id="87ed4-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="87ed4-104">Gehen Sie für jede gebundene Spalte wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="87ed4-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="87ed4-105">Weisen Sie ein Array von R (oder mehr) Spaltenpuffern zum Speichern von Datenwerten zu, wobei R die Anzahl der Zeilen im Rowset ist.</span><span class="sxs-lookup"><span data-stu-id="87ed4-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="87ed4-106">Weisen Sie optional ein Array von R (oder mehr) Spaltenpuffern zum Speichern von Datenlängen zu.</span><span class="sxs-lookup"><span data-stu-id="87ed4-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="87ed4-107">Rufen Sie [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) auf, um die Spaltendatenwert- und die Datenlängenarrays an die Spalte des Rowsets zu binden.</span><span class="sxs-lookup"><span data-stu-id="87ed4-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="87ed4-108">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="87ed4-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="87ed4-109">Stellen Sie SQL_ATTR_ROW_ARRAY_SIZE auf die Anzahl der Zeilen im Rowset ein (R).</span><span class="sxs-lookup"><span data-stu-id="87ed4-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="87ed4-110">Stellen Sie SQL_ATTR_ROW_BIND_TYPE auf SQL_BIND_BY_COLUMN ein.</span><span class="sxs-lookup"><span data-stu-id="87ed4-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="87ed4-111">Legen Sie fest, dass das SQL_ATTR_ROWS FETCHED_PTR-Attribut auf eine SQLUINTEGER-Variable verweist, die die Anzahl der abgerufenen Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="87ed4-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="87ed4-112">Lassen Sie SQL_ATTR_ROW_STATUS_PTR auf ein Array[R] von SQLUSSMALLINT-Variablen verweisen, die die Zeilenstatusindikatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="87ed4-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="87ed4-113">Ausführen der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="87ed4-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="87ed4-114">Jeder Aufruf von [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) oder [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) ruft R-Zeilen ab und überträgt die Daten in die gebundenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="87ed4-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="87ed4-115">So verwenden Sie zeilenbezogene Bindungen</span><span class="sxs-lookup"><span data-stu-id="87ed4-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="87ed4-116">Weisen Sie ein Array [R] mit Strukturen zu, wobei R der Anzahl der Zeilen im Rowset entspricht.</span><span class="sxs-lookup"><span data-stu-id="87ed4-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="87ed4-117">Die Struktur verfügt über ein Element für jede Spalte, und jedes Element besteht aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="87ed4-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="87ed4-118">Der erste Teil ist eine Variable des entsprechenden Datentyps zum Speichern der Spaltendaten.</span><span class="sxs-lookup"><span data-stu-id="87ed4-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="87ed4-119">Der zweite Teil ist eine SQLINTEGER-Variable zum Speichern des Spaltenstatusindikators.</span><span class="sxs-lookup"><span data-stu-id="87ed4-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="87ed4-120">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="87ed4-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="87ed4-121">Stellen Sie SQL_ATTR_ROW_ARRAY_SIZE auf die Anzahl der Zeilen im Rowset ein (R).</span><span class="sxs-lookup"><span data-stu-id="87ed4-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="87ed4-122">Legen Sie SQL_ATTR_ROW_BIND_TYPE auf die Größe der in Schritt 1 zugeordneten Struktur fest.</span><span class="sxs-lookup"><span data-stu-id="87ed4-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="87ed4-123">Legen Sie fest, dass das SQL_ATTR_ROWS_FETCHED_PTR-Attribut auf eine SQLUINTEGER-Variable verweist, die die Anzahl der abgerufenen Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="87ed4-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="87ed4-124">Lassen Sie SQL_ATTR_PARAMS_STATUS_PTR auf ein Array[R] von SQLUSSMALLINT-Variablen verweisen, die die Zeilenstatusindikatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="87ed4-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="87ed4-125">Rufen Sie für jede Spalte im Resultset [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) auf, um mit den Datenwert- und den Datenlängenzeigern der Spalte auf die Variablen im ersten Element des Arrays mit Strukturen zu zeigen, die in Schritt 1 zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="87ed4-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="87ed4-126">Ausführen der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="87ed4-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="87ed4-127">Jeder Aufruf von [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) oder [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) ruft R-Zeilen ab und überträgt die Daten in die gebundenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="87ed4-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ed4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87ed4-128">See Also</span></span>  
 <span data-ttu-id="87ed4-129">[Gewusst-wie-Themen zur Verwendung von Cursorn &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="87ed4-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="87ed4-130">[Implementierung von Cursorn](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="87ed4-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="87ed4-131">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="87ed4-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
