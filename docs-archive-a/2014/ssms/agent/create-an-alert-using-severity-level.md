---
title: Erstellen einer Warnung mithilfe von Schweregraden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- severity levels [SQL Server]
- alerts [SQL Server], severity levels
ms.assetid: a1fd71bf-5bf9-4ce2-9a1d-032576a4a6e9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ee353129d60fe7fc8bed0eff279920d8d4ba640
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719399"
---
# <a name="create-an-alert-using-severity-level"></a><span data-ttu-id="92382-102">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="92382-102">Create an Alert Using Severity Level</span></span>
  <span data-ttu-id="92382-103">In diesem Thema wird beschrieben, wie Sie eine- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnung erstellen, die ausgelöst wird, wenn ein Ereignis mit einem bestimmten Schweregrad in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder auftritt [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92382-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92382-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="92382-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92382-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="92382-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92382-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="92382-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="92382-107">Security</span><span class="sxs-lookup"><span data-stu-id="92382-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92382-108">**So erstellen Sie eine Warnung mithilfe von Schweregraden mit**</span><span class="sxs-lookup"><span data-stu-id="92382-108">**To create an alert using severity level, using:**</span></span>  
  
     [<span data-ttu-id="92382-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92382-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="92382-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92382-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92382-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="92382-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="92382-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="92382-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="92382-113">lässt sich das gesamte Warnungssystem auf einfache Weise mit einer grafischen Oberfläche verwalten. Dies ist die empfohlene Vorgehensweise, um eine Warnungsinfrastruktur zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="92382-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="92382-114">Ereignisse, die mit **xp_logevent** generiert werden, treten in der master-Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="92382-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="92382-115">Daher wird von **xp_logevent** erst dann eine Warnung ausgegeben, wenn der **@database_name** -Wert für die Warnung den Wert **'master'** oder NULL hat.</span><span class="sxs-lookup"><span data-stu-id="92382-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="92382-116">Bei den Schweregraden 19 bis 25 wird eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Meldung an das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows gesendet und eine Warnung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="92382-116">Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log and trigger an alert.</span></span> <span data-ttu-id="92382-117">Ereignisse mit einem Schweregrad unter 19 lösen nur dann Warnungen aus, wenn Sie **sp_altermessage**, RAISERROR WITH LOG oder **xp_logevent** verwendet haben, um zu erzwingen, dass die Warnungen in das Windows-Anwendungsprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="92382-117">Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92382-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="92382-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92382-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="92382-119">Permissions</span></span>  
 <span data-ttu-id="92382-120">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** die Prozedur **sp_add_alert**ausführen.</span><span class="sxs-lookup"><span data-stu-id="92382-120">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92382-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92382-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="92382-122">So erstellen Sie eine Warnung mithilfe von Schweregraden</span><span class="sxs-lookup"><span data-stu-id="92382-122">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="92382-123">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine Warnung mithilfe des Schweregrads erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="92382-123">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.</span></span>  
  
2.  <span data-ttu-id="92382-124">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="92382-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="92382-125">Klicken Sie mit der rechten Maustaste auf **Warnungen** , und wählen Sie **Neue Warnung**aus.</span><span class="sxs-lookup"><span data-stu-id="92382-125">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="92382-126">Geben Sie im Dialogfeld **Neue Warnung** einen **Namen** für diese Warnung ein.</span><span class="sxs-lookup"><span data-stu-id="92382-126">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="92382-127">Klicken Sie in der Liste **Typ** auf **SQL Server-Ereigniswarnung**.</span><span class="sxs-lookup"><span data-stu-id="92382-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
6.  <span data-ttu-id="92382-128">Klicken Sie in der Liste **Datenbankname**auf den **Datenbanknamen**, um die Warnung auf eine bestimmte Datenbank zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="92382-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
7.  <span data-ttu-id="92382-129">Klicken Sie unter **Warnungen werden ausgelöst basierend auf**auf **Schweregrad** , und wählen Sie dann den bestimmten Schweregrad aus, womit die Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="92382-129">Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
8.  <span data-ttu-id="92382-130">Aktivieren Sie das Kontrollkästchen neben **Warnung auslösen, wenn eine Meldung Folgendes enthält** , um die Warnung auf eine bestimmte Zeichenfolge zu beschränken, und geben Sie dann ein Schlüsselwort oder Zeichenfolge für den **Meldungstext**ein.</span><span class="sxs-lookup"><span data-stu-id="92382-130">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="92382-131">Es können maximal 100 Zeichen eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92382-131">The maximum number of characters is 100.</span></span>  
  
9. <span data-ttu-id="92382-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="92382-132">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92382-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92382-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="92382-134">So erstellen Sie eine Warnung mithilfe von Schweregraden</span><span class="sxs-lookup"><span data-stu-id="92382-134">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="92382-135">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="92382-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92382-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="92382-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92382-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="92382-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="92382-138">Weitere Informationen finden Sie unter [Sp_add_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92382-138">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
