---
title: Scrollen und Abrufen von Zeilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723829"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="a5f8d-102">Bildläufe und Abrufen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="a5f8d-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="a5f8d-103">Um einen bildlauffähigen Cursor zu verwenden, muss eine ODBC-Anwendung folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a5f8d-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="a5f8d-104">Legen Sie die Cursor Funktionen mithilfe von [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)fest.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="a5f8d-105">Öffnen Sie den Cursor mithilfe von **SQLExecute** oder **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="a5f8d-106">Scrollen und Abrufen von Zeilen mithilfe von **SQLFetch** oder [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="a5f8d-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="a5f8d-107">Sowohl **SQLFetch** als auch **sqlfetchsroll** können Zeilen Blöcke gleichzeitig abrufen.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="a5f8d-108">Die Anzahl der zurückgegebenen Zeilen wird mithilfe von **SQLSetStmtAttr** festgelegt, um den SQL_ATTR_ROW_ARRAY_SIZE-Parameter festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="a5f8d-109">ODBC-Anwendungen können **SQLFetch** zum Abrufen über einen Vorwärts Cursor verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="a5f8d-110">**SQLFetchScroll** wird verwendet, um einen Bildlauf um einen Cursor durchführen.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="a5f8d-111">**SQLFetchScroll** unterstützt das Abrufen der nächsten, vorherigen, ersten und letzten Rowsets zusätzlich zum relativen Abrufen (Abrufen der Rowsets *n* Zeilen vom Anfang des aktuellen Rowsets) und das absolute abrufen (Abrufen des Rowsets ab Zeile *n*).</span><span class="sxs-lookup"><span data-stu-id="a5f8d-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="a5f8d-112">Wenn *n* bei einem absoluten Abruf negativ ist, werden Zeilen vom Ende des Resultsets gezählt.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="a5f8d-113">Ein absoluter Abruf von Zeile -1 bedeutet den Abruf des Rowsets, das mit der letzten Zeile im Resultset beginnt.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="a5f8d-114">Anwendungen, die **SQLFetchScroll** nur für Ihre Block Cursor Funktionen verwenden, wie z. b. Berichte, werden das Resultset wahrscheinlich ein einziges Mal durchlaufen, wobei nur die Option zum Abrufen des nächsten Rowsets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="a5f8d-115">Auf der anderen Seite können bildschirmbasierte Anwendungen alle Funktionen von **SQLFetchScroll**nutzen.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="a5f8d-116">Wenn die Anwendung die Rowsetgröße auf die auf dem Bildschirm angezeigte Anzahl von Zeilen festlegt und die Bildschirm Puffer an das Resultset bindet, können Schiebe leisten Vorgänge direkt in Aufrufe von **SQLFetchScroll**übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a5f8d-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="a5f8d-117">Bildlaufleistenvorgang</span><span class="sxs-lookup"><span data-stu-id="a5f8d-117">Scroll bar operation</span></span>|<span data-ttu-id="a5f8d-118">SQLFetchScroll-Bildlaufoption</span><span class="sxs-lookup"><span data-stu-id="a5f8d-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="a5f8d-119">Bild auf</span><span class="sxs-lookup"><span data-stu-id="a5f8d-119">Page up</span></span>|<span data-ttu-id="a5f8d-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="a5f8d-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="a5f8d-121">Bild ab</span><span class="sxs-lookup"><span data-stu-id="a5f8d-121">Page down</span></span>|<span data-ttu-id="a5f8d-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="a5f8d-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="a5f8d-123">Zeile auf</span><span class="sxs-lookup"><span data-stu-id="a5f8d-123">Line up</span></span>|<span data-ttu-id="a5f8d-124">SQL_FETCH_RELATIVE mit FetchOffset gleich-1</span><span class="sxs-lookup"><span data-stu-id="a5f8d-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="a5f8d-125">Zeile ab</span><span class="sxs-lookup"><span data-stu-id="a5f8d-125">Line down</span></span>|<span data-ttu-id="a5f8d-126">SQL_FETCH_RELATIVE mit FetchOffset gleich 1</span><span class="sxs-lookup"><span data-stu-id="a5f8d-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="a5f8d-127">Bildlauffeld nach oben</span><span class="sxs-lookup"><span data-stu-id="a5f8d-127">Scroll box to top</span></span>|<span data-ttu-id="a5f8d-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="a5f8d-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="a5f8d-129">Bildlauffeld nach unten</span><span class="sxs-lookup"><span data-stu-id="a5f8d-129">Scroll box to bottom</span></span>|<span data-ttu-id="a5f8d-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="a5f8d-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="a5f8d-131">Zufällige Bildlauffeldposition</span><span class="sxs-lookup"><span data-stu-id="a5f8d-131">Random scroll box position</span></span>|<span data-ttu-id="a5f8d-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="a5f8d-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a5f8d-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a5f8d-133">In This Section</span></span>  
  
-   [<span data-ttu-id="a5f8d-134">Kennzeichnen von Zeilen in ODBC</span><span class="sxs-lookup"><span data-stu-id="a5f8d-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5f8d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5f8d-135">See Also</span></span>  
 [<span data-ttu-id="a5f8d-136">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="a5f8d-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
