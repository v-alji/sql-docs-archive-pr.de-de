---
title: Aktivieren und Deaktivieren von AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609454"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="367f1-102">Aktivieren und Deaktivieren von AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="367f1-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="367f1-103">[!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] muss aktiviert werden, damit eine Serverinstanz Verfügbarkeitsgruppen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="367f1-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="367f1-104">Bevor Sie eine beliebige Verfügbarkeitsgruppe erstellen und konfigurieren können, muss die Funktion [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] für jede Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aktiviert worden sein, auf der ein Verfügbarkeitsreplikat für mindestens eine Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="367f1-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="367f1-105">Wenn Sie einen WSFC-Cluster löschen und neu erstellen, müssen Sie die Funktion [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] für jede Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deaktivieren und erneut aktivieren, auf der auf dem ursprünglichen WSFC-Cluster ein Verfügbarkeitsreplikat gehostet wurde.</span><span class="sxs-lookup"><span data-stu-id="367f1-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="367f1-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="367f1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="367f1-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="367f1-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="367f1-108">Security</span><span class="sxs-lookup"><span data-stu-id="367f1-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="367f1-109">**So wird es gemacht:**</span><span class="sxs-lookup"><span data-stu-id="367f1-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="367f1-110">Bestimmen, ob AlwaysOn-Verfügbarkeitsgruppen aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="367f1-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="367f1-111">Aktivieren von AlwaysOn-Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="367f1-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="367f1-112">AlwaysOn-Verfügbarkeitsgruppen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="367f1-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="367f1-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="367f1-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="367f1-114">Voraussetzungen für das Aktivieren von AlwaysOn-Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="367f1-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="367f1-115">Die Serverinstanz muss sich auf einem WSFC-Knoten (Windows Server Failover Clustering) befinden.</span><span class="sxs-lookup"><span data-stu-id="367f1-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="367f1-116">Auf der Serverinstanz muss eine Edition von SQL Server ausgeführt werden, die [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="367f1-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="367f1-117">Weitere Informationen finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="367f1-118">AlwaysOn-Verfügbarkeitsgruppen sollten jeweils nur für eine Serverinstanz aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="367f1-119">Warten Sie nach der Aktivierung von AlwaysOn-Verfügbarkeitsgruppen, bis der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst neu gestartet wurde, bevor Sie mit einer anderen Serverinstanz fortfahren.</span><span class="sxs-lookup"><span data-stu-id="367f1-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="367f1-120">Weitere Informationen zu den zusätzlichen Voraussetzungen für das Erstellen und Konfigurieren von Verfügbarkeits Gruppen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="367f1-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="367f1-121">Security</span></span>  
 <span data-ttu-id="367f1-122">Während AlwaysOn-Verfügbarkeitsgruppen auf einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]aktiviert sind, verfügt die Serverinstanz über Vollzugriff auf den WSFC-Cluster.</span><span class="sxs-lookup"><span data-stu-id="367f1-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="367f1-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="367f1-123">Permissions</span></span>  
 <span data-ttu-id="367f1-124">Erfordert auf dem lokalen Computer die Mitgliedschaft in der Gruppe **Administrator** und Vollzugriff auf den WSFC-Cluster.</span><span class="sxs-lookup"><span data-stu-id="367f1-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="367f1-125">Wenn Sie AlwaysOn mit PowerShell aktivieren, öffnen Sie das Eingabeaufforderungsfenster unter Verwendung der Option **Als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="367f1-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="367f1-126">Erfordert, dass von Active Directory Objekte erstellt und Objektberechtigungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="367f1-127">Bestimmen, ob AlwaysOn-Verfügbarkeitsgruppen aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="367f1-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="367f1-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="367f1-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="367f1-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="367f1-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="367f1-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="367f1-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="367f1-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="367f1-132">**So bestimmen Sie, ob AlwaysOn-Verfügbarkeitsgruppen aktiviert sind**</span><span class="sxs-lookup"><span data-stu-id="367f1-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="367f1-133">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Serverinstanz, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="367f1-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="367f1-134">Klicken Sie im Dialogfeld **Servereigenschaften** auf die Seite **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="367f1-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="367f1-135">Die Eigenschaft **Ist HADR-aktiviert** zeigt einen der folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="367f1-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="367f1-136">**True**, wenn AlwaysOn-Verfügbarkeitsgruppen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="367f1-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="367f1-137">**False**, wenn AlwaysOn-Verfügbarkeitsgruppen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="367f1-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="367f1-138">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="367f1-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="367f1-139">**So bestimmen Sie, ob AlwaysOn-Verfügbarkeitsgruppen aktiviert sind**</span><span class="sxs-lookup"><span data-stu-id="367f1-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="367f1-140">Verwenden Sie die folgende [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) -Anweisung:</span><span class="sxs-lookup"><span data-stu-id="367f1-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="367f1-141">Die Einstellung der Servereigenschaft `IsHadrEnabled` gibt folgendermaßen an, ob eine Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] für AlwaysOn-Verfügbarkeitsgruppen aktiviert wird:</span><span class="sxs-lookup"><span data-stu-id="367f1-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="367f1-142">Falls `IsHadrEnabled` = 1, sind AlwaysOn-Verfügbarkeitsgruppen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="367f1-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="367f1-143">Wenn `IsHadrEnabled` gleich 0 ist, sind AlwaysOn-Verfügbarkeitsgruppen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="367f1-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="367f1-144">Weitere Informationen zur `IsHadrEnabled` Server Eigenschaft finden Sie unter [SERVERPROPERTY &#40;Transact-SQL-&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="367f1-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="367f1-145">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-145">Using PowerShell</span></span>  
 <span data-ttu-id="367f1-146">**So bestimmen Sie, ob AlwaysOn-Verfügbarkeitsgruppen aktiviert sind**</span><span class="sxs-lookup"><span data-stu-id="367f1-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="367f1-147">Legen Sie Default ( `cd` ) auf die Serverinstanz fest (z. b. `\SQL\NODE1\DEFAULT` ), auf der Sie bestimmen möchten, ob [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="367f1-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="367f1-148">Geben Sie den folgenden PowerShell-`Get-Item`-Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="367f1-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="367f1-149">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="367f1-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="367f1-150">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="367f1-151">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="367f1-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="367f1-152">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="367f1-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="367f1-153">AlwaysOn-Verfügbarkeitsgruppen aktivieren</span><span class="sxs-lookup"><span data-stu-id="367f1-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="367f1-154">**Aktivieren von AlwaysOn mit:**</span><span class="sxs-lookup"><span data-stu-id="367f1-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="367f1-155">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="367f1-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="367f1-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="367f1-157">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="367f1-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="367f1-158">**So aktivieren Sie AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="367f1-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="367f1-159">Stellen Sie eine Verbindung mit dem Windows Server Failover Clustering (WSFC)-Knoten her, auf dem die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz gehostet wird, auf der Sie AlwaysOn-Verfügbarkeitsgruppen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="367f1-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="367f1-160">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="367f1-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="367f1-161">Klicken Sie in **SQL Server-Konfigurations-Manager**auf **SQL Server Dienste**, klicken Sie mit der rechten Maustaste auf SQL Server (\*\* < *`instance name`*>)\*\*, wobei **<*`instance name`*>** der Name einer lokalen Server Instanz ist, für die Sie AlwaysOn-Verfügbarkeitsgruppen aktivieren möchten, und klicken Sie auf **Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="367f1-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="367f1-162">Wählen Sie die Registerkarte **Hohe Verfügbarkeit (immer aktiviert)** aus.</span><span class="sxs-lookup"><span data-stu-id="367f1-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="367f1-163">Überprüfen Sie, ob das Feld **Name des Windows-Failoverclusters** den Namen des lokalen Failoverclusters enthält.</span><span class="sxs-lookup"><span data-stu-id="367f1-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="367f1-164">Wenn dieses Feld leer ist, wird [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]von dieser Serverinstanz derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="367f1-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="367f1-165">Der lokale Computer ist kein Clusterknoten, der WSFC-Cluster wurde geschlossen oder diese Edition von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] unterstützt [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]nicht.</span><span class="sxs-lookup"><span data-stu-id="367f1-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="367f1-166">Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="367f1-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="367f1-167">-Konfigurations-Manager speichert die Änderung.</span><span class="sxs-lookup"><span data-stu-id="367f1-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="367f1-168">Dann müssen Sie den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst manuell neu starten.</span><span class="sxs-lookup"><span data-stu-id="367f1-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="367f1-169">Dies ermöglicht die Auswahl einer für die Geschäftsanforderungen optimalen Neustartzeit.</span><span class="sxs-lookup"><span data-stu-id="367f1-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="367f1-170">Wenn der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Dienst neu gestartet wird, wird AlwaysOn aktiviert, und die Servereigenschaft `IsHadrEnabled` wird auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="367f1-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="367f1-171">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="367f1-172">**So aktivieren Sie AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="367f1-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="367f1-173">Ändern Sie das Verzeichnis (`cd`) zu einer Serverinstanz, die Sie für AlwaysOn-Verfügbarkeitsgruppen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="367f1-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="367f1-174">Verwenden Sie das `Enable-SqlAlwaysOn`-Cmdlet, um AlwaysOn-Verfügbarkeitsgruppen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="367f1-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="367f1-175">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="367f1-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="367f1-176">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="367f1-177">Informationen dazu, wie Sie steuern `Enable-SqlAlwaysOn` können, ob das Cmdlet den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Dienst neu startet, finden Sie unter Wann startet [ein Cmdlet den SQL Server-Dienst neu?](#WhenCmdletRestartsSQL)weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="367f1-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="367f1-178">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="367f1-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="367f1-179">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="367f1-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="367f1-180">Beispiel: Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="367f1-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="367f1-181">Durch den folgenden PowerShell-Befehl wird [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] auf einer Instanz von SQL Server (*Computer*\\*Instanz*) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="367f1-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="367f1-182">Deaktivieren von AlwaysOn-Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="367f1-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="367f1-183">**Vor dem Deaktivieren von AlwaysOn:**</span><span class="sxs-lookup"><span data-stu-id="367f1-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="367f1-184">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="367f1-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="367f1-185">**Deaktivieren von AlwaysOn mit:**</span><span class="sxs-lookup"><span data-stu-id="367f1-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="367f1-186">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="367f1-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="367f1-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="367f1-188">**Nachverfolgung:**  [Nach dem Deaktivieren von AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="367f1-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="367f1-189">Deaktivieren Sie AlwaysOn auf jeweils nur einer Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="367f1-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="367f1-190">Warten Sie nach der Deaktivierung von AlwaysOn-Verfügbarkeitsgruppen, bis der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst neu gestartet wurde, bevor Sie mit einer anderen Serverinstanz fortfahren.</span><span class="sxs-lookup"><span data-stu-id="367f1-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="367f1-191">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="367f1-191">Recommendations</span></span>  
 <span data-ttu-id="367f1-192">Bevor Sie AlwaysOn auf einer Serverinstanz deaktivieren, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="367f1-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="367f1-193">Wenn das primäre Replikat einer Verfügbarkeitsgruppe, die beibehalten werden soll, derzeit auf einer Serverinstanz gehostet wird, sollten Sie nach Möglichkeit manuell ein Failover für die Verfügbarkeitsgruppe zum synchronisierten sekundären Replikat ausführen.</span><span class="sxs-lookup"><span data-stu-id="367f1-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="367f1-194">Weitere Informationen finden Sie unter [Ausführen eines geplanten manuellen Failovers einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="367f1-195">Entfernen Sie alle lokalen sekundären Replikate.</span><span class="sxs-lookup"><span data-stu-id="367f1-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="367f1-196">Weitere Informationen finden Sie unter [Entfernen eines sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="367f1-197">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="367f1-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="367f1-198">**So deaktivieren Sie AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="367f1-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="367f1-199">Stellen Sie eine Verbindung mit dem Windows Server Failover Clustering (WSFC)-Knoten her, auf dem die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz gehostet wird, auf der Sie AlwaysOn-Verfügbarkeitsgruppen deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="367f1-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="367f1-200">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="367f1-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="367f1-201">Klicken Sie in **SQL Server-Konfigurations-Manager**auf **SQL Server Dienste**, klicken Sie mit der rechten Maustaste auf SQL Server (\*\* < *`instance name`*>)\*\*, wobei **<*`instance name`*>** der Name einer lokalen Server Instanz ist, für die Sie AlwaysOn-Verfügbarkeitsgruppen deaktivieren möchten, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="367f1-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="367f1-202">Deaktivieren Sie auf der Registerkarte**AlwaysOn hohe Verfügbarkeit**das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="367f1-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="367f1-203">-Konfigurations-Manager speichert die Änderung und startet den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="367f1-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="367f1-204">Beim Neustart des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Diensts wird AlwaysOn deaktiviert. Zudem wird die Servereigenschaft `IsHadrEnabled` auf 0 festgelegt, um anzugeben, dass AlwaysOn-Verfügbarkeitsgruppen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="367f1-205">Es empfiehlt sich, dass Sie die Informationen unter [Nachverfolgung: Nach dem Deaktivieren von AlwaysOn](#FollowUp)später in diesem Thema lesen.</span><span class="sxs-lookup"><span data-stu-id="367f1-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="367f1-206">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="367f1-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="367f1-207">**So deaktivieren Sie AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="367f1-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="367f1-208">Wechseln `cd` Sie in das Verzeichnis () zu einer derzeit aktivierten Serverinstanz, die Sie für AlwaysOn-Verfügbarkeitsgruppen deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="367f1-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="367f1-209">Verwenden Sie das `Disable-SqlAlwaysOn`-Cmdlet, um AlwaysOn-Verfügbarkeitsgruppen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="367f1-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="367f1-210">Mit dem folgenden Befehl werden z. b. AlwaysOn-Verfügbarkeitsgruppen auf einer Instanz von SQL Server (*Computer* \\ *Instanz*) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="367f1-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="367f1-211">Dieser Befehl erfordert einen Neustart der Instanz, und Sie werden aufgefordert, diesen Neustart zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="367f1-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="367f1-212">Informationen dazu, wie Sie steuern `Disable-SqlAlwaysOn` können, ob das Cmdlet den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Dienst neu startet, finden Sie unter Wann startet [ein Cmdlet den SQL Server-Dienst neu?](#WhenCmdletRestartsSQL)weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="367f1-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="367f1-213">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="367f1-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="367f1-214">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="367f1-215">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="367f1-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="367f1-216">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="367f1-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="367f1-217">Nachverfolgung: nach dem Deaktivieren von AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="367f1-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="367f1-218">Nachdem Sie AlwaysOn-Verfügbarkeitsgruppen deaktiviert haben, muss die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="367f1-219">Die Serverinstanz wird vom SQL-Konfigurations-Manager automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="367f1-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="367f1-220">Wenn Sie jedoch das `Disable-SqlAlwaysOn`-Cmdlet verwendet haben, müssen Sie die Serverinstanz manuell neu starten.</span><span class="sxs-lookup"><span data-stu-id="367f1-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="367f1-221">Weitere Informationen finden Sie unter [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="367f1-222">Auf der neu gestarteten Serverinstanz:</span><span class="sxs-lookup"><span data-stu-id="367f1-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="367f1-223">Verfügbarkeitsdatenbanken werden bei SQL Server-Start nicht gestartet. Daher kann nicht auf sie zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="367f1-224">Die einzige unterstützte AlwaysOn- [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung ist [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="367f1-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="367f1-225">Die Optionen CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP und SET HADR von ALTER DATABASE werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="367f1-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="367f1-226">-Metadaten und [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]-Konfigurationsdaten in WSFC sind von der Deaktivierung der AlwaysOn-Verfügbarkeitsgruppen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="367f1-226">metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="367f1-227">Wenn Sie AlwaysOn-Verfügbarkeitsgruppen dauerhaft auf jeder Serverinstanz deaktivieren, die ein Verfügbarkeitsreplikat für eine oder mehrere Verfügbarkeitsgruppen hostet, empfiehlt es sich, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="367f1-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="367f1-228">Wenn Sie die lokalen Verfügbarkeitsreplikate nicht vor dem Deaktivieren von AlwaysOn entfernt haben, löschen Sie jede Verfügbarkeitsgruppe, für die die Serverinstanz ein Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="367f1-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="367f1-229">Informationen zum Löschen einer Verfügbarkeitsgruppe finden Sie unter [Entfernen einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="367f1-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="367f1-230">Um die zurückgelassenen Metadaten zu entfernen, löschen Sie jede betroffene Verfügbarkeitsgruppe auf einer Serverinstanz, die Teil des ursprünglichen WSFC-Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="367f1-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="367f1-231">Auf die primären Datenbanken kann weiterhin anhand aller Verbindungen außer der Datensynchronisierung zwischen der primären und der sekundären Datenbank zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="367f1-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="367f1-232">Die sekundären Datenbanken übernehmen den Status RESTORING.</span><span class="sxs-lookup"><span data-stu-id="367f1-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="367f1-233">Sie können sie entweder löschen oder sie mit RESTORE WITH RECOVERY wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="367f1-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="367f1-234">Wiederhergestellte Datenbanken nehmen jedoch nicht mehr an der Datensynchronisierung für Verfügbarkeitsgruppen teil.</span><span class="sxs-lookup"><span data-stu-id="367f1-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="367f1-235">Wann startet ein Cmdlet den SQL Server-Dienst neu?</span><span class="sxs-lookup"><span data-stu-id="367f1-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="367f1-236">Auf einer gerade ausgeführten Serverinstanz kann die Verwendung von `Enable-SqlAlwaysOn` oder `Disable-SqlAlwaysOn` zum Ändern der aktuellen AlwaysOn-Einstellung zu einem Neustart des SQL Server-Diensts führen.</span><span class="sxs-lookup"><span data-stu-id="367f1-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="367f1-237">Das Neustartverhalten hängt von den folgenden Bedingungen ab:</span><span class="sxs-lookup"><span data-stu-id="367f1-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="367f1-238">-NoServiceRestart-Parameter angegeben</span><span class="sxs-lookup"><span data-stu-id="367f1-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="367f1-239">-Force-Parameter angegeben</span><span class="sxs-lookup"><span data-stu-id="367f1-239">-Force parameter specified</span></span>|<span data-ttu-id="367f1-240">Wurde der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst neu gestartet?</span><span class="sxs-lookup"><span data-stu-id="367f1-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="367f1-241">Nein</span><span class="sxs-lookup"><span data-stu-id="367f1-241">No</span></span>|<span data-ttu-id="367f1-242">Nein</span><span class="sxs-lookup"><span data-stu-id="367f1-242">No</span></span>|<span data-ttu-id="367f1-243">Standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="367f1-243">By default.</span></span> <span data-ttu-id="367f1-244">Aber das Cmdlet fordert Sie folgendermaßen auf:</span><span class="sxs-lookup"><span data-stu-id="367f1-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="367f1-245">**Um diese Aktion abzuschließen, müssen wir den SQL Server-Dienst für die Serverinstanz "<instance_name>" neu starten. Möchten Sie den Vorgang fortsetzen?**</span><span class="sxs-lookup"><span data-stu-id="367f1-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="367f1-246">**[Y] Ja  [N] Nein  [S] Anhalten  [?] Hilfe (Standard ist „Y"):**</span><span class="sxs-lookup"><span data-stu-id="367f1-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="367f1-247">Wenn Sie **N** oder **S**angeben, wird der Dienst nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="367f1-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="367f1-248">Nein</span><span class="sxs-lookup"><span data-stu-id="367f1-248">No</span></span>|<span data-ttu-id="367f1-249">Ja</span><span class="sxs-lookup"><span data-stu-id="367f1-249">Yes</span></span>|<span data-ttu-id="367f1-250">Der Dienst wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="367f1-250">Service is restarted.</span></span>|  
|<span data-ttu-id="367f1-251">Ja</span><span class="sxs-lookup"><span data-stu-id="367f1-251">Yes</span></span>|<span data-ttu-id="367f1-252">Nein</span><span class="sxs-lookup"><span data-stu-id="367f1-252">No</span></span>|<span data-ttu-id="367f1-253">Der Dienst wird nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="367f1-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="367f1-254">Ja</span><span class="sxs-lookup"><span data-stu-id="367f1-254">Yes</span></span>|<span data-ttu-id="367f1-255">Ja</span><span class="sxs-lookup"><span data-stu-id="367f1-255">Yes</span></span>|<span data-ttu-id="367f1-256">Der Dienst wird nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="367f1-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="367f1-257">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="367f1-257">See Also</span></span>  
 <span data-ttu-id="367f1-258">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="367f1-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="367f1-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="367f1-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
