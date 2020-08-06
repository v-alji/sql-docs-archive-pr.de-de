---
title: Konfigurieren der Serverkonfigurationsoption „Geschachtelte Trigger“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619344"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="9315d-102">Konfigurieren der Serverkonfigurationsoption Geschachtelte Trigger</span><span class="sxs-lookup"><span data-stu-id="9315d-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="9315d-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Geschachtelte Trigger** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9315d-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9315d-104">Mit der Option **Geschachtelte Trigger** wird gesteuert, ob ein AFTER-Trigger kaskadiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9315d-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="9315d-105">Das heißt, ob eine Aktion ausgeführt werden kann, die einen anderen Trigger initiiert, der wiederum einen anderen Trigger initiiert usw.</span><span class="sxs-lookup"><span data-stu-id="9315d-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="9315d-106">Wenn die Option **Geschachtelte Trigger** auf 0 festgelegt ist, können AFTER-Trigger nicht kaskadiert werden.</span><span class="sxs-lookup"><span data-stu-id="9315d-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="9315d-107">Wenn die Option **Geschachtelte Trigger** auf 1 festgelegt ist (Standardeinstellung), können AFTER-Trigger auf bis zu 32 Ebenen kaskadiert werden.</span><span class="sxs-lookup"><span data-stu-id="9315d-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="9315d-108">INSTEAD OF-Trigger können unabhängig von der festgelegten Option geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="9315d-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="9315d-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9315d-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9315d-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9315d-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9315d-111">Security</span><span class="sxs-lookup"><span data-stu-id="9315d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9315d-112">**So konfigurieren Sie die Option Geschachtelte Trigger mit:**</span><span class="sxs-lookup"><span data-stu-id="9315d-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="9315d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9315d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9315d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9315d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="9315d-115">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Geschachtelte Trigger“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9315d-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9315d-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9315d-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9315d-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9315d-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9315d-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9315d-118">Permissions</span></span>  
 <span data-ttu-id="9315d-119">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="9315d-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="9315d-120">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="9315d-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="9315d-121">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9315d-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9315d-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9315d-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="9315d-123">So konfigurieren Sie die Option Geschachtelte Trigger</span><span class="sxs-lookup"><span data-stu-id="9315d-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="9315d-124">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf einen Server, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="9315d-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9315d-125">Legen Sie auf der Seite **Erweitert** die Option **Triggern ermöglichen, weitere Trigger auszulösen** auf **True** (Standardeinstellung) oder **False**fest.</span><span class="sxs-lookup"><span data-stu-id="9315d-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9315d-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9315d-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="9315d-127">So konfigurieren Sie die Option Geschachtelte Trigger</span><span class="sxs-lookup"><span data-stu-id="9315d-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="9315d-128">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9315d-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9315d-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9315d-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9315d-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9315d-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9315d-131">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `nested triggers` auf `0`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9315d-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="9315d-132">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9315d-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a><span data-ttu-id="9315d-133">Nächster Schritt: Nach dem Konfigurieren der Option „Geschachtelte Trigger“</span><span class="sxs-lookup"><span data-stu-id="9315d-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="9315d-134">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="9315d-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9315d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9315d-135">See Also</span></span>  
 <span data-ttu-id="9315d-136">[Erstellen von geschachtelten Triggern](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="9315d-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9315d-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="9315d-138">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="9315d-139">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9315d-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
