---
title: Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724993"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="4d71b-102">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4d71b-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="4d71b-103">In diesem Thema wird beschrieben, wie das Sitzungstimeout eines AlwaysOn-Verfügbarkeitsreplikats mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="4d71b-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4d71b-104">Das Sitzungstimeout ist eine Replikateigenschaft, die steuert, wie lange (in Sekunden) ein Verfügbarkeitsreplikat auf eine Pingantwort von einem verbundenen Replikat wartet, bevor die Verbindung als fehlgeschlagen betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="4d71b-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="4d71b-105">Standardmäßig wartet ein Replikat 10 Sekunden auf eine Pingantwort.</span><span class="sxs-lookup"><span data-stu-id="4d71b-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="4d71b-106">Diese Replikateigenschaft wendet nur die Verbindung zwischen einem angegebenen sekundären Replikat und dem primären Replikat der Verfügbarkeitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="4d71b-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="4d71b-107">Weitere Informationen finden Sie unter [Übersicht über Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4d71b-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4d71b-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4d71b-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4d71b-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4d71b-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4d71b-111">Security</span><span class="sxs-lookup"><span data-stu-id="4d71b-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4d71b-112">**Ändern des Sitzungstimeouts mit:**</span><span class="sxs-lookup"><span data-stu-id="4d71b-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="4d71b-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d71b-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4d71b-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d71b-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4d71b-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d71b-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4d71b-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4d71b-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="4d71b-118">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4d71b-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4d71b-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-119">Recommendations</span></span>  
 <span data-ttu-id="4d71b-120">Es wird empfohlen, einen Timeoutzeitraum von 10 Sekunden oder mehr zu wählen.</span><span class="sxs-lookup"><span data-stu-id="4d71b-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="4d71b-121">Wenn Sie diesen Wert auf weniger als 10 Sekunden festlegen, verpasst ein stark ausgelastetes System möglicherweise PINGs und meldet einen falschen Fehler.</span><span class="sxs-lookup"><span data-stu-id="4d71b-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4d71b-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4d71b-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4d71b-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4d71b-123">Permissions</span></span>  
 <span data-ttu-id="4d71b-124">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4d71b-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4d71b-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d71b-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4d71b-126">**So ändern Sie das Sitzungstimeout für ein Verfügbarkeitsreplikat**</span><span class="sxs-lookup"><span data-stu-id="4d71b-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="4d71b-127">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="4d71b-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4d71b-128">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="4d71b-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4d71b-129">Klicken Sie auf die Verfügbarkeitsgruppe, deren Verfügbarkeitsreplikat konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d71b-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="4d71b-130">Klicken Sie mit der rechten Maustaste auf das Replikat, das konfiguriert werden soll, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4d71b-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4d71b-131">Verwenden Sie im Dialogfeld **Eigenschaften des Verfügbarkeitsreplikats** das Feld **Sitzungstimeout (Sekunden)** , um die Anzahl der Sekunden für das Sitzungstimeout für dieses Replikat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4d71b-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4d71b-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d71b-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="4d71b-133">**So ändern Sie das Sitzungstimeout für ein Verfügbarkeitsreplikat**</span><span class="sxs-lookup"><span data-stu-id="4d71b-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="4d71b-134">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4d71b-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4d71b-135">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4d71b-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4d71b-136">ALTER AVAILABILITY GROUP *Gruppenname*</span><span class="sxs-lookup"><span data-stu-id="4d71b-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="4d71b-137">MODIFY REPLICA ON '*Instanzname*' WITH ( SESSION_TIMEOUT =*Sekunden* )</span><span class="sxs-lookup"><span data-stu-id="4d71b-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="4d71b-138">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe, *Instanzname* der Name der Serverinstanz, die das zu ändernde Verfügbarkeitsreplikat hostet, und *Sekunden* gibt die Mindestanzahl von Sekunden an, die das Replikat als sekundäres Replikat vor dem Anwenden des Protokolls auf Datenbanken warten muss.</span><span class="sxs-lookup"><span data-stu-id="4d71b-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="4d71b-139">Der Standard von 0 Sekunden gibt an, dass es keine Verzögerung gibt.</span><span class="sxs-lookup"><span data-stu-id="4d71b-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="4d71b-140">Im folgenden Beispiel, eingegeben für das primäre Replikat der `AccountsAG` -Verfügbarkeitsgruppe, wird der Sitzungstimeoutwert in `15` Sekunden für das Replikat geändert, das sich auf der Serverinstanz `INSTANCE09` befindet.</span><span class="sxs-lookup"><span data-stu-id="4d71b-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4d71b-141">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d71b-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="4d71b-142">So ändern Sie das Sitzungstimeout für ein Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="4d71b-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="4d71b-143">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4d71b-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4d71b-144">Verwenden Sie das `Set-SqlAvailabilityReplica`-Cmdlet mit dem `SessionTimeout`-Parameter, um die Anzahl der Sekunden für das Sitzungstimeout für ein angegebenes Verfügbarkeitsreplikat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4d71b-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="4d71b-145">Mit dem folgenden Befehl wird der Zeitraum für das Sitzungstimeout z. B. auf 15 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4d71b-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d71b-146">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4d71b-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4d71b-147">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4d71b-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="4d71b-148">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4d71b-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d71b-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d71b-149">See Also</span></span>  
 [<span data-ttu-id="4d71b-150">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d71b-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
