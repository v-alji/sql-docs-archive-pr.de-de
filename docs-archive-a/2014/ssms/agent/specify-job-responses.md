---
title: Angeben von Auftragsantworten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695254"
---
# <a name="specify-job-responses"></a><span data-ttu-id="cb8a8-102">Angeben von Auftragsantworten</span><span class="sxs-lookup"><span data-stu-id="cb8a8-102">Specify Job Responses</span></span>
  <span data-ttu-id="cb8a8-103">Auftragsantworten geben Aktionen an, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst nach Abschluss eines Auftrags ausführt.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="cb8a8-104">Sie stellen sicher, dass Datenbankadministratoren wissen, wann Aufträge fertig gestellt sind und wie oft diese ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="cb8a8-105">Zu den typischen Auftragsantworten gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="cb8a8-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="cb8a8-106">Benachrichtigen des Operators per E-Mail, Pager oder **NET SEND** -Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="cb8a8-107">Verwenden Sie eine dieser Auftragsantworten vor allem dann, wenn der Operator weitere Schritte ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="cb8a8-108">Wenn beispielsweise ein Sicherungsauftrag erfolgreich ausgeführt wurde, muss der Operator darüber informiert werden, um das Sicherungsband entfernen zu können und an einem sicheren Standort aufbewahren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="cb8a8-109">Schreiben einer Ereignismeldung in das Windows-Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="cb8a8-110">Diese Art der Antwort können Sie nur bei fehlgeschlagenen Aufträgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="cb8a8-111">Automatisches Löschen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="cb8a8-112">Verwenden Sie diese Auftragsantwort, wenn Sie sicher sind, dass Sie diesen Auftrag nicht erneut ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="cb8a8-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="cb8a8-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb8a8-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cb8a8-114">**Description**</span></span>|<span data-ttu-id="cb8a8-115">**Thema**</span><span class="sxs-lookup"><span data-stu-id="cb8a8-115">**Topic**</span></span>|  
|<span data-ttu-id="cb8a8-116">Beschreibt, wie ein Operator über den Auftragsstatus benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="cb8a8-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="cb8a8-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="cb8a8-118">Beschreibt, wie der Auftragsstatus in das Windows-Anwendungsprotokoll ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="cb8a8-119">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="cb8a8-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cb8a8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb8a8-120">See Also</span></span>  
 [<span data-ttu-id="cb8a8-121">Überwachen und Reagieren auf Ereignisse</span><span class="sxs-lookup"><span data-stu-id="cb8a8-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
