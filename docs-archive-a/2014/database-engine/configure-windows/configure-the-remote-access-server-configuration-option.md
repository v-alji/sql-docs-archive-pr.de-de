---
title: Konfigurieren der Serverkonfigurationsoption „Remotezugriff“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609435"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="ad280-102">Konfigurieren der Serverkonfigurationsoption Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="ad280-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="ad280-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Remotezugriff** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ad280-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ad280-104">Mithilfe der Option **Remotezugriff** können Sie die Ausführung gespeicherter Prozeduren von lokalen Servern oder Remoteservern steuern, auf denen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad280-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="ad280-105">Der Standardwert für diese Option ist 1.</span><span class="sxs-lookup"><span data-stu-id="ad280-105">This default value for this option is 1.</span></span> <span data-ttu-id="ad280-106">Damit wird die Berechtigung zum Ausführen lokal gespeicherter Prozeduren von Remoteservern aus oder zum Ausführen remote gespeicherter Prozeduren vom lokalen Server aus erteilt.</span><span class="sxs-lookup"><span data-stu-id="ad280-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="ad280-107">Legen Sie die Option auf 0 fest, um zu verhindern, dass lokal gespeicherte Prozeduren von einem Remoteserver aus ausgeführt werden oder dass remote gespeicherte Prozeduren auf dem lokalen Server ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="ad280-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="ad280-108">Verwenden Sie stattdessen [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad280-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="ad280-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ad280-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad280-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ad280-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad280-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ad280-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad280-112">Security</span><span class="sxs-lookup"><span data-stu-id="ad280-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad280-113">**So konfigurieren Sie die Option Remotezugriff mit:**</span><span class="sxs-lookup"><span data-stu-id="ad280-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="ad280-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad280-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad280-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad280-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ad280-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Remotezugriff“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ad280-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad280-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ad280-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad280-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ad280-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ad280-119">Die Option **Remotezugriff** gilt nur für Server, die mithilfe von [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)hinzugefügt wurden, und wird aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ad280-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad280-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad280-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad280-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ad280-121">Permissions</span></span>  
 <span data-ttu-id="ad280-122">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="ad280-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ad280-123">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="ad280-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ad280-124">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ad280-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad280-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad280-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="ad280-126">So konfigurieren Sie die Option Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="ad280-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="ad280-127">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="ad280-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ad280-128">Klicken Sie auf den Knoten **Verbindungen** .</span><span class="sxs-lookup"><span data-stu-id="ad280-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="ad280-129">Aktivieren oder deaktivieren Sie unter **Remoteserververbindungen**das Kontrollkästchen **Remoteverbindungen mit diesem Server zulassen** .</span><span class="sxs-lookup"><span data-stu-id="ad280-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad280-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad280-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="ad280-131">So konfigurieren Sie die Option Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="ad280-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="ad280-132">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="ad280-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad280-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ad280-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ad280-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ad280-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ad280-135">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `remote access` auf `0`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ad280-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="ad280-136">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ad280-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a><span data-ttu-id="ad280-137">Nächster Schritt: Nach dem Konfigurieren der Option „Remotezugriff“</span><span class="sxs-lookup"><span data-stu-id="ad280-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="ad280-138">Diese Einstellung wird erst wirksam, wenn Sie SQL Server neu starten.</span><span class="sxs-lookup"><span data-stu-id="ad280-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad280-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad280-139">See Also</span></span>  
 <span data-ttu-id="ad280-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad280-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ad280-141">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad280-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ad280-142">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ad280-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
