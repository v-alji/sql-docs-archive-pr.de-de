---
title: Konfigurieren von Serverstartoptionen (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], startup options
- SQL Server, startup options
- single-user mode [SQL Server], starting in
- startup options [SQL Server]
- SQL Server services, setting startup options
ms.assetid: 7a94643c-6460-4baf-bb31-0cb99eaf970d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 405a96208c774a6326a69cf9826a14ca3552eae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697157"
---
# <a name="configure-server-startup-options-sql-server-configuration-manager"></a><span data-ttu-id="203c6-102">Konfigurieren von Serverstartoptionen (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="203c6-102">Configure Server Startup Options (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="203c6-103">In diesem Thema wird beschrieben, wie Sie Startoptionen, die bei jedem Starten von [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verwendet werden, mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Managers konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="203c6-103">This topic describes how to configure startup options that will be used every time the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="203c6-104">Weitere Informationen finden Sie unter [Startoptionen für den Datenbank-Engine-Dienst](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="203c6-104">For a list of startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="203c6-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="203c6-105">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="203c6-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="203c6-106">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="203c6-107">-Konfigurations-Manager schreibt Startparameter in die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="203c6-107">Configuration Manager writes startup parameters to the registry.</span></span> <span data-ttu-id="203c6-108">Diese werden beim nächsten Start von [!INCLUDE[ssDE](../../includes/ssde-md.md)]wirksam.</span><span class="sxs-lookup"><span data-stu-id="203c6-108">They take effect upon the next startup of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="203c6-109">Bei einem Cluster müssen Änderungen auf dem aktiven Server vorgenommen werden, während [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] online ist und werden beim nächsten Start von [!INCLUDE[ssDE](../../includes/ssde-md.md)] wirksam.</span><span class="sxs-lookup"><span data-stu-id="203c6-109">On a cluster, changes must be made on the active server when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is online, and will take effect when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is restarted.</span></span> <span data-ttu-id="203c6-110">Die Registrierungsaktualisierung der Startoptionen auf dem anderen Knoten findet beim nächsten Failover statt.</span><span class="sxs-lookup"><span data-stu-id="203c6-110">The registry update of the startup options on the other node will occur upon the next failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="203c6-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="203c6-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="203c6-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="203c6-112">Permissions</span></span>  
 <span data-ttu-id="203c6-113">Die Konfiguration von Serverstartoptionen ist auf Benutzer beschränkt, die die entsprechenden Einträge in der Registrierung ändern können.</span><span class="sxs-lookup"><span data-stu-id="203c6-113">Configuring server startup options is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="203c6-114">Dazu gehören folgende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="203c6-114">This includes the following users.</span></span>  
  
-   <span data-ttu-id="203c6-115">Mitglieder der lokalen Administratorgruppe.</span><span class="sxs-lookup"><span data-stu-id="203c6-115">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="203c6-116">Das Domänenkonto, das von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] für die Ausführung unter einem Domänenkonto konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="203c6-116">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="203c6-117">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="203c6-117">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-startup-options"></a><span data-ttu-id="203c6-118">So konfigurieren Sie Startoptionen</span><span class="sxs-lookup"><span data-stu-id="203c6-118">To configure startup options</span></span>  
  
