---
title: Verwenden des PowerShell-Anbieters für erweiterte Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619120"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="31508-102">Verwenden des PowerShell-Anbieters für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="31508-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="31508-103">Erweiterte Ereignisse von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können Sie mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -PowerShell-Anbieters verwalten.</span><span class="sxs-lookup"><span data-stu-id="31508-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="31508-104">Der Unterordner XEvent ist auf dem SQLSERVER-Laufwerk verfügbar.</span><span class="sxs-lookup"><span data-stu-id="31508-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="31508-105">Auf diesen Ordner können Sie mit einer der folgenden Methoden zugreifen:</span><span class="sxs-lookup"><span data-stu-id="31508-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="31508-106">Geben Sie an der Eingabeaufforderung `sqlps` ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="31508-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="31508-107">Geben Sie `cd xevent` ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="31508-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="31508-108">Von dort aus können Sie die **CD** -und `dir` -Befehle (oder die Cmdlets " **Set-Location** " und " **Get-ChildItem** ") verwenden, um zum Servernamen und Instanznamen zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="31508-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="31508-109">Erweitern Sie im Objekt-Explorer den Instanznamen, erweitern Sie **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Erweiterte Ereignisse**, und klicken Sie anschließend auf **PowerShell starten**.</span><span class="sxs-lookup"><span data-stu-id="31508-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="31508-110">Damit wird PowerShell unter dem folgenden Pfad gestartet:</span><span class="sxs-lookup"><span data-stu-id="31508-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="31508-111">PS SQLServer: \ XEvent \\ *Servername* \\ *instanceName*></span><span class="sxs-lookup"><span data-stu-id="31508-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31508-112">PowerShell können Sie unter **Erweiterte Ereignisse**von jedem Knoten aus starten.</span><span class="sxs-lookup"><span data-stu-id="31508-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="31508-113">Sie können z.B. mit der rechten Maustaste auf **Sitzungen**klicken und anschließend auf **PowerShell starten**klicken.</span><span class="sxs-lookup"><span data-stu-id="31508-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="31508-114">Damit starten Sie PowerShell eine Ebene tiefer, mit dem Ordner Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="31508-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="31508-115">Sie können die Struktur des Ordners "XEvent" nach vorhandenen Sitzungen für erweiterte Ereignisse und deren zugeordneten Ereignissen, Zielen und Prädikaten durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="31508-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="31508-116">Wenn Sie z. b. vom PS SQLServer: \ XEvent \\ *Servername* \\ *instanceName*> Pfad `cd sessions` eingeben, drücken Sie die EINGABETASTE, geben Sie ein, `dir` und drücken Sie dann die EINGABETASTE, um die Liste der Sitzungen anzuzeigen, die auf dieser Instanz gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="31508-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="31508-117">Sie können auch anzeigen, ob die Sitzung ausgeführt wird (und wenn dies der Fall ist, die bisherige Sitzungsdauer), sowie ob die Sitzung für den Start bei Instanzstart konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="31508-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="31508-118">Wenn Sie die Ereignisse, deren Prädikate und die einer Sitzung zugeordneten Ziele anzeigen möchten, können Sie Verzeichnisse in den Sitzungsnamen ändern und dann den Ereignis- oder den Zielordner anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31508-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="31508-119">Um z. b. die Ereignisse und deren Prädikate anzuzeigen, die der standardmäßigen System Integritäts Sitzung zugeordnet sind, geben Sie aus dem Pfad PS SQLServer: \ XEvent \\ *Servername* \\ *instanceName*\sessions> Pfad die Bezeichnung `cd system_health\events,` drücken Sie EINGABETASTE, geben Sie ein, `dir` und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="31508-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="31508-120">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -PowerShell-Anbieter ist ein leistungsstarkes Tool, mit dem Sie Sitzungen für erweiterte Ereignisse erstellen, ändern und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="31508-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="31508-121">Der folgende Abschnitt enthält einige einfache Beispiele für die Verwendung von PowerShell-Skripts mit erweiterten Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="31508-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="31508-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="31508-122">Examples</span></span>  
 <span data-ttu-id="31508-123">Achten Sie in den folgenden Beispielen auf Folgendes:</span><span class="sxs-lookup"><span data-stu-id="31508-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="31508-124">Die Skripts müssen von der PS SQLServer: \\>-Eingabeaufforderung ausgeführt werden (verfügbar, wenn Sie `sqlps` an einer Eingabeaufforderung eingeben).</span><span class="sxs-lookup"><span data-stu-id="31508-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="31508-125">Die Skripts verwenden die Standardinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31508-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="31508-126">Die Skripts müssen mit der Erweiterung .ps1 gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="31508-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="31508-127">In der PowerShell-Ausführungsrichtlinie muss das auszuführende Skript zugelassen sein.</span><span class="sxs-lookup"><span data-stu-id="31508-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="31508-128">Verwenden Sie das Cmdlet **Set-Executionpolicy** , um die Ausführungsrichtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="31508-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="31508-129">(Weitere Informationen erhalten Sie durch Eingabe von `get-help set-executionpolicy -detailed` und Drücken der EINGABETASTE.)</span><span class="sxs-lookup"><span data-stu-id="31508-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="31508-130">Mit dem folgenden Skript erstellen Sie die neue Sitzung "TestSession".</span><span class="sxs-lookup"><span data-stu-id="31508-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="31508-131">Das folgende Skript fügt der im vorherigen Beispiel erstellten Sitzung das Ringpufferziel hinzu.</span><span class="sxs-lookup"><span data-stu-id="31508-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="31508-132">(In diesem Beispiel wird die Verwendung der `Alter`-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="31508-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="31508-133">Sie können das Ziel beim Erstellen der Sitzung hinzufügen.)</span><span class="sxs-lookup"><span data-stu-id="31508-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="31508-134">Mit dem folgenden Skript erstellen Sie eine neue Sitzung, in der ein Prädikatausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31508-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="31508-135">In diesem Fall werden in der Sitzung Informationen gesammelt, die in die Datei „c:\temp.log“ geschrieben werden (über das Ereignis „sqlserver.file_written“).</span><span class="sxs-lookup"><span data-stu-id="31508-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="31508-136">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="31508-136">Security</span></span>  
 <span data-ttu-id="31508-137">Zum Erstellen, Ändern oder Löschen einer Sitzung für erweiterte Ereignisse müssen Sie über die ALTER ANY EVENT SESSION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="31508-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31508-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31508-138">See Also</span></span>  
 <span data-ttu-id="31508-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="31508-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="31508-140">[Verwenden der system_health Sitzung](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="31508-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="31508-141">Tools für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="31508-141">Extended Events Tools</span></span>](extended-events-tools.md)  
