---
title: Starten, anhalten, anhalten, fortsetzen, Neustarten des Datenbank-Engine, SQL Server-Agent oder SQL Server-Browser Dienstanbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723026"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="240f7-102">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="240f7-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="240f7-103">In diesem Thema wird beschrieben- und wie [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]- und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent oder der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdienst mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager- und der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]- und **net** commands from a command prompt- und [!INCLUDE[tsql](../../includes/tsql-md.md)]- und or PowerShell.</span><span class="sxs-lookup"><span data-stu-id="240f7-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="240f7-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="240f7-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="240f7-105">Was ist die Funktion dieser Dienste?</span><span class="sxs-lookup"><span data-stu-id="240f7-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="240f7-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="240f7-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="240f7-107">Security</span><span class="sxs-lookup"><span data-stu-id="240f7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="240f7-108">**Anweisungen mit:**</span><span class="sxs-lookup"><span data-stu-id="240f7-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="240f7-109">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="240f7-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="240f7-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="240f7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="240f7-111">Net-Befehle von einem Eingabeaufforderungsfenster</span><span class="sxs-lookup"><span data-stu-id="240f7-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="240f7-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="240f7-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="240f7-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="240f7-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="240f7-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="240f7-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a><span data-ttu-id="240f7-115">Was sind der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Dienst, der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst und der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Dienst?</span><span class="sxs-lookup"><span data-stu-id="240f7-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="240f7-116">-Komponenten sind ausführbare Programme, die als Windows-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="240f7-117">Programme, die als Windows-Dienst ausgeführt werden, lassen sich ohne Anzeige von Aktivitäten auf dem Computerbildschirm weiterhin ausführen.</span><span class="sxs-lookup"><span data-stu-id="240f7-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="240f7-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]Leistungs**</span><span class="sxs-lookup"><span data-stu-id="240f7-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="240f7-119">Der ausführbare Prozess, der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]entspricht.</span><span class="sxs-lookup"><span data-stu-id="240f7-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="240f7-120">[!INCLUDE[ssDE](../../includes/ssde-md.md)] kann der Standardinstanz (eine pro Computer) oder einer von vielen benannten Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)]entsprechen.</span><span class="sxs-lookup"><span data-stu-id="240f7-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="240f7-121">Verwenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager, um zu bestimmen, welche Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="240f7-122">Die Standard Instanz (bei der Installation) wird als \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\* aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="240f7-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="240f7-123">Benannte Instanzen (bei der Installation) werden als \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\* aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="240f7-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="240f7-124">Standardmäßig [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird Express als \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLExpress)\*\* installiert.</span><span class="sxs-lookup"><span data-stu-id="240f7-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="240f7-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Dienst**</span><span class="sxs-lookup"><span data-stu-id="240f7-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="240f7-126">Entspricht einem Windows-Dienst, der geplante administrative Tasks ausführt, die als Aufträge und Warnungen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="240f7-127">Weitere Informationen finden Sie unter [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="240f7-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="240f7-128">-Agent ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240f7-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="240f7-129">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="240f7-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="240f7-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Browser Dienst**</span><span class="sxs-lookup"><span data-stu-id="240f7-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="240f7-131">Ein Windows-Dienst, der auf eingehende Anforderungen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcen lauscht und Clientinformationen zu den auf dem Computer installierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="240f7-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="240f7-132">Eine einzelne Instanz des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdiensts wird für alle auf dem Computer installierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="240f7-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="240f7-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="240f7-133">Additional Information</span></span>  
  
