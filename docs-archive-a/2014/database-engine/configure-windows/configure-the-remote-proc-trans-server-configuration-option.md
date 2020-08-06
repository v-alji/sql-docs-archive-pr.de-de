---
title: Konfigurieren der Serverkonfigurationsoption „remote proc trans“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616168"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="ecab3-102">Konfigurieren der Serverkonfigurationsoption „remote proc trans“</span><span class="sxs-lookup"><span data-stu-id="ecab3-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="ecab3-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **remote proc trans** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ecab3-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ecab3-104">Mit der Option **remote proc trans** können Sie die Aktionen einer Server-zu-Server-Prozedur über eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator-Transaktion (MS DTC) schützen.</span><span class="sxs-lookup"><span data-stu-id="ecab3-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="ecab3-105">Legen Sie den Wert von **remote proc trans** auf 1 fest, um eine von MS DTC koordinierte verteilte Transaktion zum Schutz der ACID-Eigenschaften (atomar, konsistent, isoliert und beständig) von Transaktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ecab3-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="ecab3-106">Sitzungen, die nach dem Festlegen dieser Option auf 1 beginnen, erben die Konfigurationseinstellung als Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ecab3-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="ecab3-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ecab3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ecab3-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ecab3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ecab3-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="ecab3-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ecab3-111">Security</span><span class="sxs-lookup"><span data-stu-id="ecab3-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ecab3-112">**So konfigurieren Sie die Option „remote proc trans“ mit:**</span><span class="sxs-lookup"><span data-stu-id="ecab3-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="ecab3-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecab3-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ecab3-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecab3-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ecab3-115">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „remote proc trans“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ecab3-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ecab3-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ecab3-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="ecab3-118">Um diesen Wert festlegen zu können, müssen Remoteserververbindungen zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="ecab3-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ecab3-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-119">Recommendations</span></span>  
  
-   <span data-ttu-id="ecab3-120">Diese Option wird aus Gründen der Kompatibilität mit früheren Versionen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für Anwendungen bereitgestellt, die remote gespeicherte Prozeduren verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecab3-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="ecab3-121">Anstatt remote gespeicherte Prozeduren aufzurufen, sollten Sie verteilte Abfragen verwenden, die auf Verbindungsserver verweisen. Diese werden mithilfe von [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)definiert.</span><span class="sxs-lookup"><span data-stu-id="ecab3-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ecab3-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ecab3-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ecab3-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ecab3-123">Permissions</span></span>  
 <span data-ttu-id="ecab3-124">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="ecab3-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ecab3-125">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="ecab3-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ecab3-126">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ecab3-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ecab3-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecab3-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="ecab3-128">So konfigurieren Sie die Option „remote proc trans“</span><span class="sxs-lookup"><span data-stu-id="ecab3-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="ecab3-129">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="ecab3-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ecab3-130">Klicken Sie auf den Knoten **Verbindungen** .</span><span class="sxs-lookup"><span data-stu-id="ecab3-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="ecab3-131">Aktivieren Sie unter **Remoteserververbindungen**das Kontrollkästchen **Verteilte Transaktionen für die Kommunikation zwischen Servern verlangen** .</span><span class="sxs-lookup"><span data-stu-id="ecab3-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ecab3-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecab3-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="ecab3-133">So konfigurieren Sie die Option „remote proc trans“</span><span class="sxs-lookup"><span data-stu-id="ecab3-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="ecab3-134">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="ecab3-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecab3-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ecab3-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecab3-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ecab3-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ecab3-137">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `remote proc trans` auf `1`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ecab3-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="ecab3-138">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ecab3-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a><span data-ttu-id="ecab3-139">Nächster Schritt: Nach dem Konfigurieren der Option „remote proc trans“</span><span class="sxs-lookup"><span data-stu-id="ecab3-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="ecab3-140">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="ecab3-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecab3-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecab3-141">See Also</span></span>  
 <span data-ttu-id="ecab3-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecab3-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ecab3-143">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ecab3-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ecab3-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecab3-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
