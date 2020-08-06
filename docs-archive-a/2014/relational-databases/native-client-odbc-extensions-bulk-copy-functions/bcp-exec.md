---
title: bcp_exec | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607732"
---
# <a name="bcp_exec"></a><span data-ttu-id="39ac3-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="39ac3-102">bcp_exec</span></span>
  <span data-ttu-id="39ac3-103">Führt ein vollständiges Massenkopieren der Daten zwischen einer Datenbanktabelle und einer Benutzerdatei aus.</span><span class="sxs-lookup"><span data-stu-id="39ac3-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ac3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39ac3-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="39ac3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="39ac3-105">Arguments</span></span>  
 <span data-ttu-id="39ac3-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="39ac3-106">*hdbc*</span></span>  
 <span data-ttu-id="39ac3-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="39ac3-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="39ac3-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="39ac3-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="39ac3-109">Ein Zeiger auf DBINT.</span><span class="sxs-lookup"><span data-stu-id="39ac3-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="39ac3-110">Die **bcp_exec** -Funktion füllt DBINT mit der Anzahl der erfolgreich kopierten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="39ac3-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="39ac3-111">Wenn *pnRowsProcessed* auf NULL festgelegt ist, wird es von **bcp_exec**ignoriert.</span><span class="sxs-lookup"><span data-stu-id="39ac3-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="39ac3-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="39ac3-112">Returns</span></span>  
 <span data-ttu-id="39ac3-113">SUCCEED, SUCCEED_ASYNC oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="39ac3-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="39ac3-114">Die **bcp_exec** -Funktion gibt SUCCEED zurück, wenn alle Zeilen kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="39ac3-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="39ac3-115">**bcp_exec** gibt SUCCEED_ASYNC zurück, falls ein asynchroner Massenkopiervorgang aussteht.</span><span class="sxs-lookup"><span data-stu-id="39ac3-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="39ac3-116">**bcp_exec** gibt FAIL zurück, wenn ein vollständiger Fehler auftritt oder wenn die Anzahl der Zeilen, die Fehler generieren, den in BCPMAXERRS mithilfe von [bcp_control](bcp-control.md)angegebenen Wert erreicht.</span><span class="sxs-lookup"><span data-stu-id="39ac3-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="39ac3-117">BCPMAXERRS ist standardmäßig auf 10 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39ac3-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="39ac3-118">Die BCPMAXERRS-Option wirkt sich nur auf die Syntaxfehler aus, die vom Anbieter während des Lesens der Zeilen aus der Datendatei (und nicht der Zeilen, die an den Server gesendet werden) erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="39ac3-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="39ac3-119">Der Server bricht den Batch ab, wenn er einen Fehler in einer Zeile erkennt.</span><span class="sxs-lookup"><span data-stu-id="39ac3-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="39ac3-120">Überprüfen Sie den *pnRowsProcessed* -Parameter auf die Anzahl an erfolgreich kopierten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="39ac3-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39ac3-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="39ac3-121">Remarks</span></span>  
 <span data-ttu-id="39ac3-122">Diese Funktion kopiert Daten aus einer Datendatei in eine Datenbanktabelle oder umgekehrt, abhängig vom Wert des *eDirection* -Parameters in [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="39ac3-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="39ac3-123">Vor dem Aufrufen von **bcp_exec**rufen Sie **bcp_init** mit einem gültigen Benutzerdateinamen auf.</span><span class="sxs-lookup"><span data-stu-id="39ac3-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="39ac3-124">Andernfalls wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39ac3-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="39ac3-125">**bcp_exec** ist die einzige Massenkopierfunktion, die im Allgemeinen für eine beliebige Zeitlänge aussteht.</span><span class="sxs-lookup"><span data-stu-id="39ac3-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="39ac3-126">Es ist deshalb die einzige Massenkopierfunktion, die den asynchronen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39ac3-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="39ac3-127">Um den asynchronen Modus festzulegen, verwenden Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) , um SQL_ATTR_ASYNC_ENABLE auf SQL_ASYNC_ENABLE_ON festzulegen, bevor Sie **bcp_exec**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="39ac3-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="39ac3-128">Rufen Sie **bcp_exec** mit denselben Parametern auf, um den Vorgang auf Vollständigkeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="39ac3-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="39ac3-129">Wenn das Massenkopieren noch nicht abgeschlossen wurde, gibt **bcp_exec** SUCCEED_ASYNC zurück.</span><span class="sxs-lookup"><span data-stu-id="39ac3-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="39ac3-130">Außerdem wird in *pnRowsProcessed* eine Statuszahl der Anzahl der Zeilen zurückgegeben, die an den Server gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="39ac3-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="39ac3-131">Für die zum Server gesendeten Zeilen wird erst ein Commit ausgeführt, wenn das Ende eines Batches erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="39ac3-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="39ac3-132">Informationen zu einem Breaking Change beim Massen kopieren ab finden Sie unter [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [Durchführen von Massen Kopier Vorgängen &#40;ODBC-&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="39ac3-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39ac3-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39ac3-133">Example</span></span>  
 <span data-ttu-id="39ac3-134">Im folgenden Beispiel wird die Verwendung von **bcp_exec**veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="39ac3-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="39ac3-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39ac3-135">See Also</span></span>  
 [<span data-ttu-id="39ac3-136">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="39ac3-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
