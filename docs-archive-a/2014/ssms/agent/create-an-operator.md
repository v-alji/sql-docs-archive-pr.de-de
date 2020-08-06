---
title: Erstellen eines Operators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699255"
---
# <a name="create-an-operator"></a><span data-ttu-id="1d906-102">Create an Operator</span><span class="sxs-lookup"><span data-stu-id="1d906-102">Create an Operator</span></span>
  <span data-ttu-id="1d906-103">In diesem Thema wird beschrieben, wie Sie einen Benutzer so konfigurieren, dass er Benachrichtigungen über- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder empfängt [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d906-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1d906-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1d906-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1d906-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1d906-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1d906-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d906-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1d906-107">Security</span><span class="sxs-lookup"><span data-stu-id="1d906-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1d906-108">**So erstellen Sie einen Operator mit**</span><span class="sxs-lookup"><span data-stu-id="1d906-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="1d906-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d906-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1d906-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d906-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d906-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1d906-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1d906-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d906-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1d906-113">Die Pager- und **net send** -Optionen werden in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr im [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d906-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1d906-114">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d906-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="1d906-115">Beachten Sie, dass E-Mail- und Pagerbenachrichtigungen an Operatoren nur versendet werden können, wenn der SQL Server-Agent für die Verwendung von Datenbank-E-Mail konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1d906-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="1d906-116">Weitere Informationen finden Sie unter [Zuweisen von Warnungen zu einem Operator](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1d906-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1d906-117">können Aufträge problemlos mithilfe einer grafischen Oberfläche verwaltet werden. Dies ist die empfohlene Vorgehensweise für die Erstellung und Verwaltung der Auftragsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="1d906-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d906-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1d906-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1d906-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1d906-119">Permissions</span></span>  
 <span data-ttu-id="1d906-120">Nur Mitglieder der festen Serverrolle **sysadmin** können Operatoren erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d906-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1d906-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d906-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="1d906-122">So erstellen Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="1d906-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="1d906-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie den SQL Server-Agent-Operator erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1d906-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="1d906-124">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1d906-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1d906-125">Klicken Sie mit der rechten Maustaste auf den Ordner **Operatoren** , und wählen Sie dann **Neuer Operator**aus.</span><span class="sxs-lookup"><span data-stu-id="1d906-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="1d906-126">Die folgenden Optionen befinden sich im Dialogfeld **Neuer Operator** auf der Seite **Allgemein** :</span><span class="sxs-lookup"><span data-stu-id="1d906-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="1d906-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="1d906-127">**Name**</span></span>  
     <span data-ttu-id="1d906-128">Ändern Sie den Namen des Operators.</span><span class="sxs-lookup"><span data-stu-id="1d906-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="1d906-129">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="1d906-129">**Enabled**</span></span>  
     <span data-ttu-id="1d906-130">Aktiviert den Operator.</span><span class="sxs-lookup"><span data-stu-id="1d906-130">Enable the operator.</span></span> <span data-ttu-id="1d906-131">Bei fehlender Aktivierung werden keine Benachrichtigungen an den Operator gesendet.</span><span class="sxs-lookup"><span data-stu-id="1d906-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="1d906-132">**E-Mail-Name**</span><span class="sxs-lookup"><span data-stu-id="1d906-132">**E-mail name**</span></span>  
     <span data-ttu-id="1d906-133">Gibt die E-Mail-Adresse des Operators an.</span><span class="sxs-lookup"><span data-stu-id="1d906-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="1d906-134">**NET SEND-Adresse**</span><span class="sxs-lookup"><span data-stu-id="1d906-134">**Net send address**</span></span>  
     <span data-ttu-id="1d906-135">Gibt die für **NET SEND**zu verwendende Adresse an.</span><span class="sxs-lookup"><span data-stu-id="1d906-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="1d906-136">**Pager-E-Mail-Name**</span><span class="sxs-lookup"><span data-stu-id="1d906-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="1d906-137">Gibt die E-Mail-Adresse für den Pager des Operators an.</span><span class="sxs-lookup"><span data-stu-id="1d906-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="1d906-138">**Pager empfangsbereit am**</span><span class="sxs-lookup"><span data-stu-id="1d906-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="1d906-139">Legt fest, zu welchen Zeiten der Pager aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="1d906-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="1d906-140">**Montag - Sonntag**</span><span class="sxs-lookup"><span data-stu-id="1d906-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="1d906-141">Wählen Sie die Tage aus, an denen der Pager aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="1d906-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="1d906-142">**Arbeitstag - Beginn**</span><span class="sxs-lookup"><span data-stu-id="1d906-142">**Workday begin**</span></span>  
     <span data-ttu-id="1d906-143">Wählen Sie die Tageszeit aus, nach deren Eintreten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent Meldungen an den Pager sendet.</span><span class="sxs-lookup"><span data-stu-id="1d906-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="1d906-144">**Arbeitstag - Ende**</span><span class="sxs-lookup"><span data-stu-id="1d906-144">**Workday end**</span></span>  
     <span data-ttu-id="1d906-145">Wählen Sie die Tageszeit aus, nach deren Eintreten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent keine weiteren Meldungen an den Pager sendet.</span><span class="sxs-lookup"><span data-stu-id="1d906-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="1d906-146">Die folgenden Optionen befinden sich im Dialogfeld **Neuer Operator** auf der Seite **Benachrichtigungen** :</span><span class="sxs-lookup"><span data-stu-id="1d906-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="1d906-147">**Warnungen**</span><span class="sxs-lookup"><span data-stu-id="1d906-147">**Alerts**</span></span>  
     <span data-ttu-id="1d906-148">Zeigt die Warnungen in der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="1d906-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="1d906-149">**Aufträge**</span><span class="sxs-lookup"><span data-stu-id="1d906-149">**Jobs**</span></span>  
     <span data-ttu-id="1d906-150">Zeigt die Aufträge in der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="1d906-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="1d906-151">**Warnungs Liste**</span><span class="sxs-lookup"><span data-stu-id="1d906-151">**Alert list**</span></span>  
     <span data-ttu-id="1d906-152">Listet die Warnungen in der Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="1d906-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="1d906-153">**Auftragsliste**</span><span class="sxs-lookup"><span data-stu-id="1d906-153">**Job list**</span></span>  
     <span data-ttu-id="1d906-154">Listet die Aufträge in der Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="1d906-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="1d906-155">**E**</span><span class="sxs-lookup"><span data-stu-id="1d906-155">**E-mail**</span></span>  
     <span data-ttu-id="1d906-156">Benachrichtigt den Operator per E-Mail.</span><span class="sxs-lookup"><span data-stu-id="1d906-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="1d906-157">**Pager**</span><span class="sxs-lookup"><span data-stu-id="1d906-157">**Pager**</span></span>  
     <span data-ttu-id="1d906-158">Benachrichtigt den Operator, indem eine E-Mail-Nachricht an die Pageradresse gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d906-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="1d906-159">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="1d906-159">**Net send**</span></span>  
     <span data-ttu-id="1d906-160">Benachrichtigt diesen Operator per **net send**.</span><span class="sxs-lookup"><span data-stu-id="1d906-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="1d906-161">Klicken Sie auf **OK**, wenn Sie das Erstellen des neuen Operators abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="1d906-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1d906-162">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d906-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="1d906-163">So erstellen Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="1d906-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="1d906-164">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="1d906-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d906-165">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1d906-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1d906-166">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1d906-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="1d906-167">Weitere Informationen finden Sie unter [sp_add_operator &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d906-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
