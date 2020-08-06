---
title: Konfigurieren der Serverkonfigurationsoption „Timeout für Remoteanmeldung“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609432"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="5bfd6-102">Konfigurieren der Serverkonfigurationsoption Timeout für Remoteanmeldungen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="5bfd6-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Timeout für Remoteanmeldung** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5bfd6-104">Mit der Option **Timeout für Remoteanmeldung** können Sie den Zeitraum in Sekunden angeben, wie lange gewartet werden soll, bevor ein Remoteanmeldeversuch einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="5bfd6-105">Wenn Sie z. B versuchen, sich an einem Remoteserver anzumelden, und dieser Server derzeit nicht betriebsbereit ist, wird durch **Timeout für Remoteanmeldung** sichergestellt, dass Sie nicht unbegrenzt warten müssen, bis der Computer seine Anmeldeversuche beendet.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="5bfd6-106">Der Standardwert für diese Option ist 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="5bfd6-107">Bei einem Wert von 0 ist eine unbegrenzte Wartezeit zulässig.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5bfd6-108">Der Standardwert für diese Option in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]ist 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="5bfd6-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5bfd6-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5bfd6-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5bfd6-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5bfd6-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5bfd6-112">Security</span><span class="sxs-lookup"><span data-stu-id="5bfd6-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5bfd6-113">**So konfigurieren Sie die Option Timeout für Remoteanmeldung mit:**</span><span class="sxs-lookup"><span data-stu-id="5bfd6-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="5bfd6-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bfd6-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5bfd6-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bfd6-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5bfd6-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Timeout für Remoteanmeldung“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5bfd6-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5bfd6-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5bfd6-119">Die Option **Timeout für Remoteanmeldung** wirkt sich auf Verbindungen mit OLE DB-Anbieter aus, die für heterogene Abfragen hergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5bfd6-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5bfd6-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5bfd6-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-121">Permissions</span></span>  
 <span data-ttu-id="5bfd6-122">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5bfd6-123">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5bfd6-124">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5bfd6-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bfd6-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="5bfd6-126">So konfigurieren Sie die Option Timeout für Remoteanmeldung</span><span class="sxs-lookup"><span data-stu-id="5bfd6-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="5bfd6-127">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5bfd6-128">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="5bfd6-129">Wählen Sie unter **Netzwerk**einen Wert im Feld **Timeout für Remoteanmeldung** aus.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="5bfd6-130">Sie können mithilfe der Option **Timeout für Remoteanmeldung** den Zeitraum in Sekunden angeben, wie lange gewartet werden soll, bevor für einen Remoteanmeldeversuch ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5bfd6-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bfd6-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="5bfd6-132">So konfigurieren Sie die Option Timeout für Remoteanmeldung</span><span class="sxs-lookup"><span data-stu-id="5bfd6-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="5bfd6-133">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5bfd6-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5bfd6-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5bfd6-136">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `remote login timeout` auf `35` Sekunden festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="5bfd6-137">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a><span data-ttu-id="5bfd6-138">Nächster Schritt: Nach dem Konfigurieren der Option „Timeout für Remoteanmeldung“</span><span class="sxs-lookup"><span data-stu-id="5bfd6-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="5bfd6-139">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfd6-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bfd6-140">See Also</span></span>  
 <span data-ttu-id="5bfd6-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5bfd6-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5bfd6-142">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5bfd6-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5bfd6-143">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5bfd6-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
