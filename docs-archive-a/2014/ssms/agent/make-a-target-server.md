---
title: Erstellen eines Zielservers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695261"
---
# <a name="make-a-target-server"></a><span data-ttu-id="0e885-102">Erstellen eines Zielservers</span><span class="sxs-lookup"><span data-stu-id="0e885-102">Make a Target Server</span></span>
  <span data-ttu-id="0e885-103">In diesem Thema wird beschrieben, wie Sie einen Zielserver in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder SQL Server Management Objects (SMO) erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e885-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="0e885-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0e885-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0e885-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0e885-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0e885-106">Security</span><span class="sxs-lookup"><span data-stu-id="0e885-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0e885-107">**Erstellen eines Zielservers mit:**</span><span class="sxs-lookup"><span data-stu-id="0e885-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="0e885-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0e885-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0e885-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0e885-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="0e885-110">SMO</span><span class="sxs-lookup"><span data-stu-id="0e885-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0e885-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0e885-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0e885-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0e885-112">Security</span></span>  
 <span data-ttu-id="0e885-113">Verteilte Aufträge mit Schritten, die einem Proxy zugeordnet sind, werden im Kontext des Proxykontos auf dem Zielserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e885-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="0e885-114">Stellen Sie sicher, dass die folgenden Bedingungen erfüllt sind, da andernfalls einem Proxy zugeordnete Auftragsschritte nicht vom Masterserver auf den Zielserver heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="0e885-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="0e885-115">Der Registrierungs Unterschlüssel für den Master Server **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server agent\allowprotoadedjobstomatchproxyname** (REG_DWORD) ist auf 1 (true) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e885-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="0e885-116">Dieser Unterschlüssel ist standardmäßig auf 0 (false) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e885-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="0e885-117">Auf dem Zielserver ist ein Proxykonto vorhanden, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e885-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="0e885-118">Falls bei Auftragsschritten, die Proxykonten verwenden, beim Herunterladen vom Masterserver auf den Zielserver ein Fehler auftritt, können Sie die **error_message** -Spalte in der **sysdownloadlist** -Tabelle der **msdb** -Datenbank auf die folgenden Fehlermeldungen überprüfen:</span><span class="sxs-lookup"><span data-stu-id="0e885-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="0e885-119">"Für den Auftragsschritt ist ein Proxykonto erforderlich, das Proxyabgleichen ist auf dem Zielserver aber deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="0e885-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="0e885-120">Um diesen Fehler zu beheben, legen Sie den Registrierungsunterschlüssel **AllowDownloadedJobsToMatchProxyName** auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="0e885-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="0e885-121">"Proxy nicht gefunden."</span><span class="sxs-lookup"><span data-stu-id="0e885-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="0e885-122">Um diesen Fehler zu beheben, stellen Sie sicher, dass auf dem Zielserver ein Proxykonto vorhanden ist, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e885-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0e885-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0e885-123">Permissions</span></span>  
 <span data-ttu-id="0e885-124">Berechtigungen zur Ausführung dieser Prozedur erhalten standardmäßig Mitglieder der festen Serverrolle `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="0e885-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0e885-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0e885-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="0e885-126">So erstellen Sie einen Zielserver</span><span class="sxs-lookup"><span data-stu-id="0e885-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="0e885-127">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e885-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0e885-128">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserveradministration**, und klicken Sie dann auf **Als Zielserver einrichten**.</span><span class="sxs-lookup"><span data-stu-id="0e885-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="0e885-129">Der **Zielservererstellungs-Assistent** führt Sie durch die Schritte zum Erstellen eines Zielservers.</span><span class="sxs-lookup"><span data-stu-id="0e885-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="0e885-130">Wählen Sie auf der Seite **Wählen Sie einen Masterserver aus** den Masterserver aus, von dem dieser Zielserver Aufträge erhält.</span><span class="sxs-lookup"><span data-stu-id="0e885-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="0e885-131">**Server auswählen**</span><span class="sxs-lookup"><span data-stu-id="0e885-131">**Pick Server**</span></span>  
     <span data-ttu-id="0e885-132">Stellen Sie eine Verbindung zum Masterserver her.</span><span class="sxs-lookup"><span data-stu-id="0e885-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="0e885-133">**Beschreibung dieses Servers**</span><span class="sxs-lookup"><span data-stu-id="0e885-133">**Description of this server**</span></span>  
     <span data-ttu-id="0e885-134">Geben Sie eine Beschreibung für diesen Zielserver ein.</span><span class="sxs-lookup"><span data-stu-id="0e885-134">Type a description for this target server.</span></span> <span data-ttu-id="0e885-135">Die Beschreibung wird vom Zielserver auf den Masterserver hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="0e885-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="0e885-136">Erstellen Sie ggf. auf der Seite **Masterserver-Anmeldeinformationen** einen neuen Anmeldenamen auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="0e885-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="0e885-137">**Bei Bedarf eine neue Anmeldung erstellen und ihr Rechte für MSX zuweisen**</span><span class="sxs-lookup"><span data-stu-id="0e885-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="0e885-138">Erstellt eine neue Anmeldung auf dem Zielserver, sofern die angegebene Anmeldung noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0e885-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0e885-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0e885-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="0e885-140">So erstellen Sie einen Zielserver</span><span class="sxs-lookup"><span data-stu-id="0e885-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="0e885-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="0e885-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0e885-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0e885-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0e885-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0e885-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0e885-144">Im folgenden Beispiel wird der aktuelle Server auf dem Masterserver "AdventureWorks1" eingetragen.</span><span class="sxs-lookup"><span data-stu-id="0e885-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="0e885-145">Der Speicherort für den aktuellen Server ist "Building 21, Room 309, Rack 5".</span><span class="sxs-lookup"><span data-stu-id="0e885-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="0e885-146">Weitere Informationen finden Sie unter [sp_msx_enlist &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0e885-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="0e885-147">Verwenden von SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="0e885-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e885-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e885-148">See Also</span></span>  
 [<span data-ttu-id="0e885-149">Automatisierte Verwaltung in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="0e885-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
