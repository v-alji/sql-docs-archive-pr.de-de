---
title: Direktes Ausführen einer Anweisung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607722"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="88d4c-102">Direktes Ausführen von Anweisungen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="88d4c-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="88d4c-103">So führen Sie eine Anweisung direkt und nur einmal aus</span><span class="sxs-lookup"><span data-stu-id="88d4c-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="88d4c-104">Wenn die Anweisung über Parameter Markierungen verfügt, verwenden Sie [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) , um jeden Parameter an eine Programm Variable zu binden.</span><span class="sxs-lookup"><span data-stu-id="88d4c-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="88d4c-105">Füllen Sie die Programmvariablen mit Datenwerten, und richten Sie dann alle Data-at-Execution-Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="88d4c-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="88d4c-106">Führen Sie [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) aus, um die Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88d4c-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="88d4c-107">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="88d4c-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="88d4c-108">Senden Sie die Daten in Blöcken mithilfe von [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) und [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="88d4c-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="88d4c-109">So führen Sie mit der spaltenweisen Parameterbindung eine Anweisung mehrmals aus</span><span class="sxs-lookup"><span data-stu-id="88d4c-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="88d4c-110">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="88d4c-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="88d4c-111">Legen Sie SQL_ATTR_PARAMSET_SIZE auf die Anzahl von Sätzen (S) von Parametern fest.</span><span class="sxs-lookup"><span data-stu-id="88d4c-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="88d4c-112">Legen Sie SQL_ATTR_PARAM_BIND_TYPE auf SQL_PARAMETER_BIND_BY_COLUMN fest.</span><span class="sxs-lookup"><span data-stu-id="88d4c-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="88d4c-113">Legen Sie das SQL_ATTR_PARAMS_PROCESSED_PTR-Attribut fest, um auf eine SQLUINTEGER-Variable zu zeigen und die Anzahl der verarbeiteten Parameter zu halten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="88d4c-114">Legen Sie SQL_ATTR_PARAMS_STATUS_PTR fest, um auf ein Array [S] aus SQLUSSMALLINT-Variablen zu zeigen und die Parameterstatusindikatoren zu halten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="88d4c-115">Führen Sie folgende Aktionen für jeden Parametermarker durch:</span><span class="sxs-lookup"><span data-stu-id="88d4c-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="88d4c-116">Weisen Sie ein Array mit S-Parameterpuffern zu, um Datenwerte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88d4c-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="88d4c-117">Weisen Sie ein Array mit S-Parameterpuffern zu, um Datenlängen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88d4c-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="88d4c-118">Aufrufen von [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) , um die Parameter Datenwert-und Daten Längen Arrays an den Anweisungs Parameter zu binden.</span><span class="sxs-lookup"><span data-stu-id="88d4c-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="88d4c-119">Richten Sie alle Data-at-Execution-Text- oder Imageparameter ein.</span><span class="sxs-lookup"><span data-stu-id="88d4c-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="88d4c-120">Setzen Sie S-Datenwerte und S-Datenlängen in die gebundenen Parameterarrays ein.</span><span class="sxs-lookup"><span data-stu-id="88d4c-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="88d4c-121">Führen Sie [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) aus, um die Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88d4c-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="88d4c-122">Der Treiber führt die Anweisung S-mal aus, einmal für jeden Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="88d4c-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="88d4c-123">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="88d4c-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="88d4c-124">Senden Sie die Daten in Blöcken mithilfe von [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) und [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="88d4c-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="88d4c-125">So führen Sie mit der zeilenweisen Parameterbindung eine Anweisung mehrmals aus</span><span class="sxs-lookup"><span data-stu-id="88d4c-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="88d4c-126">Ordnen Sie ein Array [S] von Strukturen zu, wobei S der Anzahl von Parametersätzen entspricht.</span><span class="sxs-lookup"><span data-stu-id="88d4c-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="88d4c-127">Die Struktur verfügt über ein Element für jeden Parameter, und jedes Element verfügt über zwei Teile:</span><span class="sxs-lookup"><span data-stu-id="88d4c-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="88d4c-128">Der erste Teil ist eine Variable des entsprechenden Datentyps zum Speichern der Parameterdaten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="88d4c-129">Der zweite Teil ist eine SQLINTEGER-Variable zum Speichern des Statusindikators.</span><span class="sxs-lookup"><span data-stu-id="88d4c-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="88d4c-130">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="88d4c-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="88d4c-131">Legen Sie SQL_ATTR_PARAMSET_SIZE auf die Anzahl von Sätzen (S) von Parametern fest.</span><span class="sxs-lookup"><span data-stu-id="88d4c-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="88d4c-132">Legen Sie SQL_ATTR_PARAM_BIND_TYPE auf die Größe der in Schritt 1 zugeordneten Struktur fest.</span><span class="sxs-lookup"><span data-stu-id="88d4c-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="88d4c-133">Legen Sie das SQL_ATTR_PARAMS_PROCESSED_PTR-Attribut fest, um auf eine SQLUINTEGER-Variable zu zeigen und die Anzahl der verarbeiteten Parameter zu halten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="88d4c-134">Legen Sie SQL_ATTR_PARAMS_STATUS_PTR fest, um auf ein Array [S] aus SQLUSSMALLINT-Variablen zu zeigen und die Parameterstatusindikatoren zu halten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="88d4c-135">Aufrufen Sie für jede Parameter Markierung [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) , um den Datenwert des Parameters und den Daten Längen Zeiger auf die Variablen im ersten Element des Arrays mit Strukturen zu verweisen, die in Schritt 1 zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="88d4c-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="88d4c-136">Falls der Parameter ein Data-at-Execution-Parameter ist, richten Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="88d4c-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="88d4c-137">Füllen Sie das gebundene Parameterpufferarray mit Datenwerten.</span><span class="sxs-lookup"><span data-stu-id="88d4c-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="88d4c-138">Führen Sie [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) aus, um die Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88d4c-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="88d4c-139">Der Treiber führt die Anweisung S-mal aus, einmal für jeden Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="88d4c-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="88d4c-140">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="88d4c-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="88d4c-141">Senden Sie die Daten in Blöcken mithilfe von [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) und [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="88d4c-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="88d4c-142">**Hinweis** Die Spalten-und zeilenweise Bindung wird in der Regel in Verbindung mit der [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360) und [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) als mit [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399)verwendet.</span><span class="sxs-lookup"><span data-stu-id="88d4c-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d4c-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88d4c-143">See Also</span></span>  
 [<span data-ttu-id="88d4c-144">Gewusst-wie-Themen zum Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="88d4c-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
