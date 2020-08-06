---
title: Konfigurieren der HealthCheckTimeout-Eigenschafteneinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617570"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="99f89-102">Konfigurieren der HealthCheckTimeout-Eigenschafteneinstellungen</span><span class="sxs-lookup"><span data-stu-id="99f89-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="99f89-103">Mit der HealthCheckTimeout-Einstellung wird die Zeitdauer in Millisekunden angegeben, die die Ressourcen-DLL für SQL Server auf Informationen warten soll, die von der gespeicherten Prozedur [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) zurückgegeben werden, bevor gemeldet wird, dass die AlwaysOn-Failoverclusterinstanz (FCI) nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="99f89-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="99f89-104">Änderungen am Timeoutwert werden unmittelbar wirksam; ein Neustart der SQL Server-Ressource ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99f89-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="99f89-105">**Vorbereitungen:**  [Beschränkungen](#Limits), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="99f89-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="99f89-106">**So konfigurieren Sie die HeathCheckTimeout-Einstellung mit**  [PowerShell](#PowerShellProcedure), [Failovercluster-Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="99f89-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99f89-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="99f89-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="99f89-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99f89-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="99f89-109">Der Standardwert für diese Eigenschaft ist 60.000 Millisekunden (60 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="99f89-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="99f89-110">Der Mindestwert ist 15.000 Millisekunden (15 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="99f89-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99f89-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="99f89-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99f89-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99f89-112">Permissions</span></span>  
 <span data-ttu-id="99f89-113">Erfordert ALTER SETTINGS- und VIEW SERVER STATE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="99f89-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="99f89-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="99f89-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="99f89-115">So konfigurieren Sie die HealthCheckTimeout-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="99f89-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="99f89-116">Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="99f89-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="99f89-117">Importieren Sie das `FailoverClusters`-Modul, um die Cluster-Cmdlets zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="99f89-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="99f89-118">Verwenden `Get-ClusterResource` Sie das Cmdlet, um die Ressource zu suchen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , und legen Sie dann mit dem `Set-ClusterParameter` Cmdlet die **healthchecktimeout** -Eigenschaft für die Failoverclusterinstanz fest.</span><span class="sxs-lookup"><span data-stu-id="99f89-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="99f89-119">Bei jedem Öffnen eines neuen PowerShell-Fensters müssen Sie das `FailoverClusters`-Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="99f89-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="99f89-120">Im folgenden Beispiel wird die Einstellung HealthCheckTimeout auf der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Ressource "`SQL Server (INST1)`" zu 60.000 Millisekunden geändert.</span><span class="sxs-lookup"><span data-stu-id="99f89-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="99f89-121">Verwandte Inhalte (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="99f89-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="99f89-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Clustering und hohe Verfügbarkeit) (Failoverclustering und Netzwerklastenausgleichs-Teamblog)</span><span class="sxs-lookup"><span data-stu-id="99f89-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="99f89-123">[Erste Schritte mit Windows PowerShell auf einem Failovercluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="99f89-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="99f89-124">Clusterressourcenbefehle und entsprechende Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="99f89-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="99f89-125">Verwenden des Failovercluster-Manager-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="99f89-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="99f89-126">**So konfigurieren Sie die HealthCheckTimeout-Einstellung**</span><span class="sxs-lookup"><span data-stu-id="99f89-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="99f89-127">Öffnen Sie des Failovercluster-Manager-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="99f89-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="99f89-128">Erweitern Sie **Dienste und Anwendungen** , und wählen Sie den FCI aus.</span><span class="sxs-lookup"><span data-stu-id="99f89-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="99f89-129">Klicken Sie mit der rechten Maustaste auf die **SQL Server-Ressource** unter **Sonstige Ressourcen** , und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="99f89-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="99f89-130">Das Dialogfeld **Eigenschaften** der SQL Server-Ressource wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99f89-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="99f89-131">Wählen Sie die Registerkarte **Eigenschaften** aus, geben Sie den gewünschten Wert für die **HealthCheckTimeout** -Eigenschaft ein, und klicken Sie dann auf **OK** , um die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="99f89-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99f89-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99f89-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="99f89-133">Mithilfe der [Alter Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) - [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung können Sie den healthchecktimeout-Eigenschafts Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="99f89-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="99f89-134">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="99f89-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="99f89-135">Im folgenden Beispiel wird die Option HealthCheckTimeout auf 15.000 Millisekunden (15 Sekunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="99f89-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="99f89-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99f89-136">See Also</span></span>  
 [<span data-ttu-id="99f89-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="99f89-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
