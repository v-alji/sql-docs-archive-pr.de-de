---
title: Verwenden des AlwaysOn-Dashboards (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615593"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="d8d27-102">Verwenden des AlwaysOn-Dashboards (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d8d27-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d8d27-103">Datenbankadministratoren verwenden das AlwaysOn-Dashboard, um die Integrität einer AlwaysOn-Verfügbarkeitsgruppe und deren Verfügbarkeitsreplikaten und -datenbanken in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]in einer übersichtlichen Ansicht darzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d8d27-104">Einige der typischen Verwendungen für das AlwaysOn-Dashboard sind:</span><span class="sxs-lookup"><span data-stu-id="d8d27-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="d8d27-105">Auswählen eines Replikats für ein manuelles Failover.</span><span class="sxs-lookup"><span data-stu-id="d8d27-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="d8d27-106">Abschätzen von Datenverlust beim Erzwingen eines Failovers.</span><span class="sxs-lookup"><span data-stu-id="d8d27-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="d8d27-107">Auswerten der Datensynchronisierungsleistung.</span><span class="sxs-lookup"><span data-stu-id="d8d27-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="d8d27-108">Auswerten der Auswirkungen auf die Leistung eines sekundären Replikats mit synchronem Commit</span><span class="sxs-lookup"><span data-stu-id="d8d27-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="d8d27-109">Das AlwaysOn-Dashboard bietet wichtige Statusangaben und Leistungsindikatoren zu Verfügbarkeitsgruppen, die Ihnen Entscheidungen zu Vorgängen mit Hochverfügbarkeit anhand folgender Informationen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="d8d27-110">Replikat-Rollupstatus</span><span class="sxs-lookup"><span data-stu-id="d8d27-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="d8d27-111">Synchronisierungsmodus und -status</span><span class="sxs-lookup"><span data-stu-id="d8d27-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="d8d27-112">Geschätzter Datenverlust</span><span class="sxs-lookup"><span data-stu-id="d8d27-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="d8d27-113">Geschätzte Wiederherstellungszeit (Aufholen wiederholen)</span><span class="sxs-lookup"><span data-stu-id="d8d27-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="d8d27-114">Datenbankreplikatdetails</span><span class="sxs-lookup"><span data-stu-id="d8d27-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="d8d27-115">Synchronisierungsmodus und -status</span><span class="sxs-lookup"><span data-stu-id="d8d27-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="d8d27-116">Zeit zum Wiederherstellen des Protokolls</span><span class="sxs-lookup"><span data-stu-id="d8d27-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8d27-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d8d27-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d8d27-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8d27-118">Prerequisites</span></span>  
 <span data-ttu-id="d8d27-119">Sie müssen mit der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (Serverinstanz) verbunden sein, die entweder das primäre Verfügbarkeitsreplikat oder ein sekundäres Replikat einer Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8d27-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d8d27-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8d27-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d8d27-121">Permissions</span></span>  
 <span data-ttu-id="d8d27-122">Erfordert CONNECT-, VIEW SERVER STATE- und VIEW ANY DEFINITION-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="d8d27-123">So starten Sie das AlwaysOn-Dashboard</span><span class="sxs-lookup"><span data-stu-id="d8d27-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="d8d27-124">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her, auf der das AlwaysOn-Dashboard ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8d27-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="d8d27-125">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** , klicken Sie mit der rechten Maustaste auf den Knoten **Verfügbarkeitsgruppen** , und klicken Sie dann auf **Dashboard anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="d8d27-126">So ändern Sie AlwaysOn-dashboardoptionen</span><span class="sxs-lookup"><span data-stu-id="d8d27-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="d8d27-127">Sie können das [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Dialogfeld **Optionen** verwenden, um das Verhalten des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn-Dashboards für das automatische Aktualisieren und Aktivieren einer automatisch definierten AlwaysOn-Richtlinie zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d8d27-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="d8d27-128">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="d8d27-129">Um das Dashboard automatisch zu aktualisieren, wählen Sie im Dialogfeld **Optionen** den Befehl **Automatische Aktualisierung aktivieren**aus, geben Sie das Aktualisierungsintervall in Sekunden ein, und geben Sie dann die Häufigkeit ein, mit der der Verbindungsversuch wiederholt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8d27-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="d8d27-130">Zum Aktivieren einer benutzerdefinierten Richtlinie wählen Sie **Benutzerdefinierte AlwaysOn-Richtlinie aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d8d27-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a><span data-ttu-id="d8d27-131">Verfügbarkeits Gruppen Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d8d27-131">Availability Group Summary</span></span>  
 <span data-ttu-id="d8d27-132">Im Verfügbarkeitsgruppen-Bildschirm wird eine Zusammenfassungszeile für jede Verfügbarkeitsgruppe angezeigt, für die die verbundene Serverinstanz ein Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="d8d27-133">In diesem Bereich werden die folgenden Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="d8d27-134">**Name der Verfügbarkeits Gruppe**</span><span class="sxs-lookup"><span data-stu-id="d8d27-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="d8d27-135">Der Name einer Verfügbarkeitsgruppe, für die die verbundene Serverinstanz ein Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="d8d27-136">**Primäre Instanz**</span><span class="sxs-lookup"><span data-stu-id="d8d27-136">**Primary Instance**</span></span>  
 <span data-ttu-id="d8d27-137">Der Name der Serverinstanz, die das primäre Replikat der Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="d8d27-138">**Failovermodus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-138">**Failover Mode**</span></span>  
 <span data-ttu-id="d8d27-139">Zeigt den Failovermodus an, für den das Replikat konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="d8d27-140">Die folgenden Werte für den Failovermodus sind möglich:</span><span class="sxs-lookup"><span data-stu-id="d8d27-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="d8d27-141">**Automatisch**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-141">**Automatic**.</span></span> <span data-ttu-id="d8d27-142">Gibt an, dass ein oder mehrere Replikate im automatischen Failovermodus sind.</span><span class="sxs-lookup"><span data-stu-id="d8d27-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="d8d27-143">**Manuell**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-143">**Manual**.</span></span> <span data-ttu-id="d8d27-144">Gibt an, dass kein Replikat im automatischen Failovermodus ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="d8d27-145">**Probleme**</span><span class="sxs-lookup"><span data-stu-id="d8d27-145">**Issues**</span></span>  
 <span data-ttu-id="d8d27-146">Klicken Sie auf den Link **Probleme** , um die Problembehandlungsdokumentation für ein angegebenes Problem zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="d8d27-147">Eine Liste aller AlwaysOn-Richtlinien Probleme finden Sie unter [AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="d8d27-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d8d27-148">Klicken Sie auf die Spaltenüberschriften, um die Verfügbarkeitsgruppeninformationen nach dem Namen der Verfügbarkeitsgruppe, primärer Instanz, Failovermodus oder Problem zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="d8d27-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a> <span data-ttu-id="d8d27-149">Verfügbarkeitsgruppendetails</span><span class="sxs-lookup"><span data-stu-id="d8d27-149">Availability Group Details</span></span>  
 <span data-ttu-id="d8d27-150">Die folgenden Detailinformationen werden für die Verfügbarkeitsgruppe angezeigt, die Sie im Zusammenfassungsbildschirm auswählen:</span><span class="sxs-lookup"><span data-stu-id="d8d27-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="d8d27-151">**Status der Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="d8d27-151">**Availability group state**</span></span>  
 <span data-ttu-id="d8d27-152">Zeigt den Zustand für die Verfügbarkeitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="d8d27-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="d8d27-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="d8d27-153">**Primary instance**</span></span>  
 <span data-ttu-id="d8d27-154">Der Name der Serverinstanz, die das primäre Replikat der Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="d8d27-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="d8d27-155">**Failover mode**</span></span>  
 <span data-ttu-id="d8d27-156">Zeigt den Failovermodus an, für den das Replikat konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="d8d27-157">Die folgenden Werte für den Failovermodus sind möglich:</span><span class="sxs-lookup"><span data-stu-id="d8d27-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="d8d27-158">**Automatisch**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-158">**Automatic**.</span></span> <span data-ttu-id="d8d27-159">Gibt an, dass ein oder mehrere Replikate im automatischen Failovermodus sind.</span><span class="sxs-lookup"><span data-stu-id="d8d27-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="d8d27-160">**Manuell**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-160">**Manual**.</span></span> <span data-ttu-id="d8d27-161">Gibt an, dass kein Replikat im automatischen Failovermodus ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="d8d27-162">**Clusterstatus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-162">**Cluster state**</span></span>  
 <span data-ttu-id="d8d27-163">Name und Zustand des Clusters, auf dem die Instanz des verbundenen Servers und die Verfügbarkeitsgruppe ein Elementknoten ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="d8d27-164">Verfügbarkeitsreplikatdetails</span><span class="sxs-lookup"><span data-stu-id="d8d27-164">Availability Replica Details</span></span>  
 <span data-ttu-id="d8d27-165">Im Bereich **Verfügbarkeitsreplikat** werden die folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d8d27-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="d8d27-166">**Name**</span><span class="sxs-lookup"><span data-stu-id="d8d27-166">**Name**</span></span>  
 <span data-ttu-id="d8d27-167">Der Namen der Serverinstanz, die das Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="d8d27-168">Diese Spalte wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="d8d27-169">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="d8d27-169">**Role**</span></span>  
 <span data-ttu-id="d8d27-170">Gibt die aktuelle Rolle des Verfügbarkeitsreplikats an, entweder **Primär** oder **Sekundär**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="d8d27-171">Informationen über [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]-Rollen finden Sie unter [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d8d27-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="d8d27-172">Diese Spalte wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="d8d27-173">**Failovermodus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-173">**Failover Mode**</span></span>  
 <span data-ttu-id="d8d27-174">Zeigt den Failovermodus an, für den das Replikat konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="d8d27-175">Die folgenden Werte für den Failovermodus sind möglich:</span><span class="sxs-lookup"><span data-stu-id="d8d27-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="d8d27-176">**Automatisch**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-176">**Automatic**.</span></span> <span data-ttu-id="d8d27-177">Gibt an, dass ein oder mehrere Replikate im automatischen Failovermodus sind.</span><span class="sxs-lookup"><span data-stu-id="d8d27-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="d8d27-178">**Manuell**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-178">**Manual**.</span></span> <span data-ttu-id="d8d27-179">Gibt an, dass kein Replikat im automatischen Failovermodus ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="d8d27-180">**Synchronisierungsstatus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-180">**Synchronization State**</span></span>  
 <span data-ttu-id="d8d27-181">Gibt an, ob ein sekundäres Replikat gerade mit dem primärem Replikat synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="d8d27-182">Diese Spalte wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-182">This column is shown by default.</span></span> <span data-ttu-id="d8d27-183">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="d8d27-184">**Nicht synchronisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-184">**Not Synchronized**.</span></span> <span data-ttu-id="d8d27-185">Mindestens eine Datenbank im Replikat ist nicht synchronisiert oder wurde noch nicht mit der Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="d8d27-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="d8d27-186">Wird **synchronisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-186">**Synchronizing**.</span></span> <span data-ttu-id="d8d27-187">Mindestens eine Datenbank im Replikat wird synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d8d27-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="d8d27-188">**Synchronisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-188">**Synchronized**.</span></span> <span data-ttu-id="d8d27-189">Alle Datenbanken im sekundären Replikat werden mit den entsprechenden primären Datenbanken auf dem aktuellen primären Replikat (falls vorhanden) oder auf dem letzten primären Replikat synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d8d27-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8d27-190">Im Leistungsmodus befindet sich die Datenbank nie im Status "Synchronisiert".</span><span class="sxs-lookup"><span data-stu-id="d8d27-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="d8d27-191">**Null**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-191">**NULL**.</span></span> <span data-ttu-id="d8d27-192">Unbekannter Status.</span><span class="sxs-lookup"><span data-stu-id="d8d27-192">Unknown state.</span></span> <span data-ttu-id="d8d27-193">Dieser Wert tritt auf, wenn die lokale Serverinstanz nicht mit dem WSFC-Failovercluster kommunizieren kann (d. h., der lokale Knoten ist nicht Teil des WSFC-Quorums).</span><span class="sxs-lookup"><span data-stu-id="d8d27-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="d8d27-194">**Probleme**</span><span class="sxs-lookup"><span data-stu-id="d8d27-194">**Issues**</span></span>  
 <span data-ttu-id="d8d27-195">Listet den Namen des Problems auf.</span><span class="sxs-lookup"><span data-stu-id="d8d27-195">Lists the issue name.</span></span> <span data-ttu-id="d8d27-196">Dieser Wert wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-196">This value is shown by default.</span></span> <span data-ttu-id="d8d27-197">Eine Liste aller AlwaysOn-Richtlinien Probleme finden Sie unter [AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="d8d27-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="d8d27-198">**Verfügbarkeitsmodus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-198">**Availability Mode**</span></span>  
 <span data-ttu-id="d8d27-199">Gibt die Replikateigenschaft an, die Sie für jedes Verfügbarkeitsreplikat einzeln festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="d8d27-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="d8d27-200">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-200">This value is hidden by default.</span></span> <span data-ttu-id="d8d27-201">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="d8d27-202">**Asynchron**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-202">**Asynchronous**.</span></span> <span data-ttu-id="d8d27-203">Das sekundäre Replikat wird nie mit dem primären Replikat synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d8d27-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="d8d27-204">**Synchron**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-204">**Synchronous**.</span></span> <span data-ttu-id="d8d27-205">Beim Aufholen zur primären Datenbank geht eine sekundäre Datenbank in diesen Status über und bleibt aufgeholt, solange die Datensynchronisierung für die Datenbank ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="d8d27-206">**Primärer Verbindungsmodus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="d8d27-207">Gibt den Modus an, der zum Herstellen einer Verbindung mit dem primären Replikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="d8d27-208">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-209">**Sekundärer Verbindungsmodus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="d8d27-210">Gibt den Modus an, der zum Herstellen einer Verbindung mit dem sekundären Replikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="d8d27-211">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-212">**Verbindungsstatus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-212">**Connection State**</span></span>  
 <span data-ttu-id="d8d27-213">Gibt an, ob ein sekundäres Replikat derzeit mit dem primären Replikat verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="d8d27-214">Diese Spalte wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-214">This column is hidden by default.</span></span> <span data-ttu-id="d8d27-215">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="d8d27-216">Nicht **getrennt**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-216">**Disconnected**.</span></span> <span data-ttu-id="d8d27-217">Gibt bei einem Remoteverfügbarkeitsreplikat an, dass es vom lokalen Verfügbarkeitsreplikat getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="d8d27-218">Die Antwort des lokalen Replikats auf den Status "Getrennt" hängt wie folgt von dessen Rolle ab:</span><span class="sxs-lookup"><span data-stu-id="d8d27-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="d8d27-219">Wenn auf dem primären Replikat ein sekundäres Replikat getrennt ist, werden die sekundären Datenbanken auf dem primären Replikat als **Nicht synchronisiert** gekennzeichnet, und das primäre Replikat wartet, bis das sekundäre Replikat wieder verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="d8d27-220">Wird erkannt, dass das sekundäre Replikat getrennt ist, wird versucht, die Verbindung des sekundären Replikats mit dem primären Replikat wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="d8d27-221">**Verbunden**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-221">**Connected**.</span></span> <span data-ttu-id="d8d27-222">Ein Remoteverfügbarkeitsreplikat, das derzeit mit dem lokalen Replikat verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="d8d27-223">**Betriebsstatus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-223">**Operational State**</span></span>  
 <span data-ttu-id="d8d27-224">Gibt den aktuellen Betriebszustand des sekundären Replikats an.</span><span class="sxs-lookup"><span data-stu-id="d8d27-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="d8d27-225">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-225">This value is hidden by default.</span></span> <span data-ttu-id="d8d27-226">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-226">The possible values are:</span></span>  
  
 <span data-ttu-id="d8d27-227">**0**. Ausstehendes Failover</span><span class="sxs-lookup"><span data-stu-id="d8d27-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="d8d27-228">**1**. Ausstehend</span><span class="sxs-lookup"><span data-stu-id="d8d27-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="d8d27-229">**2**. Online</span><span class="sxs-lookup"><span data-stu-id="d8d27-229">**2**. Online</span></span>  
  
 <span data-ttu-id="d8d27-230">**3**. Offline</span><span class="sxs-lookup"><span data-stu-id="d8d27-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="d8d27-231">**4**. Fehler</span><span class="sxs-lookup"><span data-stu-id="d8d27-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="d8d27-232">**5**. Fehler, kein Quorum</span><span class="sxs-lookup"><span data-stu-id="d8d27-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="d8d27-233">**Null**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-233">**NULL**.</span></span> <span data-ttu-id="d8d27-234">Das Replikat ist nicht lokal</span><span class="sxs-lookup"><span data-stu-id="d8d27-234">Replica is not local</span></span>  
  
 <span data-ttu-id="d8d27-235">**Nummer des letzten Verbindungsfehlers**</span><span class="sxs-lookup"><span data-stu-id="d8d27-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="d8d27-236">Die Nummer des letzten Verbindungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="d8d27-236">Number of the last connection error.</span></span>  <span data-ttu-id="d8d27-237">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-238">**Beschreibung des letzten Verbindungsfehlers**</span><span class="sxs-lookup"><span data-stu-id="d8d27-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="d8d27-239">Die Beschreibung des letzten Verbindungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="d8d27-239">Description of the last connection error.</span></span>  <span data-ttu-id="d8d27-240">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-241">**Timestamp des letzten Verbindungsfehlers**</span><span class="sxs-lookup"><span data-stu-id="d8d27-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="d8d27-242">Der Timestamp des letzten Verbindungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="d8d27-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="d8d27-243">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8d27-244">Informationen zu Leistungsindikatoren für Verfügbarkeitsreplikate finden Sie unter [SQL Server, Verfügbarkeitsreplikat](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="d8d27-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a> <span data-ttu-id="d8d27-245">So gruppieren Sie Verfügbarkeitsgruppeninformationen</span><span class="sxs-lookup"><span data-stu-id="d8d27-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="d8d27-246">Klicken Sie zum Gruppieren der Informationen auf **Gruppieren nach**, und wählen Sie eine der folgenden Möglichkeiten aus:</span><span class="sxs-lookup"><span data-stu-id="d8d27-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="d8d27-247">**Replikate**</span><span class="sxs-lookup"><span data-stu-id="d8d27-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="d8d27-248">**Verfügbarkeits Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="d8d27-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="d8d27-249">**Synchronisierungs Status**</span><span class="sxs-lookup"><span data-stu-id="d8d27-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="d8d27-250">**Failoverbereitschaft**</span><span class="sxs-lookup"><span data-stu-id="d8d27-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="d8d27-251">**Probleme**</span><span class="sxs-lookup"><span data-stu-id="d8d27-251">**Issues**</span></span>  
  
 <span data-ttu-id="d8d27-252">Im Bereich, der die gruppierten Informationen anzeigt, werden die folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d8d27-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="d8d27-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="d8d27-253">**Name**</span></span>  
 <span data-ttu-id="d8d27-254">Der Name der Verfügbarkeitsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="d8d27-254">The name of the availability database.</span></span> <span data-ttu-id="d8d27-255">Dieser Wert wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="d8d27-256">**Replikat**</span><span class="sxs-lookup"><span data-stu-id="d8d27-256">**Replica**</span></span>  
 <span data-ttu-id="d8d27-257">Der Name der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die das Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="d8d27-258">Dieser Wert wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="d8d27-259">**Synchronisierungsstatus**</span><span class="sxs-lookup"><span data-stu-id="d8d27-259">**Synchronization State**</span></span>  
 <span data-ttu-id="d8d27-260">Gibt an, ob die Verfügbarkeitsdatenbank gerade mit dem primärem Replikat synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="d8d27-261">Dieser Wert wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-261">This value is shown by default.</span></span> <span data-ttu-id="d8d27-262">Folgende Synchronisierungsstatus sind möglich:</span><span class="sxs-lookup"><span data-stu-id="d8d27-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="d8d27-263">**Synchronisierung wird nicht ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="d8d27-264">Gibt bei der primären Rolle an, dass die Datenbank nicht bereit ist, das Transaktionsprotokoll mit den entsprechenden sekundären Datenbanken zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d8d27-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="d8d27-265">Gibt bei einer sekundären Datenbank an, dass die Protokollsynchronisierung für die Datenbank aufgrund eines Verbindungsproblems nicht gestartet wurde oder beim Start oder einem Rollenwechsel verschiedene Übergangsstatuswerte durchläuft.</span><span class="sxs-lookup"><span data-stu-id="d8d27-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="d8d27-266">Wird **synchronisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="d8d27-267">Auf einem primären Replikat:</span><span class="sxs-lookup"><span data-stu-id="d8d27-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="d8d27-268">Gibt bei einer primären Datenbank an, dass diese Datenbank bereit ist, eine Scananforderung von einer sekundären Datenbank zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d8d27-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="d8d27-269">Gibt auf einem sekundären Replikat an, dass derzeit eine aktive Datenverschiebung für diese sekundäre Datenbank stattfindet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="d8d27-270">Gibt auf einem sekundären Replikat an, dass derzeit eine aktive Datenverschiebung für dieses Replikat stattfindet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="d8d27-271">**Synchronisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="d8d27-272">Gibt bei einer primären Datenbank an, dass mindestens eine sekundäre Datenbank synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="d8d27-273">Gibt bei einer sekundären Datenbank an, dass die Datenbank mit der entsprechenden primären Datenbank synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="d8d27-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="d8d27-274">**Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="d8d27-275">Gibt die Rollbackphase an, wenn eine sekundäre Datenbank aktiv Seiten von der primären Datenbank abruft.</span><span class="sxs-lookup"><span data-stu-id="d8d27-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="d8d27-276">Wenn eine Datenbank sich im Status REVERTING befindet, kann die Datenbank sich nach einem erzwungenen Failover zum sekundären Replikat in einem Status befinden, in dem sie nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8d27-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="d8d27-277">**Wird initialisiert**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="d8d27-278">Gibt die Rollbackphase an, wenn das Transaktionsprotokoll (erforderlich, um eine sekundäre Datenbank auf den gleichen Stand wie die Rückgängig-LSN zu bringen) übermittelt und auf einem sekundären Replikat festgeschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d8d27-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="d8d27-279">Wenn eine Datenbank den Status INITIALIZING aufweist, befindet sich die Datenbank nach einem erzwungenen Failover zum sekundären Replikat immer in einem Status, in dem sie nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8d27-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="d8d27-280">**Failoverbereitschaft**</span><span class="sxs-lookup"><span data-stu-id="d8d27-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="d8d27-281">Gibt an, für welches Verfügbarkeitsreplikat ein Failover mit oder ohne potenziellen Datenverlust ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8d27-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="d8d27-282">Diese Spalte wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-282">This column is shown by default.</span></span> <span data-ttu-id="d8d27-283">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="d8d27-284">**Datenverlust**</span><span class="sxs-lookup"><span data-stu-id="d8d27-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="d8d27-285">**Kein Datenverlust**</span><span class="sxs-lookup"><span data-stu-id="d8d27-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="d8d27-286">**Probleme**</span><span class="sxs-lookup"><span data-stu-id="d8d27-286">**Issues**</span></span>  
 <span data-ttu-id="d8d27-287">Listet den Namen des Problems auf.</span><span class="sxs-lookup"><span data-stu-id="d8d27-287">Lists the issue name.</span></span> <span data-ttu-id="d8d27-288">Diese Spalte wird standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-288">This column is shown by default.</span></span> <span data-ttu-id="d8d27-289">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d8d27-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="d8d27-290">**Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-290">**Warnings**.</span></span> <span data-ttu-id="d8d27-291">Klicken Sie, um die Schwellenwerte und Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="d8d27-292">**Kritisch**.</span><span class="sxs-lookup"><span data-stu-id="d8d27-292">**Critical**.</span></span> <span data-ttu-id="d8d27-293">Klicken Sie, um die kritischen Probleme anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8d27-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="d8d27-294">Eine Liste aller AlwaysOn-Richtlinien Probleme finden Sie unter [AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="d8d27-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="d8d27-295">**Angehalten**</span><span class="sxs-lookup"><span data-stu-id="d8d27-295">**Suspended**</span></span>  
 <span data-ttu-id="d8d27-296">Gibt an, ob der Status der Datenbank **Angehalten** oder **Fortgesetzt**lautet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="d8d27-297">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-298">**Ursache für das Anhalten**</span><span class="sxs-lookup"><span data-stu-id="d8d27-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="d8d27-299">Gibt die Ursache für den Status "Angehalten" an.</span><span class="sxs-lookup"><span data-stu-id="d8d27-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="d8d27-300">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-301">**Geschätzter Datenverlust (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="d8d27-302">Zeigt den Zeitunterschied des letzten Transaktionsprotokolleintrags im primären und sekundären Replikat an.</span><span class="sxs-lookup"><span data-stu-id="d8d27-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="d8d27-303">Bei einem Fehler auf dem primären Replikat gehen alle Transaktionsprotokolleinträge innerhalb des Zeitfensters verloren.</span><span class="sxs-lookup"><span data-stu-id="d8d27-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="d8d27-304">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-305">**Geschätzte Wiederherstellungszeit (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="d8d27-306">Gibt die Zeit in Sekunden an, die das Wiederholen der Aufholzeit dauert.</span><span class="sxs-lookup"><span data-stu-id="d8d27-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="d8d27-307">Die *Aufholzeit* ist die Zeit, die das sekundäre Replikat zum Aufholen des primären Replikats benötigt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="d8d27-308">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-309">**Synchronisierungsleistung (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="d8d27-310">Gibt die Zeit in Sekunden an, die die Synchronisierung zwischen dem primären und sekundären Replikat dauert.</span><span class="sxs-lookup"><span data-stu-id="d8d27-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="d8d27-311">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-312">**Größe der Protokoll-Sendewarteschlange (KB)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="d8d27-313">Gibt die Menge an Protokolldatensätzen in den Protokolldateien der primären Datenbank an, die noch nicht an das sekundäre Replikat gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="d8d27-314">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-315">**Protokoll-Senderate (KB/s)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="d8d27-316">Gibt die Rate in KB pro Sekunde an, mit der Protokolldatensätze an das sekundäre Replikat gesendet werden. Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-317">**Größe der Wiederholungswarteschlange (KB)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="d8d27-318">Gibt die Menge an Protokolldatensätzen in den Protokolldateien des sekundären Replikats an, die noch nicht wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="d8d27-319">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-320">**Rollforwardrate (KB/s)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="d8d27-321">Gibt die Rate in KB pro Sekunde an, mit der die Protokolldatensätze wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="d8d27-322">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-323">**Dateidatenstrom-Senderate (KB/s)**</span><span class="sxs-lookup"><span data-stu-id="d8d27-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="d8d27-324">Gibt die Rate des Dateidatenstroms in KB pro Sekunde an, mit der Transaktionen an das Replikat gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="d8d27-325">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-326">**Protokollende-LSN**</span><span class="sxs-lookup"><span data-stu-id="d8d27-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="d8d27-327">Gibt die tatsächliche Protokollfolgenummer (LSN) an, die dem letzten Protokolldatensatz im Protokollcache auf den primären und sekundären Replikaten entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8d27-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="d8d27-328">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-329">**Wiederherstellungs-LSN**</span><span class="sxs-lookup"><span data-stu-id="d8d27-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="d8d27-330">Gibt bei einem primären Replikat das Ende des Transaktionsprotokolls an, bevor das Replikat nach einer Wiederherstellung oder einem Failover neue Protokolldatensätze schreibt.</span><span class="sxs-lookup"><span data-stu-id="d8d27-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="d8d27-331">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-332">**Kürzungs-LSN**</span><span class="sxs-lookup"><span data-stu-id="d8d27-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="d8d27-333">Gibt den minimalen Protokollkürzungswert für das primäre Replikat an.</span><span class="sxs-lookup"><span data-stu-id="d8d27-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="d8d27-334">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-335">**LSN des letzten Commits**</span><span class="sxs-lookup"><span data-stu-id="d8d27-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="d8d27-336">Gibt die tatsächliche LSN an, die dem letzten Commitdatensatz im Transaktionsprotokoll entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8d27-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="d8d27-337">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-338">**Letzte Commitzeit**</span><span class="sxs-lookup"><span data-stu-id="d8d27-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="d8d27-339">Gibt die Zeit an, die dem letzten Commitdatensatz entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8d27-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="d8d27-340">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-341">**LSN des letzten Sendevorgangs**</span><span class="sxs-lookup"><span data-stu-id="d8d27-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="d8d27-342">Gibt den Punkt an, bis zu dem alle Protokollblöcke vom primären Replikat gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="d8d27-343">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-344">**Letzte Sendezeit**</span><span class="sxs-lookup"><span data-stu-id="d8d27-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="d8d27-345">Gibt die Zeit an, zu der der letzte Protokollblock gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d8d27-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="d8d27-346">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-347">**LSN des letzten Empfangsvorgangs**</span><span class="sxs-lookup"><span data-stu-id="d8d27-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="d8d27-348">Gibt den Punkt an, bis zu dem alle Protokollblöcke vom sekundären Replikat empfangen wurden, das die sekundäre Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="d8d27-349">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-350">**Letzte Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="d8d27-350">**Last Received Time**</span></span>  
 <span data-ttu-id="d8d27-351">Gibt die Zeit an, zu der der in der letzten Meldung empfangene Protokollblockbezeichner auf dem sekundären Replikat gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d8d27-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="d8d27-352">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-353">**LSN der letzten Festschreibung**</span><span class="sxs-lookup"><span data-stu-id="d8d27-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="d8d27-354">Gibt den Punkt an, bis zu dem alle Protokolldatensätze auf dem sekundären Replikat auf den Datenträger geleert wurden.</span><span class="sxs-lookup"><span data-stu-id="d8d27-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="d8d27-355">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-356">**Uhrzeit der letzten Festschreibung**</span><span class="sxs-lookup"><span data-stu-id="d8d27-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="d8d27-357">Gibt die Zeit an, zu der der Protokollblockbezeichner für die letzte festgeschriebene LSN auf dem sekundären Replikat empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d8d27-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="d8d27-358">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-359">**LSN der letzten Wiederholung**</span><span class="sxs-lookup"><span data-stu-id="d8d27-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="d8d27-360">Gibt die tatsächliche LSN des Protokolldatensatzes an, der zuletzt auf dem sekundären Replikat wiederholt wurde.</span><span class="sxs-lookup"><span data-stu-id="d8d27-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="d8d27-361">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="d8d27-362">**Letzte Wiederholungszeit**</span><span class="sxs-lookup"><span data-stu-id="d8d27-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="d8d27-363">Gibt die Zeit an, zu der der letzte Protokolldatensatz in der sekundären Datenbank wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d8d27-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="d8d27-364">Dieser Wert wird standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d8d27-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d8d27-365">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d8d27-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d8d27-366">Verwenden Sie AlwaysOn-Richtlinien, um die Integrität einer Verfügbarkeits Gruppe &#40;SQL Server anzuzeigen&#41;</span><span class="sxs-lookup"><span data-stu-id="d8d27-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8d27-367">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8d27-367">See Also</span></span>  
 <span data-ttu-id="d8d27-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8d27-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="d8d27-369">Überwachen von Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d8d27-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
