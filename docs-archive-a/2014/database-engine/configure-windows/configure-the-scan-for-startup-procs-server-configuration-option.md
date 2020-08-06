---
title: Konfigurieren der Serverkonfigurationsoption „Startprozeduren suchen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616167"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="27b9b-102">Konfigurieren der Serverkonfigurationsoption Startprozeduren suchen</span><span class="sxs-lookup"><span data-stu-id="27b9b-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="27b9b-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Startprozeduren suchen** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="27b9b-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="27b9b-104">Sie können mithilfe der Option **Startprozeduren suchen** nach der automatischen Ausführung gespeicherter Prozeduren zum Startzeitpunkt von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suchen.</span><span class="sxs-lookup"><span data-stu-id="27b9b-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="27b9b-105">Wenn diese Option auf 1 festgelegt ist, sucht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nach allen automatisch ausgeführten gespeicherten Prozeduren, die auf dem Server definiert sind, und führt diese aus.</span><span class="sxs-lookup"><span data-stu-id="27b9b-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="27b9b-106">Der Standardwert für **Startprozeduren suchen** ist „0“ (kein Scannen).</span><span class="sxs-lookup"><span data-stu-id="27b9b-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="27b9b-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="27b9b-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="27b9b-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="27b9b-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="27b9b-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="27b9b-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="27b9b-110">Security</span><span class="sxs-lookup"><span data-stu-id="27b9b-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="27b9b-111">**So konfigurieren Sie die Option Startprozeduren suchen mit:**</span><span class="sxs-lookup"><span data-stu-id="27b9b-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="27b9b-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27b9b-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="27b9b-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27b9b-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="27b9b-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Startprozeduren suchen“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="27b9b-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27b9b-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="27b9b-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="27b9b-116">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="27b9b-116">Recommendations</span></span>  
  
-   <span data-ttu-id="27b9b-117">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="27b9b-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="27b9b-118">Der Wert für diese Option kann mithilfe von **sp_configure**festgelegt werden. Er wird jedoch automatisch festgelegt, wenn Sie die gespeicherte Systemprozedur **sp_procoption**verwenden. Diese Prozedur wird verwendet, um gespeicherte Prozeduren als automatisch ausgeführte Prozeduren zu kennzeichnen oder die Kennzeichnung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="27b9b-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="27b9b-119">Wird **sp_procoption** zum Kennzeichnen der ersten gespeicherten Prozedur als autoproc verwendet, wird für diese Option automatisch der Wert „1“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27b9b-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="27b9b-120">Wenn **sp_procoption** verwendet wird, um die Kennzeichnung der letzten gespeicherten Prozedur als autoproc aufzuheben, wird der Wert für diese Option automatisch auf „0“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27b9b-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="27b9b-121">Wenn Sie **sp_procoption** zum Kennzeichnen bzw. zum Aufheben von Kennzeichnungen verwenden und die Kennzeichnungen von autoprocs vor dem Löschen immer aufheben, ist es nicht notwendig, diese Option manuell festzulegen.</span><span class="sxs-lookup"><span data-stu-id="27b9b-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27b9b-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27b9b-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27b9b-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="27b9b-123">Permissions</span></span>  
 <span data-ttu-id="27b9b-124">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="27b9b-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="27b9b-125">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="27b9b-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="27b9b-126">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="27b9b-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="27b9b-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27b9b-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="27b9b-128">So konfigurieren Sie die Option "Startprozeduren suchen"</span><span class="sxs-lookup"><span data-stu-id="27b9b-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="27b9b-129">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="27b9b-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="27b9b-130">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="27b9b-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="27b9b-131">Ändern Sie unter **Sonstiges**die Option **Startprozeduren suchen** in TRUE oder FALSE, indem Sie im Dropdown-Listenfeld den gewünschten Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="27b9b-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="27b9b-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27b9b-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="27b9b-133">So konfigurieren Sie die Option "Startprozeduren suchen"</span><span class="sxs-lookup"><span data-stu-id="27b9b-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="27b9b-134">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="27b9b-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="27b9b-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="27b9b-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="27b9b-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="27b9b-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="27b9b-137">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `scan for startup procs` auf `1`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="27b9b-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a><span data-ttu-id="27b9b-138">Nächster Schritt: Nach dem Konfigurieren der Option „Startprozeduren suchen“</span><span class="sxs-lookup"><span data-stu-id="27b9b-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="27b9b-139">Der Server muss neu gestartet werden, bevor die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="27b9b-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b9b-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27b9b-140">See Also</span></span>  
 <span data-ttu-id="27b9b-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27b9b-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="27b9b-142">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="27b9b-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="27b9b-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27b9b-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="27b9b-144">sp_procoption (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="27b9b-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
