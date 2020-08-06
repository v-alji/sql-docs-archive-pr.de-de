---
title: MSSQLSERVER_1205 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607813"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="4dd00-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="4dd00-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="4dd00-103">Details</span><span class="sxs-lookup"><span data-stu-id="4dd00-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4dd00-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4dd00-104">Product Name</span></span>|<span data-ttu-id="4dd00-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4dd00-105">SQL Server</span></span>|  
|<span data-ttu-id="4dd00-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4dd00-106">Event ID</span></span>|<span data-ttu-id="4dd00-107">1205</span><span class="sxs-lookup"><span data-stu-id="4dd00-107">1205</span></span>|  
|<span data-ttu-id="4dd00-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4dd00-108">Event Source</span></span>|<span data-ttu-id="4dd00-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4dd00-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4dd00-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4dd00-110">Component</span></span>|<span data-ttu-id="4dd00-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4dd00-111">SQLEngine</span></span>|  
|<span data-ttu-id="4dd00-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4dd00-112">Symbolic Name</span></span>|<span data-ttu-id="4dd00-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="4dd00-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="4dd00-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4dd00-114">Message Text</span></span>|<span data-ttu-id="4dd00-115">Die Transaktion (Prozess-ID %d) befand sich auf %.\*ls Ressourcen aufgrund eines anderen Prozesses in einer Deadlocksituation und wurde als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="4dd00-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="4dd00-116">Führen Sie die Transaktion erneut aus.</span><span class="sxs-lookup"><span data-stu-id="4dd00-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4dd00-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4dd00-117">Explanation</span></span>  
 <span data-ttu-id="4dd00-118">Auf Ressourcen wird für separate Transaktionen in einer Reihenfolge zugegriffen, die zu einem Konflikt führt und einen Deadlock verursacht.</span><span class="sxs-lookup"><span data-stu-id="4dd00-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="4dd00-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4dd00-119">For example:</span></span>  
  
-   <span data-ttu-id="4dd00-120">Transaction1 aktualisiert **Table1.Row1** und Transaction2 aktualisiert **Table2.Row2**.</span><span class="sxs-lookup"><span data-stu-id="4dd00-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="4dd00-121">Transaction1 versucht **Table2.Row2** zu aktualisieren. Transaction1 wird jedoch blockiert, weil für Transaction2 noch kein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4dd00-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="4dd00-122">Nun versucht Transaction2, **Table1.Row1** zu aktualisieren. Transaction2 wird jedoch blockiert, weil für Transaction1 noch kein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4dd00-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="4dd00-123">Es kommt zu einem Deadlock, weil von Transaction1 auf die Beendigung von Transaction2 gewartet wird, während gleichzeitig von Transaction2 auf die Beendigung von Transaction1 gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="4dd00-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="4dd00-124">Das System erkennt diesen Deadlock und wählt eine der beteiligten Transaktionen als „Opfer“ aus. Es wird diese Meldung ausgegeben, und für die Transaktion des Opfers wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4dd00-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4dd00-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4dd00-125">User Action</span></span>  
 <span data-ttu-id="4dd00-126">Führen Sie die Transaktion erneut aus.</span><span class="sxs-lookup"><span data-stu-id="4dd00-126">Execute the transaction again.</span></span> <span data-ttu-id="4dd00-127">Sie können auch die Anwendung überarbeiten, um Deadlocks zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4dd00-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="4dd00-128">Die Transaktion, die als Opfer ausgewählt wurde, kann erneut ausgeführt werden und wird wahrscheinlich erfolgreich verlaufen, je nachdem, welche Vorgänge gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4dd00-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="4dd00-129">Wenn Sie Deadlocks verhindern oder vermeiden möchten, sollten alle Transaktionszugriffszeilen in derselben Reihenfolge (**Table1** und dann **Table2**) vorliegen. Auf diese Weise kann es zwar zum Blockieren kommen, ein Deadlock tritt jedoch nicht auf.</span><span class="sxs-lookup"><span data-stu-id="4dd00-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
