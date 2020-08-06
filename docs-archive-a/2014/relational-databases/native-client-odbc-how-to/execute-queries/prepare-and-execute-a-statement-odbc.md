---
title: Vorbereiten und Ausführen einer Anweisung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723810"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="d828c-102">Vorbereiten und Ausführen von Anweisungen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d828c-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="d828c-103">So bereiten Sie eine Anweisung vor und führen sie dann mehrmals aus</span><span class="sxs-lookup"><span data-stu-id="d828c-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="d828c-104">Ruft die [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360) auf, um die Anweisung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="d828c-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="d828c-105">Optional können Sie [sqlnumparser](https://go.microsoft.com/fwlink/?LinkId=58404) zum Ermitteln der Anzahl der Parameter in der vorbereiteten Anweisung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d828c-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="d828c-106">Optional führen Sie für jeden Parameter in der vorbereiteten Anweisung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d828c-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="d828c-107">Aufrufen von [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) zum Abrufen von Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="d828c-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="d828c-108">Binden Sie jeden Parameter mithilfe von [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md)an eine Programm Variable.</span><span class="sxs-lookup"><span data-stu-id="d828c-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="d828c-109">Richten Sie alle Data-at-Execution-Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="d828c-110">Für jede Ausführung einer vorbereiteten Anweisung gilt:</span><span class="sxs-lookup"><span data-stu-id="d828c-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d828c-111">Wenn die Anweisung über Parametermarkierungen verfügt, fügen Sie die Datenwerte in den gebundenen Parameterpuffer ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="d828c-112">Ruft [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) auf, um die vorbereitete Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d828c-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="d828c-113">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="d828c-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d828c-114">Senden Sie die Daten in Blöcken mithilfe von [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) und [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="d828c-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="d828c-115">So bereiten Sie eine Anweisung mit spaltenweiser Parameterbindung vor</span><span class="sxs-lookup"><span data-stu-id="d828c-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="d828c-116">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="d828c-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="d828c-117">Legen Sie SQL_ATTR_PARAMSET_SIZE auf die Anzahl von Sätzen (S) von Parametern fest.</span><span class="sxs-lookup"><span data-stu-id="d828c-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="d828c-118">Legen Sie SQL_ATTR_PARAM_BIND_TYPE auf SQL_PARAMETER_BIND_BY_COLUMN fest.</span><span class="sxs-lookup"><span data-stu-id="d828c-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="d828c-119">Legen Sie das SQL_ATTR_PARAMS_PROCESSED_PTR-Attribut fest, um auf eine SQLUINTEGER-Variable zu zeigen und die Anzahl der verarbeiteten Parameter zu halten.</span><span class="sxs-lookup"><span data-stu-id="d828c-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="d828c-120">Legen Sie das SQL_ATTR_PARAMS_STATUS_PTR-Attribut fest, sodass es auf ein Array mit S SQLUSSMALLINT-Variablen zeigt, welche die Parameterstatusindikatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="d828c-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="d828c-121">Erstellen Sie SQLPrepare, um die Anweisung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="d828c-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="d828c-122">Optional können Sie [sqlnumparser](https://go.microsoft.com/fwlink/?LinkId=58404) zum Ermitteln der Anzahl der Parameter in der vorbereiteten Anweisung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d828c-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="d828c-123">Optional können Sie für jeden Parameter in der vorbereiteten Anweisung SQLDescribeParam aufrufen, um Parameterinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d828c-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="d828c-124">Führen Sie folgende Aktionen für jeden Parametermarker durch:</span><span class="sxs-lookup"><span data-stu-id="d828c-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="d828c-125">Weisen Sie ein Array mit S-Parameterpuffern zu, um Datenwerte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d828c-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="d828c-126">Weisen Sie ein Array mit S-Parameterpuffern zu, um Datenlängen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d828c-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="d828c-127">Aufrufen von SQLBindParameter, um die Parameter Datenwert-und Daten Längen Arrays an den Anweisungs Parameter zu binden.</span><span class="sxs-lookup"><span data-stu-id="d828c-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="d828c-128">Falls der Parameter ein Data-at-Execution-Textparameter oder –Imageparameter ist, richten Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="d828c-129">Wenn Data-at-Execution-Parameter verwendet werden, richten Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="d828c-130">Für jede Ausführung einer vorbereiteten Anweisung gilt:</span><span class="sxs-lookup"><span data-stu-id="d828c-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d828c-131">Fügen Sie die S Datenwerte und S Datenlängen in die gebundenen Parameterarrays ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="d828c-132">Rufen Sie SQLExecute auf, um die vorbereitete Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d828c-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="d828c-133">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt SQLExecute SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="d828c-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d828c-134">Senden Sie die Daten in Blöcken mithilfe von SQLParamData und SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="d828c-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="d828c-135">So bereiten Sie eine Anweisung mit zeilenweiser Parameterbindung vor</span><span class="sxs-lookup"><span data-stu-id="d828c-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="d828c-136">Ordnen Sie ein Array [S] von Strukturen zu, wobei S der Anzahl von Parametersätzen entspricht.</span><span class="sxs-lookup"><span data-stu-id="d828c-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="d828c-137">Die Struktur verfügt über ein Element für jeden Parameter, und jedes Element verfügt über zwei Teile:</span><span class="sxs-lookup"><span data-stu-id="d828c-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="d828c-138">Der erste Teil ist eine Variable des entsprechenden Datentyps zum Speichern der Parameterdaten.</span><span class="sxs-lookup"><span data-stu-id="d828c-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="d828c-139">Der zweite Teil ist eine SQLINTEGER-Variable zum Speichern des Statusindikators.</span><span class="sxs-lookup"><span data-stu-id="d828c-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="d828c-140">Rufen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um die folgenden Attribute festzulegen:</span><span class="sxs-lookup"><span data-stu-id="d828c-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="d828c-141">Legen Sie SQL_ATTR_PARAMSET_SIZE auf die Anzahl von Sätzen (S) von Parametern fest.</span><span class="sxs-lookup"><span data-stu-id="d828c-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="d828c-142">Legen Sie SQL_ATTR_PARAM_BIND_TYPE auf die Größe der in Schritt 1 zugeordneten Struktur fest.</span><span class="sxs-lookup"><span data-stu-id="d828c-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="d828c-143">Legen Sie das SQL_ATTR_PARAMS_PROCESSED_PTR-Attribut fest, um auf eine SQLUINTEGER-Variable zu zeigen und die Anzahl der verarbeiteten Parameter zu halten.</span><span class="sxs-lookup"><span data-stu-id="d828c-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="d828c-144">Legen Sie das SQL_ATTR_PARAMS_STATUS_PTR-Attribut fest, sodass es auf ein Array mit S SQLUSSMALLINT-Variablen zeigt, welche die Parameterstatusindikatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="d828c-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="d828c-145">Erstellen Sie SQLPrepare, um die Anweisung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="d828c-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="d828c-146">Aufrufen Sie für jede Parameter Markierung SQLBindParameter, um den Parameter Datenwert und den Daten Längen Zeiger auf die Variablen im ersten Element des Arrays mit Strukturen zu verweisen, die in Schritt 1 zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="d828c-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="d828c-147">Falls der Parameter ein Data-at-Execution-Parameter ist, richten Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="d828c-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="d828c-148">Für jede Ausführung einer vorbereiteten Anweisung gilt:</span><span class="sxs-lookup"><span data-stu-id="d828c-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d828c-149">Füllen Sie das gebundene Parameterpufferarray mit Datenwerten.</span><span class="sxs-lookup"><span data-stu-id="d828c-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="d828c-150">Rufen Sie SQLExecute auf, um die vorbereitete Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d828c-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="d828c-151">Der Treiber führt die SQL-Anweisung S Mal aus, einmal für jeden Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="d828c-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="d828c-152">Wenn Data-at-Execution-Eingabeparameter verwendet werden, gibt SQLExecute SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="d828c-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d828c-153">Senden Sie die Daten in Blöcken mithilfe von SQLParamData und SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="d828c-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d828c-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d828c-154">See Also</span></span>  
 [<span data-ttu-id="d828c-155">Gewusst-wie-Themen zum Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="d828c-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
