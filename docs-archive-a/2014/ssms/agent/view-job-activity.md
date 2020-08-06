---
title: Auftragsaktivitäten anzeigen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725225"
---
# <a name="view-job-activity"></a><span data-ttu-id="605c8-102">Auftragsaktivitäten anzeigen</span><span class="sxs-lookup"><span data-stu-id="605c8-102">View Job Activity</span></span>
  <span data-ttu-id="605c8-103">In diesem Thema wird beschrieben, wie Sie den Laufzeitstatus von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträgen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="605c8-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="605c8-104">Wenn der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Dienst startet, wird eine neue Sitzung erstellt, und die **sysjobactivity**-Tabelle in der **msdb**-Datenbank wird mit allen vorhandenen definierten Aufträgen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="605c8-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="605c8-105">In dieser Tabelle werden die aktuelle Auftragsaktivität und der aktuelle Auftragsstatus aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="605c8-105">This table records current job activity and status.</span></span> <span data-ttu-id="605c8-106">Mithilfe des Auftragsaktivitätsmonitors im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent können Sie den aktuellen Status von Aufträgen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="605c8-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="605c8-107">Falls der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unerwartet beendet wird, ersehen Sie aus der **sysjobactivity** -Tabelle, welche Aufträge ausgeführt wurden, als der Dienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="605c8-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="605c8-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="605c8-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="605c8-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="605c8-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="605c8-110">Security</span><span class="sxs-lookup"><span data-stu-id="605c8-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="605c8-111">**So zeigen Sie die Auftragsaktivität an mit**</span><span class="sxs-lookup"><span data-stu-id="605c8-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="605c8-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="605c8-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="605c8-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="605c8-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="605c8-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="605c8-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="605c8-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="605c8-115">Security</span></span>  
 <span data-ttu-id="605c8-116">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="605c8-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="605c8-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="605c8-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="605c8-118">So zeigen Sie die Auftragsaktivität an</span><span class="sxs-lookup"><span data-stu-id="605c8-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="605c8-119">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="605c8-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="605c8-120">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="605c8-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="605c8-121">Klicken Sie mit der rechten Maustaste auf **Auftrags Aktivitäts Monitor** , und klicken Sie auf **Auftrag anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="605c8-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="605c8-122">Im **Auftragsaktivitätsmonitor**können Sie Details zu jedem Auftrag anzeigen, der für diesen Server definiert ist.</span><span class="sxs-lookup"><span data-stu-id="605c8-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="605c8-123">Klicken Sie mit der rechten Maustaste auf einen Auftrag. Nun können Sie den Auftrag starten, beenden, aktivieren oder deaktivieren, löschen, dessen Status im Auftragsaktivitätsmonitor aktualisieren oder dessen Verlauf oder Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="605c8-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="605c8-124">Um mehrere Aufträge zu starten, beenden, aktivieren, deaktivieren oder aktualisieren, wählen Sie mehrere Zeilen im Auftragsaktivitätsmonitor aus, und klicken Sie mit der rechten Maustaste auf die Auswahl.</span><span class="sxs-lookup"><span data-stu-id="605c8-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="605c8-125">Klicken Sie auf **Aktualisieren**, um den Auftragsaktivitätsmonitor zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="605c8-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="605c8-126">Um weniger Zeilen anzuzeigen, klicken Sie auf **Filter** , und geben Sie Filterparameter ein.</span><span class="sxs-lookup"><span data-stu-id="605c8-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="605c8-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="605c8-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="605c8-128">So zeigen Sie die Auftragsaktivität an</span><span class="sxs-lookup"><span data-stu-id="605c8-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="605c8-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="605c8-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="605c8-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="605c8-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="605c8-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="605c8-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="605c8-132">Weitere Informationen finden Sie unter [sp_help_jobactivity &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="605c8-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
