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
# <a name="implicit-cursor-conversions-odbc"></a>Implizite Cursorkonvertierung (ODBC)
  Anwendungen können mithilfe von [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) einen Cursortyp anfordern und dann eine SQL-Anweisung ausführen, die von Server Cursorn des angeforderten Typs nicht unterstützt wird. Ein-Befehl von **SQLExecute** oder **SQLExecDirect** gibt SQL_SUCCESS_WITH_INFO zurück, und **SQLGetDiagRec** gibt Folgendes zurück:  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 Die Anwendung kann ermitteln, welcher Cursortyp jetzt verwendet wird, indem **SQLGetStmtOption** auf SQL_CURSOR_TYPE festgelegt wird. Die Cursortypkonvertierung gilt nur für eine Anweisung. Der nächste **SQLExecDirect** -oder **SQLExecute** -Vorgang wird mit den ursprünglichen Anweisungs Cursor Einstellungen durchgeführt.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Details zur Cursor Programmierung &#40;ODBC-&#41;](cursor-programming-details-odbc.md)  
  
  
