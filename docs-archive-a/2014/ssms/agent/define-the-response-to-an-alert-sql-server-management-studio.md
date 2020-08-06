---
title: Definieren der Antwort auf eine Warnung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699218"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="0a6ed-102">Define the Response to an Alert (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0a6ed-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0a6ed-103">In diesem Thema wird beschrieben, wie Sie definieren können [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , wie auf-Agent- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Warnungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder reagiert [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a6ed-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0a6ed-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0a6ed-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a6ed-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0a6ed-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a6ed-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0a6ed-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0a6ed-107">Security</span><span class="sxs-lookup"><span data-stu-id="0a6ed-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a6ed-108">**So definieren Sie die Antwort auf eine Warnung mit**</span><span class="sxs-lookup"><span data-stu-id="0a6ed-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="0a6ed-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a6ed-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0a6ed-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a6ed-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a6ed-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0a6ed-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0a6ed-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0a6ed-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0a6ed-113">Die Pager- und **net send** -Optionen werden in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr im [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a6ed-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0a6ed-114">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="0a6ed-115">Beachten Sie, dass E-Mail- und Pagerbenachrichtigungen an Operatoren nur versendet werden können, wenn der SQL Server-Agent für die Verwendung von Datenbank-E-Mail konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="0a6ed-116">Weitere Informationen finden Sie unter [Zuweisen von Warnungen zu einem Operator](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0a6ed-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0a6ed-117">können Aufträge problemlos mithilfe einer grafischen Oberfläche verwaltet werden. Dies ist die empfohlene Vorgehensweise für die Erstellung und Verwaltung der Auftragsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a6ed-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0a6ed-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a6ed-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a6ed-119">Permissions</span></span>  
 <span data-ttu-id="0a6ed-120">Nur Mitglieder der festen Serverrolle **sysadmin** können die Antwort auf eine Warnung definieren.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a6ed-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a6ed-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="0a6ed-122">So definieren Sie die Antwort auf eine Warnung</span><span class="sxs-lookup"><span data-stu-id="0a6ed-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="0a6ed-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der die Warnung enthält, für die Sie eine Warnung definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="0a6ed-124">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0a6ed-125">Klicken Sie auf das Pluszeichen, um den Ordner **Warnungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="0a6ed-126">Klicken Sie mit der rechten Maustaste auf die Warnung, für die Sie eine Antwort definieren möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="0a6ed-127">Wählen Sie im Dialogfeld _Warnungsname_**Eigenschaften von Warnung** unter **Seite auswählen**die Option **Antwort**aus.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="0a6ed-128">Aktivieren Sie das Kontrollkästchen **Auftrag ausführen** , und wählen Sie aus der Liste unter dem Kontrollkästchen **Auftrag ausführen** einen Auftrag aus, der ausgeführt werden soll, wenn die Warnung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="0a6ed-129">Sie können einen neuen Auftrag erstellen, indem Sie auf **Neuer Auftrag**klicken.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="0a6ed-130">Um weitere Informationen zu dem Auftrag anzuzeigen, klicken Sie auf **Auftrag anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="0a6ed-131">Weitere Informationen zu den verfügbaren Optionen in den Dialogfeldern **Neuer Auftrag** und **Auftragseigenschaften**_Auftragsname_ finden Sie unter [Erstellen eines Auftrags](create-a-job.md) und [Anzeigen eines Auftrags](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="0a6ed-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="0a6ed-132">Aktivieren Sie das Kontrollkästchen **Operatoren benachrichtigen** , sofern Sie Operatoren benachrichtigen möchten, wenn eine Warnung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="0a6ed-133">Wählen Sie in der Liste **Operator**mindestens eine der folgenden Methoden für die Benachrichtigung eines Operators bzw. von Operatoren aus: **E-Mail**, **Pager**oder **NET SEND**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="0a6ed-134">Sie können einen neuen Operator erstellen, indem Sie auf **Neuer Operator**klicken.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="0a6ed-135">Um weitere Informationen über einen Operator anzuzeigen, klicken Sie auf **Operator anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="0a6ed-136">Weitere Informationen zu den verfügbaren Optionen im Dialogfeld **Neuer Operator** und im Dialogfeld zum **Anzeigen von Operatoreigenschaften** unter [Create an Operator](create-an-operator.md) und [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0a6ed-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="0a6ed-137">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a6ed-138">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a6ed-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="0a6ed-139">So definieren Sie die Antwort auf eine Warnung</span><span class="sxs-lookup"><span data-stu-id="0a6ed-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="0a6ed-140">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0a6ed-141">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0a6ed-142">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0a6ed-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="0a6ed-143">Weitere Informationen finden Sie unter [sp_add_notification &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a6ed-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
