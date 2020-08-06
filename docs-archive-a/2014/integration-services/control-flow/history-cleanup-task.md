---
title: Verlaufscleanup (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607934"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="e2c22-102">Verlaufscleanup (Task)</span><span class="sxs-lookup"><span data-stu-id="e2c22-102">History Cleanup Task</span></span>
  <span data-ttu-id="e2c22-103">Der Task Verlaufscleanup löscht Einträge in den folgenden Verlaufstabellen in der msdb-Datenbank von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2c22-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="e2c22-104">backupfile</span><span class="sxs-lookup"><span data-stu-id="e2c22-104">backupfile</span></span>  
  
-   <span data-ttu-id="e2c22-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="e2c22-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="e2c22-106">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="e2c22-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="e2c22-107">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="e2c22-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="e2c22-108">backupset</span><span class="sxs-lookup"><span data-stu-id="e2c22-108">backupset</span></span>  
  
-   <span data-ttu-id="e2c22-109">restorefile</span><span class="sxs-lookup"><span data-stu-id="e2c22-109">restorefile</span></span>  
  
-   <span data-ttu-id="e2c22-110">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="e2c22-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="e2c22-111">restorehistory</span><span class="sxs-lookup"><span data-stu-id="e2c22-111">restorehistory</span></span>  
  
 <span data-ttu-id="e2c22-112">Mithilfe des Tasks "Verlaufscleanup" können für ein Paket Vergangenheitsdaten für Sicherungs- und Wiederherstellungsaktivitäten, Aufträge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents und Datenbankwartungspläne gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e2c22-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="e2c22-113">Dieser Task kapselt die gespeicherte Systemprozedur sp_delete_backuphistory und übergibt das angegebene Datum als Argument an die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e2c22-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="e2c22-114">Weitere Informationen finden Sie unter [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2c22-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="e2c22-115">Konfiguration der Task "Verlaufscleanup"</span><span class="sxs-lookup"><span data-stu-id="e2c22-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="e2c22-116">Dieser Task umfasst eine Eigenschaft zur Angabe des am weitesten zurückliegenden Datums von Daten, die in Verlaufstabellen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="e2c22-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="e2c22-117">Sie können das Datum anhand der Anzahl von Tagen, Wochen, Monaten oder Jahren ab dem aktuellen Datum angeben. Der Task übersetzt das Intervall dann automatisch in ein Datum.</span><span class="sxs-lookup"><span data-stu-id="e2c22-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="e2c22-118">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="e2c22-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e2c22-119">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2c22-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e2c22-120">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e2c22-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2c22-121">Task „Verlaufscleanup“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="e2c22-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="e2c22-122">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e2c22-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2c22-123">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="e2c22-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2c22-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2c22-124">See Also</span></span>  
 <span data-ttu-id="e2c22-125">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e2c22-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e2c22-126">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="e2c22-126">Control Flow</span></span>](control-flow.md)  
  
  
