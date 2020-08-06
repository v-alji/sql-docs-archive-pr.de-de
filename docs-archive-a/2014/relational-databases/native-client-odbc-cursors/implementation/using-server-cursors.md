---
title: Verwenden von Server Cursorn | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616065"
---
# <a name="using-server-cursors"></a><span data-ttu-id="efa2e-102">Verwenden von Servercursorn</span><span class="sxs-lookup"><span data-stu-id="efa2e-102">Using Server Cursors</span></span>
  <span data-ttu-id="efa2e-103">Wenn eine ODBC-Anwendung ODBC-Cursor Attribute auf andere als die Standardwerte festlegt, fordert der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber den Server auf, einen API-Server Cursor desselben Typs zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="efa2e-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="efa2e-104">Durch die Verwendung von API-Servercursorn wird auf dem Client Arbeitsspeicher freigegeben, und zudem kann der Netzwerkdatenverkehr zwischen dem Client und dem Server erheblich reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="efa2e-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="efa2e-105">Ein potenzieller Nachteil von API-Servercursorn liegt darin, dass sie zurzeit nicht alle SQL-Anweisungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="efa2e-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="efa2e-106">API-Servercursor können nicht verwendet werden, um Folgendes auszuführen:</span><span class="sxs-lookup"><span data-stu-id="efa2e-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="efa2e-107">Batches oder gespeicherte Prozeduren, die mehrere Resultsets zurückgeben</span><span class="sxs-lookup"><span data-stu-id="efa2e-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="efa2e-108">SELECT-Anweisungen, die die Klauseln COMPUTE, COMPUTE BY, FOR BROWSE oder INTO enthalten</span><span class="sxs-lookup"><span data-stu-id="efa2e-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="efa2e-109">Eine EXECUTE-Anweisung, die auf eine remote gespeicherte Prozedur verweist</span><span class="sxs-lookup"><span data-stu-id="efa2e-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="efa2e-110">Wenn eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] besteht, führt die Ausführung einer Anweisung mit diesen Merkmalen mithilfe eines Servercursors dazu, dass der Cursor in ein Standardresultset konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="efa2e-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="efa2e-111">Wenn eine Verbindung zu früheren Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hergestellt ist, verursacht sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="efa2e-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa2e-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efa2e-112">See Also</span></span>  
 [<span data-ttu-id="efa2e-113">Implementieren von Cursorn</span><span class="sxs-lookup"><span data-stu-id="efa2e-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
