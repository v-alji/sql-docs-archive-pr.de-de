---
title: Schreiben des Auftragsstatus in das Windows-Anwendungsprotokoll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719360"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="d92ee-102">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="d92ee-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="d92ee-103">In diesem Thema wird beschrieben, wie der-Agent in so konfiguriert wird, dass [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] der Auftragsstatus mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , oder SQL Server Management Objects in das Windows-Anwendungs Ereignisprotokoll geschrieben wird [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d92ee-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="d92ee-104">Sie stellen sicher, dass Datenbankadministratoren wissen, wann Aufträge fertig gestellt sind und wie oft diese ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d92ee-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="d92ee-105">Zu den typischen Auftragsantworten gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="d92ee-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="d92ee-106">Benachrichtigen des Operators per E-Mail, Pager oder **NET SEND** -Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d92ee-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="d92ee-107">Verwenden Sie eine dieser Auftragsantworten vor allem dann, wenn der Operator weitere Schritte ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="d92ee-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="d92ee-108">Wenn beispielsweise ein Sicherungsauftrag erfolgreich ausgeführt wurde, muss der Operator darüber informiert werden, um das Sicherungsband entfernen zu können und an einem sicheren Standort aufbewahren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="d92ee-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="d92ee-109">Schreiben einer Ereignismeldung in das Windows-Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d92ee-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="d92ee-110">Diese Art der Antwort können Sie nur bei fehlgeschlagenen Aufträgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d92ee-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="d92ee-111">Automatisches Löschen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="d92ee-111">Automatically deleting the job.</span></span> <span data-ttu-id="d92ee-112">Verwenden Sie diese Auftragsantwort, wenn Sie sicher sind, dass Sie diesen Auftrag nicht erneut ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="d92ee-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="d92ee-113">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d92ee-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d92ee-114">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d92ee-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d92ee-115">Security</span><span class="sxs-lookup"><span data-stu-id="d92ee-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d92ee-116">**So schreiben Sie den Auftragsstatus in das Windows-Anwendungsprotokoll, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="d92ee-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="d92ee-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d92ee-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d92ee-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d92ee-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d92ee-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d92ee-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d92ee-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d92ee-120">Security</span></span>  
 <span data-ttu-id="d92ee-121">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d92ee-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d92ee-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d92ee-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="d92ee-123">So schreiben Sie den Auftragsstatus in das Windows-Anwendungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="d92ee-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="d92ee-124">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d92ee-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d92ee-125">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d92ee-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d92ee-126">Wählen Sie die Seite **Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="d92ee-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="d92ee-127">Aktivieren Sie **In Windows-Anwendungsereignisprotokoll schreiben**, und wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d92ee-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="d92ee-128">Klicken Sie auf**Bei erfolgreicher Auftragsausführung**, um den Auftragsstatus zu protokollieren, wenn der Auftrag erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d92ee-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="d92ee-129">Klicken Sie auf**Bei Auftragsfehler**, um den Auftragsstatus zu protokollieren, wenn der Auftrag nicht erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d92ee-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="d92ee-130">Klicken Sie auf**Beim Abschluss des Auftrags** , um den Auftragsstatus unabhängig vom Abschlussstatus zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="d92ee-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d92ee-131">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d92ee-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="d92ee-132">So schreiben Sie den Auftragsstatus in das Windows-Anwendungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="d92ee-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="d92ee-133">Rufen Sie die `EventLogLevel`-Eigenschaft der `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d92ee-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="d92ee-134">Im folgenden Codebeispiel wird der Auftrag so festgelegt, dass bei Abschluss der Auftragsausführung ein Betriebssystem-Ereignisprotokolleintrag generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d92ee-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
