---
title: Verarbeitungsergebnisse (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722758"
---
# <a name="process-results-odbc"></a><span data-ttu-id="526c9-102">Verarbeiten von Ergebnissen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="526c9-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="526c9-103">So verarbeiten Sie Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="526c9-103">To process results</span></span>  
  
1.  <span data-ttu-id="526c9-104">Rufen Sie Resultsetinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="526c9-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="526c9-105">Wenn gebundene Spalten verwendet werden, rufen Sie für jede Spalte, für die eine Bindung erstellt werden soll, [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) auf, um einen Programmpuffer an die Spalte zu binden.</span><span class="sxs-lookup"><span data-stu-id="526c9-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="526c9-106">Für jede Zeile im Resultset wird Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="526c9-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="526c9-107">Rufen Sie [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) auf, um die nächste Zeile abzurufen.</span><span class="sxs-lookup"><span data-stu-id="526c9-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="526c9-108">Bei der Verwendung von gebundenen Spalten verwenden Sie die Daten, die nun in den Puffern mit gebundenen Spalten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="526c9-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="526c9-109">Wenn ungebundene Spalten verwendet werden, rufen Sie [SQLGetData](../native-client-odbc-api/sqlgetdata.md) ein oder mehrere Male auf, um die Daten für ungebundene Spalten nach der letzten gebundenen Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="526c9-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="526c9-110">Aufrufe `SQLGetData` von sollten in aufsteigender Reihenfolge der Spaltennummer erfolgen.</span><span class="sxs-lookup"><span data-stu-id="526c9-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="526c9-111">Rufen Sie `SQLGetData` mehrere Male auf, um Daten aus einer text- oder image-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="526c9-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="526c9-112">Wenn [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) das Ende des Resultsets durch Rückgabe von SQL_NO_DATA signalisiert, rufen Sie [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) auf, um zu bestimmen, ob ein weiteres Resultset verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="526c9-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="526c9-113">Wenn SQL_SUCCESS zurückgegeben wird, ist ein anderes Resultset verfügbar.</span><span class="sxs-lookup"><span data-stu-id="526c9-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="526c9-114">Wenn SQL_NO_DATA zurückgegeben wird, sind keine weiteren Resultsets verfügbar.</span><span class="sxs-lookup"><span data-stu-id="526c9-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="526c9-115">Wenn SQL_SUCCESS_WITH_INFO oder SQL_ERROR zurückgegeben wird, rufen Sie [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) auf, um festzustellen, ob die Ausgabe von einer PRINT- oder RAISERROR-Anweisung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="526c9-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="526c9-116">Wenn für Ausgabeparameter oder für den Rückgabewert einer gespeicherten Prozedur gebundene Anweisungsparameter verwendet werden, verwenden Sie die jetzt in den Puffern für gebundene Parameter verfügbaren Daten.</span><span class="sxs-lookup"><span data-stu-id="526c9-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="526c9-117">Wenn gebundene Parameter verwendet werden, hat jeder Aufruf von [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) oder [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) die SQL-Anweisung *S*-mal ausgeführt, wobei *S* die Anzahl der Elemente im Array von gebundenen Parametern ist.</span><span class="sxs-lookup"><span data-stu-id="526c9-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="526c9-118">Dies bedeutet, dass *S* Sätze von Ergebnissen verarbeitet werden müssen, wobei jeder Resultset alle Resultsets, Ausgabeparameter und Rückgabecodes enthält, die normalerweise von einer einzelnen Ausführung der SQL-Anweisung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="526c9-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="526c9-119">Wenn ein Resultset COMPUTE-Zeilen (Berechnungszeilen) enthält, wird jede COMPUTE-Zeile als eigenes Resultset verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="526c9-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="526c9-120">Diese COMPUTE-Resultsets werden in die normalen Zeilen eingefügt und teilen normale Zeilen in mehrere Resultsets.</span><span class="sxs-lookup"><span data-stu-id="526c9-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="526c9-121">Sie können optional [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) mit SQL_UNBIND aufrufen, um Puffer mit gebundenen Spalten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="526c9-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="526c9-122">Wenn ein weiteres Resultset verfügbar ist, fahren Sie mit Schritt 1 fort.</span><span class="sxs-lookup"><span data-stu-id="526c9-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="526c9-123">Um das Verarbeiten eines Resultsets abzubrechen, bevor [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) SQL_NO_DATA zurückgibt, rufen Sie [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md) auf.</span><span class="sxs-lookup"><span data-stu-id="526c9-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526c9-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="526c9-124">See Also</span></span>  
 [<span data-ttu-id="526c9-125">Themen zur Vorgehensweise bei der Verarbeitung von Ergebnissen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="526c9-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
