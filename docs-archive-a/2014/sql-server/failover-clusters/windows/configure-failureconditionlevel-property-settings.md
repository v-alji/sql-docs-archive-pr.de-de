---
title: Konfigurieren von FailureConditionLevel-Eigenschafteneinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617572"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="96d11-102">Konfigurieren von FailureConditionLevel-Eigenschafteneinstellungen</span><span class="sxs-lookup"><span data-stu-id="96d11-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="96d11-103">Mit der FailureConditionLevel-Eigenschaft können Sie die Bedingungen für einen Failover oder Neustart der AlwaysOn-Failoverclusterinstanz (FCI) festlegen.</span><span class="sxs-lookup"><span data-stu-id="96d11-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="96d11-104">Änderungen an dieser Eigenschaft werden unmittelbar übernommen, ohne dass ein Neustart des Windows Server-Failoverclusterdiensts (WSFC) oder der FCI-Ressource erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="96d11-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="96d11-105">**Vorbereitungen:**  [FailureConditionLevel-Eigenschafteneinstellungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="96d11-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="96d11-106">**So konfigurieren Sie die FailureConditionLevel-Eigenschafteneinstellungen mithilfe von** [PowerShell](#PowerShellProcedure), dem [Failovercluster-Manager](#WSFC) und [Transact-SQL](#TsqlProcedure).</span><span class="sxs-lookup"><span data-stu-id="96d11-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96d11-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="96d11-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="96d11-108">FailureConditionLevel-Eigenschafteneinstellungen</span><span class="sxs-lookup"><span data-stu-id="96d11-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="96d11-109">Die Fehlerbedingungen werden auf einer ansteigenden Skala festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96d11-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="96d11-110">Auf der Ebene 1-5 enthält jede Ebene die Bedingungen der vorherigen Ebenen sowie die eigenen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="96d11-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="96d11-111">Dies bedeutet, dass die Wahrscheinlichkeit eines Failovers oder Neustarts mit jeder Ebene zunimmt.</span><span class="sxs-lookup"><span data-stu-id="96d11-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="96d11-112">Weitere Informationen finden Sie im Abschnitt "Bestimmen von Fehlern" des Themas [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="96d11-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96d11-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96d11-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96d11-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="96d11-114">Permissions</span></span>  
 <span data-ttu-id="96d11-115">Erfordert ALTER SETTINGS- und VIEW SERVER STATE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="96d11-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="96d11-116">PowerShell</span><span class="sxs-lookup"><span data-stu-id="96d11-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="96d11-117">So konfigurieren Sie die FailureConditionLevel-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="96d11-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="96d11-118">Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="96d11-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="96d11-119">Importieren Sie das `FailoverClusters`-Modul, um die Cluster-Cmdlets zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="96d11-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="96d11-120">Verwenden `Get-ClusterResource` Sie das Cmdlet, um die Ressource zu suchen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , und verwenden `Set-ClusterParameter` Sie dann das Cmdlet, um die **failureconditionlevel** -Eigenschaft für eine Failoverclusterinstanz festzulegen.</span><span class="sxs-lookup"><span data-stu-id="96d11-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="96d11-121">Bei jedem Öffnen eines neuen PowerShell-Fensters müssen Sie das `FailoverClusters`-Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="96d11-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="96d11-122">Im folgenden Beispiel wird die FailureConditionLevel-Einstellung auf der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Ressource "`SQL Server (INST1)`" in "Failover oder Neustart bei wichtigen Serverfehlern" geändert.</span><span class="sxs-lookup"><span data-stu-id="96d11-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="96d11-123">Verwandte Inhalte (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="96d11-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="96d11-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Clustering und hohe Verfügbarkeit) (Failoverclustering und Netzwerklastenausgleichs-Teamblog)</span><span class="sxs-lookup"><span data-stu-id="96d11-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="96d11-125">[Erste Schritte mit Windows PowerShell auf einem Failovercluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="96d11-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="96d11-126">Clusterressourcenbefehle und entsprechende Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="96d11-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="96d11-127">Verwenden des Failovercluster-Manager-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="96d11-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="96d11-128">So konfigurieren Sie failureconditionlevel-Eigenschaften Einstellungen</span><span class="sxs-lookup"><span data-stu-id="96d11-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="96d11-129">Öffnen Sie des Failovercluster-Manager-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="96d11-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="96d11-130">Erweitern Sie **Dienste und Anwendungen** , und wählen Sie den FCI aus.</span><span class="sxs-lookup"><span data-stu-id="96d11-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="96d11-131">Klicken Sie mit der rechten Maustaste auf die **SQL Server-Ressource** unter **Sonstige Ressourcen**, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="96d11-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="96d11-132">Das Dialogfeld **Eigenschaften** der SQL Server-Ressource wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96d11-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="96d11-133">Wählen Sie die Registerkarte **Eigenschaften** aus, geben Sie den gewünschten Wert für die **FailureConditionLevel** -Eigenschaft ein, und klicken Sie dann auf **OK** , um die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="96d11-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96d11-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96d11-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="96d11-135">So konfigurieren Sie failureconditionlevel-Eigenschaften Einstellungen</span><span class="sxs-lookup"><span data-stu-id="96d11-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="96d11-136">Mit der Anweisung [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] können Sie den FailureConditionLevel-Eigenschaftswert angeben.</span><span class="sxs-lookup"><span data-stu-id="96d11-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="96d11-137">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="96d11-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="96d11-138">Im folgenden Beispiel wird die FailureConditionLevel-Eigenschaft auf 0 gesetzt. Dadurch wird angegeben, dass bei einer Fehlerbedingung nicht automatisch ein Failover oder Neustart ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="96d11-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="96d11-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96d11-139">See Also</span></span>  
 <span data-ttu-id="96d11-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96d11-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="96d11-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="96d11-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
