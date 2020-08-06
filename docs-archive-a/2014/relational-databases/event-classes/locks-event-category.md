---
title: Sperren-Ereigniskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609897"
---
# <a name="locks-event-category"></a><span data-ttu-id="4a4fd-102">Sperren-Ereigniskategorie</span><span class="sxs-lookup"><span data-stu-id="4a4fd-102">Locks Event Category</span></span>
  <span data-ttu-id="4a4fd-103">Verwenden Sie die Ereignisklassen der Ereigniskategorie **Sperren**, um die Sperraktivitäten in einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="4a4fd-104">Diese Ereignisklassen können Ihnen die Untersuchung von Sperrproblemen erleichtern, die auftreten können, wenn Daten von mehreren Benutzern gleichzeitig gelesen und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="4a4fd-105">Da das [!INCLUDE[ssDE](../../includes/ssde-md.md)] häufig mehrere Sperren verarbeitet, kann das Erfassen der **Sperren** -Ereignisklassen während einer Ablaufverfolgung einen deutlich höheren Verarbeitungsaufwand zur Folge haben. Außerdem können dabei große Ablaufverfolgungsdateien oder -tabellen entstehen.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a4fd-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4a4fd-106">In This Section</span></span>  
  
|<span data-ttu-id="4a4fd-107">Thema</span><span class="sxs-lookup"><span data-stu-id="4a4fd-107">Topic</span></span>|<span data-ttu-id="4a4fd-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a4fd-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4a4fd-109">Deadlock Graph (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="4a4fd-110">Stellt eine XML-Beschreibung eines Deadlocks bereit.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="4a4fd-111">Lock:Acquired (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="4a4fd-112">Gibt an, dass für eine Ressource, z. B. eine Zeile in einer Tabelle, eine Sperre eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="4a4fd-113">Lock:Cancel-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="4a4fd-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="4a4fd-114">Verfolgt Sperranforderungen nach, die vor dem Einrichten der Sperre abgebrochen wurden (beispielsweise, um einen Deadlock zu verhindern).</span><span class="sxs-lookup"><span data-stu-id="4a4fd-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="4a4fd-115">Lock:Deadlock Chain (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="4a4fd-116">Überwacht, wann Deadlockbedingungen auftreten und welche Objekte betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="4a4fd-117">Lock:Deadlock (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="4a4fd-118">Verfolgt nach, wann eine Transaktion eine Sperre für eine bereits durch eine andere Transaktion gesperrte Ressource angefordert hat, wodurch ein Deadlock auftritt.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="4a4fd-119">Lock:Escalation-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="4a4fd-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="4a4fd-120">Zeigt an, dass eine differenziertere Sperre in eine gröbere Sperre konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="4a4fd-121">Lock:Released (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="4a4fd-122">Verfolgt nach, wann eine Sperre aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="4a4fd-123">Lock:Timeout &#40;timeout &#62; 0&#41; Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="4a4fd-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="4a4fd-124">Verfolgt nach, wann Sperranforderungen nicht erfüllt werden können, weil eine andere Transaktion eine blockierende Sperre für die angeforderte Ressource aufrechterhält.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="4a4fd-125">Dieses Ereignis tritt nur in Situationen auf, in denen der Wert für den Sperrtimeout größer als Null ist.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="4a4fd-126">Lock:Timeout (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="4a4fd-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="4a4fd-127">Verfolgt nach, wann Sperranforderungen nicht erfüllt werden können, weil eine andere Transaktion eine blockierende Sperre für die angeforderte Ressource aufrechterhält.</span><span class="sxs-lookup"><span data-stu-id="4a4fd-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
