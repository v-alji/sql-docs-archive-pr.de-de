---
title: Einrichten eines Masterservers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617356"
---
# <a name="make-a-master-server"></a><span data-ttu-id="1dd81-102">Make a Master Server</span><span class="sxs-lookup"><span data-stu-id="1dd81-102">Make a Master Server</span></span>
  <span data-ttu-id="1dd81-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] einen [!INCLUDE[tsql](../../includes/tsql-md.md)]-Masterserver einrichten.</span><span class="sxs-lookup"><span data-stu-id="1dd81-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1dd81-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1dd81-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1dd81-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1dd81-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1dd81-106">Security</span><span class="sxs-lookup"><span data-stu-id="1dd81-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1dd81-107">**Einrichten eines Masterservers mit:**</span><span class="sxs-lookup"><span data-stu-id="1dd81-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="1dd81-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1dd81-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1dd81-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1dd81-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1dd81-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1dd81-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1dd81-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1dd81-111">Security</span></span>  
 <span data-ttu-id="1dd81-112">Verteilte Aufträge mit Schritten, die einem Proxy zugeordnet sind, werden im Kontext des Proxykontos auf dem Zielserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1dd81-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="1dd81-113">Stellen Sie sicher, dass die folgenden Bedingungen erfüllt sind, da andernfalls einem Proxy zugeordnete Auftragsschritte nicht vom Masterserver auf den Zielserver heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="1dd81-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="1dd81-114">Der Registrierungs Unterschlüssel für den Master Server **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server agent\allowprotoadedjobstomatchproxyname** (REG_DWORD) ist auf 1 (true) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1dd81-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="1dd81-115">Dieser Unterschlüssel ist standardmäßig auf 0 (false) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1dd81-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="1dd81-116">Auf dem Zielserver ist ein Proxykonto vorhanden, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dd81-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="1dd81-117">Falls bei Auftragsschritten, die Proxykonten verwenden, beim Herunterladen vom Masterserver auf den Zielserver ein Fehler auftritt, können Sie die **error_message** -Spalte in der **sysdownloadlist** -Tabelle der **msdb** -Datenbank auf die folgenden Fehlermeldungen überprüfen:</span><span class="sxs-lookup"><span data-stu-id="1dd81-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="1dd81-118">"Für den Auftragsschritt ist ein Proxykonto erforderlich, das Proxyabgleichen ist auf dem Zielserver aber deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="1dd81-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="1dd81-119">Um diesen Fehler zu beheben, legen Sie den Registrierungsunterschlüssel **AllowDownloadedJobsToMatchProxyName** auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="1dd81-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="1dd81-120">"Proxy nicht gefunden."</span><span class="sxs-lookup"><span data-stu-id="1dd81-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="1dd81-121">Um diesen Fehler zu beheben, stellen Sie sicher, dass auf dem Zielserver ein Proxykonto vorhanden ist, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dd81-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1dd81-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1dd81-122">Permissions</span></span>  
 <span data-ttu-id="1dd81-123">Berechtigungen zur Ausführung dieser Prozedur erhalten standardmäßig Mitglieder der festen Serverrolle `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="1dd81-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1dd81-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1dd81-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="1dd81-125">So richten Sie einen Masterserver ein</span><span class="sxs-lookup"><span data-stu-id="1dd81-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="1dd81-126">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="1dd81-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1dd81-127">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserveradministration**, und klicken Sie dann auf **Als Masterserver einrichten**.</span><span class="sxs-lookup"><span data-stu-id="1dd81-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="1dd81-128">Der **Masterserver-Assistent** führt Sie durch die Schritte zum Einrichten eines Masterservers und Hinzufügen eines Zielservers.</span><span class="sxs-lookup"><span data-stu-id="1dd81-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="1dd81-129">Konfigurieren Sie auf der Seite **Masterserveroperator** einen Operator, damit der Masterserver Benachrichtigungen per E-Mail oder mittels Pager an Operatoren sendet. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zum Senden von E-Mails konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1dd81-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="1dd81-130">Um Operatoren die Benachrichtigungen mithilfe von **NET SEND**zu senden, muss auf dem Server mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent der Messenger-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1dd81-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="1dd81-131">**E-Mail Adresse**</span><span class="sxs-lookup"><span data-stu-id="1dd81-131">**E-mail address**</span></span>  
     <span data-ttu-id="1dd81-132">Legt die E-Mail-Adresse des Operators fest.</span><span class="sxs-lookup"><span data-stu-id="1dd81-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="1dd81-133">**Pageradresse**</span><span class="sxs-lookup"><span data-stu-id="1dd81-133">**Pager address**</span></span>  
     <span data-ttu-id="1dd81-134">Legt die Pager-E-Mail-Adresse des Operators fest.</span><span class="sxs-lookup"><span data-stu-id="1dd81-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="1dd81-135">**NET SEND-Adresse**</span><span class="sxs-lookup"><span data-stu-id="1dd81-135">**Net send address**</span></span>  
     <span data-ttu-id="1dd81-136">Legt die **NET SEND** -Adresse des Operators fest.</span><span class="sxs-lookup"><span data-stu-id="1dd81-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="1dd81-137">Wählen Sie auf der Seite **Zielserver** Zielserver für den Masterserver aus.</span><span class="sxs-lookup"><span data-stu-id="1dd81-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="1dd81-138">**Registrierte Server**</span><span class="sxs-lookup"><span data-stu-id="1dd81-138">**Registered Servers**</span></span>  
     <span data-ttu-id="1dd81-139">Listet die in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] registrierten Server auf, die noch nicht als Zielserver festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="1dd81-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="1dd81-140">**Zielserver**</span><span class="sxs-lookup"><span data-stu-id="1dd81-140">**Target Servers**</span></span>  
     <span data-ttu-id="1dd81-141">Listet die Server auf, die Zielserver sind.</span><span class="sxs-lookup"><span data-stu-id="1dd81-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="1dd81-142">Verschiebt den ausgewählten Server in die Liste mit den Zielservern.</span><span class="sxs-lookup"><span data-stu-id="1dd81-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="1dd81-143">Verschiebt alle Server auf die Zielserverliste.</span><span class="sxs-lookup"><span data-stu-id="1dd81-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="1dd81-144">Entfernt den ausgewählten Server aus der Liste mit den Zielservern.</span><span class="sxs-lookup"><span data-stu-id="1dd81-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="1dd81-145">Entfernt alle Server von der Zielserverliste.</span><span class="sxs-lookup"><span data-stu-id="1dd81-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="1dd81-146">**Verbindung hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="1dd81-146">**Add connection**</span></span>  
     <span data-ttu-id="1dd81-147">Fügt der Zielserverliste einen Server hinzu, ohne diesen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="1dd81-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="1dd81-148">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1dd81-148">**Connection**</span></span>  
     <span data-ttu-id="1dd81-149">Ändert die Verbindungseigenschaften der ausgewählten Server.</span><span class="sxs-lookup"><span data-stu-id="1dd81-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="1dd81-150">Geben Sie auf der Seite **Masterserver-Anmeldeinformationen** an, ob für den Zielserver ein neuer Anmeldename erstellt werden soll, und weisen Sie ihm ggf. Rechte für den Masterserver zu.</span><span class="sxs-lookup"><span data-stu-id="1dd81-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="1dd81-151">**Bei Bedarf eine neue Anmeldung erstellen und ihr Rechte für MSX zuweisen**</span><span class="sxs-lookup"><span data-stu-id="1dd81-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="1dd81-152">Erstellt eine neue Anmeldung auf dem Zielserver, sofern die angegebene Anmeldung noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1dd81-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1dd81-153">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1dd81-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="1dd81-154">So richten Sie einen Masterserver ein</span><span class="sxs-lookup"><span data-stu-id="1dd81-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="1dd81-155">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1dd81-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1dd81-156">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1dd81-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1dd81-157">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1dd81-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1dd81-158">Im folgenden Beispiel wird der aktuelle Server auf dem Masterserver "AdventureWorks1" eingetragen.</span><span class="sxs-lookup"><span data-stu-id="1dd81-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="1dd81-159">Der Speicherort für den aktuellen Server ist "Building 21, Room 309, Rack 5".</span><span class="sxs-lookup"><span data-stu-id="1dd81-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="1dd81-160">Weitere Informationen finden Sie unter [sp_msx_enlist &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1dd81-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd81-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1dd81-161">See Also</span></span>  
 <span data-ttu-id="1dd81-162">[Erstellen einer Multiserverumgebung](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="1dd81-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="1dd81-163">Automatisierte Verwaltung in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1dd81-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
