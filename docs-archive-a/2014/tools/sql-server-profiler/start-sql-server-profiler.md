---
title: SQL Server Profiler starten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719153"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="11d5f-102">Starten von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="11d5f-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="11d5f-103">Sie können [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in einer Reihe von Szenarien auf verschiedene Arten starten, um das Erfassen der Ablaufverfolgungsausgabe zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="11d5f-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="11d5f-104">Sie können [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf unterschiedliche Weise starten: über das Menü **Start** , über das Menü **Extras** im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Optimierungsratgeber und über verschiedene Positionen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d5f-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="11d5f-105">Wenn Sie [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zum ersten Mal starten und im Menü **Datei** die Option **Neue Ablaufverfolgung** auswählen, zeigt die Anwendung das Dialogfeld **Verbindung mit Server herstellen** an, in dem Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angeben können, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="11d5f-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="11d5f-106">So starten Sie SQL Server Profiler aus dem Startmenü</span><span class="sxs-lookup"><span data-stu-id="11d5f-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="11d5f-107">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Leistungstools**, und klicken Sie dann auf **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="11d5f-108">So starten Sie SQL Server Profiler im Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="11d5f-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="11d5f-109">Klicken Sie im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Optimierungsratgeber im Menü **Extras** auf **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="11d5f-110">So starten Sie SQL Server Profiler in Management Studio</span><span class="sxs-lookup"><span data-stu-id="11d5f-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="11d5f-111">startet jede Profilersitzung in einer eigenen Instanz und wird weiterhin ausgeführt, wenn Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="11d5f-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="11d5f-112">Sie können [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] von mehreren Positionen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aus starten, wie in den folgenden Prozeduren erläutert.</span><span class="sxs-lookup"><span data-stu-id="11d5f-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="11d5f-113">Wenn [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] gestartet wird, lädt es den Verbindungskontext, die Ablaufverfolgungsvorlage und den Filterkontext seines Startpunkts.</span><span class="sxs-lookup"><span data-stu-id="11d5f-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="11d5f-114">So starten Sie SQL Server Profiler über das Menü "Extras"</span><span class="sxs-lookup"><span data-stu-id="11d5f-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="11d5f-115">Klicken Sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Menü **Extras** auf **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="11d5f-116">So starten Sie SQL Server Profiler über den Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="11d5f-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="11d5f-117">Klicken Sie in der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Menüleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="11d5f-118">Klicken Sie im Abfrage-Editor mit der rechten Maustaste, und wählen Sie dann **Ablaufverfolgungsabfrage in SQL Server Profiler**aus.</span><span class="sxs-lookup"><span data-stu-id="11d5f-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11d5f-119">Der Verbindungskontext ist die Editor-Verbindung, die Ablaufverfolgungsvorlage lautet TSQL_SPs, und der angewendete Filter ist SPID = Abfragefenster-SPID.</span><span class="sxs-lookup"><span data-stu-id="11d5f-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="11d5f-120">So starten Sie SQL Server Profiler über den Aktivitätsmonitor</span><span class="sxs-lookup"><span data-stu-id="11d5f-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="11d5f-121">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], und klicken Sie dann auf **Aktivitätsmonitor**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="11d5f-122">Klicken Sie auf den Bereich **Prozesse** , klicken Sie mit der rechten Maustaste auf den Prozess, für den Sie ein Profil erstellen möchten, und klicken Sie dann auf **Ablaufverfolgungsprozess in SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="11d5f-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11d5f-123">Wenn ein Prozess ausgewählt ist, ist der Verbindungskontext die Verbindung für den Objekt-Explorer, und zwar so, wie sie war, als der Aktivitätsmonitor geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="11d5f-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="11d5f-124">Die Ablaufverfolgungsvorlage ist der auf dem Servertyp basierende Standard, und die SPID entspricht der SPID für den ausgewählten Prozess.</span><span class="sxs-lookup"><span data-stu-id="11d5f-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="11d5f-125">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="11d5f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="11d5f-126">Im Windows-Authentifizierungsmodus muss das Benutzerkonto, das zum Ausführen von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] verwendet wird, die Berechtigung haben, eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="11d5f-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="11d5f-127">Zum Ausführen der Ablaufverfolgung mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]müssen die Benutzer außerdem die ALTER TRACE-Berechtigung haben.</span><span class="sxs-lookup"><span data-stu-id="11d5f-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d5f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11d5f-128">See Also</span></span>  
 <span data-ttu-id="11d5f-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="11d5f-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="11d5f-130">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11d5f-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
