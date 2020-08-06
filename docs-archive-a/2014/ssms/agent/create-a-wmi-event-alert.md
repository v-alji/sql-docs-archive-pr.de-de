---
title: Erstellen einer WMI-Ereigniswarnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619541"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="9e17e-102">Erstellen einer WMI-Ereigniswarnung</span><span class="sxs-lookup"><span data-stu-id="9e17e-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="9e17e-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine Warnung des [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Agents erstellen, die beim Auftreten eines bestimmten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Ereignisses ausgelöst wird, das vom WMI-Anbieter für Serverereignisse überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="9e17e-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9e17e-104">Informationen zum Verwenden des WMI-Anbieters zum Überwachen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ereignissen finden Sie unter [WMI-Anbieter für Server Ereignisse-Konzepte](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="9e17e-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="9e17e-105">Informationen zu den Berechtigungen, die erforderlich sind, um Benachrichtigungen zu WMI-Ereigniswarnungen zu erhalten, finden Sie unter [Auswählen eines Kontos für den SQL Server-Agent-Dienst](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="9e17e-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="9e17e-106">Weitere Informationen zu WQL finden Sie unter [Verwenden von WQL mit dem WMI-Anbieter für Serverereignisse](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="9e17e-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="9e17e-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9e17e-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9e17e-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9e17e-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9e17e-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9e17e-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9e17e-110">Security</span><span class="sxs-lookup"><span data-stu-id="9e17e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9e17e-111">**Erstellen einer WMI-Ereigniswarnung mit:**</span><span class="sxs-lookup"><span data-stu-id="9e17e-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="9e17e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9e17e-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9e17e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9e17e-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9e17e-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9e17e-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9e17e-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9e17e-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="9e17e-116">lässt sich das gesamte Warnungssystem auf einfache Weise mit einer grafischen Oberfläche verwalten. Dies ist die empfohlene Vorgehensweise, um eine Warnungsinfrastruktur zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e17e-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="9e17e-117">Ereignisse, die mit **xp_logevent** generiert werden, treten in der master-Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="9e17e-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="9e17e-118">Daher wird von **xp_logevent** erst dann eine Warnung ausgegeben, wenn der **@database_name** -Wert für die Warnung den Wert **'master'** oder NULL hat.</span><span class="sxs-lookup"><span data-stu-id="9e17e-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="9e17e-119">Es werden nur WMI-Namespaces auf dem Computer unterstützt, auf dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9e17e-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9e17e-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9e17e-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9e17e-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9e17e-121">Permissions</span></span>  
 <span data-ttu-id="9e17e-122">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** die Prozedur **sp_add_alert**ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e17e-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9e17e-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9e17e-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="9e17e-124">So erstellen Sie eine WMI-Ereigniswarnung</span><span class="sxs-lookup"><span data-stu-id="9e17e-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="9e17e-125">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine WMI-Ereigniswarnung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9e17e-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="9e17e-126">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="9e17e-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="9e17e-127">Klicken Sie mit der rechten Maustaste auf **Warnungen** , und wählen Sie **Neue Warnung**aus.</span><span class="sxs-lookup"><span data-stu-id="9e17e-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="9e17e-128">Geben Sie im Dialogfeld **Neue Warnung** einen **Namen** für diese Warnung ein.</span><span class="sxs-lookup"><span data-stu-id="9e17e-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="9e17e-129">Aktivieren Sie das Kontrollkästchen **Aktivieren** , um die Ausführung der Warnung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9e17e-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="9e17e-130">Standardmäßig ist **Aktivieren** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e17e-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="9e17e-131">Klicken Sie in der Liste **Typ** auf **WMI-Ereigniswarnung**.</span><span class="sxs-lookup"><span data-stu-id="9e17e-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="9e17e-132">Geben Sie unter **WMI-Ereigniswarnungsdefinition**im Feld **Namespace** den WMI-Namespace für die WQL-Anweisung (WMI Query Language) an, die das WMI-Ereignis identifiziert, welches diese Warnung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9e17e-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="9e17e-133">Geben Sie im Feld **Abfrage** die WQL-Anweisung an, die das Ereignis identifiziert, auf das diese Warnung reagiert.</span><span class="sxs-lookup"><span data-stu-id="9e17e-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="9e17e-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e17e-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9e17e-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9e17e-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="9e17e-136">So erstellen Sie eine WMI-Ereigniswarnung</span><span class="sxs-lookup"><span data-stu-id="9e17e-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="9e17e-137">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="9e17e-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9e17e-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9e17e-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9e17e-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9e17e-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="9e17e-140">Weitere Informationen finden Sie unter [Sp_add_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9e17e-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
