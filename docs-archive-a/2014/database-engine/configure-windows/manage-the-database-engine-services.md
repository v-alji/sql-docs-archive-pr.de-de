---
title: Verwalten des Datenbank-Engine-Dienstes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, accessing
- Database Engine [SQL Server], services
- managing services [SQL Server], about service management
- services [SQL Server]
- SQL Server Agent service, managing
- SQL Server services, about SQL Server service
- MSSQLServer
- server configuration [SQL Server]
- managing services [SQL Server]
- SQL Server Agent service
- services [SQL Server], managing
- administering SQL Server, services
- SQL Server services
ms.assetid: aa732e43-53ba-4eea-bb9b-089da0766fc1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c18338493777d14c5e6fe28cb38bd71aaffd5da3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696057"
---
# <a name="manage-the-database-engine-services"></a><span data-ttu-id="ddf92-102">Verwalten der Datenbank-Engine-Dienste</span><span class="sxs-lookup"><span data-stu-id="ddf92-102">Manage the Database Engine Services</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ddf92-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird unter den Betriebssystemen als Dienst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ddf92-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on the operating systems as a service.</span></span> <span data-ttu-id="ddf92-104">Ein Dienst ist ein Anwendungstyp, der im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ddf92-104">A service is a type of application that runs in the system background.</span></span> <span data-ttu-id="ddf92-105">Dienste stellen gewöhnlich wichtige Betriebssystemfunktionen bereit, wie z. B. Webbereitstellung, Ereignisprotokollierung oder Dateibereitstellung.</span><span class="sxs-lookup"><span data-stu-id="ddf92-105">Services usually provide core operating system features, such as Web serving, event logging, or file serving.</span></span> <span data-ttu-id="ddf92-106">Dienste können ausgeführt werden, ohne dass auf dem Computerdesktop eine Benutzeroberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ddf92-106">Services can run without showing a user interface on the computer desktop.</span></span> <span data-ttu-id="ddf92-107">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent und mehrere andere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Komponenten werden als Dienste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ddf92-107">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and several other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components run as services.</span></span> <span data-ttu-id="ddf92-108">Diese Dienste werden in der Regel zusammen mit dem Betriebssystem gestartet.</span><span class="sxs-lookup"><span data-stu-id="ddf92-108">These services typically are started when the operating system starts.</span></span> <span data-ttu-id="ddf92-109">Dies hängt von der Konfiguration während der Installation ab. Manche Dienste werden standardmäßig nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="ddf92-109">This depends on what is specified during setup; some services are not started by default.</span></span> <span data-ttu-id="ddf92-110">In diesem Abschnitt wird die Verwaltung verschiedener [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddf92-110">This section describes the management of the various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span> <span data-ttu-id="ddf92-111">Vor dem Anmelden an einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sollten Sie wissen, wie eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gestartet, beendet, angehalten, fortgesetzt und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ddf92-111">Before you log in to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you need to know how to start, stop, pause, resume, and restart an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ddf92-112">Nach dem Anmelden können Sie verschiedene Aufgaben ausführen, wie z. B. das Verwalten des Servers oder das Abfragen einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ddf92-112">After you are logged in, you can perform tasks such as administering the server or querying a database.</span></span>  
  
## <a name="using-the-sql-server-service"></a><span data-ttu-id="ddf92-113">Verwenden des SQL Server-Diensts</span><span class="sxs-lookup"><span data-stu-id="ddf92-113">Using the SQL Server Service</span></span>  
 <span data-ttu-id="ddf92-114">Beim Starten einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="ddf92-114">When you start an instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you are starting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="ddf92-115">Nach dem Starten des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensts können Benutzer neue Verbindungen mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="ddf92-115">After you start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, users can establish new connections to the server.</span></span> <span data-ttu-id="ddf92-116">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst kann als Dienst lokal oder remote gestartet und beendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddf92-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service can be started and stopped as a service, either locally or remotely.</span></span> <span data-ttu-id="ddf92-117">Der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Dienst wird als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) bezeichnet, wenn es sich um die Standard Instanz handelt, oder als MSSQL $, *\<instancename>* Wenn es sich um eine benannte Instanz handelt.</span><span class="sxs-lookup"><span data-stu-id="ddf92-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is referred to as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) if it is the default instance, or MSSQL$*\<instancename>* if it is a named instance.</span></span>  
  
