---
title: Implizite Cursor Konvertierungen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620340"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="66140-102">Implizite Cursorkonvertierung (ODBC)</span><span class="sxs-lookup"><span data-stu-id="66140-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="66140-103">Anwendungen können mithilfe von [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) einen Cursortyp anfordern und dann eine SQL-Anweisung ausführen, die von Server Cursorn des angeforderten Typs nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="66140-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="66140-104">Ein-Befehl von **SQLExecute** oder **SQLExecDirect** gibt SQL_SUCCESS_WITH_INFO zurück, und **SQLGetDiagRec** gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="66140-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="66140-105">Die Anwendung kann ermitteln, welcher Cursortyp jetzt verwendet wird, indem **SQLGetStmtOption** auf SQL_CURSOR_TYPE festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="66140-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="66140-106">Die Cursortypkonvertierung gilt nur für eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="66140-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="66140-107">Der nächste **SQLExecDirect** -oder **SQLExecute** -Vorgang wird mit den ursprünglichen Anweisungs Cursor Einstellungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="66140-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66140-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66140-108">See Also</span></span>  
 [<span data-ttu-id="66140-109">Details zur Cursor Programmierung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="66140-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
