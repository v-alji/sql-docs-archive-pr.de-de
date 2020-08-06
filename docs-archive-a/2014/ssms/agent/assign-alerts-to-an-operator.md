---
title: Zuweisen von Warnungen zu einem Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617369"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="e9f29-102">Assign Alerts to an Operator</span><span class="sxs-lookup"><span data-stu-id="e9f29-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="e9f29-103">In diesem Thema wird beschrieben, wie- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnungen zu Operatoren zugewiesen werden, damit diese in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder Benachrichtigungen über Aufträge empfangen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9f29-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e9f29-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e9f29-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e9f29-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e9f29-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e9f29-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e9f29-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e9f29-107">Security</span><span class="sxs-lookup"><span data-stu-id="e9f29-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e9f29-108">**So weisen Sie einem Operator Warnungen zu mit**</span><span class="sxs-lookup"><span data-stu-id="e9f29-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="e9f29-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9f29-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e9f29-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9f29-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e9f29-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e9f29-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e9f29-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e9f29-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="e9f29-113">kann das gesamte Warnungssystem auf einfache Weise über eine grafische Oberfläche verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e9f29-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="e9f29-114">Für die Konfiguration einer Warnungsinfrastruktur sollte [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9f29-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="e9f29-115">Zum Senden einer Benachrichtigung als Reaktion auf eine Warnung müssen Sie zunächst den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent für das Senden von E-Mail konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e9f29-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="e9f29-116">Weitere Informationen finden Sie unter [Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="e9f29-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="e9f29-117">Wenn beim Senden einer E-Mail- oder Pagerbenachrichtigung ein Fehler auftritt, wird der Fehler im Fehlerprotokoll des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e9f29-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e9f29-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e9f29-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e9f29-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e9f29-119">Permissions</span></span>  
 <span data-ttu-id="e9f29-120">Nur Mitglieder der festen Serverrolle **sysadmin** können Operatoren Warnungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e9f29-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e9f29-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9f29-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="e9f29-122">So weisen Sie einem Operator Warnungen zu</span><span class="sxs-lookup"><span data-stu-id="e9f29-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="e9f29-123">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Operator enthält, dem Sie die Warnung zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="e9f29-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="e9f29-124">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e9f29-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e9f29-125">Klicken Sie auf das Pluszeichen, um den Ordner **Operatoren** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e9f29-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="e9f29-126">Klicken Sie mit der rechten Maustaste auf den Operator, dem Sie eine Warnung zuweisen möchten, wählen Sie **Eigenschaften**aus, und wählen Sie die Seite **Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e9f29-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="e9f29-127">Wählen Sie im Dialogfeld _operator_name_**Eigenschaften** unter **Seite auswählen**die Option **Benachrichtigungen**aus.</span><span class="sxs-lookup"><span data-stu-id="e9f29-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="e9f29-128">Wählen Sie unter **Benachrichtigungen an diesen Benutzer anzeigen von**die Option **Warnung** aus, um eine Liste der Warnungen anzuzeigen, die an diesen Operator gesendet wurden, oder wählen Sie **Aufträge** aus, um eine Liste der Aufträge anzuzeigen, von denen Benachrichtigungen an diesen Operator gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9f29-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="e9f29-129">Aktivieren Sie mindestens eines der folgenden Kontrollkästchen, um die Benachrichtigungsmethode für jede Benachrichtigung zu definieren: **E-Mail**, **Pager**oder **NET SEND**.</span><span class="sxs-lookup"><span data-stu-id="e9f29-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="e9f29-130">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9f29-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e9f29-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9f29-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="e9f29-132">So weisen Sie einem Operator Warnungen zu</span><span class="sxs-lookup"><span data-stu-id="e9f29-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="e9f29-133">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e9f29-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9f29-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e9f29-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e9f29-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e9f29-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="e9f29-136">Weitere Informationen finden Sie unter [sp_add_notification &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9f29-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
