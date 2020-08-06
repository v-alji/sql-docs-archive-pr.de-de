---
title: Verwenden von AlwaysOn-Richtlinien zum Anzeigen des Zustands einer Verfügbarkeits Gruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724942"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="1719f-102">Verwenden von AlwaysOn-Richtlinien zum Anzeigen des Zustands einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1719f-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="1719f-103">In diesem Thema wird beschrieben, wie der Betriebsstatus einer AlwaysOn-Verfügbarkeitsgruppe in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] mithilfe einer AlwaysOn-Richtlinie in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]bzw. mit PowerShell geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1719f-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1719f-104">Weitere Informationen zur Richtlinien basierten Verwaltung von AlwaysOn finden Sie unter [AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="1719f-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1719f-105">Für AlwaysOn-Richtlinien werden die Kategorienamen als IDs verwendet.</span><span class="sxs-lookup"><span data-stu-id="1719f-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="1719f-106">Durch die Änderung des Namens einer AlwaysOn-Kategorie wird die Funktion zur Integritätsüberprüfung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="1719f-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="1719f-107">Daher sollten die Namen der AlwaysOn-Kategorie nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1719f-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1719f-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1719f-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1719f-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1719f-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1719f-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1719f-110">Permissions</span></span>  
 <span data-ttu-id="1719f-111">Erfordert CONNECT-, VIEW SERVER STATE- und VIEW ANY DEFINITION-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1719f-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="1719f-112">Verwenden des AlwaysOn-Dashboards</span><span class="sxs-lookup"><span data-stu-id="1719f-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="1719f-113">**So öffnen Sie das AlwaysOn-Dashboard**</span><span class="sxs-lookup"><span data-stu-id="1719f-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="1719f-114">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die eines der Verfügbarkeitsreplikate hostet.</span><span class="sxs-lookup"><span data-stu-id="1719f-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="1719f-115">Verwenden Sie zum Anzeigen von Informationen zu allen Verfügbarkeitsreplikaten in einer Verfügbarkeitsgruppe die Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="1719f-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1719f-116">Klicken Sie auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1719f-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="1719f-117">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** .</span><span class="sxs-lookup"><span data-stu-id="1719f-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="1719f-118">Klicken Sie entweder mit der rechten Maustaste auf den Knoten **Verfügbarkeitsgruppen** , oder erweitern Sie diesen Knoten, und klicken Sie mit der rechten Maustaste auf eine bestimmte Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1719f-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="1719f-119">Wählen Sie den Befehl **Dashboard anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="1719f-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="1719f-120">Informationen zur Verwendung des AlwaysOn-Dashboards finden Sie unter [Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1719f-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1719f-121">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1719f-121">Using PowerShell</span></span>  
 <span data-ttu-id="1719f-122">**Verwenden von AlwaysOn-Richtlinien zum Anzeigen des Zustands einer Verfügbarkeits Gruppe**</span><span class="sxs-lookup"><span data-stu-id="1719f-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="1719f-123">Legen Sie den Standardwert (`cd`) auf eine Serverinstanz fest, auf der eines der Verfügbarkeitsreplikate gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1719f-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="1719f-124">Verwenden Sie zum Anzeigen von Informationen zu allen Verfügbarkeitsreplikaten in einer Verfügbarkeitsgruppe die Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="1719f-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1719f-125">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="1719f-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="1719f-126">Bewertet die Integrität einer Verfügbarkeitsgruppe durch die Auswertung der Richtlinien der richtlinienbasierten SQL Server-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1719f-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="1719f-127">Sie müssen über CONNECT-, VIEW SERVER STATE- und VIEW ANY DEFINITION-Berechtigungen verfügen, um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1719f-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="1719f-128">Beispielsweise werden durch den folgenden Befehl alle Verfügbarkeitsgruppen im „Error“-Zustand auf der Serverinstanz angezeigt `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="1719f-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="1719f-129">Bewertet die Integrität von Verfügbarkeitsreplikaten durch die Auswertung der Richtlinien der richtlinienbasierten SQL Server-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1719f-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="1719f-130">Sie müssen über CONNECT-, VIEW SERVER STATE- und VIEW ANY DEFINITION-Berechtigungen verfügen, um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1719f-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="1719f-131">Durch den folgenden Befehl werden beispielsweise die Integrität des Verfügbarkeitsreplikats `MyReplica` in der Verfügbarkeitsgruppe `MyAg` ausgewertet und eine kurze Zusammenfassung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1719f-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="1719f-132">Bewertet die Integrität einer Verfügbarkeitsdatenbank für alle hinzugefügten Verfügbarkeitsreplikate durch die Auswertung der Richtlinien der richtlinienbasierten SQL Server-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1719f-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="1719f-133">Durch den folgenden Befehl werden beispielsweise die Integrität aller Verfügbarkeitsdatenbanken in der Verfügbarkeitsgruppe `MyAg` ausgewertet und eine kurze Zusammenfassung für jede Datenbank ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1719f-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="1719f-134">Diese Cmdlets akzeptieren die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="1719f-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="1719f-135">Option</span><span class="sxs-lookup"><span data-stu-id="1719f-135">Option</span></span>|<span data-ttu-id="1719f-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1719f-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="1719f-137">Führt in den AlwaysOn-Richtlinienkategorien gefundene Benutzerrichtlinien aus.</span><span class="sxs-lookup"><span data-stu-id="1719f-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="1719f-138">Eine Auflistung von Objekten, die abhängig vom verwendeten Cmdlet den Status von Verfügbarkeitsgruppen, Verfügbarkeitsreplikaten oder Verfügbarkeitsdatenbanken darstellen.</span><span class="sxs-lookup"><span data-stu-id="1719f-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="1719f-139">Das Cmdlet berechnet die Integrität der angegebenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="1719f-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="1719f-140">Wenn dieser Parameter festgelegt wird, werden die vom `-Path`-Parameter oder `-InputObject`-Parameter angegebenen Objekte nicht manuell vom Cmdlet aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1719f-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="1719f-141">Abhängig vom verwendeten Cmdlet der Pfad zur Verfügbarkeitsgruppe, zu den Verfügbarkeitsreplikaten oder zum Status des Datenbankreplikatclusters.</span><span class="sxs-lookup"><span data-stu-id="1719f-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="1719f-142">Dies ist ein optionaler Parameter.</span><span class="sxs-lookup"><span data-stu-id="1719f-142">This is an optional parameter.</span></span> <span data-ttu-id="1719f-143">Wird dieser Parameter nicht angegeben, wird der Wert standardmäßig auf den aktuellen Arbeitsstandort festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1719f-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="1719f-144">Zeigt das Ergebnis aller von diesem Cmdlet ausgeführten Richtlinienauswertungen an.</span><span class="sxs-lookup"><span data-stu-id="1719f-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="1719f-145">Das Cmdlet gibt ein Objekt pro Richtlinienauswertung aus. Dieses Objekt verfügt über Felder, in denen die Ergebnisse der Auswertung beschrieben werden, z. B. ob die Richtlinie eingehalten wurde sowie den Richtliniennamen und die Kategorie.</span><span class="sxs-lookup"><span data-stu-id="1719f-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="1719f-146">Durch den folgenden `Test-SqlAvailabilityGroup`-Befehl wird beispielsweise der `-ShowPolicyDetails`-Parameter angegeben, um das Ergebnis aller Richtlinienauswertungen anzuzeigen, die von diesem Cmdlet für die einzelnen Richtlinien der richtlinienbasierten Verwaltung ausgeführt wurden, die für die Verfügbarkeitsgruppe `MyAg` ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="1719f-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1719f-147">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="1719f-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1719f-148">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1719f-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="1719f-149">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="1719f-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="1719f-150">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="1719f-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="1719f-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1719f-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1719f-152">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1719f-152">Related Content</span></span>  
 <span data-ttu-id="1719f-153">**SQL Server AlwaysOn-Teamblogs: Überwachen des AlwaysOn-Zustands mit PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="1719f-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="1719f-154">Teil 1: Übersicht über grundlegende Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1719f-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="1719f-155">Teil 2: Verwendung erweiterter Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1719f-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="1719f-156">Teil 3: Eine einfache Überwachungsanwendung</span><span class="sxs-lookup"><span data-stu-id="1719f-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="1719f-157">Teil 4: Integration in SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="1719f-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="1719f-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1719f-158">See Also</span></span>  
 <span data-ttu-id="1719f-159">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1719f-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1719f-160">[Verwaltung einer Verfügbarkeits Gruppe &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1719f-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="1719f-161">[Überwachen von Verfügbarkeitsgruppen (SQL Server)](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1719f-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1719f-162">AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1719f-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
