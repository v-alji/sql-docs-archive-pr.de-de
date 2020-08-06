---
title: Entfernen eines Verfügbarkeitsgruppenlisteners (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615604"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="4e7c0-102">Entfernen eines Verfügbarkeitsgruppenlisteners (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e7c0-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="4e7c0-103">In diesem Thema wird beschrieben, wie ein Verfügbarkeitsgruppenlistener unter Verwendung von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]aus einer AlwaysOn-Verfügbarkeitsgruppe entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="4e7c0-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4e7c0-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4e7c0-106">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4e7c0-107">Security</span><span class="sxs-lookup"><span data-stu-id="4e7c0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4e7c0-108">**Entfernen eines Listeners mit:**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="4e7c0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e7c0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4e7c0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e7c0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4e7c0-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e7c0-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4e7c0-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4e7c0-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="4e7c0-114">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4e7c0-115">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-115">Recommendations</span></span>  
 <span data-ttu-id="4e7c0-116">Bevor Sie einen Verfügbarkeitsgruppenlistener löschen, sollten Sie sicherstellen, dass er nicht von Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4e7c0-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4e7c0-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e7c0-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-118">Permissions</span></span>  
 <span data-ttu-id="4e7c0-119">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e7c0-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e7c0-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4e7c0-121">**So entfernen Sie einen Verfügbarkeitsgruppenlistener**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4e7c0-122">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet, und klicken Sie auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4e7c0-123">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="4e7c0-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4e7c0-124">Erweitern Sie den Knoten der Verfügbarkeitsgruppe, und erweitern Sie den Knoten **Verfügbarkeitsgruppenlistener** .</span><span class="sxs-lookup"><span data-stu-id="4e7c0-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="4e7c0-125">Klicken Sie mit der rechten Maustaste auf den Listener, und wählen Sie den Befehl **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="4e7c0-126">Dadurch wird das Dialogfeld **Listener aus Verfügbarkeitsgruppe entfernen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="4e7c0-127">Weitere Informationen finden Sie weiter unten in diesem Thema unter [Listener aus Verfügbarkeitsgruppe entfernen](#AgListenerPropertiesDialog).</span><span class="sxs-lookup"><span data-stu-id="4e7c0-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="4e7c0-128">Listener aus Verfügbarkeitsgruppe entfernen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="4e7c0-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="4e7c0-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-129">**Name**</span></span>  
 <span data-ttu-id="4e7c0-130">Der Name des zu entfernenden Listeners.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="4e7c0-131">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-131">**Result**</span></span>  
 <span data-ttu-id="4e7c0-132">Zeigt einen Link an, entweder **Erfolgreich** oder **Fehler**, auf den Sie klicken können, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e7c0-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e7c0-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="4e7c0-134">**So entfernen Sie einen Verfügbarkeitsgruppenlistener**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4e7c0-135">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4e7c0-136">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4e7c0-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4e7c0-137">Alter Availability Group *group_name* Remove Listener **' *`dns_name`* '**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="4e7c0-138">dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe und *DNS-Name* der DNS-Name des Verfügbarkeitsgruppenlisteners.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="4e7c0-139">Im folgenden Beispiel wird der Listener der `AccountsAG` -Verfügbarkeitsgruppe gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="4e7c0-140">Der DNS-Name lautet AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4e7c0-141">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e7c0-141">Using PowerShell</span></span>  
 <span data-ttu-id="4e7c0-142">**So entfernen Sie einen Verfügbarkeitsgruppenlistener**</span><span class="sxs-lookup"><span data-stu-id="4e7c0-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4e7c0-143">Legen Sie den Standard (`cd`) auf die Serverinstanz fest, auf der das primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4e7c0-144">Verwenden Sie das integrierte `Remove-Item`-Cmdlet, um einen Listener zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="4e7c0-145">Beispielsweise wird durch den folgenden Befehl der Listener `MyListener` aus einer Verfügbarkeitsgruppe namens `MyAg`entfernt.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e7c0-146">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4e7c0-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4e7c0-147">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4e7c0-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4e7c0-148">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="4e7c0-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4e7c0-149">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e7c0-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="4e7c0-150">Anzeigen von Eigenschaften des Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e7c0-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e7c0-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e7c0-151">See Also</span></span>  
 <span data-ttu-id="4e7c0-152">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4e7c0-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4e7c0-153">Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e7c0-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
