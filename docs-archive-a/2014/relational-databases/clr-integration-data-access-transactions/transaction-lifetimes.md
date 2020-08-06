---
title: Transaktions Lebensdauer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725974"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="d9e09-102">Lebensdauer von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d9e09-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="d9e09-103">Es gibt einen wichtigen Unterschied zwischen Transaktionen, die in gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozeduren gestartet werden, und Transaktionen, die in verwaltetem Code gestartet werden: CLR-Code (Common Language Runtime) kann den Transaktionsstatus bei Eintritt oder Verlassen eines CLR-Aufrufs nicht aus dem Gleichgewicht bringen.</span><span class="sxs-lookup"><span data-stu-id="d9e09-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="d9e09-104">Dieser Unterschied wirkt sich wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d9e09-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="d9e09-105">Für eine in einem CLR-Rahmen gestartete Transaktion muss ein Commit oder ein Rollback ausgeführt werden, da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sonst beim Verlassen des Rahmens einen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d9e09-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="d9e09-106">Für eine äußere Transaktion kann im CLR-Code kein Commit oder Rollback ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9e09-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="d9e09-107">Wenn für eine Transaktion, die nicht in derselben Prozedur gestartet wurde, ein Commit ausgeführt wird, wird ein Laufzeitfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="d9e09-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="d9e09-108">Der Versuch, einen Rollback für eine Transaktion auszuführen, der nicht in derselben Prozedur gestartet wurde, reagiert nicht mehr, da die Transaktion nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="d9e09-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="d9e09-109">Die Transaktion reagiert nicht mehr, bis der CLR-Code den Bereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="d9e09-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="d9e09-110">Dies kann hilfreich sein, wenn Sie innerhalb der Prozedur einen Fehler erkennen und sicherstellen möchten, dass die ganze Transaktion beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9e09-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e09-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9e09-111">See Also</span></span>  
 [<span data-ttu-id="d9e09-112">CLR-Integration und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d9e09-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
