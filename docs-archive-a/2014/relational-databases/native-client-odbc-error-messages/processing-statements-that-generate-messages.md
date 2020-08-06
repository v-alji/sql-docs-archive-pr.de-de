---
title: Verarbeiten von Anweisungen, die Meldungen generieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698175"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="b51e8-102">Verarbeiten von Anweisungen, die Meldungen generieren</span><span class="sxs-lookup"><span data-stu-id="b51e8-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="b51e8-103">Die [!INCLUDE[tsql](../../includes/tsql-md.md)]-SET-Anweisungsoptionen STATISTICS TIME und STATISTICS IO werden verwendet, um Informationen zur Unterstützung bei der Diagnose von Abfragen mit langer Ausführungszeit zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="b51e8-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="b51e8-104">Frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützen auch die SHOWPLAN-Option zur Analyse von Abfrageplänen.</span><span class="sxs-lookup"><span data-stu-id="b51e8-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="b51e8-105">Eine ODBC-Anwendung kann diese Optionen festlegen, indem sie die folgenden Anweisungen ausführt:</span><span class="sxs-lookup"><span data-stu-id="b51e8-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="b51e8-106">Wenn SET STATISTICS Time oder SET SHOWPLAN on ist, werden **SQLExecute** und **SQLExecDirect** SQL_SUCCESS_WITH_INFO zurückgegeben. an diesem Punkt kann die Anwendung die Ausgabe des Showplan oder der Statistik Zeit abrufen, indem Sie **SQLGetDiagRec** aufruft, bis SQL_NO_DATA zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b51e8-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="b51e8-107">Jede Zeile der SHOWPLAN-Daten wird im folgenden Format ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="b51e8-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 <span data-ttu-id="b51e8-108">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Version 7.0 wurde die SHOWPLAN-Option durch SHOWPLAN_ALL und SHOWPLAN_TEXT ersetzt. Beide Optionen geben die Ausgabe als Resultset, nicht wie zuvor als Meldungssätze, zurück.</span><span class="sxs-lookup"><span data-stu-id="b51e8-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="b51e8-109">Jede Zeile der STATISTICS TIME-Daten wird im folgenden Format ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="b51e8-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="b51e8-110">Die Ausgabe von SET STATISTICS IO ist bis zum Ende eines Resultsets nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b51e8-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="b51e8-111">Zum Abrufen der Statistik-e/a-Ausgabe Ruft die Anwendung **SQLGetDiagRec** auf, wenn **SQLFetch** oder [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) SQL_NO_DATA zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b51e8-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="b51e8-112">Die Ausgabe der STATISTICS IO-Option erfolgt in folgendem Format:</span><span class="sxs-lookup"><span data-stu-id="b51e8-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="b51e8-113">Verwenden von DBCC-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b51e8-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="b51e8-114">DBCC-Anweisungen geben Daten als Meldungen, nicht als Resultsets, zurück.</span><span class="sxs-lookup"><span data-stu-id="b51e8-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="b51e8-115">**SQLExecDirect** oder **SQLExecute** geben SQL_SUCCESS_WITH_INFO zurück, und die Anwendung ruft die Ausgabe ab, indem Sie **SQLGetDiagRec** aufrufen, bis Sie SQL_NO_DATA zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b51e8-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="b51e8-116">Beispielsweise gibt die folgende Anweisung SQL_SUCCESS_WITH_INFO zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="b51e8-117">Aufrufe von **SQLGetDiagRec** geben Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="b51e8-118">Verwenden der Anweisungen PRINT und RAISERROR</span><span class="sxs-lookup"><span data-stu-id="b51e8-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="b51e8-119">Print-und RAISERROR-Anweisungen geben auch Daten durch Aufrufen von **SQLGetDiagRec**zurück.</span><span class="sxs-lookup"><span data-stu-id="b51e8-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="b51e8-120">Print-Anweisungen bewirken, dass die Ausführung der SQL-Anweisung SQL_SUCCESS_WITH_INFO zurückgibt, und ein nachfolgende-Befehl von **SQLGetDiagRec** gibt den *SQLSTATE* -Wert 01000 zurück.</span><span class="sxs-lookup"><span data-stu-id="b51e8-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="b51e8-121">Ein RAISERROR mit einem Schweregrad bis einschließlich 10 zeigt dasselbe Verhalten wie PRINT.</span><span class="sxs-lookup"><span data-stu-id="b51e8-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="b51e8-122">Ein RAISERROR mit einem Schweregrad von 11 oder höher bewirkt, dass die Execute-SQL_ERROR zurückgibt, und ein nachfolgende-Befehl von **SQLGetDiagRec** gibt *SQLSTATE* 42000 zurück.</span><span class="sxs-lookup"><span data-stu-id="b51e8-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="b51e8-123">Beispielsweise gibt die folgende Anweisung SQL_SUCCESS_WITH_INFO zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="b51e8-124">Der Aufruf von **SQLGetDiagRec** gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="b51e8-125">Die folgende Anweisung gibt SQL_SUCCESS_WITH_INFO zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="b51e8-126">Der Aufruf von **SQLGetDiagRec** gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="b51e8-127">Die folgende Anweisung gibt SQL_ERROR zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="b51e8-128">Der Aufruf von **SQLGetDiagRec** gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="b51e8-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="b51e8-129">Die zeitliche Steuerung von **SQLGetDiagRec** ist wichtig, wenn die Ausgabe von Print-oder RAISERROR-Anweisungen in einem Resultset enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b51e8-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="b51e8-130">Der Aufrufen von **SQLGetDiagRec** zum Abrufen der Print-oder RAISERROR-Ausgabe muss direkt nach der Anweisung erfolgen, die SQL_ERROR oder SQL_SUCCESS_WITH_INFO empfängt.</span><span class="sxs-lookup"><span data-stu-id="b51e8-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="b51e8-131">Dies ist einfach, wenn nur eine einzelne SQL-Anweisung ausgeführt wird, wie in den oben stehenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="b51e8-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="b51e8-132">In diesen Fällen gibt der Aufruf von **SQLExecDirect** oder **SQLExecute** SQL_ERROR oder SQL_SUCCESS_WITH_INFO zurück, und **SQLGetDiagRec** kann dann aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b51e8-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="b51e8-133">Komplizierter wird es, wenn Schleifen zum Behandeln der Ausgabe einer Reihe von SQL-Anweisungen codiert, oder wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-gespeicherte Prozeduren ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b51e8-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="b51e8-134">In diesem Fall gibt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Resultset für jede SELECT-Anweisung zurück, die in einem Batch oder in einer gespeicherten Prozedur ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="b51e8-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="b51e8-135">Wenn der Batch bzw. die Prozedur PRINT- oder RAISERROR-Anweisungen enthält, ist die Ausgabe dieser Anweisungen mit den Resultsets der SELECT-Anweisungen verschachtelt.</span><span class="sxs-lookup"><span data-stu-id="b51e8-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="b51e8-136">Wenn die erste Anweisung im Batch oder in der Prozedur ein Druck-oder RAISERROR-Wert ist, gibt **SQLExecute** oder **SQLExecDirect** SQL_SUCCESS_WITH_INFO oder SQL_ERROR zurück, und die Anwendung muss **SQLGetDiagRec** aufrufen, bis SQL_NO_DATA zum Abrufen der Druck-oder RAISERROR-Informationen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b51e8-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="b51e8-137">Wenn die Print-oder RAISERROR-Anweisung auf eine SQL-Anweisung (z. b. eine SELECT-Anweisung) folgt, werden die Print-oder RAISERROR-Informationen zurückgegeben, wenn [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)in dem Resultset, das den Fehler enthält, positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="b51e8-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="b51e8-138">**SQLMoreResults** gibt SQL_SUCCESS_WITH_INFO oder SQL_ERROR zurück, je nach Schweregrad der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b51e8-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="b51e8-139">Nachrichten werden durch Aufrufen von **SQLGetDiagRec** abgerufen, bis SQL_NO_DATA zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b51e8-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51e8-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b51e8-140">See Also</span></span>  
 [<span data-ttu-id="b51e8-141">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="b51e8-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
