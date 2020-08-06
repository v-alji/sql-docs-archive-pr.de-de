---
title: Ausführen von Windows PowerShell-Schritten in SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617144"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="4fab9-102">Ausführen von Windows PowerShell-Schritten in SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="4fab9-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="4fab9-103">Führen Sie die SQL Server PowerShell-Skripts mithilfe des SQL Server-Agent nach Zeitplan aus.</span><span class="sxs-lookup"><span data-stu-id="4fab9-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="4fab9-104">**Vorbereitungen:**  [Einschränkungen](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="4fab9-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="4fab9-105">**So führen Sie PowerShell in SQL Server Agent mit folgenden Auftragsschritten aus:**  [PowerShell-Auftragsschritt](#PShellJob), [Eingabeaufforderungs-Auftragsschritt](#CmdExecJob)</span><span class="sxs-lookup"><span data-stu-id="4fab9-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="4fab9-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4fab9-106">Before You Begin</span></span>  
 <span data-ttu-id="4fab9-107">Es gibt mehrere Typen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Auftragsschritten.</span><span class="sxs-lookup"><span data-stu-id="4fab9-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="4fab9-108">Jeder Typ ist einem Subsystem zugeordnet, das eine bestimmte Umgebung implementiert, wie eine Replikations-Agent- oder Eingabeaufforderungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="4fab9-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="4fab9-109">Sie können Windows PowerShell-Skripts schreiben und die Skripts dann mit dem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent in Aufträge integrieren, die zu festgelegten Zeiten oder in Reaktion auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Ereignisse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fab9-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="4fab9-110">Windows PowerShell-Skripts können mit entweder einem Eingabeaufforderungs-Auftragsschritt oder einem PowerShell-Auftragsschritt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fab9-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="4fab9-111">Verwenden Sie einen PowerShell-Auftragsschritt, damit das Subsystem des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Agent das Hilfsprogramm `sqlps` ausführt, das PowerShell 2.0 startet und das `sqlps`-Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="4fab9-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="4fab9-112">Verwenden Sie einen Auftragsschritt an einer Eingabeaufforderung, um &lt;ui&gt;PowerShell.exe&lt;/ui&gt; auszuführen, und geben Sie ein Skript an, das das `sqlps`-Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="4fab9-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4fab9-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4fab9-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4fab9-114">Jeder Auftragsschritt des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Agents, der PowerShell mit dem Modul `sqlps` ausführt, startet einen Prozess, der etwa 20 MB Arbeitsspeicher in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="4fab9-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="4fab9-115">Die gleichzeitige Ausführung einer großen Anzahl von Windows PowerShell-Auftragsschritten kann sich negativ auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="4fab9-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="4fab9-116">Erstellen eines PowerShell-Auftrags Schritts</span><span class="sxs-lookup"><span data-stu-id="4fab9-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="4fab9-117">**So erstellen Sie einen PowerShell-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="4fab9-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="4fab9-118">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4fab9-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="4fab9-119">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4fab9-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="4fab9-120">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="4fab9-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="4fab9-121">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="4fab9-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="4fab9-122">Klicken Sie in der Liste **Typ** auf **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4fab9-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="4fab9-123">Wählen Sie in der Liste **Ausführen als** das Proxykonto mit den Anmeldeinformationen für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="4fab9-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="4fab9-124">Geben Sie im Feld **Befehl** die PowerShell-Skriptsyntax ein, die für den Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4fab9-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="4fab9-125">Klicken Sie alternativ auf **Öffnen** , und wählen Sie eine Datei aus, die die Skriptsyntax enthält.</span><span class="sxs-lookup"><span data-stu-id="4fab9-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="4fab9-126">Klicken Sie auf die Seite **Erweitert** , um die folgenden Optionen für den Auftragsschritt festzulegen: welche Aktion bei der erfolgreichen oder fehlerhaften Ausführung des Auftragsschrittes jeweils auszuführen ist, wie oft der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und wie viele Wiederholungsversuche unternommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fab9-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="4fab9-127">Erstellen eines Eingabeaufforderungs-Auftrags Schritts</span><span class="sxs-lookup"><span data-stu-id="4fab9-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="4fab9-128">**So erstellen Sie einen CmdExec-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="4fab9-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="4fab9-129">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4fab9-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="4fab9-130">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4fab9-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="4fab9-131">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="4fab9-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="4fab9-132">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="4fab9-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="4fab9-133">Wählen Sie in der Liste **Typ** den Eintrag **Betriebssystem (CmdExec)** aus.</span><span class="sxs-lookup"><span data-stu-id="4fab9-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="4fab9-134">Wählen Sie in der Liste **Ausführen als** das Proxykonto mit den Anmeldeinformationen für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="4fab9-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="4fab9-135">Standardmäßig werden CmdExec-Auftragsschritte im Kontext des Kontos des SQL Server-Agent-Dienstes ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4fab9-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="4fab9-136">Geben Sie in das Feld **Prozessexitcode eines erfolgreichen Befehls** einen Wert zwischen 0 und 999999 ein.</span><span class="sxs-lookup"><span data-stu-id="4fab9-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="4fab9-137">Geben Sie im Feld **Befehl** "powershell.exe" zusammen mit Parametern, die das auszuführende PowerShell-Skript angeben, ein.</span><span class="sxs-lookup"><span data-stu-id="4fab9-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="4fab9-138">Klicken Sie auf die Seite **Erweitert** , um Optionen für Auftragsschritte festzulegen, z. B. welche Aktion bei der erfolgreichen oder fehlerhaften Ausführung des Auftragsschrittes jeweils auszuführen ist, wie oft der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und in welche Datei der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent die Auftragsschrittausgabe schreiben soll.</span><span class="sxs-lookup"><span data-stu-id="4fab9-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="4fab9-139">Nur Mitglieder der festen Serverrolle **sysadmin** können die Auftragsschrittausgabe in eine Betriebssystemdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="4fab9-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fab9-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fab9-140">See Also</span></span>  
 [<span data-ttu-id="4fab9-141">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fab9-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