## <a name="using-sql-server-configuration-manager"></a><span data-ttu-id="ddf92-118">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="ddf92-118">Using SQL Server Configuration Manager</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ddf92-119">-Konfigurations-Manager können Sie verschiedene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddf92-119">Configuration Manager allows you to stop, start, or pause various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ddf92-120">Configuration Manager kann keine [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]-Dienste verwalten.</span><span class="sxs-lookup"><span data-stu-id="ddf92-120">Configuration Manager cannot manage [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] services.</span></span>  
  
 <span data-ttu-id="ddf92-121">Mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager können auch die Eigenschaften des ausgewählten Diensts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ddf92-121">You can also use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to view the properties of the selected service.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ddf92-122">-Konfigurations-Manager ist ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] -MMC-Snap-In (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="ddf92-122">Configuration Manager is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) snap-in.</span></span> <span data-ttu-id="ddf92-123">Weitere Informationen über MMC und die Funktionsweise von Snap-Ins finden Sie in der Windows-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="ddf92-123">For more information about MMC and how a snap-in works, see Windows Help.</span></span>  
  
 <span data-ttu-id="ddf92-124">**So greifen Sie auf den SQL Server-Konfigurations-Manager zu**</span><span class="sxs-lookup"><span data-stu-id="ddf92-124">**To access SQL Server Configuration Manager**</span></span>  
  
