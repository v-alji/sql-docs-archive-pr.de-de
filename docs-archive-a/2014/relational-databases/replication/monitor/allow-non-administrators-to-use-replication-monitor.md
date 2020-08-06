---
title: Zulassen, dass Nichtadministratoren den Replikationsmonitor verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615940"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="13465-102">Zulassen, dass Nichtadministratoren den Replikationsmonitor verwenden</span><span class="sxs-lookup"><span data-stu-id="13465-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="13465-103">In diesem Thema wird beschrieben, wie Nicht-Administratoren ermöglicht wird, den Replikationsmonitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="13465-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="13465-104">Der Replikationsmonitor kann von Benutzern verwendet werden, die Mitglieder der folgenden Rollen sind:</span><span class="sxs-lookup"><span data-stu-id="13465-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="13465-105">Feste Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="13465-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="13465-106">Diese Benutzer können die Replikation überwachen und haben den vollen Zugriff in Bezug auf Änderungen der Replikationseigenschaften, wie beispielsweise Zeitpläne für Agents, Agentprofile usw.</span><span class="sxs-lookup"><span data-stu-id="13465-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="13465-107">Die `replmonitor` Daten Bank Rolle in der Verteilungs Datenbank.</span><span class="sxs-lookup"><span data-stu-id="13465-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="13465-108">Diese Benutzer können die Replikation überwachen, aber keine Replikationseigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="13465-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="13465-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="13465-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="13465-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="13465-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="13465-111">Security</span><span class="sxs-lookup"><span data-stu-id="13465-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="13465-112">**So ermöglichen Sie Nichtadministratoren die Verwendung des Replikationsmonitors mit:**</span><span class="sxs-lookup"><span data-stu-id="13465-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="13465-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13465-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="13465-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13465-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="13465-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="13465-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="13465-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="13465-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="13465-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="13465-117">Permissions</span></span>  
 <span data-ttu-id="13465-118">Um nicht Administratoren die Verwendung des Replikations Monitors zu gestatten, muss ein Mitglied der festen Server Rolle **sysadmin** den Benutzer der Verteilungs Datenbank hinzufügen und diesen Benutzer der `replmonitor` Rolle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="13465-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="13465-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13465-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="13465-120">So lassen Sie zu, dass Nichtadministratoren den Replikationsmonitor verwenden</span><span class="sxs-lookup"><span data-stu-id="13465-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="13465-121">Stellen Sie in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verteiler her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="13465-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="13465-122">Erweitern Sie **Datenbanken**und **Systemdatenbanken**, und erweitern Sie die Verteilungsdatenbank (standardmäßig als **distribution** bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="13465-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="13465-123">Erweitern Sie **Sicherheit**, klicken Sie mit der rechten Maustaste auf **Benutzer**, und klicken Sie dann auf **Neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="13465-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="13465-124">Geben Sie einen Benutzernamen und ein Kennwort für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="13465-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="13465-125">Wählen Sie ein Standardschema aus `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="13465-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="13465-126">Aktivieren Sie das `replmonitor` Kontrollkästchen im Raster **Daten bankrollen Mitgliedschaft** .</span><span class="sxs-lookup"><span data-stu-id="13465-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="13465-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13465-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="13465-128">So fügen Sie der festen Datenbankrolle "replmonitor" einen Benutzer hinzu</span><span class="sxs-lookup"><span data-stu-id="13465-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="13465-129">Führen Sie auf dem Verteiler für die Verteilungsdatenbank [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="13465-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="13465-130">Wenn der Benutzer nicht im `UserName` Resultset aufgeführt ist, muss dem Benutzer mithilfe der Anweisung [Create User &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) Zugriff auf die Verteilungs Datenbank erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="13465-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="13465-131">Führen Sie auf dem Verteiler für die Verteilungs Datenbank [sp_helprolemember &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql)aus, und geben Sie dabei `replmonitor` den Wert für den-Parameter an **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="13465-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="13465-132">Wenn der Benutzer in `MemberName` dem Resultset aufgeführt ist, gehört der Benutzer bereits zu dieser Rolle.</span><span class="sxs-lookup"><span data-stu-id="13465-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="13465-133">Wenn der Benutzer nicht zur `replmonitor` Rolle gehört, führen Sie [sp_addrolemember &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) auf dem Verteiler für die Verteilungs Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="13465-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="13465-134">Geben Sie den Wert `replmonitor` für **@rolename** und den Namen des Daten Bank Benutzers oder den [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows-Anmelde Namen an, der für hinzugefügt wird **@membername** .</span><span class="sxs-lookup"><span data-stu-id="13465-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="13465-135">So entfernen Sie einen Benutzer aus der festen Datenbankrolle "replmonitor"</span><span class="sxs-lookup"><span data-stu-id="13465-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="13465-136">Um zu überprüfen, ob der Benutzer der `replmonitor` Rolle angehört, führen Sie [sp_helprolemember &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) auf dem Verteiler für die Verteilungs Datenbank aus, und geben Sie den Wert für an `replmonitor` **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="13465-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="13465-137">Wenn der Benutzer unter `MemberName` im Resultset nicht aufgeführt wird, gehört der Benutzer aktuell nicht zu der Rolle.</span><span class="sxs-lookup"><span data-stu-id="13465-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="13465-138">Wenn der Benutzer der `replmonitor` Rolle angehört, führen Sie [sp_droprolemember &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) auf dem Verteiler für die Verteilungs Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="13465-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="13465-139">Geben Sie den Wert `replmonitor` für **@rolename** und den Namen des Daten Bank Benutzers oder den Windows-Anmelde Namen an, der für entfernt wird **@membername** .</span><span class="sxs-lookup"><span data-stu-id="13465-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
