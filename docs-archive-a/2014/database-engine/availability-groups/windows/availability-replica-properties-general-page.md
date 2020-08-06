---
title: Eigenschaften des Verfügbarkeitsreplikats (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725006"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="be52e-102">Eigenschaften des Verfügbarkeitsreplikats (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="be52e-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="be52e-103">Verwenden Sie dieses Dialogfeld, um die Eigenschaften eines Verfügbarkeitsreplikats anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="be52e-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="be52e-104">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="be52e-104">Task List</span></span>  
 <span data-ttu-id="be52e-105">**So zeigen Sie Verfügbarkeitsreplikateigenschaften an**</span><span class="sxs-lookup"><span data-stu-id="be52e-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="be52e-106">Anzeigen von Verfügbarkeitsreplikateigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be52e-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="be52e-107">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="be52e-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="be52e-108">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="be52e-108">UI element list</span></span>  
 <span data-ttu-id="be52e-109">**Name der Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="be52e-109">**Availability group name**</span></span>  
 <span data-ttu-id="be52e-110">Der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="be52e-110">Name of the availability group.</span></span> <span data-ttu-id="be52e-111">Dies ist ein vom Benutzer angegebener Name, der innerhalb des Windows Server-Failoverclusters (WSFC) eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="be52e-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="be52e-112">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="be52e-112">**Server instance**</span></span>  
 <span data-ttu-id="be52e-113">Entspricht dem Servernamen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz, die dieses Replikat hostet, sowie bei einer nicht standardmäßigen Instanz dem Instanznamen.</span><span class="sxs-lookup"><span data-stu-id="be52e-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="be52e-114">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="be52e-114">**Role**</span></span>  
 <span data-ttu-id="be52e-115">**Primärer Server/verwaltete Instanz**</span><span class="sxs-lookup"><span data-stu-id="be52e-115">**Primary**</span></span>  
 <span data-ttu-id="be52e-116">Derzeit das primäre Replikat.</span><span class="sxs-lookup"><span data-stu-id="be52e-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="be52e-117">**Sekundärer Server/verwaltete Instanz**</span><span class="sxs-lookup"><span data-stu-id="be52e-117">**Secondary**</span></span>  
 <span data-ttu-id="be52e-118">Derzeit ein sekundäres Replikat.</span><span class="sxs-lookup"><span data-stu-id="be52e-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="be52e-119">**Wird aufgelöst**</span><span class="sxs-lookup"><span data-stu-id="be52e-119">**Resolving**</span></span>  
 <span data-ttu-id="be52e-120">Die Replikatrolle wird derzeit zur primären oder sekundären Rolle aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="be52e-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="be52e-121">**Verfügbarkeitsmodus**</span><span class="sxs-lookup"><span data-stu-id="be52e-121">**Availability mode**</span></span>  
 <span data-ttu-id="be52e-122">Der Verfügbarkeitsmodus des Replikats. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="be52e-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="be52e-123">**Asynchroner Commit**</span><span class="sxs-lookup"><span data-stu-id="be52e-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="be52e-124">Das primäre Replikat kann einen Commit für Transaktionen ausführen, ohne das Schreiben des Protokolls auf den Datenträger durch das sekundäre Replikat abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="be52e-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="be52e-125">**Synchroner Commit**</span><span class="sxs-lookup"><span data-stu-id="be52e-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="be52e-126">Das primäre Replikat wartet mit dem Ausführen des Commits für eine bestimmte Transaktion, bis das sekundäre Replikat die Transaktion auf den Datenträger geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="be52e-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="be52e-127">Weitere Informationen finden Sie unter [Verfügbarkeits Modi (AlwaysOn-Verfügbarkeitsgruppen)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="be52e-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="be52e-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="be52e-128">**Failover mode**</span></span>  
 <span data-ttu-id="be52e-129">Der Failovermodus des Replikats. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="be52e-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="be52e-130">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="be52e-130">**Automatic**</span></span>  
 <span data-ttu-id="be52e-131">Automatisches Failover.</span><span class="sxs-lookup"><span data-stu-id="be52e-131">Automatic failover.</span></span> <span data-ttu-id="be52e-132">Das Replikat ist ein Ziel für automatische Failover.</span><span class="sxs-lookup"><span data-stu-id="be52e-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="be52e-133">Diese Option wird nur unterstützt, wenn der Verfügbarkeitsmodus auf synchrone Commits festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="be52e-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="be52e-134">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="be52e-134">**Manual**</span></span>  
 <span data-ttu-id="be52e-135">Manuelles Failover.</span><span class="sxs-lookup"><span data-stu-id="be52e-135">Manual failover.</span></span> <span data-ttu-id="be52e-136">Ein Failover des Replikats kann nur manuell vom Datenbankadministrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be52e-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="be52e-137">**Verbindungen in primärer Rolle**</span><span class="sxs-lookup"><span data-stu-id="be52e-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="be52e-138">Der unterstützte Clientverbindungstyp, wenn das Replikat die primäre Rolle besitzt.</span><span class="sxs-lookup"><span data-stu-id="be52e-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="be52e-139">**Alle Verbindungen zulassen**</span><span class="sxs-lookup"><span data-stu-id="be52e-139">**Allow all connections**</span></span>  
 <span data-ttu-id="be52e-140">Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="be52e-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="be52e-141">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="be52e-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="be52e-142">**Verbindungen mit Lese-/Schreibzugriff zulassen**</span><span class="sxs-lookup"><span data-stu-id="be52e-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="be52e-143">Verbindungen, bei denen die Verbindungseigenschaft für den Anwendungszweck auf **ReadOnly** festgelegt ist, werden nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="be52e-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="be52e-144">Wenn die Eigenschaft für den Anwendungszweck auf **ReadWrite** festgelegt ist oder keine Verbindungseigenschaft für den Anwendungszweck festgelegt wurde, wird die Verbindung zugelassen.</span><span class="sxs-lookup"><span data-stu-id="be52e-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="be52e-145">**Lesbares sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="be52e-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="be52e-146">Gibt an, ob ein Verfügbarkeitsreplikat, das die sekundäre Rolle ausführt (also einem sekundären Replikat entspricht), Verbindungen von Clients zulassen kann. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="be52e-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="be52e-147">**Nein**</span><span class="sxs-lookup"><span data-stu-id="be52e-147">**No**</span></span>  
 <span data-ttu-id="be52e-148">Es werden keine direkten Verbindungen mit sekundären Datenbanken dieses Replikats zugelassen.</span><span class="sxs-lookup"><span data-stu-id="be52e-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="be52e-149">Sie sind für den Lesezugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="be52e-149">They are not available for read access.</span></span> <span data-ttu-id="be52e-150">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="be52e-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="be52e-151">**Nur beabsichtigte Lesevorgänge**</span><span class="sxs-lookup"><span data-stu-id="be52e-151">**Read-intent only**</span></span>  
 <span data-ttu-id="be52e-152">Es sind nur direkte, schreibgeschützte Verbindungen mit sekundären Datenbanken dieses Replikats zulässig.</span><span class="sxs-lookup"><span data-stu-id="be52e-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="be52e-153">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="be52e-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="be52e-154">**Ja**</span><span class="sxs-lookup"><span data-stu-id="be52e-154">**Yes**</span></span>  
 <span data-ttu-id="be52e-155">Alle Verbindungen zu sekundären Datenbanken dieses Replikats sind zugelassen, aber nur für Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="be52e-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="be52e-156">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="be52e-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="be52e-157">Weitere Informationen finden Sie unter [aktive sekundäre Replikate: lesbare sekundäre Replikate (AlwaysOn-Verfügbarkeitsgruppen)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="be52e-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="be52e-158">**Sitzungstimeout (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="be52e-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="be52e-159">Der Timeoutzeitraum in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="be52e-159">The time-out period, in seconds.</span></span> <span data-ttu-id="be52e-160">Der Timeoutzeitraum ist die maximale Zeit, die das Replikat für den Empfang einer Meldung von einem anderen Replikat abwartet, bevor die Verbindung zwischen dem primären und sekundären Replikat als fehlerhaft betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="be52e-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="be52e-161">Das Sitzungstimeout erkennt, ob sekundäre Replikate mit dem primären Replikat verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="be52e-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="be52e-162">Bei der Erkennung einer fehlerhaften Verbindung mit einem sekundären Replikat betrachtet das primäre Replikat das sekundäre Replikat als nicht synchronisiert und weist diesem den Wert NOT_SYNCHRONIZED zu.</span><span class="sxs-lookup"><span data-stu-id="be52e-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="be52e-163">Ein sekundäres Replikat versucht einfach, erneut eine Verbindung herzustellen, wenn eine fehlgeschlagene Verbindung mit dem primären Replikat erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="be52e-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be52e-164">Sitzungstimeouts verursachen keine automatischen Failovers.</span><span class="sxs-lookup"><span data-stu-id="be52e-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="be52e-165">**Endpunkt-URL**</span><span class="sxs-lookup"><span data-stu-id="be52e-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="be52e-166">Entspricht der Zeichenfolgendarstellung des vom Benutzer angegebenen Datenbankspiegelungs-Endpunkts, der von Verbindungen zwischen primären und sekundären Replikaten für die Datensynchronisierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be52e-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="be52e-167">Informationen zur Syntax von Endpunkt-URLs finden Sie unter [Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="be52e-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be52e-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be52e-168">See Also</span></span>  
 [<span data-ttu-id="be52e-169">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be52e-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
