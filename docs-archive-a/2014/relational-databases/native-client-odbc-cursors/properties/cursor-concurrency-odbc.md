---
title: Cursor Parallelität (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620342"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="162ad-102">Cursorparallelität (ODBC)</span><span class="sxs-lookup"><span data-stu-id="162ad-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="162ad-103">Cursorvorgänge werden, wie Cursortypen, von den von der Anwendung festgelegten Parallelitätsoptionen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="162ad-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="162ad-104">Parallelitäts Optionen werden mithilfe der Option SQL_ATTR_CONCURRENCY von [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="162ad-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="162ad-105">Es gibt folgende Parallelitätstypen:</span><span class="sxs-lookup"><span data-stu-id="162ad-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="162ad-106">Schreibgeschützt (SQL_CONCUR_READONLY)</span><span class="sxs-lookup"><span data-stu-id="162ad-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="162ad-107">Werte (SQL_CONCUR_VALUES)</span><span class="sxs-lookup"><span data-stu-id="162ad-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="162ad-108">Zeilenversion (SQL_CONCUR_ROWVER)</span><span class="sxs-lookup"><span data-stu-id="162ad-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="162ad-109">Sperre (SQL_CONCUR_LOCK)</span><span class="sxs-lookup"><span data-stu-id="162ad-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162ad-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="162ad-110">See Also</span></span>  
 [<span data-ttu-id="162ad-111">Cursoreigenschaften</span><span class="sxs-lookup"><span data-stu-id="162ad-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
