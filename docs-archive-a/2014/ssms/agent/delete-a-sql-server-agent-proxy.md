---
title: Löschen eines SQL Server-Agent-Proxys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620110"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="226cf-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="226cf-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="226cf-103">In diesem Thema wird beschrieben, wie Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxykonto in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen können.</span><span class="sxs-lookup"><span data-stu-id="226cf-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="226cf-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="226cf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="226cf-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="226cf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="226cf-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="226cf-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="226cf-107">Security</span><span class="sxs-lookup"><span data-stu-id="226cf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="226cf-108">**So löschen Sie einen SQL Server-Agent-Proxykonto mit**</span><span class="sxs-lookup"><span data-stu-id="226cf-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="226cf-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="226cf-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="226cf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="226cf-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="226cf-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="226cf-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="226cf-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="226cf-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="226cf-113">Wenn Sie das Proxykonto eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents löschen, sollten Sie sicherstellen, dass der Proxy keine Verweise auf aktive Auftragsschritte enthält.</span><span class="sxs-lookup"><span data-stu-id="226cf-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="226cf-114">Klicken Sie mit der rechten Maustaste auf den Proxy, um nach Auftragsschritten zu suchen, die auf den Proxy verweisen. Wählen Sie **Eigenschaften**aus, und wählen Sie dann im Dialogfeld _Proxyname_**-Proxykonto** die Seite **Verweise** aus.</span><span class="sxs-lookup"><span data-stu-id="226cf-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="226cf-115">Beim Löschen eines Proxys können Sie im Dialogfeld **Objekt löschen** die Auftragsschritte, die diesen Proxy verwenden, neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="226cf-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="226cf-116">Von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxys werden Anmeldeinformationen zum Speichern von Informationen zu Windows-Benutzerkonten verwendet.</span><span class="sxs-lookup"><span data-stu-id="226cf-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="226cf-117">Der in der Anmeldeinformation angegebene Benutzer muss über eine Berechtigung des Typs "Anmelden als Stapelverarbeitungsauftrag" auf dem Computer verfügen, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="226cf-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="226cf-118">-Agent wird der Subsystemzugriff für einen Proxy überprüft und der Zugriff auf den Proxy jedes Mal dann gewährt, wenn der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="226cf-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="226cf-119">Wenn der Proxyzugriff auf das Subsystem nicht mehr länger möglich ist, erzeugt der Auftragsschritt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="226cf-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="226cf-120">Ansonsten wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Identität des Benutzers angenommen, der im Proxy angegeben ist und von dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="226cf-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="226cf-121">Wenn die Anmeldung für den Benutzer Zugriffsrecht auf den Proxy hat, oder der Benutzer zu einer Rolle mit Zugriffsrechten auf den Proxy gehört, kann der Benutzer den Proxy in einem Auftragsschritt verwenden.</span><span class="sxs-lookup"><span data-stu-id="226cf-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="226cf-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="226cf-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="226cf-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="226cf-123">Permissions</span></span>  
 <span data-ttu-id="226cf-124">Nur Mitglieder der festen Serverrolle **sysadmin** können Proxykonten erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="226cf-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="226cf-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="226cf-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="226cf-126">So löschen Sie ein SQL Server-Agent-Proxykonto</span><span class="sxs-lookup"><span data-stu-id="226cf-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="226cf-127">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der das Proxykonto enthält, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="226cf-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="226cf-128">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="226cf-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="226cf-129">Klicken Sie auf das Pluszeichen, um den Ordner **Proxys** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="226cf-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="226cf-130">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um das Subsystem zu erweitern, das zu löschende Proxykonto enthält (z. B. **ActiveX-Skript**).</span><span class="sxs-lookup"><span data-stu-id="226cf-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="226cf-131">Klicken Sie mit der rechten Maustaste auf das Proxykonto, das Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="226cf-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="226cf-132">Bestätigen Sie im Dialogfeld **Objekt löschen** , dass das richtige Proxykonto ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="226cf-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="226cf-133">Aktivieren Sie das Kontrollkästchen **Neu zuweisen an** , um die Auftragsschritte, die auf dieses Proxykonto verweisen, einem anderen Proxykonto zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="226cf-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="226cf-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="226cf-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="226cf-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="226cf-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="226cf-136">So löschen Sie ein SQL Server-Agent-Proxykonto</span><span class="sxs-lookup"><span data-stu-id="226cf-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="226cf-137">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="226cf-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="226cf-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="226cf-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="226cf-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="226cf-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="226cf-140">Weitere Informationen finden Sie unter [sp_delete_proxy &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="226cf-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  
