---
title: MSSQL_ENG020598 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697953"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="31142-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="31142-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="31142-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="31142-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31142-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="31142-104">Product Name</span></span>|<span data-ttu-id="31142-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="31142-105">SQL Server</span></span>|  
|<span data-ttu-id="31142-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="31142-106">Event ID</span></span>|<span data-ttu-id="31142-107">20598</span><span class="sxs-lookup"><span data-stu-id="31142-107">20598</span></span>|  
|<span data-ttu-id="31142-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="31142-108">Event Source</span></span>|<span data-ttu-id="31142-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="31142-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="31142-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="31142-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="31142-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="31142-111">Symbolic Name</span></span>||  
|<span data-ttu-id="31142-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="31142-112">Message Text</span></span>|<span data-ttu-id="31142-113">Die Zeile wurde bei der Anwendung des replizierten Befehls auf dem Abonnenten nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="31142-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31142-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="31142-114">Explanation</span></span>  
 <span data-ttu-id="31142-115">Dieser Fehler wird bei der Transaktionsreplikation ausgegeben, wenn der Verteilungs-Agent versucht, eine Zeile auf dem Abonnenten zu aktualisieren, die Zeile jedoch gelöscht bzw. der Primärschlüssel geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="31142-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="31142-116">Standardmäßig sollten Abonnenten von Transaktionsreplikationen schreibgeschützt sein, da Änderungen nicht an den Verleger zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31142-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="31142-117">Bei der Transaktionsreplikation sollten Benutzeränderungen nur am Abonnenten vorgenommen werden, wenn aktualisierbare Abonnements oder Peer-zu-Peer-Replikationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31142-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="31142-118">Informationen zu diesen Optionen finden Sie unter [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) und [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="31142-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31142-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="31142-119">User Action</span></span>  
 <span data-ttu-id="31142-120">**So lösen Sie dieses Problem**</span><span class="sxs-lookup"><span data-stu-id="31142-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="31142-121">Wenn die Replikation fortgesetzt werden muss, während Sie den Ursprung des Fehlers ermitteln, geben Sie den Parameter **-SkipErrors 20598** für den Verteilungs-Agent an.</span><span class="sxs-lookup"><span data-stu-id="31142-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="31142-122">Hierdurch kann der Agent Änderungen auslassen, die den Fehler 20598 verursachen, und dennoch zulassen, dass andere Änderungen repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="31142-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="31142-123">Stellen Sie fest, welche Zeilen auf dem Abonnenten gelöscht wurden bzw. einen anderen Primärschlüssel aufweisen als die Zeilen auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="31142-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="31142-124">Verwenden Sie [tablediff Utility](../../tools/tablediff-utility.md) , um zu ermitteln, welche Zeilen sich in den Veröffentlichungs- und Abonnementdatenbanken unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="31142-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="31142-125">Informationen zum Verwenden dieses Hilfsprogramms finden Sie unter [Überprüfen replizierter Tabellen auf Unterschiede &#40;Replikationsprogrammierung&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="31142-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="31142-126">Verbessern Sie die Zeilen auf dem Abonnenten mithilfe des Hilfsprogramms **tablediff** oder einer anderen Methode.</span><span class="sxs-lookup"><span data-stu-id="31142-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="31142-127">(Optional) Entfernen Sie den Parameter **-SkipErrors** .</span><span class="sxs-lookup"><span data-stu-id="31142-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31142-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31142-128">See Also</span></span>  
 [<span data-ttu-id="31142-129">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="31142-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