-   <span data-ttu-id="240f7-134">Durch das Anhalten des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Diensts wird verhindert, dass neue Benutzer eine Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)]herstellen. Benutzer, die bereits verbunden sind, können jedoch ihre Arbeit fortsetzen, bis die jeweilige Verbindung unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="240f7-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="240f7-135">Halten Sie den Dienst an, wenn Benutzer zuerst ihre Arbeit abschließen sollen, bevor Sie den Dienst beenden.</span><span class="sxs-lookup"><span data-stu-id="240f7-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="240f7-136">Dadurch können sie Transaktionen abschließen, die gerade verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="240f7-137">Mit der Funktion zum Fortsetzen kann [!INCLUDE[ssDE](../../includes/ssde-md.md)] neue Verbindungen wieder zulassen.</span><span class="sxs-lookup"><span data-stu-id="240f7-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="240f7-138">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst kann nicht angehalten oder fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="240f7-139">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager und [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zeigen den aktuellen Dienststatus an. Dazu werden folgende Symbole verwendet.</span><span class="sxs-lookup"><span data-stu-id="240f7-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="240f7-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="240f7-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="240f7-141">Ein grüner Pfeil im Symbol neben dem Dienstnamen gibt an, dass der Dienst gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="240f7-142">Ein rotes Quadrat im Symbol neben dem Dienstnamen gibt an, dass der Dienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="240f7-143">Zwei vertikale blaue Linien im Symbol neben dem Dienstnamen geben an, dass der Dienst angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="240f7-144">Beim Neustart von [!INCLUDE[ssDE](../../includes/ssde-md.md)]weist ein rotes Quadrat darauf hin, dass der Dienst beendet wurde. Ein grüner Pfeil gibt daraufhin an, dass der Dienst erfolgreich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="240f7-145">Ein weißer Pfeil in einem grünen Kreis neben dem Dienstnamen gibt an, dass der Dienst gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="240f7-146">Ein weißes Quadrat in einem roten Kreis neben dem Dienstnamen gibt an, dass der Dienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="240f7-147">Zwei vertikale weiße Linien in einem blauen Kreis neben dem Dienstnamen geben an, dass der Dienst angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="240f7-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="240f7-148">Bei Verwendung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers oder bei Verwendung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]sind nur mögliche Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="240f7-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="240f7-149">Wurde der Dienst beispielsweise bereits gestartet, ist die Option **Start** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="240f7-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="240f7-150">Im Fall der Ausführung auf einem Cluster lässt sich der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Dienst am besten mittels Clusterverwaltung verwalten.</span><span class="sxs-lookup"><span data-stu-id="240f7-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="240f7-151">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="240f7-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="240f7-152">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="240f7-152">Permissions</span></span>  
 <span data-ttu-id="240f7-153">Standardmäßig können nur Mitglieder der lokalen Administratorgruppe einen Dienst starten, beenden, anhalten, fortsetzen oder neu starten.</span><span class="sxs-lookup"><span data-stu-id="240f7-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="240f7-154">Informationen dazu, wie Sie es Nichtadministratoren ermöglichen, Dienste zu verwalten, finden Sie unter [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349)(So erteilen Sie Benutzern die Berechtigung zum Verwalten von Diensten in Windows Server 2003).</span><span class="sxs-lookup"><span data-stu-id="240f7-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="240f7-155">(Dieser Vorgang ist bei anderen Versionen von Windows ähnlich.)</span><span class="sxs-lookup"><span data-stu-id="240f7-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="240f7-156">Das Beenden [!INCLUDE[ssDE](../../includes/ssde-md.md)] von mit dem [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` Befehl erfordert die Mitgliedschaft in den festen Server Rollen **sysadmin** oder **serveradmin** und ist nicht übertragbar.</span><span class="sxs-lookup"><span data-stu-id="240f7-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a><span data-ttu-id="240f7-157">Verwenden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="240f7-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="240f7-158">So wird eine [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="240f7-159">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="240f7-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="240f7-160">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="240f7-161">Klicken Sie im linken Bereich des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="240f7-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="240f7-162">Klicken Sie im Ergebnisbereich mit der rechten Maustaste auf **SQL Server (MSSQLServer)** oder auf eine benannte Instanz, und klicken Sie anschließend auf **Starten**, **Beenden**, **Anhalten**, **Fortsetzen**oder **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="240f7-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="240f7-163">Klicken Sie auf **OK** , um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager zu schließen.</span><span class="sxs-lookup"><span data-stu-id="240f7-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="240f7-164">Weitere Informationen zum Starten einer [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz mit Startoptionen finden Sie unter [Konfigurieren von Serverstartoptionen &#40;SQL Server-Konfigurations-Manager&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="240f7-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="240f7-165">So wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browser oder eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Instanz gestartet, beendet, angehalten, fortgesetzt oder neu gestartet</span><span class="sxs-lookup"><span data-stu-id="240f7-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="240f7-166">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="240f7-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="240f7-167">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="240f7-168">Klicken Sie im linken Bereich des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="240f7-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="240f7-169">Klicken Sie im Ergebnisbereich mit der rechten Maustaste auf \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**oder \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLSERVER)** oder \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)\*\* für eine benannte Instanz, und klicken Sie dann auf **starten**, anhalten **Resume**, **Anhalten** **, fort**setzen oder **neu starten**.</span><span class="sxs-lookup"><span data-stu-id="240f7-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="240f7-170">Klicken Sie auf **OK** , um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager zu schließen.</span><span class="sxs-lookup"><span data-stu-id="240f7-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="240f7-171">-Agent kann nicht angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-171">Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a><span data-ttu-id="240f7-172">Verwenden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="240f7-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="240f7-173">So wird eine [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="240f7-174">Stellen Sie im Objekt-Explorer eine Verbindung mit der [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her, klicken Sie mit der rechten Maustaste auf die zu startende [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz und anschließend auf **Starten**, **Beenden**, **Anhalten**, **Fortsetzen**oder **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="240f7-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="240f7-175">Klicken Sie alternativ im Bereich „Registrierte Server“ mit der rechten Maustaste auf die zu startende [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz, zeigen Sie auf die Option **Dienstkontrolle**, und klicken Sie anschließend auf **Starten**, **Beenden**, **Anhalten**, **Fortsetzen**oder **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="240f7-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="240f7-176">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="240f7-177">Klicken Sie bei der Frage, ob die Aktion ausgeführt werden soll, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="240f7-178">So wird eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Instanz gestartet, beendet oder neu gestartet</span><span class="sxs-lookup"><span data-stu-id="240f7-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="240f7-179">Stellen Sie in Objekt-Explorer eine Verbindung mit der Instanz von her [!INCLUDE[ssDE](../../includes/ssde-md.md)] , klicken Sie mit der rechten Maustaste auf \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent\*\*, und klicken Sie dann auf **starten, starten**oder **neu starten**. **Stop**</span><span class="sxs-lookup"><span data-stu-id="240f7-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="240f7-180">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="240f7-181">Klicken Sie bei der Frage, ob die Aktion ausgeführt werden soll, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="240f7-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a> <span data-ttu-id="240f7-182">Über das Eingabeaufforderungsfenster mit Net-Befehlen</span><span class="sxs-lookup"><span data-stu-id="240f7-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="240f7-183">Die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste können mithilfe von **net**-Befehlen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows gestartet, beendet oder pausiert werden.</span><span class="sxs-lookup"><span data-stu-id="240f7-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a> <span data-ttu-id="240f7-184">So starten Sie die Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="240f7-185">Geben Sie an einer Eingabeaufforderung einen der folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="240f7-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="240f7-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="240f7-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="240f7-187">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-187">-or-</span></span>  
  
     <span data-ttu-id="240f7-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="240f7-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="240f7-189">So starten Sie eine benannte Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="240f7-190">Geben Sie an einer Eingabeaufforderung einen der folgenden Befehle ein.</span><span class="sxs-lookup"><span data-stu-id="240f7-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="240f7-191">Ersetzen Sie *\<instancename>* durch den Namen der Instanz, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="240f7-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="240f7-192">**net start "SQL Server (** *Instanzname* **)"**</span><span class="sxs-lookup"><span data-stu-id="240f7-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="240f7-193">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-193">-or-</span></span>  
  
     <span data-ttu-id="240f7-194">**net start MSSQL$** *Instanzname*</span><span class="sxs-lookup"><span data-stu-id="240f7-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a><span data-ttu-id="240f7-195">So starten Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] mit Startoptionen</span><span class="sxs-lookup"><span data-stu-id="240f7-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="240f7-196">Fügen Sie Startoptionen am Ende der Anweisung **net start "SQL Server (MSSQLSERVER)"** hinzu (durch ein Leerzeichen getrennt).</span><span class="sxs-lookup"><span data-stu-id="240f7-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="240f7-197">Beim Starten mithilfe von **net start**wird ein Schrägstrich (/) anstelle eines Bindestriches (-) für die Startoptionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="240f7-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="240f7-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="240f7-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="240f7-199">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-199">-or-</span></span>  
  
     <span data-ttu-id="240f7-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="240f7-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="240f7-201">Weitere Informationen finden Sie unter [Startoptionen für den Datenbank-Engine-Dienst](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="240f7-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a><span data-ttu-id="240f7-202">So starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent auf der Standard Instanz von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="240f7-203">Geben Sie an einer Eingabeaufforderung einen der folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="240f7-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="240f7-204">**net start "SQL Server-Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="240f7-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="240f7-205">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-205">-or-</span></span>  
  
     <span data-ttu-id="240f7-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="240f7-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a> <span data-ttu-id="240f7-207">So starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent auf einer benannten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="240f7-208">Geben Sie an einer Eingabeaufforderung einen der folgenden Befehle ein.</span><span class="sxs-lookup"><span data-stu-id="240f7-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="240f7-209">Ersetzen Sie *Instanzname* durch den Namen der Instanz, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="240f7-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="240f7-210">**net start "SQL Server Agent(** *Instanzname* **)"**</span><span class="sxs-lookup"><span data-stu-id="240f7-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="240f7-211">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-211">-or-</span></span>  
  
     <span data-ttu-id="240f7-212">**net start SQLAgent$** *Instanzname*</span><span class="sxs-lookup"><span data-stu-id="240f7-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="240f7-213">Informationen zum Ausführen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents im ausführlichen Modus zur Problembehandlung finden Sie unter [sqlagent90 (Anwendung)](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="240f7-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="240f7-214">So starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser</span><span class="sxs-lookup"><span data-stu-id="240f7-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="240f7-215">Geben Sie an einer Eingabeaufforderung einen der folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="240f7-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="240f7-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="240f7-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="240f7-217">Oder</span><span class="sxs-lookup"><span data-stu-id="240f7-217">-or-</span></span>  
  
     <span data-ttu-id="240f7-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="240f7-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="240f7-219">So werden Dienste über das Eingabeaufforderungsfenster angehalten oder beendet</span><span class="sxs-lookup"><span data-stu-id="240f7-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="240f7-220">Ändern Sie zum Anhalten oder Beenden von Diensten die Befehle wie folgt.</span><span class="sxs-lookup"><span data-stu-id="240f7-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="240f7-221">Um einen Dienst anzuhalten, ersetzen Sie **net start** durch **net pause**.</span><span class="sxs-lookup"><span data-stu-id="240f7-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="240f7-222">Um einen Dienst zu beenden, ersetzen Sie **net start** durch **net stop**.</span><span class="sxs-lookup"><span data-stu-id="240f7-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="240f7-223">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="240f7-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="240f7-224">[!INCLUDE[ssDE](../../includes/ssde-md.md)] lässt sich mit der `SHUTDOWN`-Anweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="240f7-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="240f7-225">So beenden Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] mit [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240f7-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="240f7-226">Um nach der vollständigen Ausführung von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen und gespeicherten Prozeduren [!INCLUDE[ssDE](../../includes/ssde-md.md)]zu beenden, führen Sie die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="240f7-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="240f7-227">Um [!INCLUDE[ssDE](../../includes/ssde-md.md)] sofort zu beenden, führen Sie die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="240f7-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="240f7-228">Weitere Informationen zur- `SHUTDOWN` Anweisung finden Sie unter [Shutdown &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="240f7-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="240f7-229">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="240f7-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="240f7-230">So starten und beenden Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Dienste</span><span class="sxs-lookup"><span data-stu-id="240f7-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="240f7-231">Starten Sie in einem Eingabeaufforderungsfenster [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell durch das Ausführen des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="240f7-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="240f7-232">Führen Sie an einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell-Eingabeaufforderung den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="240f7-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="240f7-233">Ersetzen Sie `computername` durch den Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="240f7-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="240f7-234">Identifizieren Sie den Dienst, den Sie beenden oder starten möchten.</span><span class="sxs-lookup"><span data-stu-id="240f7-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="240f7-235">Wählen Sie eine der folgenden Zeilen aus.</span><span class="sxs-lookup"><span data-stu-id="240f7-235">Pick one of the following lines.</span></span> <span data-ttu-id="240f7-236">Ersetzen Sie `instancename` durch den Namen der benannten Instanz.</span><span class="sxs-lookup"><span data-stu-id="240f7-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="240f7-237">Abrufen eines Verweises auf die Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240f7-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="240f7-238">Abrufen eines Verweises auf die benannte Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240f7-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="240f7-239">Abrufen eines Verweises auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst auf der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240f7-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="240f7-240">Abrufen eines Verweises auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst auf einer benannten Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240f7-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="240f7-241">Abrufen eines Verweises auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdienst.</span><span class="sxs-lookup"><span data-stu-id="240f7-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="240f7-242">Starten Sie anhand des Beispiels den ausgewählten Dienst, und beenden Sie ihn anschließend.</span><span class="sxs-lookup"><span data-stu-id="240f7-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="240f7-243">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="240f7-243">See Also</span></span>  
 <span data-ttu-id="240f7-244">[SQL Server mit minimaler Konfiguration starten](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="240f7-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="240f7-245">Von den Editionen von SQL Server 2014 unterstützte Features</span><span class="sxs-lookup"><span data-stu-id="240f7-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
