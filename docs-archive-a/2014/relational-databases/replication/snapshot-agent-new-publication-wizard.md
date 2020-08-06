---
title: Momentaufnahme-Agent (Assistent für neue Veröffentlichung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622543"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="7232e-102">Momentaufnahme-Agent (Assistent für neue Veröffentlichung)</span><span class="sxs-lookup"><span data-stu-id="7232e-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="7232e-103">Der Momentaufnahme-Agent erstellt Dateien, die das Veröffentlichungsschema und die Daten enthalten, die zum Initialisieren neuer Abonnements verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7232e-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="7232e-104">Standardmäßig wird der Momentaufnahme-Agent sofort nach dem Erstellen der Veröffentlichung im Assistenten für neue Veröffentlichung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7232e-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="7232e-105">Danach wird der Agent nach einem angegebenen Zeitplan ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7232e-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="7232e-106">Ob der Agent bei jeder Ausführung neue Momentaufnahmedateien erstellt, hängt vom Typ der Replikation und den ausgewählten Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="7232e-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="7232e-107">Weitere Informationen finden Sie unter [Erstellen und Anwenden der Momentaufnahme](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="7232e-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="7232e-108">Bei Mergeveröffentlichungen, die parametrisierte Filter verwenden, müssen Sie für jede Datenpartition eine Momentaufnahme erstellen, nachdem die Veröffentlichungsmomentaufnahme abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7232e-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="7232e-109">Weitere Informationen finden Sie unter [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="7232e-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7232e-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7232e-110">Options</span></span>  
 <span data-ttu-id="7232e-111">**Momentaufnahme sofort erstellen** (Mergereplikation) oder **Momentaufnahme sofort erstellen und zum Initialisieren von Abonnements verfügbar halten** (Transaktionsreplikation)</span><span class="sxs-lookup"><span data-stu-id="7232e-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="7232e-112">Aktivieren Sie dieses Kontrollkästchen, um sofort nach dem Abschließen des Assistenten für neue Veröffentlichung eine Momentaufnahme zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7232e-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="7232e-113">Deaktivieren Sie dieses Kontrollkästchen, wenn Sie planen, die Momentaufnahmeeigenschaften im Dialogfeld **Veröffentlichungseigenschaften** vor dem Erstellen einer Momentaufnahme zu ändern, oder wenn Sie den Abonnenten ohne Momentaufnahme initialisieren werden.</span><span class="sxs-lookup"><span data-stu-id="7232e-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="7232e-114">Weitere Informationen finden Sie unter [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md)initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7232e-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7232e-115">Der Assistent fordert möglicherweise zur Eingabe einer Verbindung mit dem Verteiler auf, um den entsprechenden Auftrag für den Verteilungs- oder Merge-Agent zu starten.</span><span class="sxs-lookup"><span data-stu-id="7232e-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="7232e-116">**Ausführung des Momentaufnahme-Agents zu folgenden Zeitpunkten planen**</span><span class="sxs-lookup"><span data-stu-id="7232e-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="7232e-117">Nehmen Sie den Standardzeitplan für das Ausführen des Momentaufnahme-Agents an, oder klicken Sie auf **Ändern** , um einen Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7232e-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7232e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7232e-118">See Also</span></span>  
 <span data-ttu-id="7232e-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="7232e-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="7232e-120">[Erstellen und Anwenden der Anfangsmomentaufnahme](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="7232e-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="7232e-121">[Anzeigen und Ändern von Veröffentlichungseigenschaften](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7232e-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="7232e-122">[Initialisieren eines Abonnements mit einer Momentaufnahme](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="7232e-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="7232e-123">[Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="7232e-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="7232e-124">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="7232e-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
