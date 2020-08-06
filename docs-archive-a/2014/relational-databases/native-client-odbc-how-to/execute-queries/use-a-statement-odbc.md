---
title: Use a-Anweisung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723813"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="cc406-102">Verwenden einer Anweisung (ODBC)</span><span class="sxs-lookup"><span data-stu-id="cc406-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="cc406-103">So verwenden Sie eine Anweisung</span><span class="sxs-lookup"><span data-stu-id="cc406-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="cc406-104">Rufen Sie [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) mit einem *HandleType* von SQL_HANDLE_STMT auf, um ein Anweisungshandle zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc406-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="cc406-105">Rufen Sie optional [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um Anweisungsoptionen festzulegen, oder [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md), um Anweisungsattribute abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cc406-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="cc406-106">Um Servercursor zu verwenden, müssen Sie die Cursorattribute auf Werte setzen, die von den Standardwerten abweichen.</span><span class="sxs-lookup"><span data-stu-id="cc406-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="cc406-107">Bereiten Sie optional die Anweisung mit der [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360)auf die Ausführung vor, wenn die Anweisung mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc406-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="cc406-108">Binden Sie optional mit [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md)die Parametermarkierungen an Programmvariablen, wenn die Anweisung über gebundene Parametermarkierungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="cc406-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="cc406-109">Wenn die Anweisung vorbereitet wurde, können Sie [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) und [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number und characteristics of the parameters.</span><span class="sxs-lookup"><span data-stu-id="cc406-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="cc406-110">Führen Sie eine Anweisung direkt mit SQLExecDirect aus.</span><span class="sxs-lookup"><span data-stu-id="cc406-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="cc406-111">\- oder -</span><span class="sxs-lookup"><span data-stu-id="cc406-111">\- or -</span></span>  
  
     <span data-ttu-id="cc406-112">Wenn die Anweisung vorbereitet wurde, führen Sie sie mehrmals mit [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400)aus.</span><span class="sxs-lookup"><span data-stu-id="cc406-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="cc406-113">\- oder -</span><span class="sxs-lookup"><span data-stu-id="cc406-113">\- or -</span></span>  
  
     <span data-ttu-id="cc406-114">Rufen Sie eine Katalogfunktion auf, die Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cc406-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="cc406-115">Verarbeiten Sie die Ergebnisse, indem Sie die Resultset-Spalten an Programmvariablen binden, indem Sie Daten mit [SQLGetData](../../native-client-odbc-api/sqlgetdata.md)oder einer Kombination der beiden Methoden aus den Resultset-Spalten zu Programmvariablen verschieben.</span><span class="sxs-lookup"><span data-stu-id="cc406-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="cc406-116">Rufen Sie eine Zeile nach der anderen über das Resultset einer Anweisung ab.</span><span class="sxs-lookup"><span data-stu-id="cc406-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="cc406-117">\- oder -</span><span class="sxs-lookup"><span data-stu-id="cc406-117">\- or -</span></span>  
  
     <span data-ttu-id="cc406-118">Rufen Sie mehrere Zeilen gleichzeitig über das Resultset mithilfe eines Blockcursors ab.</span><span class="sxs-lookup"><span data-stu-id="cc406-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="cc406-119">\- oder -</span><span class="sxs-lookup"><span data-stu-id="cc406-119">\- or -</span></span>  
  
     <span data-ttu-id="cc406-120">Rufen Sie [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) auf, um die Anzahl der Zeilen, die von einer INSERT-, UPDATE- oder DELETE-Anweisung betroffen sind, zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cc406-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="cc406-121">Wenn die SQL-Anweisung über mehrere Resultsets verfügen kann, rufen Sie am Ende des Resultsets [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) auf, um zu überprüfen, ob zusätzliche Resultsets verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cc406-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="cc406-122">Nachdem die Ergebnisse verarbeitet wurden, müssen möglicherweise die folgenden Aktionen ausgeführt werden, um das Anweisungshandle zum Ausführen einer neuen Anweisung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="cc406-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="cc406-123">Wenn Sie [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) nicht aufgerufen haben, bis SQL_NO_DATA zurückgegeben wurde, rufen Sie [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) auf, um den Cursor zu schließen.</span><span class="sxs-lookup"><span data-stu-id="cc406-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="cc406-124">Wenn Sie Parametermarkierungen an Programmvariablen gebunden haben, rufen Sie [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) auf, wobei *Option* auf SQL_RESET_PARAMS gesetzt ist, um die gebundenen Parameter freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cc406-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="cc406-125">Wenn Sie Resultset-Spalten an Programmvariablen gebunden haben, rufen Sie [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) auf, wobei *Option* auf SQL_UNBIND gesetzt ist, um die gebundenen Spalten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cc406-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="cc406-126">Gehen Sie zu Schritt 2, um das Anweisungshandle wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="cc406-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="cc406-127">Rufen Sie [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) mit einem *HandleType* von SQL_HANDLE_STMT auf, um das Anweisungshandle freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cc406-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc406-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc406-128">See Also</span></span>  
 [<span data-ttu-id="cc406-129">Gewusst-wie-Themen zum Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="cc406-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
