---
title: CLR-Integration und Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725981"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="b4f62-102">CLR-Integration und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b4f62-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="b4f62-103">Durch den `System.Transactions`-Namespace wird ein neues Transaktionsframework bereitgestellt, das voll in ADO.NET und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR (Common Language Runtime) integriert ist.</span><span class="sxs-lookup"><span data-stu-id="b4f62-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="b4f62-104">`System.Transactions` und ADO.NET greifen ineinander, um die Verwendung lokaler und verteilter Transaktionen in verwalteten Anwendungen zu erweitern und zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b4f62-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4f62-105">Eine CLR-benutzerdefinierte Prozedur (UDP) kann keine Verbindung zu dem gleichen Server herstellen, auf dem sie ausgeführt wird (Loopbackverbindung), und sich in die gleiche Transaktion eintragen.</span><span class="sxs-lookup"><span data-stu-id="b4f62-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="b4f62-106">Wird ein solcher Versuch unternommen, wird die Verbindung blockiert und die Kontrolle nicht wieder an die benutzerdefinierte Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4f62-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="b4f62-107">Dies führt für die benutzerdefinierte Prozedur zu einem Timeoutfehler (Msg 1206).</span><span class="sxs-lookup"><span data-stu-id="b4f62-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="b4f62-108">Weitere Informationen zu Transaktionen und .NET Framework finden Sie in den Abschnitten zum Ausführen von Transaktionen und zur Nutzung von Transaktionen im .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="b4f62-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4f62-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b4f62-109">In This Section</span></span>  
 [<span data-ttu-id="b4f62-110">Transaktionshöherstufung</span><span class="sxs-lookup"><span data-stu-id="b4f62-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="b4f62-111">Beschreibt die Möglichkeit der Höherstufung von Transaktionen und die Verwendung dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="b4f62-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="b4f62-112">Zugriff auf die aktuelle Transaktion</span><span class="sxs-lookup"><span data-stu-id="b4f62-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="b4f62-113">Beschreibt, wie auf eine Transaktion, die gerade auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prozessintern ausgeführt wird, zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b4f62-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="b4f62-114">Verwenden von 'System.Transactions'</span><span class="sxs-lookup"><span data-stu-id="b4f62-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="b4f62-115">Beschreibt, wie die `System.Transactions`-Anwendungsprogrammierschnittstelle (API) in der verwalteten Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4f62-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="b4f62-116">Lebensdauer von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b4f62-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="b4f62-117">Beschreibt den Unterschied in der Lebensdauer von Transaktionen, die in [!INCLUDE[tsql](../../includes/tsql-md.md)]-gespeicherten Prozeduren gestartet wurden, und Transaktionen, die in CLR-Anwendungen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="b4f62-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f62-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4f62-118">See Also</span></span>  
 [<span data-ttu-id="b4f62-119">Data Access from CLR Database Objects</span><span class="sxs-lookup"><span data-stu-id="b4f62-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
