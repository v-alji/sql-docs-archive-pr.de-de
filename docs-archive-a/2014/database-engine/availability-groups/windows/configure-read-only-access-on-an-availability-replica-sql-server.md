---
title: Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697193"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="5cb70-102">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb70-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="5cb70-103">Standardmäßig sind sowohl der Lese-/Schreibzugriff als auch der Zugriff für beabsichtigte Lesevorgänge für das primäre Replikat zulässig, während für sekundäre Replikate einer AlwaysOn-Verfügbarkeitsgruppe keine Verbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="5cb70-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="5cb70-104">In diesem Thema wird beschrieben, wie der Verbindungszugriff für ein Verfügbarkeitsreplikat einer AlwaysOn-Verfügbarkeitsgruppe in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] unter Verwendung von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5cb70-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="5cb70-105">Informationen dazu, welche Auswirkungen die Aktivierung des schreibgeschützten Zugriffs für ein sekundäres Replikat hat, und eine Einführung in den Verbindungszugriff finden Sie unter [ Informationen zum Clientverbindungszugriff auf Verfügbarkeitsreplikate &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) und [Aktive sekundäre Replikate: Lesbare sekundäre Replikate &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5cb70-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5cb70-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="5cb70-107">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5cb70-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="5cb70-108">Um einen anderen Verbindungszugriff zu konfigurieren, benötigen Sie eine Verbindung zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="5cb70-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5cb70-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5cb70-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5cb70-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5cb70-110">Permissions</span></span>  
  
|<span data-ttu-id="5cb70-111">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5cb70-111">Task</span></span>|<span data-ttu-id="5cb70-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5cb70-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5cb70-113">So konfigurieren Sie Replikate beim Erstellen einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="5cb70-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="5cb70-114">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** und die CREATE AVAILABILITY GROUP-Serverberechtigung, ALTER ANY AVAILABILITY GROUP-Berechtigung oder CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="5cb70-115">So ändern Sie ein Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="5cb70-115">To modify an availability replica</span></span>|<span data-ttu-id="5cb70-116">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5cb70-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cb70-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5cb70-118">**So konfigurieren Sie den Zugriff auf einem Verfügbarkeitsreplikat**</span><span class="sxs-lookup"><span data-stu-id="5cb70-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="5cb70-119">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="5cb70-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5cb70-120">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="5cb70-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="5cb70-121">Klicken Sie auf die Verfügbarkeitsgruppe, deren Replikat geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5cb70-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="5cb70-122">Klicken Sie mit der rechten Maustaste auf das Verfügbarkeitsreplikat, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5cb70-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="5cb70-123">Im Dialogfeld **Eigenschaften des Verfügbarkeitsreplikats** können Sie den Verbindungszugriff für die primäre Rolle und die sekundäre Rolle wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="5cb70-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="5cb70-124">Wählen Sie für die sekundäre Rolle aus der Dropdownliste für die **lesbare sekundäre** Rolle wie folgt einen neuen Wert aus:</span><span class="sxs-lookup"><span data-stu-id="5cb70-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="5cb70-125">**Nein**</span><span class="sxs-lookup"><span data-stu-id="5cb70-125">**No**</span></span>  
         <span data-ttu-id="5cb70-126">Es werden keine Verbindungen mit sekundären Datenbanken dieses Replikats zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5cb70-127">Sie sind für den Lesezugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-127">They are not available for read access.</span></span> <span data-ttu-id="5cb70-128">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="5cb70-129">**Nur beabsichtigte Lesevorgänge**</span><span class="sxs-lookup"><span data-stu-id="5cb70-129">**Read-intent only**</span></span>  
         <span data-ttu-id="5cb70-130">Es sind nur schreibgeschützte Verbindungen zu sekundären Datenbanken dieses Replikats zulässig.</span><span class="sxs-lookup"><span data-stu-id="5cb70-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5cb70-131">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="5cb70-132">**Ja**</span><span class="sxs-lookup"><span data-stu-id="5cb70-132">**Yes**</span></span>  
         <span data-ttu-id="5cb70-133">Alle Verbindungen zu sekundären Datenbanken dieses Replikats sind zugelassen, aber nur für Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="5cb70-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="5cb70-134">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="5cb70-135">Wählen Sie für die primäre Rolle aus der Dropdownliste für **Verbindungen in der primären Rolle** einen neuen Wert wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5cb70-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="5cb70-136">**Alle Verbindungen zulassen**</span><span class="sxs-lookup"><span data-stu-id="5cb70-136">**Allow all connections**</span></span>  
         <span data-ttu-id="5cb70-137">Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="5cb70-138">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="5cb70-139">**Verbindungen mit Lese-/Schreibzugriff zulassen**</span><span class="sxs-lookup"><span data-stu-id="5cb70-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="5cb70-140">Wenn die Eigenschaft für die Anwendungsabsicht auf **ReadWrite** festgelegt ist oder keine Verbindungseigenschaft für die Anwendungsabsicht festgelegt wurde, wird die Verbindung zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="5cb70-141">Verbindungen, bei denen die Verbindungseigenschaft für die Anwendungsabsicht auf **ReadOnly** festgelegt ist, werden zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="5cb70-142">Dies kann verhindern, dass Kunden mit dem primären Replikat versehentlich eine leseintensive Arbeitsauslastung verbinden.</span><span class="sxs-lookup"><span data-stu-id="5cb70-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="5cb70-143">Weitere Informationen zur Verbindungseigenschaft für die Anwendungsabsicht finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5cb70-144">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cb70-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="5cb70-145">**So konfigurieren Sie den Zugriff auf einem Verfügbarkeitsreplikat**</span><span class="sxs-lookup"><span data-stu-id="5cb70-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cb70-146">Ein Beispiel für diese Prozedur finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).</span><span class="sxs-lookup"><span data-stu-id="5cb70-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="5cb70-147">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="5cb70-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="5cb70-148">Wenn Sie ein Replikat für eine neue Verfügbarkeitsgruppe angeben, verwenden Sie die [-Anweisung](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cb70-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="5cb70-149">Verwenden Sie zum Hinzufügen oder Ändern eines Replikats für eine vorhandene Verfügbarkeitsgruppe die [-Anweisung](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cb70-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="5cb70-150">Geben Sie zum Konfigurieren des Verbindungszugriffs für die sekundäre Rolle in der ADD REPLICA- bzw. MODIFY REPLICA WITH-Klausel die SECONDARY_ROLE-Option wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="5cb70-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="5cb70-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="5cb70-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="5cb70-152">Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="5cb70-152">where,</span></span>  
  
         <span data-ttu-id="5cb70-153">Nein</span><span class="sxs-lookup"><span data-stu-id="5cb70-153">NO</span></span>  
         <span data-ttu-id="5cb70-154">Es werden keine direkten Verbindungen mit sekundären Datenbanken dieses Replikats zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5cb70-155">Sie sind für den Lesezugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-155">They are not available for read access.</span></span> <span data-ttu-id="5cb70-156">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="5cb70-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="5cb70-157">READ_ONLY</span></span>  
         <span data-ttu-id="5cb70-158">Es sind nur schreibgeschützte Verbindungen zu sekundären Datenbanken dieses Replikats zulässig.</span><span class="sxs-lookup"><span data-stu-id="5cb70-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5cb70-159">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="5cb70-160">ALL</span><span class="sxs-lookup"><span data-stu-id="5cb70-160">ALL</span></span>  
         <span data-ttu-id="5cb70-161">Alle Verbindungen zu sekundären Datenbanken dieses Replikats sind zugelassen, aber nur für Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="5cb70-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="5cb70-162">Die sekundären Datenbanken sind alle für Lesezugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="5cb70-163">Geben Sie zum Konfigurieren des Verbindungszugriffs für die primäre Rolle in der ADD REPLICA- bzw. MODIFY REPLICA WITH-Klausel die PRIMARY_ROLE-Option wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="5cb70-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="5cb70-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="5cb70-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="5cb70-165">Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="5cb70-165">where,</span></span>  
  
     <span data-ttu-id="5cb70-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="5cb70-166">READ_WRITE</span></span>  
     <span data-ttu-id="5cb70-167">Verbindungen, bei denen die Verbindungseigenschaft für den Anwendungszweck auf **ReadOnly** festgelegt ist, werden nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="5cb70-168">Wenn die Eigenschaft für die Anwendungsabsicht auf **ReadWrite** festgelegt ist oder keine Verbindungseigenschaft für die Anwendungsabsicht festgelegt wurde, wird die Verbindung zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="5cb70-169">Weitere Informationen zur Verbindungseigenschaft für die Anwendungsabsicht finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="5cb70-170">ALL</span><span class="sxs-lookup"><span data-stu-id="5cb70-170">ALL</span></span>  
     <span data-ttu-id="5cb70-171">Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="5cb70-172">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="5cb70-173">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5cb70-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="5cb70-174">Im folgenden Beispiel wird einer Verfügbarkeitsgruppe namens *AG2*ein sekundäres Replikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5cb70-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="5cb70-175">Zum Hosten des neuen Verfügbarkeitsreplikats wurde die eigenständige Serverinstanz *COMPUTER03\HADR_INSTANCE*angegeben.</span><span class="sxs-lookup"><span data-stu-id="5cb70-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="5cb70-176">Dieses Replikat ist zum ausschließlichen Zulassen von Verbindungen mit Lese-/Schreibzugriff für die primäre Rolle sowie zum ausschließlichen Zulassen von Verbindungen mit beabsichtigten Lesevorgängen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5cb70-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="5cb70-177">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cb70-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="5cb70-178">So konfigurieren Sie den Zugriff auf einem Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="5cb70-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="5cb70-179">Ein Codebeispiel finden Sie in den PowerShell-Beispielen weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5cb70-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="5cb70-180">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="5cb70-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="5cb70-181">Wenn Sie einer Verfügbarkeitsgruppe ein Verfügbarkeitsreplikat hinzufügen, verwenden Sie das `New-SqlAvailabilityReplica`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb70-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="5cb70-182">Wenn Sie ein vorhandenes Verfügbarkeitsreplikat ändern, verwenden Sie das `Set-SqlAvailabilityReplica`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cb70-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="5cb70-183">Die relevanten Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5cb70-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="5cb70-184">Um den Verbindungs Zugriff für die sekundäre Rolle zu konfigurieren, geben Sie den `ConnectionModeInSecondaryRole` *secondary_role_keyword* -Parameter an, wobei *secondary_role_keyword* einem der folgenden Werte entspricht:</span><span class="sxs-lookup"><span data-stu-id="5cb70-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="5cb70-185">Für die Datenbanken im sekundären Replikat sind keine direkten Verbindungen zugelassen, und die Datenbanken sind für den Lesezugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cb70-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="5cb70-186">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="5cb70-187">Verbindungen mit den Datenbanken im sekundären Replikat sind nur zulässig, wenn die Eigenschaft für die Anwendungsabsicht auf **ReadOnly**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5cb70-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="5cb70-188">Weitere Informationen zu dieser Eigenschaft finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="5cb70-189">Für alle Verbindungen mit den Datenbanken im sekundären Replikat ist der schreibgeschützte Zugriff zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="5cb70-190">Um den Verbindungs Zugriff für die primäre Rolle zu konfigurieren, geben Sie `ConnectionModeInPrimaryRole` *primary_role_keyword*an, wobei *primary_role_keyword* einem der folgenden Werte entspricht:</span><span class="sxs-lookup"><span data-stu-id="5cb70-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="5cb70-191">Verbindungen, bei denen die Verbindungseigenschaft für die Anwendungsabsicht auf ReadOnly festgelegt ist, werden nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="5cb70-192">Wenn die Eigenschaft für die Anwendungsabsicht auf ReadWrite festgelegt ist oder keine Verbindungseigenschaft für die Anwendungsabsicht festgelegt wurde, wird die Verbindung zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="5cb70-193">Weitere Informationen zur Verbindungseigenschaft für die Anwendungsabsicht finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="5cb70-194">Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5cb70-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="5cb70-195">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5cb70-196">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="5cb70-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="5cb70-197">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="5cb70-198">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5cb70-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="5cb70-199">Im folgenden Beispiel wird sowohl der `ConnectionModeInSecondaryRole`-Parameter als auch der `ConnectionModeInPrimaryRole`-Parameter auf `AllowAllConnections` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5cb70-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a><span data-ttu-id="5cb70-200">Nächster Schritt: Nach der Konfiguration des schreibgeschützten Zugriffs für ein Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="5cb70-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="5cb70-201">**Schreibgeschützter Zugriff auf ein lesbares sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="5cb70-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="5cb70-202">Wenn Sie das [Hilfsprogramm bcp](../../../tools/bcp-utility.md) oder das [Hilfsprogramm sqlcmd](../../../tools/sqlcmd-utility.md)verwenden, können Sie den schreibgeschützten Zugriff auf alle sekundären Replikate angeben, die für den schreibgeschützten Zugriff aktiviert sind, indem Sie den- `-K ReadOnly` Schalter angeben.</span><span class="sxs-lookup"><span data-stu-id="5cb70-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="5cb70-203">So ermöglichen Sie, dass Clientanwendungen eine Verbindung mit lesbaren sekundären Replikaten herstellen können</span><span class="sxs-lookup"><span data-stu-id="5cb70-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="5cb70-204">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="5cb70-204">Prerequisite</span></span>|<span data-ttu-id="5cb70-205">Link</span><span class="sxs-lookup"><span data-stu-id="5cb70-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="5cb70-206">![Kontrollkästchen](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span><span class="sxs-lookup"><span data-stu-id="5cb70-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="5cb70-207">Stellen Sie sicher, dass die Verfügbarkeitsgruppe über einen Listener verfügt.</span><span class="sxs-lookup"><span data-stu-id="5cb70-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="5cb70-208">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5cb70-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="5cb70-209">![Kontrollkästchen](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span><span class="sxs-lookup"><span data-stu-id="5cb70-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="5cb70-210">Konfigurieren Sie das schreibgeschützte Routing für eine Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5cb70-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="5cb70-211">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5cb70-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="5cb70-212">**Faktoren, die sich auf Trigger und Aufträge nach einem Failover auswirken können**</span><span class="sxs-lookup"><span data-stu-id="5cb70-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="5cb70-213">Wenn Sie Trigger und Aufträge haben, die beim Ausführen auf einer nicht lesbaren sekundären Datenbank oder einer lesbaren sekundären Datenbank fehlschlagen, müssen Sie ein Skript für die Trigger und Aufträge erstellen, die auf einem angegebenen Replikat kontrolliert werden sollen, um zu bestimmen, ob die Datenbank eine primäre Datenbank oder eine lesbare sekundäre Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="5cb70-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="5cb70-214">Um diese Informationen abzurufen, verwenden Sie die [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) -Funktion, um die **Updatability** -Eigenschaft der Datenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5cb70-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="5cb70-215">Um eine schreibgeschützte Datenbank zu identifizieren, geben Sie READ_ONLY wie folgt als Wert an:</span><span class="sxs-lookup"><span data-stu-id="5cb70-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="5cb70-216">Um eine Datenbank mit Lese-/Schreibzugriff zu identifizieren, geben Sie READ_WRITE als Wert an.</span><span class="sxs-lookup"><span data-stu-id="5cb70-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5cb70-217">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="5cb70-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5cb70-218">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5cb70-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5cb70-219">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5cb70-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="5cb70-220">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5cb70-220">Related Content</span></span>  
  
-   [<span data-ttu-id="5cb70-221">Always On: Value Proposition of Readable Secondary (Always On: Leistungsversprechen lesbarer sekundärer Replikate)</span><span class="sxs-lookup"><span data-stu-id="5cb70-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="5cb70-222">Always On: Why there are two options to enable a secondary replica for read workload? (Always On: Warum gibt es zwei Optionen zum Aktivieren eines sekundären Replikats für die Lesearbeitslast?)</span><span class="sxs-lookup"><span data-stu-id="5cb70-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="5cb70-223">Always On: Setting up Readable Secondary Replica (Always On: Einrichten eines lesbaren sekundären Replikats)</span><span class="sxs-lookup"><span data-stu-id="5cb70-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="5cb70-224">Always On: I just enabled Readable Secondary but my query is blocked? (Always On: Ich habe gerade lesbare sekundäre Replikate aktiviert, meine Abfrage wird jedoch blockiert.)</span><span class="sxs-lookup"><span data-stu-id="5cb70-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="5cb70-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot (Always On: Zur Verfügung stellen aktueller Statistiken auf lesbaren sekundären Replikaten, schreibgeschützten Datenbanken und Datenbankmomentaufnahmen)</span><span class="sxs-lookup"><span data-stu-id="5cb70-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="5cb70-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica (Always On: Herausforderungen bei Statistiken auf schreibgeschützten Datenbanken, Datenbank-Momentaufnahmen und sekundären Replikaten)</span><span class="sxs-lookup"><span data-stu-id="5cb70-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="5cb70-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica (Always On: Auswirkungen auf die primäre Arbeitslast, wenn die Berichterstellungsarbeitslast auf dem sekundären Replikat ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="5cb70-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="5cb70-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation (Always On: Auswirkungen der Zuordnung der Berichterstellungsarbeitslast vom lesbaren sekundären Replikat zur Momentaufnahmeisolation)</span><span class="sxs-lookup"><span data-stu-id="5cb70-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="5cb70-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica (Always On: Minimieren der Blockierung von REDO-Threads beim Ausführen der Berichterstellungsarbeitslast auf sekundären Replikaten)</span><span class="sxs-lookup"><span data-stu-id="5cb70-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="5cb70-230">Always On: Readable Secondary and data latency (Always On: Lesbares sekundäres Replikat und Datenlatenz)</span><span class="sxs-lookup"><span data-stu-id="5cb70-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="5cb70-231">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cb70-231">See Also</span></span>  
 <span data-ttu-id="5cb70-232">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5cb70-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="5cb70-233">Aktive sekundäre Replikate: lesbare sekundäre Replikate &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="5cb70-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="5cb70-234">Informationen zum Clientverbindungszugriff auf Verfügbarkeitsreplikate (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cb70-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
