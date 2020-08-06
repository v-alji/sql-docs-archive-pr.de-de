---
title: Verwenden von Cursorn (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607729"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="74406-102">Verwenden von Cursorn (ODBC)</span><span class="sxs-lookup"><span data-stu-id="74406-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="74406-103">So verwenden Sie Cursor</span><span class="sxs-lookup"><span data-stu-id="74406-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="74406-104">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die gewünschten Cursorattribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="74406-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="74406-105">Legen Sie die Attribute SQL_ATTR_CURSOR_TYPE und SQL_ATTR_CONCURRENCY fest (dies ist die bevorzugte Option).</span><span class="sxs-lookup"><span data-stu-id="74406-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="74406-106">oder</span><span class="sxs-lookup"><span data-stu-id="74406-106">Or</span></span>  
  
     <span data-ttu-id="74406-107">Legen Sie die Attribute SQL_CURSOR_SCROLLABLE und SQL_CURSOR_SENSITIVITY fest.</span><span class="sxs-lookup"><span data-stu-id="74406-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="74406-108">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die Rowsetgröße mit dem SQL_ATTR_ROW_ARRAY_SIZE-Attribut festzulegen.</span><span class="sxs-lookup"><span data-stu-id="74406-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="74406-109">Sie können auch [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) aufrufen, um einen Cursornamen festzulegen, wenn positionierte Updates mit der WHERE CURRENT OF-Klausel durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="74406-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="74406-110">Führen Sie die SQL-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="74406-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="74406-111">Sie können optional auch [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) aufrufen, um den Cursornamen abzurufen, wenn positionierte Updates mit der WHERE CURRENT OF-Klausel durchgeführt werden und in Schritt 3 mit [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) kein Cursorname angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="74406-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="74406-112">Rufen Sie [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) auf, um die Anzahl von Spalten (C) im Rowset abzurufen.</span><span class="sxs-lookup"><span data-stu-id="74406-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="74406-113">Verwenden Sie spaltenbezogene Bindungen.</span><span class="sxs-lookup"><span data-stu-id="74406-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="74406-114">\- oder -</span><span class="sxs-lookup"><span data-stu-id="74406-114">\- or -</span></span>  
  
     <span data-ttu-id="74406-115">Verwenden Sie zeilenbezogene Bindungen.</span><span class="sxs-lookup"><span data-stu-id="74406-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="74406-116">Rufen Sie beliebige Rowsets vom Cursor ab.</span><span class="sxs-lookup"><span data-stu-id="74406-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="74406-117">Rufen [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) auf, um zu ermitteln, ob ein anderes Resultset verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="74406-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="74406-118">Wenn SQL_SUCCESS zurückgegeben wird, ist ein anderes Resultset verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74406-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="74406-119">Wenn SQL_NO_DATA zurückgegeben wird, sind keine weiteren Resultsets verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74406-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="74406-120">Wenn SQL_SUCCESS_WITH_INFO oder SQL_ERROR zurückgegeben wird, rufen Sie [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) auf, um festzustellen, ob die Ausgabe von einer PRINT- oder RAISERROR-Anweisung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="74406-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="74406-121">Wenn für Ausgabeparameter oder für den Rückgabewert einer gespeicherten Prozedur gebundene Anweisungsparameter verwendet werden, verwenden Sie die jetzt in den Puffern für gebundene Parameter verfügbaren Daten.</span><span class="sxs-lookup"><span data-stu-id="74406-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="74406-122">Wenn gebundene Parameter verwendet werden, hat jeder Aufruf von [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) oder [SQLExecDirect die SQL](https://go.microsoft.com/fwlink/?LinkId=58399)-Anweisung S mal ausgeführt, wobei S die Anzahl der Elemente im Array von gebundenen Parametern ist.</span><span class="sxs-lookup"><span data-stu-id="74406-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="74406-123">Das bedeutet, dass S Ergebnismengen verarbeitet werden müssen, wobei jede Ergebnismenge sämtliche Resultsets, Ausgabeparameter und Rückgabecodes enthält, die in der Regel von einer einzelnen Ausführung der SQL-Anweisung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="74406-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="74406-124">Wenn ein Resultset COMPUTE-Zeilen enthält, wird jede COMPUTE-Zeile als eigenes Resultset verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="74406-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="74406-125">Diese COMPUTE-Resultsets werden in die normalen Zeilen eingefügt und teilen normale Zeilen in mehrere Resultsets.</span><span class="sxs-lookup"><span data-stu-id="74406-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="74406-126">Sie können optional [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) mit SQL_UNBIND aufrufen, um Puffer mit gebundenen Spalten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="74406-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="74406-127">Wenn ein weiteres Resultset verfügbar ist, fahren Sie mit Schritt 6 fort.</span><span class="sxs-lookup"><span data-stu-id="74406-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="74406-128">Wenn in Schritt 9 [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) für ein teilweise verarbeitetes Resultset aufgerufen wird, wird das restliche Resultset gelöscht.</span><span class="sxs-lookup"><span data-stu-id="74406-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="74406-129">Eine andere Möglichkeit, ein teilweise verarbeitetes Resultset zu löschen, besteht darin, [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="74406-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="74406-130">Sie können den Typ des verwendeten Cursors entweder durch die Festlegung von SQL_ATTR_CURSOR_TYPE und SQL_ATTR_CONCURRENCY oder die Festlegung von SQL_ATTR_CURSOR_SENSITIVITY und SQL_ATTR_CURSOR_SCROLLABLE steuern.</span><span class="sxs-lookup"><span data-stu-id="74406-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="74406-131">Sie sollten die zwei Methoden zur Angabe des Cursorverhaltens nicht kombinieren.</span><span class="sxs-lookup"><span data-stu-id="74406-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74406-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74406-132">See Also</span></span>  
 [<span data-ttu-id="74406-133">Gewusst-wie-Themen zur Verwendung von Cursorn &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="74406-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
