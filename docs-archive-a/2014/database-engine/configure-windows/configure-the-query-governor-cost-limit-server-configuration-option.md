---
title: Konfigurieren der Serverkonfigurationsoption „Kostenbeschränkung der Abfragekontrolle“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609440"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="5392f-102">Konfigurieren der Serverkonfigurationsoption Kostenbeschränkung der Abfragekontrolle</span><span class="sxs-lookup"><span data-stu-id="5392f-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="5392f-103">In diesem Thema wird beschrieben, wie die `query governor cost limit` Server Konfigurationsoption in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder konfiguriert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5392f-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5392f-104">Die Kostenbeschränkungsoption der Abfragekontrolle legt ein Höchstlimit für den Zeitraum an, in dem eine Abfrage ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5392f-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="5392f-105">Die Abfragekosten beziehen sich auf eine geschätzte Zeit in Sekunden, die für das Ausführen einer Abfrage bei einer bestimmten Hardwarekonfiguration benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5392f-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="5392f-106">Der Standardwert für diese Option ist 0, mit dem die Abfragekontrolle deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="5392f-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="5392f-107">Alle Abfragen können dann ohne zeitliche Begrenzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5392f-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="5392f-108">Wenn Sie einen nicht negativen Wert ungleich Null angeben, lässt die Abfragekontrolle die Ausführung von Abfragen nicht zu, deren geschätzte Kosten über diesem Wert liegen.</span><span class="sxs-lookup"><span data-stu-id="5392f-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="5392f-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5392f-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5392f-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5392f-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5392f-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="5392f-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5392f-112">Security</span><span class="sxs-lookup"><span data-stu-id="5392f-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5392f-113">**So konfigurieren Sie die Option Kostenbeschränkung der Abfragekontrolle mit:**</span><span class="sxs-lookup"><span data-stu-id="5392f-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="5392f-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5392f-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5392f-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5392f-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5392f-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Kostenbeschränkung der Abfragekontrolle“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5392f-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5392f-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5392f-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5392f-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="5392f-118">Recommendations</span></span>  
  
-   <span data-ttu-id="5392f-119">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5392f-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5392f-120">Wenn Sie den Wert der Option Kostenbeschränkung der Abfragekontrolle jeweils für eine Verbindung ändern möchten, können Sie dazu die [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) -Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5392f-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5392f-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5392f-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5392f-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5392f-122">Permissions</span></span>  
 <span data-ttu-id="5392f-123">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="5392f-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5392f-124">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="5392f-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5392f-125">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5392f-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5392f-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5392f-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="5392f-127">So konfigurieren Sie die Option Kostenbeschränkung der Abfragekontrolle</span><span class="sxs-lookup"><span data-stu-id="5392f-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="5392f-128">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="5392f-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5392f-129">Klicken Sie auf die Seite **Verbindungen** .</span><span class="sxs-lookup"><span data-stu-id="5392f-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="5392f-130">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Abfragekontrolle verwenden, um Abfragen mit langer Ausführungszeit zu verhindern** .</span><span class="sxs-lookup"><span data-stu-id="5392f-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="5392f-131">Wenn Sie dieses Kontrollkästchen aktivieren, geben Sie in das untere Feld einen positiven Wert ein, der von der Abfragekontrolle verwendet wird, um das Ausführen von Abfragen nicht zuzulassen, deren Ausführungszeiten diesen Wert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="5392f-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5392f-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5392f-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="5392f-133">So konfigurieren Sie die Option Kostenbeschränkung der Abfragekontrolle</span><span class="sxs-lookup"><span data-stu-id="5392f-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="5392f-134">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="5392f-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5392f-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5392f-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5392f-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5392f-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5392f-137">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `query governor cost limit` auf `120` Sekunden festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5392f-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="5392f-138">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5392f-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a><span data-ttu-id="5392f-139">Nächster Schritt: Nach dem Konfigurieren der Option „Kostenbeschränkung der Abfragekontrolle“</span><span class="sxs-lookup"><span data-stu-id="5392f-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="5392f-140">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="5392f-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5392f-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5392f-141">See Also</span></span>  
 <span data-ttu-id="5392f-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5392f-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5392f-143">[SET QUERY_GOVERNOR_COST_LIMIT (Transact-SQL)](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5392f-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="5392f-144">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5392f-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5392f-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5392f-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
