---
title: 'Beispiel: Erstellen einer SQL Server-Agent Warnung mithilfe des WMI-Anbieters für Server Ereignisse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717560"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="6b696-102">Beispiel: Erstellen einer SQL Server-Agent-Warnung mit dem WMI-Anbieter für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="6b696-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="6b696-103">Eine gebräuchliche Möglichkeit zum Verwenden des WMI-Ereignisanbieters ist die Erstellung von SQL Server-Agent-Warnungen, die auf bestimmte Ereignisse antworten.</span><span class="sxs-lookup"><span data-stu-id="6b696-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="6b696-104">Das folgende Beispiel stellt eine einfache Warnung dar, die XML-Deadlockdiagrammereignisse in einer Tabelle zur späteren Analyse speichert.</span><span class="sxs-lookup"><span data-stu-id="6b696-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="6b696-105">SQL Server-Agent übermittelt eine WQL-Anforderung, empfängt WMI-Ereignisse und führt als Antwort auf das Ereignis einen Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="6b696-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="6b696-106">Beachten Sie, dass der WMI-Ereignisanbieter die Details bei der Erstellung und Verwaltung von Service Broker-Objekten behandelt, obwohl mehrere dieser Objekte an der Verarbeitung der Benachrichtigungsmeldung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="6b696-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b696-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b696-107">Example</span></span>  
 <span data-ttu-id="6b696-108">Zuerst wird in der `AdventureWorks`-Datenbank eine Tabelle erstellt, in der das Deadlockdiagrammereignis gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b696-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="6b696-109">Die Tabelle enthält zwei Spalten: Die `AlertTime`-Spalte enthält die Uhrzeit, zu der die Warnung ausgeführt wird, und die `DeadlockGraph`-Spalte enthält das XML-Dokument mit dem Deadlockdiagramm.</span><span class="sxs-lookup"><span data-stu-id="6b696-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="6b696-110">Anschließend wird die Warnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b696-110">Then, the alert is created.</span></span> <span data-ttu-id="6b696-111">Das Skript erstellt zunächst den Auftrag zur Ausführung der Warnung, fügt dem Auftrag einen Auftragsschritt hinzu und weist den Auftrag der aktuellen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu.</span><span class="sxs-lookup"><span data-stu-id="6b696-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6b696-112">Das Skript erstellt dann die Warnung.</span><span class="sxs-lookup"><span data-stu-id="6b696-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="6b696-113">Der Auftrags Schritt ruft die **TextData** -Eigenschaft der WMI-Ereignis Instanz ab und fügt diesen Wert in die **DeadlockGraph** -Spalte der **DeadlockEvents** -Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="6b696-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="6b696-114">Beachten Sie, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diese Zeichenfolge implizit in das XML-Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6b696-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="6b696-115">Da der Auftragsschritt das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Subsystem verwendet, gibt der Auftragsschritt keinen Proxy an.</span><span class="sxs-lookup"><span data-stu-id="6b696-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="6b696-116">Die Warnung führt den Auftrag immer dann aus, wenn ein Deadlockdiagrammablaufverfolgungsereignis protokolliert werden würde.</span><span class="sxs-lookup"><span data-stu-id="6b696-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="6b696-117">Für eine WMI-Warnung erstellt SQL Server-Agent mittels angegebenem Namespace und WQL-Anweisung eine Abfragebenachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="6b696-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="6b696-118">Für diese Warnung überwacht SQL Server-Agent die Standardinstanz auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="6b696-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="6b696-119">Die WQL-Anweisung fordert ein beliebiges `DEADLOCK_GRAPH`-Ereignis in der Standardinstanz an.</span><span class="sxs-lookup"><span data-stu-id="6b696-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="6b696-120">Zum Ändern der Instanz, das von der Warnung überwacht wird, ersetzen Sie den Instanznamen durch `MSSQLSERVER` im `@wmi_namespace` für die Warnung.</span><span class="sxs-lookup"><span data-stu-id="6b696-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b696-121">Damit SQL Server-Agent WMI-Ereignisse empfangen kann, [!INCLUDE[ssSB](../../includes/sssb-md.md)] muss in **msdb** und aktiviert werden [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b696-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="6b696-122">Testen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="6b696-122">Testing the Sample</span></span>  
 <span data-ttu-id="6b696-123">Um zu sehen, dass der Auftrag ausgeführt wird, provozieren Sie einen Deadlock.</span><span class="sxs-lookup"><span data-stu-id="6b696-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="6b696-124">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Öffnen Sie in zwei **SQL-Abfrage** Registerkarten, und verbinden Sie beide Abfragen mit derselben Instanz.</span><span class="sxs-lookup"><span data-stu-id="6b696-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="6b696-125">Führen Sie auf einer der Abfrageregisterkarten das folgende Skript aus.</span><span class="sxs-lookup"><span data-stu-id="6b696-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="6b696-126">Dieses Skript erzeugt ein Resultset und endet.</span><span class="sxs-lookup"><span data-stu-id="6b696-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="6b696-127">Führen Sie das folgende Skript auf der zweiten Abfrage Registerkarte aus. Dieses Skript erzeugt ein Resultset und dann einen Block, der darauf wartet, eine Sperre zu erhalten `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="6b696-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="6b696-128">Führen Sie das folgende Skript auf der ersten Abfrage Registerkarte aus. Dieses Skript wird blockiert und wartet darauf, eine Sperre für zu erhalten `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="6b696-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="6b696-129">Nach einem kurzen Timeout wählt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dieses Skript oder das Skript aus dem Beispiel als Deadlockopfer aus und beendet die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6b696-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="6b696-130">Warten Sie nach dem Provozieren des Deadlocks einen Moment, damit SQL Server-Agent die Warnung aktivieren und den Auftrag ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="6b696-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="6b696-131">Untersuchen Sie den Inhalt der Tabelle `DeadlockEvents`, indem Sie das folgende Skript ausführen:</span><span class="sxs-lookup"><span data-stu-id="6b696-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="6b696-132">Die `DeadlockGraph`-Spalte sollte ein XML-Dokument enthalten, das alle Eigenschaften des Deadlockdiagrammereignisses enthält.</span><span class="sxs-lookup"><span data-stu-id="6b696-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b696-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b696-133">See Also</span></span>  
 [<span data-ttu-id="6b696-134">Konzepte des WMI-Anbieters für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="6b696-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
