---
title: Benachrichtigen eines Operators über den Auftragsstatus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616331"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="e2e63-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="e2e63-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="e2e63-103">In diesem Thema wird beschrieben, wie Benachrichtigungs Optionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects festgelegt werden, damit der- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Benachrichtigungen zu Aufträgen an Operatoren senden kann.</span><span class="sxs-lookup"><span data-stu-id="e2e63-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="e2e63-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e2e63-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e2e63-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e2e63-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2e63-106">Security</span><span class="sxs-lookup"><span data-stu-id="e2e63-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e2e63-107">**So benachrichtigen Sie einen Operator über einen Auftragsstatus mit**</span><span class="sxs-lookup"><span data-stu-id="e2e63-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="e2e63-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2e63-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e2e63-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2e63-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e2e63-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e2e63-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2e63-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e2e63-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2e63-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e2e63-112">Security</span></span>  
 <span data-ttu-id="e2e63-113">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e2e63-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e2e63-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2e63-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="e2e63-115">So benachrichtigen Sie einen Operator über einen Auftragsstatus</span><span class="sxs-lookup"><span data-stu-id="e2e63-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="e2e63-116">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="e2e63-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e2e63-117">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie bearbeiten möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e2e63-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="e2e63-118">Wählen Sie im Dialogfeld **Auftragseigenschaften** die Seite **Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e2e63-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="e2e63-119">Wenn ein Operator per E-Mail benachrichtigt werden soll, aktivieren Sie die Option **E-Mail**, wählen Sie aus der Liste einen Operator aus, und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e2e63-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="e2e63-120">**Bei erfolgreicher Auftragsausführung** , um den Operator zu benachrichtigen, wenn der Auftrag erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e63-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-121">**Bei Auftragsfehler** , um den Operator zu benachrichtigen, wenn der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="e2e63-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-122">**Beim Abschluss des Auftrags** , um den Operator unabhängig vom Abschlussstatus zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="e2e63-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="e2e63-123">Wenn ein Operator per Pager benachrichtigt werden soll, aktivieren Sie die Option **Pager**, wählen Sie aus der Liste einen Operator aus, und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e2e63-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="e2e63-124">**Bei erfolgreicher Auftragsausführung** , um den Operator zu benachrichtigen, wenn der Auftrag erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e63-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-125">**Bei Auftragsfehler** , um den Operator zu benachrichtigen, wenn der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="e2e63-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-126">**Beim Abschluss des Auftrags** , um den Operator unabhängig vom Abschlussstatus zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="e2e63-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="e2e63-127">Wenn ein Operator per NET SEND benachrichtigt werden soll, aktivieren Sie die Option **NET SEND**, wählen Sie aus der Liste einen Operator aus, und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e2e63-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="e2e63-128">**Bei erfolgreicher Auftragsausführung** , um den Operator zu benachrichtigen, wenn der Auftrag erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e63-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-129">**Bei Auftragsfehler** , um den Operator zu benachrichtigen, wenn der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="e2e63-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="e2e63-130">**Beim Abschluss des Auftrags** , um den Operator unabhängig vom Abschlussstatus zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="e2e63-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e2e63-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2e63-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="e2e63-132">So benachrichtigen Sie einen Operator über einen Auftragsstatus</span><span class="sxs-lookup"><span data-stu-id="e2e63-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="e2e63-133">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e2e63-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2e63-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e2e63-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e2e63-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e2e63-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="e2e63-136">Weitere Informationen finden Sie unter [sp_add_notification &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2e63-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e2e63-137">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e2e63-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e2e63-138">**So benachrichtigen Sie einen Operator über einen Auftragsstatus**</span><span class="sxs-lookup"><span data-stu-id="e2e63-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="e2e63-139">Verwenden Sie die `Job`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2e63-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="e2e63-140">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e2e63-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
