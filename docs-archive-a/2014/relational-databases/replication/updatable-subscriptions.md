---
title: Aktualisierbare Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697886"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="1b571-102">Aktualisierbare Abonnements</span><span class="sxs-lookup"><span data-stu-id="1b571-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="1b571-103">Bei der Transaktionsreplikation müssen replizierte Daten als schreibgeschützte Daten behandelt werden. Allerdings können Sie replizierte Daten auf einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Abonnenten ändern, indem Sie aktualisierbare Abonnements verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b571-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="1b571-104">Wenn Sie Daten auf dem Abonnenten ändern möchten, wählen Sie in Abhängigkeit von Ihren Anforderungen eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1b571-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="1b571-105">Aktualisierbarer Abonnementtyp</span><span class="sxs-lookup"><span data-stu-id="1b571-105">Updatable Subscription Type</span></span>|<span data-ttu-id="1b571-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1b571-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="1b571-107">Sofortige Updates</span><span class="sxs-lookup"><span data-stu-id="1b571-107">Immediate Updating</span></span>|<span data-ttu-id="1b571-108">Verleger und Abonnent müssen verbunden sein, damit Daten auf dem Abonnenten aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1b571-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="1b571-109">Verzögerte Updates über eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="1b571-109">Queued Updating</span></span>|<span data-ttu-id="1b571-110">Verleger und Abonnent müssen nicht verbunden sein, damit Daten auf dem Abonnenten aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1b571-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="1b571-111">Updates können zunächst offline vorgenommen und später dann zwischen Verleger und Abonnent synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b571-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="1b571-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1b571-112">Options</span></span>  
 <span data-ttu-id="1b571-113">**Abonnentenänderungen replizieren**</span><span class="sxs-lookup"><span data-stu-id="1b571-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="1b571-114">Aktivieren Sie das Kontrollkästchen in der **Replizieren** -Spalte für jeden Abonnenten, der in der Lage sein soll, Updates vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1b571-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="1b571-115">Für jene Abonnenten, die Updates vornehmen können, wählen Sie aus dem Dropdownlistenfeld in der **Commit auf Verleger ausführen** -Spalte die entsprechende Option aus.</span><span class="sxs-lookup"><span data-stu-id="1b571-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="1b571-116">Für ein Abonnement mit sofortigem Update wählen Sie **Commit für Änderungen gleichzeitig ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b571-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="1b571-117">Für ein Abonnement mit verzögertem Update über eine Warteschlange wählen Sie **Änderungen in die Warteschlange einreihen und Commit baldmöglichst ausführen** .</span><span class="sxs-lookup"><span data-stu-id="1b571-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b571-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b571-118">See Also</span></span>  
 <span data-ttu-id="1b571-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1b571-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="1b571-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1b571-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="1b571-121">[Abonnieren von Veröffentlichungen](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="1b571-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="1b571-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="1b571-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
