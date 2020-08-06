---
title: Verwenden von Cursorn (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723821"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="7f19e-102">Verwenden von Cursorn (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7f19e-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="7f19e-103">ODBC unterstützt ein Cursormodell, das Folgendes zulässt:</span><span class="sxs-lookup"><span data-stu-id="7f19e-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="7f19e-104">Mehrere Typen von Cursorn</span><span class="sxs-lookup"><span data-stu-id="7f19e-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="7f19e-105">Das Durchführen eines Bildlaufs und Positionieren innerhalb eines Cursors</span><span class="sxs-lookup"><span data-stu-id="7f19e-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="7f19e-106">Mehrere Parallelitätsoptionen</span><span class="sxs-lookup"><span data-stu-id="7f19e-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="7f19e-107">Positionierte Updates.</span><span class="sxs-lookup"><span data-stu-id="7f19e-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="7f19e-108">ODBC-Anwendungen deklarieren und öffnen Cursor oder verwenden cursorspezifische [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen nur selten.</span><span class="sxs-lookup"><span data-stu-id="7f19e-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7f19e-109">ODBC öffnet automatisch einen Cursor für jedes Resultset, das von einer SQL-Anweisung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7f19e-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="7f19e-110">Die Eigenschaften der Cursor werden mithilfe von Anweisungs Attributen gesteuert, die mit [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) festgelegt werden, bevor die SQL-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7f19e-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="7f19e-111">Die ODBC-API-Funktionen zum Verarbeiten der Resultsets unterstützen sämtliche Cursorfunktionalitäten einschließlich Abrufen, Durchführen eines Bildlaufs und positionierte Updates.</span><span class="sxs-lookup"><span data-stu-id="7f19e-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="7f19e-112">Dies ist ein Vergleich der Funktionsweise von Cursorn in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skripts und ODBC-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7f19e-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="7f19e-113">Aktion</span><span class="sxs-lookup"><span data-stu-id="7f19e-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="7f19e-114">ODBC</span><span class="sxs-lookup"><span data-stu-id="7f19e-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="7f19e-115">Definieren des Cursorverhaltens</span><span class="sxs-lookup"><span data-stu-id="7f19e-115">Define cursor behavior</span></span>|<span data-ttu-id="7f19e-116">Angeben durch DECLARE CURSOR-Parameter</span><span class="sxs-lookup"><span data-stu-id="7f19e-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="7f19e-117">Festlegen von Cursor Attributen mithilfe von [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="7f19e-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="7f19e-118">Öffnen eines Cursors</span><span class="sxs-lookup"><span data-stu-id="7f19e-118">Open a cursor</span></span>|<span data-ttu-id="7f19e-119">DECLARE Cursor geöffnet *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="7f19e-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="7f19e-120">**SQLExecDirect** oder **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="7f19e-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="7f19e-121">Zeilen abrufen</span><span class="sxs-lookup"><span data-stu-id="7f19e-121">Fetch rows</span></span>|<span data-ttu-id="7f19e-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="7f19e-122">FETCH</span></span>|<span data-ttu-id="7f19e-123">**SQLFetch** oder [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="7f19e-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="7f19e-124">Positioniertes Update</span><span class="sxs-lookup"><span data-stu-id="7f19e-124">Positioned update</span></span>|<span data-ttu-id="7f19e-125">WHERE CURRENT OF-Klausel mit UPDATE oder DELETE</span><span class="sxs-lookup"><span data-stu-id="7f19e-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="7f19e-126">**SQLSetPos**</span><span class="sxs-lookup"><span data-stu-id="7f19e-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="7f19e-127">Schließen eines Cursors</span><span class="sxs-lookup"><span data-stu-id="7f19e-127">Close a cursor</span></span>|<span data-ttu-id="7f19e-128">Schließen *cursor_name* Aufhebung der Freigabe</span><span class="sxs-lookup"><span data-stu-id="7f19e-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="7f19e-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="7f19e-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="7f19e-130">Die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementierten Servercursor unterstützen die Funktionalität des ODBC-Cursormodells.</span><span class="sxs-lookup"><span data-stu-id="7f19e-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="7f19e-131">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Treiber verwendet Servercursor, um die Cursorfunktionalität der ODBC-API zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7f19e-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f19e-132">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7f19e-132">In This Section</span></span>  
  
-   [<span data-ttu-id="7f19e-133">Implementieren von Cursorn</span><span class="sxs-lookup"><span data-stu-id="7f19e-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="7f19e-134">Cursortypen</span><span class="sxs-lookup"><span data-stu-id="7f19e-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="7f19e-135">Cursorverhalten</span><span class="sxs-lookup"><span data-stu-id="7f19e-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="7f19e-136">Cursoreigenschaften</span><span class="sxs-lookup"><span data-stu-id="7f19e-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="7f19e-137">Details zur Cursor Programmierung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7f19e-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="7f19e-138">Bildläufe und Abrufen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="7f19e-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="7f19e-139">Positionierte Updates &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7f19e-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="7f19e-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f19e-140">See Also</span></span>  
 <span data-ttu-id="7f19e-141">[SQL Server Native Client &#40;ODBC-&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="7f19e-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="7f19e-142">[Schließen Sie &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f19e-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="7f19e-143">[Cursor](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="7f19e-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="7f19e-144">[Freigabe &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f19e-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="7f19e-145">[DECLARE CURSOR &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f19e-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="7f19e-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f19e-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="7f19e-147">OPEN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f19e-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
