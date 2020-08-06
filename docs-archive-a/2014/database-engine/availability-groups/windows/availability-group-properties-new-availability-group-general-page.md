---
title: Eigenschaften von Verfügbarkeits Gruppen und neue Verfügbarkeits Gruppe (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608861"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="eac59-102">„Eigenschaften der Verfügbarkeitsgruppe“ und „Neue Verfügbarkeitsgruppe“ (Seite „Allgemein“)</span><span class="sxs-lookup"><span data-stu-id="eac59-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="eac59-103">Dieses Thema gilt für die Registerkarte **Allgemein** des Dialogfelds **Neue Verfügbarkeitsgruppe** und des Dialogfelds **Eigenschaften der Verfügbarkeitsgruppe** .</span><span class="sxs-lookup"><span data-stu-id="eac59-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="eac59-104">Das Dialogfeld **Neue Verfügbarkeitsgruppe** ermöglicht es Ihnen, eine neue Verfügbarkeitsgruppe zu erstellen, ohne den [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)]zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="eac59-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="eac59-105">Das Dialogfeld **Eigenschaften der Verfügbarkeitsgruppe** ermöglicht es Ihnen, die Konfiguration einer vorhandenen Verfügbarkeitsgruppe anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="eac59-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="eac59-106">**So zeigen Sie Verfügbarkeitsgruppeneigenschaften an**</span><span class="sxs-lookup"><span data-stu-id="eac59-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="eac59-107">Anzeigen von Verfügbarkeitsgruppeneigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eac59-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="eac59-108">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="eac59-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="eac59-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="eac59-109">UI element list</span></span>  
 <span data-ttu-id="eac59-110">**Name der Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="eac59-110">**Availability group name**</span></span>  
 <span data-ttu-id="eac59-111">Der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="eac59-111">Name of the availability group.</span></span> <span data-ttu-id="eac59-112">Dies ist ein vom Benutzer angegebener Name, der innerhalb des Windows Server-Failoverclusters (WSFC) eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="eac59-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="eac59-113">Verfügbarkeitsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="eac59-113">Availability Databases</span></span>  
 <span data-ttu-id="eac59-114">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="eac59-114">**Database Name**</span></span>  
 <span data-ttu-id="eac59-115">Name einer Datenbank, die der Verfügbarkeitsgruppe hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="eac59-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="eac59-116">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="eac59-116">**Add**</span></span>  
 <span data-ttu-id="eac59-117">Klicken Sie, um der Verfügbarkeitsgruppe eine Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eac59-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="eac59-118">**Remove**</span><span class="sxs-lookup"><span data-stu-id="eac59-118">**Remove**</span></span>  
 <span data-ttu-id="eac59-119">Klicken Sie, um eine ausgewählte Datenbank aus der Verfügbarkeitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="eac59-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="eac59-120">Verfügbarkeitsreplikate</span><span class="sxs-lookup"><span data-stu-id="eac59-120">Availability Replicas</span></span>  
 <span data-ttu-id="eac59-121">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="eac59-121">**Server instance**</span></span>  
 <span data-ttu-id="eac59-122">Entspricht dem Servernamen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz, die dieses Replikat hostet, sowie bei einer nicht standardmäßigen Instanz dem Instanznamen.</span><span class="sxs-lookup"><span data-stu-id="eac59-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="eac59-123">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="eac59-123">**Role**</span></span>  
 <span data-ttu-id="eac59-124">**Primärer Server/verwaltete Instanz**</span><span class="sxs-lookup"><span data-stu-id="eac59-124">**Primary**</span></span>  
 <span data-ttu-id="eac59-125">Derzeit das primäre Replikat.</span><span class="sxs-lookup"><span data-stu-id="eac59-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="eac59-126">**Sekundärer Server/verwaltete Instanz**</span><span class="sxs-lookup"><span data-stu-id="eac59-126">**Secondary**</span></span>  
 <span data-ttu-id="eac59-127">Derzeit ein sekundäres Replikat.</span><span class="sxs-lookup"><span data-stu-id="eac59-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="eac59-128">**Wird aufgelöst**</span><span class="sxs-lookup"><span data-stu-id="eac59-128">**Resolving**</span></span>  
 <span data-ttu-id="eac59-129">Die Replikatrolle wird derzeit zur primären oder sekundären Rolle aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="eac59-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="eac59-130">**Verfügbarkeitsmodus**</span><span class="sxs-lookup"><span data-stu-id="eac59-130">**Availability Mode**</span></span>  
 <span data-ttu-id="eac59-131">Der Verfügbarkeitsmodus des Replikats. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="eac59-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="eac59-132">**Asynchroner Commit**</span><span class="sxs-lookup"><span data-stu-id="eac59-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="eac59-133">Das primäre Replikat kann einen Commit für Transaktionen ausführen, ohne das Schreiben des Protokolls auf den Datenträger durch das sekundäre Replikat abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="eac59-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="eac59-134">**Synchroner Commit**</span><span class="sxs-lookup"><span data-stu-id="eac59-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="eac59-135">Das primäre Replikat wartet mit dem Ausführen des Commits für eine bestimmte Transaktion, bis das sekundäre Replikat die Transaktion auf den Datenträger geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="eac59-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="eac59-136">Weitere Informationen finden Sie unter [Verfügbarkeits Modi (AlwaysOn-Verfügbarkeitsgruppen)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="eac59-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="eac59-137">**Failovermodus**</span><span class="sxs-lookup"><span data-stu-id="eac59-137">**Failover Mode**</span></span>  
 <span data-ttu-id="eac59-138">Der Failovermodus des Replikats. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="eac59-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="eac59-139">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="eac59-139">**Automatic**</span></span>  
 <span data-ttu-id="eac59-140">Automatisches Failover.</span><span class="sxs-lookup"><span data-stu-id="eac59-140">Automatic failover.</span></span> <span data-ttu-id="eac59-141">Das Replikat ist ein Ziel für automatische Failover.</span><span class="sxs-lookup"><span data-stu-id="eac59-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="eac59-142">Diese Option wird nur unterstützt, wenn der Verfügbarkeitsmodus auf synchrone Commits festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="eac59-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="eac59-143">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="eac59-143">**Manual**</span></span>  
 <span data-ttu-id="eac59-144">Manuelles Failover.</span><span class="sxs-lookup"><span data-stu-id="eac59-144">Manual failover.</span></span> <span data-ttu-id="eac59-145">Ein Failover des Replikats kann nur manuell vom Datenbankadministrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eac59-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="eac59-146">**Verbindungen in primärer Rolle**</span><span class="sxs-lookup"><span data-stu-id="eac59-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="eac59-147">Der unterstützte Clientverbindungstyp, wenn das Replikat die primäre Rolle besitzt.</span><span class="sxs-lookup"><span data-stu-id="eac59-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="eac59-148">**Alle Verbindungen zulassen**</span><span class="sxs-lookup"><span data-stu-id="eac59-148">**Allow all connections**</span></span>  
 <span data-ttu-id="eac59-149">Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="eac59-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="eac59-150">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eac59-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="eac59-151">**Verbindungen mit Lese-/Schreibzugriff zulassen**</span><span class="sxs-lookup"><span data-stu-id="eac59-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="eac59-152">Verbindungen, bei denen die Verbindungseigenschaft für den Anwendungszweck auf **ReadOnly** festgelegt ist, werden nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="eac59-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="eac59-153">Wenn die Eigenschaft für die Anwendungsabsicht auf **ReadWrite** festgelegt ist oder keine Verbindungseigenschaft für die Anwendungsabsicht festgelegt wurde, wird die Verbindung zugelassen.</span><span class="sxs-lookup"><span data-stu-id="eac59-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="eac59-154">Weitere Informationen zur Verbindungseigenschaft für die Anwendungsabsicht finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="eac59-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="eac59-155">**Lesbares sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="eac59-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="eac59-156">Gibt an, ob ein Verfügbarkeitsreplikat, das die sekundäre Rolle ausführt (also einem sekundären Replikat entspricht), Verbindungen von Clients zulassen kann. Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="eac59-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="eac59-157">**Nein**</span><span class="sxs-lookup"><span data-stu-id="eac59-157">**No**</span></span>  
 <span data-ttu-id="eac59-158">Es werden keine direkten Verbindungen mit sekundären Datenbanken dieses Replikats zugelassen.</span><span class="sxs-lookup"><span data-stu-id="eac59-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="eac59-159">Sie sind für den Lesezugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eac59-159">They are not available for read access.</span></span> <span data-ttu-id="eac59-160">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eac59-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="eac59-161">**Nur beabsichtigte Lesevorgänge**</span><span class="sxs-lookup"><span data-stu-id="eac59-161">**Read-intent only**</span></span>  
 <span data-ttu-id="eac59-162">Es sind nur direkte, schreibgeschützte Verbindungen mit sekundären Datenbanken dieses Replikats zulässig.</span><span class="sxs-lookup"><span data-stu-id="eac59-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="eac59-163">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eac59-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="eac59-164">**Ja**</span><span class="sxs-lookup"><span data-stu-id="eac59-164">**Yes**</span></span>  
 <span data-ttu-id="eac59-165">Alle Verbindungen zu sekundären Datenbanken dieses Replikats sind zugelassen, aber nur für Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="eac59-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="eac59-166">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eac59-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="eac59-167">**Sitzungstimeout (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="eac59-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="eac59-168">Die Anzahl der Sekunden für das Sitzungstimeout auf diesem Replikat.</span><span class="sxs-lookup"><span data-stu-id="eac59-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="eac59-169">**Endpunkt-URL**</span><span class="sxs-lookup"><span data-stu-id="eac59-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="eac59-170">Die URL des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="eac59-170">The URL of the endpoint.</span></span> <span data-ttu-id="eac59-171">Informationen über das Format dieser URLs finden Sie unter [Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="eac59-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="eac59-172">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="eac59-172">**Add**</span></span>  
 <span data-ttu-id="eac59-173">Klicken Sie, um ein sekundäres Replikat zur Verfügbarkeitsgruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eac59-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="eac59-174">**Remove**</span><span class="sxs-lookup"><span data-stu-id="eac59-174">**Remove**</span></span>  
 <span data-ttu-id="eac59-175">Klicken Sie, um ein sekundäres Replikat aus der Verfügbarkeitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="eac59-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac59-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eac59-176">See Also</span></span>  
 [<span data-ttu-id="eac59-177">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eac59-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
