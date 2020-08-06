---
title: Erstellen eines Proxys für den SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620114"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="d36ef-102">Erstellen eines Proxys für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="d36ef-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="d36ef-103">In diesem Thema wird beschrieben, wie SQL Server-Agent-Proxys in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d36ef-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d36ef-104">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxykonto definiert einen Sicherheitskontext, in dem ein Auftragsschritt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d36ef-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="d36ef-105">Jeder Proxy entspricht einem Satz Sicherheitsanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="d36ef-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="d36ef-106">Um Berechtigungen für einen bestimmten Auftragsschritt festzulegen, erstellen Sie ein Proxykonto mit den erforderlichen Berechtigungen für ein Subsystem des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents und weisen dann dieses Proxykonto dem Auftragsschritt zu.</span><span class="sxs-lookup"><span data-stu-id="d36ef-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="d36ef-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d36ef-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d36ef-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d36ef-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d36ef-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d36ef-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d36ef-110">Security</span><span class="sxs-lookup"><span data-stu-id="d36ef-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d36ef-111">**So erstellen Sie einen Proxy für den SQL Server-Agent mit**</span><span class="sxs-lookup"><span data-stu-id="d36ef-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="d36ef-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d36ef-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d36ef-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d36ef-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d36ef-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d36ef-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d36ef-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d36ef-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d36ef-116">Sie müssen, falls keine Anmeldeinformationen vorhanden sind, Anmeldeinformationen erstellen, bevor Sie ein Proxykonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="d36ef-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="d36ef-117">Von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxys werden Anmeldeinformationen zum Speichern von Informationen zu Windows-Benutzerkonten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d36ef-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="d36ef-118">Der in der Anmeldeinformation angegebene Benutzer muss über eine Berechtigung des Typs "Anmelden als Stapelverarbeitungsauftrag" auf dem Computer verfügen, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d36ef-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d36ef-119">-Agent wird der Subsystemzugriff für einen Proxy überprüft und der Zugriff auf den Proxy jedes Mal dann gewährt, wenn der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d36ef-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="d36ef-120">Wenn der Proxyzugriff auf das Subsystem nicht mehr länger möglich ist, erzeugt der Auftragsschritt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d36ef-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="d36ef-121">Ansonsten wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Identität des Benutzers angenommen, der im Proxy angegeben ist und von dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d36ef-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="d36ef-122">Die Berechtigungen für den Benutzer werden nicht durch das Erstellen eines Proxys geändert, der in den Anmeldeinformationen für den Proxy angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d36ef-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="d36ef-123">Sie können beispielsweise einen Proxy für einen Benutzer erstellen, der keine Verbindungsberechtigung für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hat.</span><span class="sxs-lookup"><span data-stu-id="d36ef-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d36ef-124">In diesem Fall kann von Auftragsschritten, die diesen Proxy verwenden, keine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d36ef-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d36ef-125">Wenn die Anmeldung für den Benutzer Zugriffsrecht auf den Proxy hat, oder der Benutzer zu einer Rolle mit Zugriffsrechten auf den Proxy gehört, kann der Benutzer den Proxy in einem Auftragsschritt verwenden.</span><span class="sxs-lookup"><span data-stu-id="d36ef-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d36ef-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d36ef-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d36ef-127">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d36ef-127">Permissions</span></span>  
  
-   <span data-ttu-id="d36ef-128">Nur Mitglieder der festen Serverrolle **sysadmin** haben die Berechtigung zum Erstellen, Ändern oder Löschen von Proxykonten.</span><span class="sxs-lookup"><span data-stu-id="d36ef-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="d36ef-129">Benutzer, die nicht Mitglieder der festen Serverrolle **sysadmin** sind, müssen zur Verwendung von Proxys einer der folgenden festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents in der **msdb** -Datenbank hinzugefügt werden: **SQLAgentUserRole**, **SQLAgentReaderRole**oder **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="d36ef-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="d36ef-130">Erfordert die `ALTER ANY CREDENTIAL`-Berechtigung, wenn für den Proxy zusätzlich eine Anmeldeinformation erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d36ef-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d36ef-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d36ef-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="d36ef-132">So erstellen Sie einen Proxy für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="d36ef-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="d36ef-133">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie ein Proxy auf dem SQL Server-Agent erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d36ef-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="d36ef-134">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d36ef-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d36ef-135">Klicken Sie mit der rechten Maustaste auf den Ordner **Proxys** , und wählen Sie dann **Neuer Proxy**aus.</span><span class="sxs-lookup"><span data-stu-id="d36ef-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="d36ef-136">Geben Sie in das Dialogfeld **Neues Proxykonto** auf der Seite **Allgemein** den Namen des neuen Proxykontos in das Feld **Proxyname** ein.</span><span class="sxs-lookup"><span data-stu-id="d36ef-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="d36ef-137">Geben Sie im Feld **Anmeldeinformationsname** den Namen der Sicherheitsanmeldeinformationen ein, die vom Proxykonto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d36ef-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="d36ef-138">Geben Sie im Feld **Beschreibung** eine Beschreibung für das Proxykonto ein.</span><span class="sxs-lookup"><span data-stu-id="d36ef-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="d36ef-139">Wählen Sie unter **Folgenden Subsystemen gegenüber aktiv**das bzw. die entsprechenden Subsysteme für diesen Proxy aus.</span><span class="sxs-lookup"><span data-stu-id="d36ef-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="d36ef-140">Auf der Seite **Prinzipale** können Sie Anmeldenamen oder Rollen hinzufügen oder entfernen, um den Zugriff auf das Proxykonto zu erteilen oder zu entziehen.</span><span class="sxs-lookup"><span data-stu-id="d36ef-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="d36ef-141">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d36ef-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d36ef-142">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d36ef-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="d36ef-143">So erstellen Sie einen Proxy für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="d36ef-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="d36ef-144">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d36ef-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d36ef-145">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d36ef-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d36ef-146">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d36ef-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="d36ef-147">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="d36ef-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d36ef-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d36ef-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="d36ef-149">sp_add_proxy &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="d36ef-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="d36ef-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="d36ef-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
