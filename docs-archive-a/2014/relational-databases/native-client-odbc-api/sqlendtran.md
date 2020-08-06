---
title: SQLEndTran | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLEndTran function
ms.assetid: 95cff841-c2d5-4e1e-a18d-f3d4696a5b85
author: rothja
ms.author: jroth
ms.openlocfilehash: e5d44756131b6133baec69e34da11055a965e2da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698181"
---
# <a name="sqlendtran"></a><span data-ttu-id="35e1f-102">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="35e1f-102">SQLEndTran</span></span>
  <span data-ttu-id="35e1f-103">In der Standardeinstellung schließt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber den mit einer Anweisung verknüpften Cursor, wenn **SQLEndTran** für einen Vorgang ein Commit oder Rollback ausführt.</span><span class="sxs-lookup"><span data-stu-id="35e1f-103">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver closes a statement's associated cursor when **SQLEndTran** commits or rolls back an operation.</span></span> <span data-ttu-id="35e1f-104">Servercursor werden nicht geschlossen, wenn sie statisch sind.</span><span class="sxs-lookup"><span data-stu-id="35e1f-104">Server cursors are closed unless they are static.</span></span> <span data-ttu-id="35e1f-105">Wenn **SQLEndTran** für einen Vorgang ein Commit oder Rollback ausführt, wird das Verhalten des mit der Anweisung verknüpften Cursors vom Wert des treiberspezifischen ODBC-Verbindungsattributs SQL_COPT_SS_PRESERVE_CURSORS bestimmt, das von [SQLSetConnectAttr](sqlsetconnectattr.md)festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="35e1f-105">When **SQLEndTran** commits or rolls back an operation, the behavior of the statement's associated cursor is determined by the value of the driver-specific ODBC connection attribute SQL_COPT_SS_PRESERVE_CURSORS, set by [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e1f-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35e1f-106">See Also</span></span>  
 <span data-ttu-id="35e1f-107">[Details zur ODBC-API-Implementierung](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="35e1f-107">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 [<span data-ttu-id="35e1f-108">SQLEndTran-Funktion</span><span class="sxs-lookup"><span data-stu-id="35e1f-108">SQLEndTran Function</span></span>](https://go.microsoft.com/fwlink/?LinkId=59342)  
  
  
