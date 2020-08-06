---
title: Verwenden SQL Server Standard Resultsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616063"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="d1858-102">Verwenden von SQL Server-Standardresultsets</span><span class="sxs-lookup"><span data-stu-id="d1858-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="d1858-103">Die standardmäßigen ODBC-Cursorattribute sind:</span><span class="sxs-lookup"><span data-stu-id="d1858-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="d1858-104">Wenn diese Attribute auf ihre Standardwerte festgelegt sind, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet der Native Client-ODBC-Treiber ein [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Standardresultset.</span><span class="sxs-lookup"><span data-stu-id="d1858-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="d1858-105">Standardresultsets können für beliebige, von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützte SQL-Anweisungen verwendet werden und stellen die effizienteste Methode für die Übertragung des gesamten Resultsets an den Client dar.</span><span class="sxs-lookup"><span data-stu-id="d1858-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="d1858-106">Einführung in die Unterstützung von Mars (Multiple Active Result Sets); Anwendungen können nun über mehr als ein aktives Standard Resultset pro Verbindung verfügen.</span><span class="sxs-lookup"><span data-stu-id="d1858-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="d1858-107">MARS ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d1858-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="d1858-108">Vor [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] unterstützten Standardresultsets nicht mehrere aktive Anweisungen über die gleiche Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d1858-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="d1858-109">Nach der Ausführung einer SQL-Anweisung über eine Verbindung akzeptiert der Server keine Befehle vom Client für diese Verbindung (außer der Anforderung zum Abbrechen des restlichen Resultsets), bis alle Zeilen im Resultset verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="d1858-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="d1858-110">Um den Rest eines teilweise verarbeiteten Resultsets abzubrechen, rufen Sie [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) oder [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) auf, wobei der *fOption* -Parameter auf SQL_CLOSE festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d1858-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="d1858-111">Um ein teilweise verarbeitetes Resultset abzuschließen und auf das vorhanden sein eines anderen Resultsets zu testen, müssen Sie [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md)aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d1858-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="d1858-112">Wenn eine ODBC-Anwendung versucht, einen Befehl für ein Verbindungs Handle durchzuführen, bevor ein Standardresultset vollständig verarbeitet wurde, generiert der-Befehl SQL_ERROR, und ein **SQLGetDiagRec** -Befehl gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="d1858-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1858-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1858-113">See Also</span></span>  
 [<span data-ttu-id="d1858-114">Implementieren von Cursorn</span><span class="sxs-lookup"><span data-stu-id="d1858-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
