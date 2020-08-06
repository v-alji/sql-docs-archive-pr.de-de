---
title: SQLCancel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616994"
---
# <a name="sqlcancel"></a><span data-ttu-id="01859-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="01859-102">SQLCancel</span></span>
  <span data-ttu-id="01859-103">Das [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) -Thema besagt, dass in ODBC 2. x, wenn eine Anwendung aufruft, `SQLCancel` Wenn keine Verarbeitung in der Anweisung ausgeführt wird, `SQLCancel` denselben Effekt hat wie `SQLFreeStmt` bei der `SQL_CLOSE` -Option. dieses Verhalten wird nur aus Gründen der Vollständigkeit definiert, und Anwendungen sollten `SQLFreeStmt` oder aufrufen `SQLCloseCursor` , um Cursor zu schließen.</span><span class="sxs-lookup"><span data-stu-id="01859-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="01859-104">Aber auch wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anwendung die ODBC API-Version auf 3.5.x oder höher festlegt, verwendet die `SQLCancel`-Funktion das ODBC 2.x-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="01859-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01859-105">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01859-105">See Also</span></span>  
 <span data-ttu-id="01859-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="01859-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="01859-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="01859-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