-   <span data-ttu-id="ddf92-125">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="ddf92-125">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
 <span data-ttu-id="ddf92-126">**So greifen Sie über Windows 8 auf den SQL Server-Konfigurations-Manager zu**</span><span class="sxs-lookup"><span data-stu-id="ddf92-126">**To access SQL Server Configuration Manager Using Windows 8**</span></span>  
  
 <span data-ttu-id="ddf92-127">Da der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager ein Snap-In für das [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Verwaltungskonsolenprogramm und kein eigenständiges Programm ist, wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager beim Ausführen von Windows 8.0 nicht als Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddf92-127">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager not does not appear as an application when running Windows 8.0.</span></span> <span data-ttu-id="ddf92-128">Um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager zu öffnen, geben Sie im Charm **Suchen** unter **Apps**Folgendes ein: **SQLServerManager12.msc** (für [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]), **SQLServerManager11.msc** (für [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]) oder **SQLServerManager10.msc** (für[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]) ein. Drücken Sie dann die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="ddf92-128">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager12.msc** (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]), **SQLServerManager11.msc** (for [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or **SQLServerManager10.msc** for ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]), and then press **Enter**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddf92-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ddf92-129">In this Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="ddf92-130">Sicherheitsanforderungen für das Verwalten von Diensten</span><span class="sxs-lookup"><span data-stu-id="ddf92-130">Security Requirements for Managing Services</span></span>](security-requirements-for-managing-services.md)|[<span data-ttu-id="ddf92-131">Verhindern des automatischen Starts einer Instanz von SQL Server &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-131">Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-prevent-automatic-startup-of-an-instance.md)|  
|[<span data-ttu-id="ddf92-132">Konfigurieren von Windows-Dienstkonten und -Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ddf92-132">Configure Windows Service Accounts and Permissions</span></span>](configure-windows-service-accounts-and-permissions.md)|[<span data-ttu-id="ddf92-133">Ändern des Dienststartkontos für SQL Server &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-133">Change the Service Startup Account for SQL Server &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-change-the-service-startup-account.md)|  
|[<span data-ttu-id="ddf92-134">Ausführen von SQL Server mit oder ohne Netzwerk</span><span class="sxs-lookup"><span data-stu-id="ddf92-134">Run SQL Server With or Without a Network</span></span>](run-sql-server-with-or-without-a-network.md)|[<span data-ttu-id="ddf92-135">Konfigurieren von Serverstartoptionen &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-135">Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-configure-server-startup-options.md)|  
|[<span data-ttu-id="ddf92-136">SQL Server-Browserdienst &#40;Datenbank-Engine und SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-136">SQL Server Browser Service &#40;Database Engine and SSAS&#41;</span></span>](sql-server-browser-service-database-engine-and-ssas.md)|[<span data-ttu-id="ddf92-137">Ändern des Kennworts der von SQL Server verwendeten Konten &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-137">Change the Password of the Accounts Used by SQL Server &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-change-the-password-of-the-accounts-used.md)|  
|[<span data-ttu-id="ddf92-138">Startoptionen für den Datenbank-Engine-Dienst</span><span class="sxs-lookup"><span data-stu-id="ddf92-138">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)|[<span data-ttu-id="ddf92-139">Konfigurieren von SQL Server-Fehlerprotokollen</span><span class="sxs-lookup"><span data-stu-id="ddf92-139">Configure SQL Server Error Logs</span></span>](scm-services-configure-sql-server-error-logs.md)|  
|[<span data-ttu-id="ddf92-140">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="ddf92-140">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)|[<span data-ttu-id="ddf92-141">Ändern des Serverauthentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="ddf92-141">Change Server Authentication Mode</span></span>](change-server-authentication-mode.md)|  
|[<span data-ttu-id="ddf92-142">Starten von SQL Server im Einzelbenutzermodus</span><span class="sxs-lookup"><span data-stu-id="ddf92-142">Start SQL Server in Single-User Mode</span></span>](start-sql-server-in-single-user-mode.md)|[<span data-ttu-id="ddf92-143">SQL Writer-Dienst</span><span class="sxs-lookup"><span data-stu-id="ddf92-143">SQL Writer Service</span></span>](sql-writer-service.md)|  
|[<span data-ttu-id="ddf92-144">Starten Sie von SQL Server mit Minimalkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ddf92-144">Start SQL Server with Minimal Configuration</span></span>](start-sql-server-with-minimal-configuration.md)|[<span data-ttu-id="ddf92-145">Senden einer Nachricht über das Herunterfahren &#40;Eingabeaufforderung&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-145">Broadcast a Shutdown Message &#40;Command Prompt&#41;</span></span>](broadcast-a-shutdown-message-command-prompt.md)|  
|[<span data-ttu-id="ddf92-146">Herstellen einer Verbindung mit einem anderen Computer &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-146">Connect to Another Computer &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-connect-to-another-computer.md)|[<span data-ttu-id="ddf92-147">Anmelden an einer Instanz von SQL Server &#40;Befehlszeile&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-147">Log In to an Instance of SQL Server &#40;Command Prompt&#41;</span></span>](log-in-to-an-instance-of-sql-server-command-prompt.md)|  
|[<span data-ttu-id="ddf92-148">Festlegen des automatischen Starts einer Instanz von SQL Server &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf92-148">Set an Instance of SQL Server to Start Automatically &#40;SQL Server Configuration Manager&#41;</span></span>](scm-services-set-an-instance-to-start-automatically.md)|[<span data-ttu-id="ddf92-149">Konfigurieren von Dateisystemberechtigungen für den Datenbank-Engine-Zugriff</span><span class="sxs-lookup"><span data-stu-id="ddf92-149">Configure File System Permissions for Database Engine Access</span></span>](configure-file-system-permissions-for-database-engine-access.md)|  
  
## <a name="related-content"></a><span data-ttu-id="ddf92-150">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ddf92-150">Related Content</span></span>  
 [<span data-ttu-id="ddf92-151">Konfigurieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="ddf92-151">Configure SQL Server Agent</span></span>](../../ssms/agent/sql-server-agent.md)  
  
 [<span data-ttu-id="ddf92-152">Anmelden an SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddf92-152">Logging In to SQL Server</span></span>](logging-in-to-sql-server.md)  
  
  