1.  <span data-ttu-id="203c6-119">Klicken Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="203c6-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click **SQL Server Services**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="203c6-120">Da der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager ein Snap-In für das [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Verwaltungskonsolenprogramm und kein eigenständiges Programm ist, wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager in neueren Versionen von Windows nicht als Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="203c6-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="203c6-121">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="203c6-121">**Windows 10**:</span></span>  
    >          <span data-ttu-id="203c6-122">Um Configuration Manager zu öffnen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , geben Sie auf der **Start Seite**SQLServerManager12. msc (für [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ) ein.</span><span class="sxs-lookup"><span data-stu-id="203c6-122">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="203c6-123">Ersetzen Sie für frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 12 durch eine kleinere Zahl.</span><span class="sxs-lookup"><span data-stu-id="203c6-123">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="203c6-124">Durch Klicken auf SQLServerManager12.msc wird der Konfigurations-Manager geöffnet.</span><span class="sxs-lookup"><span data-stu-id="203c6-124">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="203c6-125">Um die Configuration Manager an die Start Seite oder Task Leiste anzuheften, klicken Sie mit der rechten Maustaste auf SQLServerManager12. msc, und klicken Sie dann auf **Datei Speicherort öffnen**.</span><span class="sxs-lookup"><span data-stu-id="203c6-125">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="203c6-126">Klicken Sie im Windows-Datei-Explorer mit der rechten Maustaste auf SQLServerManager12. msc, und klicken Sie dann auf am **Anfang anheften** oder **an Taskleiste**anheften</span><span class="sxs-lookup"><span data-stu-id="203c6-126">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="203c6-127">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="203c6-127">**Windows 8**:</span></span>  
    >          <span data-ttu-id="203c6-128">Um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager im Charm **Suchen** unter **apps**zu öffnen, geben Sie **SQLServerManager \<version> . msc** ein, z `SQLServerManager12.msc` . b., und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="203c6-128">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="203c6-129">Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server (***<instance_name>***)**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="203c6-129">In the right pane, right-click **SQL Server (***<instance_name>***)**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="203c6-130">Geben Sie auf der Registerkarte **Startparameter** im Feld **Startparameter angeben** den Parameter ein, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="203c6-130">On the **Startup Parameters** tab, in the **Specify a startup parameter** box, type the parameter, and then click **Add**.</span></span>  
  
     <span data-ttu-id="203c6-131">Wenn Sie z. b. im Einzelbenutzermodus starten möchten, geben `-m` Sie im Feld **Startparameter angeben ein** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="203c6-131">For example, to start in single-user mode, type `-m` in the **Specify a startup parameter** box and then click **Add**.</span></span> <span data-ttu-id="203c6-132">(Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im Einzelbenutzermodus erneut starten, müssen Sie zunächst den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent beenden.</span><span class="sxs-lookup"><span data-stu-id="203c6-132">(When you restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="203c6-133">Andernfalls stellt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent möglicherweise zuerst eine Verbindung her und verhindert, dass Sie als zweiter Benutzer eine Verbindung herstellen können.)</span><span class="sxs-lookup"><span data-stu-id="203c6-133">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent might connect first and prevent you from connecting as a second user.)</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="203c6-134">Starten Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="203c6-134">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="203c6-135">Nachdem Sie die Verwendung des Einzelbenutzermodus abgeschlossen haben, wählen Sie im Feld Startparameter im Feld `-m` **vorhandene Parameter** den Parameter aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="203c6-135">After you are finished using single-user mode, in the Startup Parameters box, select the `-m` parameter in the **Existing Parameters** box, and then click **Remove**.</span></span> <span data-ttu-id="203c6-136">Starten Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] erneut, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im typischen Multibenutzermodus wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="203c6-136">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the typical multi-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203c6-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="203c6-137">See Also</span></span>  
 <span data-ttu-id="203c6-138">[Starten von SQL Server im Einzelbenutzermodus](start-sql-server-in-single-user-mode.md) </span><span class="sxs-lookup"><span data-stu-id="203c6-138">[Start SQL Server in Single-User Mode](start-sql-server-in-single-user-mode.md) </span></span>  
 <span data-ttu-id="203c6-139">[Herstellen einer Verbindung mit SQL Server, wenn Systemadministratoren gesperrt sind](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span><span class="sxs-lookup"><span data-stu-id="203c6-139">[Connect to SQL Server When System Administrators Are Locked Out](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span></span>  
 [<span data-ttu-id="203c6-140">Starten, Beenden oder Anhalten des SQL Server-Agent-Diensts</span><span class="sxs-lookup"><span data-stu-id="203c6-140">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
