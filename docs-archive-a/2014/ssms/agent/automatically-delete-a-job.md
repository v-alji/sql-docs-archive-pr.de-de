---
title: Automatisches Löschen eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619547"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="83bdb-102">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="83bdb-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="83bdb-103">In diesem Thema wird beschrieben, wie der-Agent in so konfiguriert wird, dass [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Aufträge mithilfe von oder SQL Server Management Objects automatisch gelöscht werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83bdb-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="83bdb-104">Sie stellen sicher, dass Datenbankadministratoren wissen, wann Aufträge fertig gestellt sind und wie oft diese ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="83bdb-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="83bdb-105">Zu den typischen Auftragsantworten gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="83bdb-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="83bdb-106">Benachrichtigen des Operators per E-Mail, Pager oder **NET SEND** -Nachricht.</span><span class="sxs-lookup"><span data-stu-id="83bdb-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="83bdb-107">Verwenden Sie eine dieser Auftragsantworten vor allem dann, wenn der Operator weitere Schritte ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="83bdb-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="83bdb-108">Wenn beispielsweise ein Sicherungsauftrag erfolgreich ausgeführt wurde, muss der Operator darüber informiert werden, um das Sicherungsband entfernen zu können und an einem sicheren Standort aufbewahren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="83bdb-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="83bdb-109">Schreiben einer Ereignismeldung in das Windows-Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="83bdb-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="83bdb-110">Diese Art der Antwort können Sie nur bei fehlgeschlagenen Aufträgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83bdb-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="83bdb-111">Automatisches Löschen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="83bdb-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="83bdb-112">Verwenden Sie diese Auftragsantwort, wenn Sie sicher sind, dass Sie diesen Auftrag nicht erneut ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="83bdb-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="83bdb-113">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="83bdb-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="83bdb-114">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="83bdb-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="83bdb-115">Security</span><span class="sxs-lookup"><span data-stu-id="83bdb-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="83bdb-116">**So geben Sie Auftragsantworten an mit**</span><span class="sxs-lookup"><span data-stu-id="83bdb-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="83bdb-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83bdb-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="83bdb-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="83bdb-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83bdb-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="83bdb-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="83bdb-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="83bdb-120">Security</span></span>  
 <span data-ttu-id="83bdb-121">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="83bdb-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="83bdb-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83bdb-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="83bdb-123">So löschen Sie einen Auftrag automatisch</span><span class="sxs-lookup"><span data-stu-id="83bdb-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="83bdb-124">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="83bdb-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="83bdb-125">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="83bdb-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="83bdb-126">Wählen Sie die Seite **Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="83bdb-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="83bdb-127">Aktivieren Sie **Auftrag automatisch löschen**, und führen Sie eine der folgenden Handlungen aus:</span><span class="sxs-lookup"><span data-stu-id="83bdb-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="83bdb-128">Klicken Sie auf **Bei erfolgreicher Ausführung des Auftrags** , um den Auftragsstatus zu löschen, wenn der Auftrag erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="83bdb-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="83bdb-129">Klicken Sie auf **Bei Auftragsfehler** , um den Auftrag zu löschen, wenn er nicht erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="83bdb-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="83bdb-130">Klicken Sie auf **Beim Abschluss des Auftrags** , um den Auftrag unabhängig vom Abschlussstatus zu löschen.</span><span class="sxs-lookup"><span data-stu-id="83bdb-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="83bdb-131">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="83bdb-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="83bdb-132">**So löschen Sie einen Auftrag automatisch**</span><span class="sxs-lookup"><span data-stu-id="83bdb-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="83bdb-133">Verwenden Sie die `DeleteLevel`-Eigenschaft der `Job`-Klasse in einer Programmiersprache Ihrer Wahl, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83bdb-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="83bdb-134">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="83bdb-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
