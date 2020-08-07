---
title: Konfigurieren der Serverkonfigurationsoption „Abfragewartezeit“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619334"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="98c24-102">Konfigurieren der Serverkonfigurationsoption Abfragewartezeit</span><span class="sxs-lookup"><span data-stu-id="98c24-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="98c24-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Abfragewartezeit** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="98c24-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="98c24-104">Arbeitsspeicherintensive Abfragen, wie Abfragen mit Sortier- und Hashvorgängen, werden in Warteschlangen eingereiht, wenn nicht ausreichend Arbeitsspeicher zum Ausführen der Abfrage zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="98c24-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="98c24-105">Die Option **Abfragewartezeit** gibt die Zeit in Sekunden (von 0 bis 2147483647) an, die eine Abfrage vor dem Timeout auf Ressourcen warten soll. Der Standardwert für diese Option ist -1.</span><span class="sxs-lookup"><span data-stu-id="98c24-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="98c24-106">Das bedeutet, der Timeout wird als das 25-fache der geschätzten Abfragekosten berechnet.</span><span class="sxs-lookup"><span data-stu-id="98c24-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98c24-107">Eine Transaktion, die die wartende Abfrage enthält, kann Sperren aufrechterhalten, während die Abfrage auf freien Arbeitsspeicher wartet.</span><span class="sxs-lookup"><span data-stu-id="98c24-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="98c24-108">In seltenen Situationen kann ein nicht zu erkennender Deadlock auftreten.</span><span class="sxs-lookup"><span data-stu-id="98c24-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="98c24-109">Das Reduzieren der Abfragewartezeit verringert die Wahrscheinlichkeit solcher Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="98c24-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="98c24-110">Schließlich wird die wartende Abfrage beendet, und die Transaktionssperren werden aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="98c24-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="98c24-111">Durch das Erhöhen der maximalen Wartezeit kann jedoch auch der Zeitaufwand bis zum Beenden der Abfrage erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="98c24-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="98c24-112">Änderungen an dieser Option werden nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="98c24-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="98c24-113">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="98c24-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98c24-114">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="98c24-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98c24-115">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="98c24-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="98c24-116">Security</span><span class="sxs-lookup"><span data-stu-id="98c24-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98c24-117">**So konfigurieren Sie die Option "Abfragewartezeit" mit**</span><span class="sxs-lookup"><span data-stu-id="98c24-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="98c24-118">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98c24-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98c24-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98c24-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="98c24-120">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Abfragewartezeit“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="98c24-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98c24-121">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="98c24-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="98c24-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="98c24-122">Recommendations</span></span>  
  
-   <span data-ttu-id="98c24-123">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="98c24-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98c24-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="98c24-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98c24-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="98c24-125">Permissions</span></span>  
 <span data-ttu-id="98c24-126">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="98c24-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="98c24-127">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="98c24-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="98c24-128">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="98c24-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98c24-129">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98c24-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="98c24-130">So konfigurieren Sie die Option Abfragewartezeit</span><span class="sxs-lookup"><span data-stu-id="98c24-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="98c24-131">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="98c24-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="98c24-132">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="98c24-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="98c24-133">Geben Sie unter **Parallelität**den gewünschten Wert für die Option **Abfragewartezeit** ein.</span><span class="sxs-lookup"><span data-stu-id="98c24-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98c24-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98c24-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="98c24-135">So konfigurieren Sie die Option Abfragewartezeit</span><span class="sxs-lookup"><span data-stu-id="98c24-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="98c24-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="98c24-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98c24-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="98c24-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98c24-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="98c24-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="98c24-139">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `query wait` auf `7500` Sekunden festzulegen.</span><span class="sxs-lookup"><span data-stu-id="98c24-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="98c24-140">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="98c24-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a><span data-ttu-id="98c24-141">Nächster Schritt: Nach dem Konfigurieren der Option „Abfragewartezeit“</span><span class="sxs-lookup"><span data-stu-id="98c24-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="98c24-142">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="98c24-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c24-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98c24-143">See Also</span></span>  
 <span data-ttu-id="98c24-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98c24-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="98c24-145">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98c24-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="98c24-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98c24-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
