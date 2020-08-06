---
title: Bearbeiten eines Proxys für den SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616340"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="adc43-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="adc43-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="adc43-103">In diesem Thema wird beschrieben, wie ein- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder geändert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adc43-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="adc43-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="adc43-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="adc43-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="adc43-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="adc43-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="adc43-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="adc43-107">Security</span><span class="sxs-lookup"><span data-stu-id="adc43-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="adc43-108">**So ändern Sie einen SQL Server-Agent-Proxy mit**</span><span class="sxs-lookup"><span data-stu-id="adc43-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="adc43-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="adc43-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="adc43-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="adc43-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="adc43-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="adc43-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="adc43-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="adc43-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="adc43-113">Von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxys werden Anmeldeinformationen zum Speichern von Informationen zu Windows-Benutzerkonten verwendet.</span><span class="sxs-lookup"><span data-stu-id="adc43-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="adc43-114">Der in der Anmeldeinformation angegebene Benutzer muss über eine Berechtigung des Typs "Anmelden als Stapelverarbeitungsauftrag" auf dem Computer verfügen, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="adc43-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="adc43-115">-Agent wird der Subsystemzugriff für einen Proxy überprüft und der Zugriff auf den Proxy jedes Mal dann gewährt, wenn der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="adc43-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="adc43-116">Wenn der Proxyzugriff auf das Subsystem nicht mehr länger möglich ist, erzeugt der Auftragsschritt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="adc43-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="adc43-117">Ansonsten wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Identität des Benutzers angenommen, der im Proxy angegeben ist und von dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="adc43-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="adc43-118">Wenn die Anmeldung für den Benutzer Zugriffsrecht auf den Proxy hat, oder der Benutzer zu einer Rolle mit Zugriffsrechten auf den Proxy gehört, kann der Benutzer den Proxy in einem Auftragsschritt verwenden.</span><span class="sxs-lookup"><span data-stu-id="adc43-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="adc43-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adc43-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="adc43-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="adc43-120">Permissions</span></span>  
 <span data-ttu-id="adc43-121">Nur Mitglieder der festen Serverrolle **sysadmin** können Proxykonten erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="adc43-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="adc43-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="adc43-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="adc43-123">So ändern Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxy</span><span class="sxs-lookup"><span data-stu-id="adc43-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="adc43-124">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxykonto enthält, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="adc43-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="adc43-125">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="adc43-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="adc43-126">Klicken Sie auf das Pluszeichen, um den Ordner **Proxys** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="adc43-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="adc43-127">Klicken Sie auf das Pluszeichen, um den Subsystemknoten für den Proxy (z. B. **ActiveX-Skript**) zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="adc43-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="adc43-128">Klicken Sie mit der rechten Maustaste auf das Proxykonto, das Sie ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="adc43-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="adc43-129">Nehmen Sie im Dialogfeld Eigenschaften des _proxy_name_**Proxy Kontos** nach Bedarf Änderungen am Proxy Konto vor.</span><span class="sxs-lookup"><span data-stu-id="adc43-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="adc43-130">Weitere Informationen über die Optionen in diesem Dialogfeld finden Sie unter [Erstellen eines Proxys für den SQL Server-Agent](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="adc43-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="adc43-131">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adc43-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="adc43-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="adc43-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="adc43-133">So ändern Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Proxy</span><span class="sxs-lookup"><span data-stu-id="adc43-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="adc43-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="adc43-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="adc43-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="adc43-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="adc43-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="adc43-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="adc43-137">Weitere Informationen finden Sie unter [sp_update_proxy &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="adc43-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  
