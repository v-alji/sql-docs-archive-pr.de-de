---
title: Abonnements initialisieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609072"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="f9163-102">Abonnements initialisieren</span><span class="sxs-lookup"><span data-stu-id="f9163-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="f9163-103">Bevor Abonnenten replizierte Daten empfangen können, müssen sie initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9163-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="f9163-104">Zwar ist kein Anfangsdataset erforderlich, jedoch müssen für den Abonnenten mindestens das Schema für jedes replizierte Objekt sowie alle für die Replikation benötigten Metadatentabellen und -prozeduren vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="f9163-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9163-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f9163-105">Options</span></span>  
 <span data-ttu-id="f9163-106">**Abonnementeigenschaften**</span><span class="sxs-lookup"><span data-stu-id="f9163-106">**Subscription properties**</span></span>  
 <span data-ttu-id="f9163-107">Aktivieren Sie dieses Kontrollkästchen in der **Initialisieren** -Spalte für jeden Abonnenten, für den ein Anfangsdataset erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9163-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="f9163-108">Wenn das Kontrollkästchen deaktiviert ist, werden nur die Metadaten und Prozeduren für die Replikation initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f9163-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="f9163-109">Weitere Informationen über das Initialisieren eines Abonnements ohne Momentaufnahmen finden Sie unter [Initialisieren eines Transaktionsabonnements ohne Momentaufnahme](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="f9163-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="f9163-110">Wählen Sie aus der Dropdownliste in der **Initialisierungszeitpunkt** -Spalte die Option **Sofort** aus, wenn die Momentaufnahmedateien vom Merge- oder Verteilungs-Agent unmittelbar nach dem Abschließen des Assistenten an den Abonnenten übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f9163-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="f9163-111">Wählen Sie **Bei der ersten Synchronisierung** aus, wenn die Dateien bei der nächsten laut Zeitplan festgelegten Ausführung der Momentaufnahme übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f9163-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="f9163-112">Die Option **Sofort** steht für Pullabonnements in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f9163-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="f9163-113">Da der Merge-Agent und der Verteilungs-Agent für Instanzen von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]nicht ausgeführt werden können, muss das Abonnement durch eine andere Methode initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9163-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9163-114">Der Assistent fordert möglicherweise zur Eingabe einer Verbindung mit dem Verteiler auf, um den entsprechenden Auftrag für den Verteilungs- oder Merge-Agent zu starten.</span><span class="sxs-lookup"><span data-stu-id="f9163-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9163-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9163-115">See Also</span></span>  
 <span data-ttu-id="f9163-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f9163-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f9163-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f9163-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="f9163-118">[Initialize a Subscription](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f9163-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="f9163-119">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="f9163-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
