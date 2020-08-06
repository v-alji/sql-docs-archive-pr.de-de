---
title: Konfigurieren der Serverkonfigurationsoption „Prioritätserhöhung“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616171"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="8fcf7-102">Konfigurieren der Serverkonfigurationsoption Prioritätserhöhung</span><span class="sxs-lookup"><span data-stu-id="8fcf7-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="8fcf7-103">In diesem Thema wird beschrieben, wie die Konfigurationsoption **Prioritätserhöhung** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8fcf7-104">Verwenden Sie die Option **Prioritätserhöhung**, um anzugeben, ob [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit einer höheren Planungspriorität von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 bzw. Windows 2008 R2 als andere Prozesse auf demselben Computer ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="8fcf7-105">Wenn Sie diese Option auf 1 festlegen, wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit der Basispriorität 13 im Windows 2008- oder Windows Server 2008 R2-Taskplaner ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="8fcf7-106">Der Standardwert ist 0, was der Basispriorität 7 entspricht.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="8fcf7-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8fcf7-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8fcf7-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8fcf7-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8fcf7-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8fcf7-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8fcf7-110">Security</span><span class="sxs-lookup"><span data-stu-id="8fcf7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8fcf7-111">**So konfigurieren Sie die Option Prioritätserhöhung mit:**</span><span class="sxs-lookup"><span data-stu-id="8fcf7-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="8fcf7-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8fcf7-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8fcf7-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8fcf7-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8fcf7-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Prioritätserhöhung“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8fcf7-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8fcf7-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8fcf7-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8fcf7-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8fcf7-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8fcf7-117">Wird die Priorität zu stark angehoben, können dadurch Ressourcen von wichtigen Betriebssystem- und Netzwerkfunktionen abgezogen werden, was zu Problemen beim Herunterfahren von SQL Server oder bei der Verwendung anderer Betriebssystemtasks auf dem Server führen kann.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8fcf7-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8fcf7-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8fcf7-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8fcf7-119">Permissions</span></span>  
 <span data-ttu-id="8fcf7-120">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8fcf7-121">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8fcf7-122">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8fcf7-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8fcf7-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="8fcf7-124">So konfigurieren Sie die Option Prioritätserhöhung</span><span class="sxs-lookup"><span data-stu-id="8fcf7-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="8fcf7-125">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8fcf7-126">Klicken Sie auf den Knoten **Prozessoren** .</span><span class="sxs-lookup"><span data-stu-id="8fcf7-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="8fcf7-127">Aktivieren Sie unter **Threads**das Kontrollkästchen **SQL Server-Priorität höher stufen** .</span><span class="sxs-lookup"><span data-stu-id="8fcf7-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="8fcf7-128">Schließen Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], und starten Sie das Programm neu.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8fcf7-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8fcf7-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="8fcf7-130">So konfigurieren Sie die Option Prioritätserhöhung</span><span class="sxs-lookup"><span data-stu-id="8fcf7-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="8fcf7-131">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8fcf7-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8fcf7-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8fcf7-134">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `priority boost` auf `1`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="8fcf7-135">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a><span data-ttu-id="8fcf7-136">Nächster Schritt: Nach dem Konfigurieren der Option „Prioritätserhöhung“</span><span class="sxs-lookup"><span data-stu-id="8fcf7-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="8fcf7-137">Der Server muss neu gestartet werden, bevor die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fcf7-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fcf7-138">See Also</span></span>  
 <span data-ttu-id="8fcf7-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8fcf7-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8fcf7-140">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8fcf7-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="8fcf7-141">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8fcf7-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
