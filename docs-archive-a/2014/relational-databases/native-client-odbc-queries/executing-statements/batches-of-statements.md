---
title: Batches von Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608616"
---
# <a name="batches-of-statements"></a><span data-ttu-id="8958a-102">Batches von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8958a-102">Batches of Statements</span></span>
  <span data-ttu-id="8958a-103">Ein Batch von- [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisungen enthält zwei oder mehr-Anweisungen, getrennt durch ein Semikolon (;), in eine einzelne Zeichenfolge, die an die **SQLExecDirect** -oder [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360)weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8958a-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="8958a-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8958a-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="8958a-105">Batches können effizienter als das Senden getrennter Anweisungen sein, da der Netzwerkdatenverkehr dadurch meist reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="8958a-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="8958a-106">Verwenden Sie [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) , um auf dem nächsten Resultset positioniert zu werden, wenn es mit dem aktuellen Resultset abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8958a-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="8958a-107">Batches können immer dann verwendet werden, wenn die ODBC-Cursorattribute auf die Standardeinstellungen eines schreibgeschützten Vorwärtscursors mit der Rowsetgröße 1 festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="8958a-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="8958a-108">Wenn ein Batch ausgeführt wird und Servercursor für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet werden, dann wird der Servercursor implizit in ein Standardresultset umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="8958a-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="8958a-109">**SQLExecDirect** oder **SQLExecute** geben SQL_SUCCESS_WITH_INFO zurück, und ein **SQLGetDiagRec** -Befehl gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="8958a-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="8958a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8958a-110">See Also</span></span>  
 [<span data-ttu-id="8958a-111">Ausführen von Anweisungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="8958a-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
