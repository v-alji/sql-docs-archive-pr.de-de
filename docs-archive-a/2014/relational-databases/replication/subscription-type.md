---
title: Abonnementtyp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699447"
---
# <a name="subscription-type"></a><span data-ttu-id="b4d38-102">Abonnementtyp</span><span class="sxs-lookup"><span data-stu-id="b4d38-102">Subscription Type</span></span>
  <span data-ttu-id="b4d38-103">Die Mergereplikation bietet zwei Abonnementtypen: Server und Client (in früheren Versionen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] als global bzw. lokal bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="b4d38-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="b4d38-104">Abonnenten mit einem Serverabonnement können:</span><span class="sxs-lookup"><span data-stu-id="b4d38-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="b4d38-105">Daten für andere Abonnenten erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b4d38-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="b4d38-106">Als alternative Synchronisierungspartner dienen.</span><span class="sxs-lookup"><span data-stu-id="b4d38-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="b4d38-107">Konflikte entsprechend einer von Ihnen festgelegten Priorität lösen.</span><span class="sxs-lookup"><span data-stu-id="b4d38-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="b4d38-108">Die meisten Abonnenten benötigen diese Funktionalität nicht und können das Clientabonnement verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4d38-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="b4d38-109">Mit Clientabonnements können immer noch Konflikte erkannt und gelöst werden, Abonnenten wird jedoch keine Priorität zugeordnet: der erste Abonnent, der eine Änderung an den Verleger sendet, gewinnt in Konflikten, die durch diese Änderung auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b4d38-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4d38-110">Nach dem Erstellen eines Abonnements kann der Abonnementtyp nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b4d38-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4d38-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b4d38-111">Options</span></span>  
 <span data-ttu-id="b4d38-112">**Abonnementeigenschaften**</span><span class="sxs-lookup"><span data-stu-id="b4d38-112">**Subscription properties**</span></span>  
 <span data-ttu-id="b4d38-113">Wählen Sie für jeden Abonnenten aus der Dropdownliste in der **Abonnementtyp** -Spalte die Option **Client** oder **Server** aus.</span><span class="sxs-lookup"><span data-stu-id="b4d38-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="b4d38-114">Geben Sie für Abonnenten mit Serverabonnements in der **Priorität für Konfliktlösung** -Spalte eine Zahl zwischen 0 und 99,99 ein (je höher die Zahl, desto höher die Priorität des Abonnenten).</span><span class="sxs-lookup"><span data-stu-id="b4d38-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d38-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4d38-115">See Also</span></span>  
 <span data-ttu-id="b4d38-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b4d38-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="b4d38-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b4d38-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="b4d38-118">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="b4d38-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
