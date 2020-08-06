---
title: Freigeben eines Anweisungs Handles | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608602"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="859a7-102">Freigeben eines Anweisungshandles</span><span class="sxs-lookup"><span data-stu-id="859a7-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="859a7-103">Es ist effizienter, Anweisungshandles wieder zu verwenden, als sie zu löschen und neu zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="859a7-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="859a7-104">Vor dem Ausführen einer neuen SQL-Anweisung für ein Anweisungshandle sollten Anwendungen überprüfen, ob die aktuellen Anweisungseinstellungen korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="859a7-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="859a7-105">Dazu zählen beispielsweise Anweisungsattribute, Parameterbindungen und Resultsetbindungen.</span><span class="sxs-lookup"><span data-stu-id="859a7-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="859a7-106">Im Allgemeinen müssen die Bindung von Parametern und Resultsets für die alte SQL-Anweisung aufgehoben werden, indem [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) mit den Optionen SQL_RESET_PARAMS und SQL_UNBIND aufgerufen und dann für die neue SQL-Anweisung erneut gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="859a7-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="859a7-107">Wenn die Anwendung die Verwendung der-Anweisung abgeschlossen hat, wird [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) aufgerufen, um die-Anweisung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="859a7-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="859a7-108">Beachten Sie, dass **SQLDisconnect** automatisch alle-Anweisungen für eine Verbindung freigibt.</span><span class="sxs-lookup"><span data-stu-id="859a7-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859a7-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="859a7-109">See Also</span></span>  
 [<span data-ttu-id="859a7-110">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="859a7-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
