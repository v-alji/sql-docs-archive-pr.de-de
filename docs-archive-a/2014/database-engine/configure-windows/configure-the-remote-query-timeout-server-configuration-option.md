---
title: Konfigurieren der Serverkonfigurationsoption „Timeout für Remoteabfragen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724182"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="9c4e6-102">Konfigurieren der Serverkonfigurationsoption Timeout für Remoteabfragen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="9c4e6-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Timeout für Remoteabfragen** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9c4e6-104">Mithilfe der Option **Timeout für Remoteabfragen** können Sie angeben, wie viel Zeit (in Sekunden) ein Remotevorgang in Anspruch nehmen kann, bevor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Timeout auftritt. Der Standardwert für diese Option beträgt 600, was einer Wartezeit von 10 Minuten entspricht.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="9c4e6-105">Dieser Wert gilt für eine von [!INCLUDE[ssDE](../../includes/ssde-md.md)] als Remoteabfrage initiierte ausgehende Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="9c4e6-106">Der Wert hat keine Auswirkungen auf von [!INCLUDE[ssDE](../../includes/ssde-md.md)]empfangene Abfragen.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="9c4e6-107">Wenn Sie das Timeout deaktivieren möchten, setzen Sie den Wert auf 0.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="9c4e6-108">Bei einer Abfrage wird dann bis zum Abschluss gewartet.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="9c4e6-109">Bei heterogenen Abfragen wird durch **Timeout für Remoteabfragen** die Anzahl der Sekunden angegeben (initialisiert im Befehlsobjekt mithilfe der DBPROP_COMMANDTIMEOUT-Rowseteigenschaft), die ein Remoteanbieter auf Resultsets warten sollte, bevor für die Abfrage ein Timeout eintritt. Dieser Wert wird, soweit dies vom Remoteanbieter unterstützt wird, auch zum Festlegen von DBPROP_GENERALTIMEOUT verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="9c4e6-110">Dadurch tritt für alle anderen Vorgänge nach Ablauf der angegebenen Anzahl von Sekunden ein Timeout ein.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="9c4e6-111">Bei remote gespeicherten Prozeduren wird durch **Timeout für Remoteabfragen** die Anzahl der Sekunden angegeben, die nach dem Senden einer `EXEC` -Anweisung vergehen müssen, bevor für die remote gespeicherte Prozedur ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="9c4e6-112">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9c4e6-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9c4e6-113">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9c4e6-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9c4e6-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9c4e6-115">Security</span><span class="sxs-lookup"><span data-stu-id="9c4e6-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9c4e6-116">**So konfigurieren Sie die Option Timeout für Remoteabfragen mit:**</span><span class="sxs-lookup"><span data-stu-id="9c4e6-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="9c4e6-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c4e6-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9c4e6-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c4e6-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="9c4e6-119">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Timeout für Remoteabfragen“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9c4e6-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9c4e6-120">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9c4e6-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="9c4e6-122">Um diesen Wert festlegen zu können, müssen Remoteserververbindungen zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9c4e6-123">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9c4e6-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9c4e6-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-124">Permissions</span></span>  
 <span data-ttu-id="9c4e6-125">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="9c4e6-126">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="9c4e6-127">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c4e6-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c4e6-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="9c4e6-129">So konfigurieren Sie die Option Timeout für Remoteabfragen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="9c4e6-130">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9c4e6-131">Klicken Sie auf den Knoten **Verbindungen** .</span><span class="sxs-lookup"><span data-stu-id="9c4e6-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="9c4e6-132">Unter **Remoteserververbindungen**im Feld **Timeout für Remoteabfragen** können Sie einen Wert zwischen 0 und 2.147.483.647 eingeben oder auswählen, um die maximale Anzahl von Sekunden festzulegen, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wartet, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9c4e6-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c4e6-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="9c4e6-134">So konfigurieren Sie die Option Timeout für Remoteabfragen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="9c4e6-135">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9c4e6-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9c4e6-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9c4e6-138">In diesem Beispiel wird gezeigt, wie Sie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) zum Festlegen des Werts der Option `remote query timeout` auf `0` verwenden, um das Timeout zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="9c4e6-139">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a><span data-ttu-id="9c4e6-140">Nächster Schritt: Nach dem Konfigurieren der Option „Timeout für Remoteabfragen“</span><span class="sxs-lookup"><span data-stu-id="9c4e6-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="9c4e6-141">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="9c4e6-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4e6-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c4e6-142">See Also</span></span>  
 <span data-ttu-id="9c4e6-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9c4e6-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="9c4e6-144">[Eigenschaften und Verhaltensweisen von Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="9c4e6-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="9c4e6-145">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c4e6-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="9c4e6-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9c4e6-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
