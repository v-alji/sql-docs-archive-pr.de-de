---
title: Verwalten von Ereignissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695258"
---
# <a name="manage-events"></a><span data-ttu-id="699bc-102">Verwalten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="699bc-102">Manage Events</span></span>
  <span data-ttu-id="699bc-103">Sie können an eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alle Ereignismeldungen weiterleiten, die einen bestimmten Fehlerschweregrad aufweisen oder überschreiten.</span><span class="sxs-lookup"><span data-stu-id="699bc-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="699bc-104">Dies wird als *Ereignisweiterleitung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="699bc-104">This is called *event forwarding*.</span></span> <span data-ttu-id="699bc-105">Der Weiterleitungsserver ist ein dedizierter Server, bei dem es sich auch um einen Masterserver handeln kann.</span><span class="sxs-lookup"><span data-stu-id="699bc-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="699bc-106">Durch die Ereignisweiterleitung können Sie die Warnungsverwaltung für eine Gruppe von Servern zentralisieren und so die Arbeitsauslastung stark belasteter Server reduzieren.</span><span class="sxs-lookup"><span data-stu-id="699bc-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="699bc-107">Wenn ein Server Ereignisse für eine Gruppe anderer Server empfängt, wird dieser Server als *Warnungsverwaltungsserver*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="699bc-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="699bc-108">In einer Multiserverumgebung bestimmen Sie den Masterserver zum Warnungsverwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="699bc-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="699bc-109">Vorteile der Verwendung eines Warnungsverwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="699bc-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="699bc-110">Das Einrichten eines Warnungsverwaltungsservers hat u. a. folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="699bc-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="699bc-111">**Zentralisierung**.</span><span class="sxs-lookup"><span data-stu-id="699bc-111">**Centralization**.</span></span> <span data-ttu-id="699bc-112">Die zentralisierte Steuerung und eine zusammenfassende Ansicht der Ereignisse mehrerer Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sind von einem einzigen Server aus möglich.</span><span class="sxs-lookup"><span data-stu-id="699bc-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="699bc-113">**Skalierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="699bc-113">**Scalability**.</span></span> <span data-ttu-id="699bc-114">Viele physische Server können als ein einziger logischer Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="699bc-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="699bc-115">Sie können nach Bedarf Server zur Gruppe der physischen Server hinzufügen oder Server aus dieser Gruppe entfernen.</span><span class="sxs-lookup"><span data-stu-id="699bc-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="699bc-116">**Effizienz**.</span><span class="sxs-lookup"><span data-stu-id="699bc-116">**Efficiency**.</span></span> <span data-ttu-id="699bc-117">Der Konfigurationsaufwand wird reduziert, da Warnungen und Operatoren nur einmal definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="699bc-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="699bc-118">Nachteile der Verwendung eines Warnungsverwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="699bc-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="699bc-119">Das Einrichten eines Warnungsverwaltungsservers hat u. a. folgende Nachteile:</span><span class="sxs-lookup"><span data-stu-id="699bc-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="699bc-120">**Erhöhter Datenverkehr**.</span><span class="sxs-lookup"><span data-stu-id="699bc-120">**Increased traffic**.</span></span> <span data-ttu-id="699bc-121">Das Weiterleiten von Ereignissen an einen Warnungsverwaltungsserver kann den Netzwerkverkehr erhöhen.</span><span class="sxs-lookup"><span data-stu-id="699bc-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="699bc-122">Diese Erhöhung kann durch Beschränken der Ereignisweiterleitung auf Ereignisse, die einen bestimmten Schweregrad überschreiten, verringert werden.</span><span class="sxs-lookup"><span data-stu-id="699bc-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="699bc-123">**Einzelne Fehlerquelle**.</span><span class="sxs-lookup"><span data-stu-id="699bc-123">**Single point of failure**.</span></span> <span data-ttu-id="699bc-124">Wenn der Warnungsverwaltungsserver offline geschaltet wird, werden keine Warnungen für Ereignisse auf der verwalteten Servergruppe ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="699bc-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="699bc-125">**Server Auslastung**.</span><span class="sxs-lookup"><span data-stu-id="699bc-125">**Server load**.</span></span> <span data-ttu-id="699bc-126">Das Behandeln von Warnungen für die weitergeleiteten Ereignisse verursacht eine erhöhte Verarbeitungsauslastung des Warnungsverwaltungsservers.</span><span class="sxs-lookup"><span data-stu-id="699bc-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="699bc-127">Richtlinien für das Verwenden eines Warnungsverwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="699bc-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="699bc-128">Beachten Sie beim Konfigurieren eines Warnungsverwaltungsservers folgende Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="699bc-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="699bc-129">Zum Empfangen weitergeleiteter Ereignisse muss der Warnungsverwaltungsserver eine Standardinstanz von SQL Server sein.</span><span class="sxs-lookup"><span data-stu-id="699bc-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="699bc-130">Vermeiden Sie es, auf dem Warnungsverwaltungsserver Anwendungen auszuführen, die störanfällig sind oder das System stark beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="699bc-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="699bc-131">Ziehen Sie den Netzwerkverkehr in Betracht, der entsteht, wenn Sie mehrere Server für die Verwendung desselben Warnungsverwaltungsservers konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="699bc-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="699bc-132">Reduzieren Sie bei Überlastung die Anzahl der Server, die einen bestimmten Warnungsverwaltungsserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="699bc-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="699bc-133">Die Server, die in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] registriert sind, stellen die Liste der verfügbaren Server dar, die von diesem Server als Warnungsweiterleitungsserver ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="699bc-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="699bc-134">Definieren Sie Warnungen, die eine serverspezifische Antwort erfordern, auf der lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , statt sie an den Warnungsverwaltungsserver weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="699bc-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="699bc-135">Für den Warnungsverwaltungsserver bilden alle an ihn weiterleitenden Server eine logische Einheit.</span><span class="sxs-lookup"><span data-stu-id="699bc-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="699bc-136">So antwortet ein Warnungsverwaltungsserver auf dieselbe Art auf ein 605-Ereignis von Server A wie auf ein 605-Ereignis von Server B.</span><span class="sxs-lookup"><span data-stu-id="699bc-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="699bc-137">Nach dem Konfigurieren des Warnungssystems sollten Sie das Microsoft Windows-Anwendungsprotokoll auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Ereignisse hin überprüfen.</span><span class="sxs-lookup"><span data-stu-id="699bc-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="699bc-138">Fehlerbedingungen, die von der Warnungs-Engine erkannt werden, werden mit dem Quellnamen "SQL Server-Agent" in das lokale Windows-Anwendungsprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="699bc-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="699bc-139">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent beispielsweise eine E-Mail-Benachrichtigung nicht wie definiert senden kann, wird ein Ereignis im Anwendungsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="699bc-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="699bc-140">Tritt nach dem Deaktivieren einer lokal definierten Warnung ein Ereignis auf, das diese Warnung ausgelöst hätte, wird dieses Ereignis an den Warnungsverwaltungsserver weitergeleitet (sofern die Bedingung für die Warnungsweiterleitung erfüllt wird).</span><span class="sxs-lookup"><span data-stu-id="699bc-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="699bc-141">Die Weiterleitung ermöglicht es, dass lokale Überschreibungen (lokal definierte Warnungen, die auch auf dem Warnungsverwaltungsserver definiert sind) nach Bedarf des Benutzers am lokalen Standort aktiviert und deaktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="699bc-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="699bc-142">Sie können auch anfordern, dass Ereignisse immer weitergeleitet werden, selbst wenn sie auch von lokalen Warnungen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="699bc-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="699bc-143">Beim Verwalten von Ereignissen in einer Multiserverumgebung fallen die folgenden allgemeinen Aufgaben an:</span><span class="sxs-lookup"><span data-stu-id="699bc-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="699bc-144">**So bestimmen Sie einen Server zum Warnungsverwaltungsserver**</span><span class="sxs-lookup"><span data-stu-id="699bc-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="699bc-145">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="699bc-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="699bc-146">**So definieren Sie die Antwort auf eine Warnung**</span><span class="sxs-lookup"><span data-stu-id="699bc-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="699bc-147">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="699bc-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="699bc-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="699bc-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="699bc-149">Ausführen von ereignisgesteuerten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="699bc-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="699bc-150">Sie können einen Auftrag so definieren, dass er als Antwort auf eine Warnung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="699bc-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="699bc-151">Sie können beispielsweise einen Auftrag ausführen, der ein von einer Warnung erkanntes Problem behebt oder weiter diagnostiziert.</span><span class="sxs-lookup"><span data-stu-id="699bc-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="699bc-152">Da ein Auftrag ein Ereignis auslösen kann, sollten Sie darauf achten, keine rekursive Schleife aus Warnungen und Aufträgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="699bc-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699bc-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="699bc-153">See Also</span></span>  
 [<span data-ttu-id="699bc-154">sys.sysMeldungen &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="699bc-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
