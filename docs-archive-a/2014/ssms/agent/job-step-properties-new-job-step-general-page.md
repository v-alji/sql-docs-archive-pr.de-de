---
title: 'Auftrags Schritt-Eigenschaften: neuer Auftrags Schritt (Seite "Allgemein") | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620109"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="6a939-102">Auftragsschritteigenschaften: Neuer Auftragsschritt (Seite „Allgemein“)</span><span class="sxs-lookup"><span data-stu-id="6a939-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="6a939-103">Mithilfe dieser Seite können Sie die Eigenschaften eines-Agent-Auftrags Schritts anzeigen und ändern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder einen neuen Auftrags Schritt definieren.</span><span class="sxs-lookup"><span data-stu-id="6a939-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="6a939-104">Erweitern Sie im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent, klicken Sie mit der rechten Maustaste auf **Aufträge**, klicken Sie auf **Neuer Auftrag**, wählen Sie die Seite **Schritte** aus, und klicken Sie auf **Neu**, um zu dieser Seite zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="6a939-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="6a939-105">Sie können auch zu dieser Seite navigieren, indem Sie mit der rechten Maustaste auf einen Auftrag im Objekt-Explorer klicken, auf **Eigenschaften**klicken, die Seite **Schritte** auswählen, und auf **Neu**, **Einfügen**oder **Bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="6a939-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6a939-106">Optionen</span><span class="sxs-lookup"><span data-stu-id="6a939-106">Options</span></span>  
 <span data-ttu-id="6a939-107">**Schrittname**</span><span class="sxs-lookup"><span data-stu-id="6a939-107">**Step name**</span></span>  
 <span data-ttu-id="6a939-108">Legt den Namen des Auftrags fest.</span><span class="sxs-lookup"><span data-stu-id="6a939-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="6a939-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6a939-109">**Type**</span></span>  
 <span data-ttu-id="6a939-110">Legt das durch den Auftrag verwendete Subsystem fest.</span><span class="sxs-lookup"><span data-stu-id="6a939-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="6a939-111">Basierend auf dem von Ihnen ausgewählten Subsystem ändern sich die für das Definieren des Auftragsschritts angezeigten Optionen.</span><span class="sxs-lookup"><span data-stu-id="6a939-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="6a939-112">**Ausführen als**</span><span class="sxs-lookup"><span data-stu-id="6a939-112">**Run as**</span></span>  
 <span data-ttu-id="6a939-113">Legt das Proxykonto für den Auftragsschritt fest.</span><span class="sxs-lookup"><span data-stu-id="6a939-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="6a939-114">Mitglieder der festen Serverrolle „sysadmin“ können auch das **SQL-Agent-Dienstkonto**angeben.</span><span class="sxs-lookup"><span data-stu-id="6a939-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="6a939-115">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="6a939-115">**Database**</span></span>  
 <span data-ttu-id="6a939-116">Legt die Datenbank fest, in der der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a939-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="6a939-117">Diese Option ist nicht für alle Auftragsschritttypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a939-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="6a939-118">**Befehl**</span><span class="sxs-lookup"><span data-stu-id="6a939-118">**Command**</span></span>  
 <span data-ttu-id="6a939-119">Legt den durch den Auftrag ausgeführten Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="6a939-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="6a939-120">Optionen für Transact-SQL-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="6a939-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="6a939-121">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-121">**Open**</span></span>  
 <span data-ttu-id="6a939-122">Lädt den Befehl aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="6a939-123">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-123">**Select All**</span></span>  
 <span data-ttu-id="6a939-124">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-125">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-125">**Copy**</span></span>  
 <span data-ttu-id="6a939-126">Kopiert den ausgewählten Text in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="6a939-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="6a939-127">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-127">**Paste**</span></span>  
 <span data-ttu-id="6a939-128">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="6a939-129">**Parse**</span><span class="sxs-lookup"><span data-stu-id="6a939-129">**Parse**</span></span>  
 <span data-ttu-id="6a939-130">Überprüft die Syntax des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="6a939-131">Optionen für Auftragsschritte von ActiveX-Skript</span><span class="sxs-lookup"><span data-stu-id="6a939-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6a939-132">Das ActiveX Scripting-Subsystem wird in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent entfernt.</span><span class="sxs-lookup"><span data-stu-id="6a939-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6a939-133">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a939-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="6a939-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="6a939-134">**VBScript**</span></span>  
 <span data-ttu-id="6a939-135">Gibt [!INCLUDE[msCoName](../../includes/msconame-md.md)] VBScript als Sprache für die Auftragsschritte an.</span><span class="sxs-lookup"><span data-stu-id="6a939-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="6a939-136">**JScript**</span><span class="sxs-lookup"><span data-stu-id="6a939-136">**JScript**</span></span>  
 <span data-ttu-id="6a939-137">Gibt JScript als Sprache für die Auftragsschritte an.</span><span class="sxs-lookup"><span data-stu-id="6a939-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="6a939-138">**Andere**</span><span class="sxs-lookup"><span data-stu-id="6a939-138">**Other**</span></span>  
 <span data-ttu-id="6a939-139">Geben Sie den Namen der Sprache für Auftragsschritte ein, die in einer anderen Skriptsprache geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="6a939-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="6a939-140">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-140">**Open**</span></span>  
 <span data-ttu-id="6a939-141">Lädt den Befehl aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="6a939-142">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-142">**Select All**</span></span>  
 <span data-ttu-id="6a939-143">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-144">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-144">**Copy**</span></span>  
 <span data-ttu-id="6a939-145">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-146">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-146">**Paste**</span></span>  
 <span data-ttu-id="6a939-147">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="6a939-148">Optionen für Auftragsschritte des Betriebssystems (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="6a939-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="6a939-149">**Prozessexitcode eines erfolgreichen Befehls**</span><span class="sxs-lookup"><span data-stu-id="6a939-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="6a939-150">Geben Sie den Exitcode ein, den der Befehl zurückgibt, um einen Erfolg zu melden.</span><span class="sxs-lookup"><span data-stu-id="6a939-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="6a939-151">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-151">**Open**</span></span>  
 <span data-ttu-id="6a939-152">Lädt den Befehl aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="6a939-153">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-153">**Select All**</span></span>  
 <span data-ttu-id="6a939-154">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-155">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-155">**Copy**</span></span>  
 <span data-ttu-id="6a939-156">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-157">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-157">**Paste**</span></span>  
 <span data-ttu-id="6a939-158">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="6a939-159">Optionen für PowerShell-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="6a939-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="6a939-160">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-160">**Open**</span></span>  
 <span data-ttu-id="6a939-161">Lädt das Skript aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="6a939-162">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-162">**Select All**</span></span>  
 <span data-ttu-id="6a939-163">Markiert den Text des Skripts.</span><span class="sxs-lookup"><span data-stu-id="6a939-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="6a939-164">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-164">**Copy**</span></span>  
 <span data-ttu-id="6a939-165">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-166">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-166">**Paste**</span></span>  
 <span data-ttu-id="6a939-167">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="6a939-168">Optionen für Replikationsverteiler-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="6a939-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="6a939-169">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-169">**Select All**</span></span>  
 <span data-ttu-id="6a939-170">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-171">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-171">**Copy**</span></span>  
 <span data-ttu-id="6a939-172">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-173">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-173">**Paste**</span></span>  
 <span data-ttu-id="6a939-174">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="6a939-175">Optionen für Replikationsmerge-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="6a939-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="6a939-176">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-176">**Select All**</span></span>  
 <span data-ttu-id="6a939-177">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-178">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-178">**Copy**</span></span>  
 <span data-ttu-id="6a939-179">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-180">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-180">**Paste**</span></span>  
 <span data-ttu-id="6a939-181">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="6a939-182">Optionen für Auftragsschritte des Replikation-Warteschlangenlesers</span><span class="sxs-lookup"><span data-stu-id="6a939-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="6a939-183">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="6a939-183">**Database**</span></span>  
 <span data-ttu-id="6a939-184">Die Datenbank, die für den Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="6a939-185">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-185">**Select All**</span></span>  
 <span data-ttu-id="6a939-186">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-187">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-187">**Copy**</span></span>  
 <span data-ttu-id="6a939-188">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-189">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-189">**Paste**</span></span>  
 <span data-ttu-id="6a939-190">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="6a939-191">Optionen für Replikationsmomentaufnahme-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="6a939-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="6a939-192">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-192">**Select All**</span></span>  
 <span data-ttu-id="6a939-193">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-194">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-194">**Copy**</span></span>  
 <span data-ttu-id="6a939-195">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-196">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-196">**Paste**</span></span>  
 <span data-ttu-id="6a939-197">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="6a939-198">Optionen für Auftragsschritte des Replikationstransaktionsprotokoll-Lesers</span><span class="sxs-lookup"><span data-stu-id="6a939-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="6a939-199">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-199">**Select All**</span></span>  
 <span data-ttu-id="6a939-200">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-201">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-201">**Copy**</span></span>  
 <span data-ttu-id="6a939-202">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-203">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-203">**Paste**</span></span>  
 <span data-ttu-id="6a939-204">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="6a939-205">Optionen für Auftragsschritte von SQL Server Analysis Services-Befehlen</span><span class="sxs-lookup"><span data-stu-id="6a939-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="6a939-206">**Server**</span><span class="sxs-lookup"><span data-stu-id="6a939-206">**Server**</span></span>  
 <span data-ttu-id="6a939-207">Wählt den Server aus, auf dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a939-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="6a939-208">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-208">**Open**</span></span>  
 <span data-ttu-id="6a939-209">Lädt den Befehl aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="6a939-210">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-210">**Select All**</span></span>  
 <span data-ttu-id="6a939-211">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-212">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-212">**Copy**</span></span>  
 <span data-ttu-id="6a939-213">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-214">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-214">**Paste**</span></span>  
 <span data-ttu-id="6a939-215">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="6a939-216">Optionen für Auftragsschritte von SQL Server Analysis Services-Abfragen</span><span class="sxs-lookup"><span data-stu-id="6a939-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="6a939-217">**Server**</span><span class="sxs-lookup"><span data-stu-id="6a939-217">**Server**</span></span>  
 <span data-ttu-id="6a939-218">Wählt den Server aus, auf dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a939-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="6a939-219">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="6a939-219">**Database**</span></span>  
 <span data-ttu-id="6a939-220">Die Datenbank, die für den Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="6a939-221">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="6a939-221">**Open**</span></span>  
 <span data-ttu-id="6a939-222">Lädt den Befehl aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6a939-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="6a939-223">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-223">**Select All**</span></span>  
 <span data-ttu-id="6a939-224">Markiert den Text des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a939-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="6a939-225">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-225">**Copy**</span></span>  
 <span data-ttu-id="6a939-226">Kopiert den markierten Text.</span><span class="sxs-lookup"><span data-stu-id="6a939-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="6a939-227">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="6a939-227">**Paste**</span></span>  
 <span data-ttu-id="6a939-228">Fügt die Inhalte aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="6a939-229">Optionen für Auftragsschritte von Integration Services-Paketausführungen</span><span class="sxs-lookup"><span data-stu-id="6a939-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="6a939-230">Registerkarte Allgemein</span><span class="sxs-lookup"><span data-stu-id="6a939-230">General Tab</span></span>  
 <span data-ttu-id="6a939-231">Gibt den Speicherort des [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)])-Pakets an, und welche Authentifizierungsmethode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="6a939-232">Die folgenden Optionen sind verfügbar, wenn Sie diese Registerkarte auswählen.</span><span class="sxs-lookup"><span data-stu-id="6a939-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="6a939-233">**Paketquelle**</span><span class="sxs-lookup"><span data-stu-id="6a939-233">**Package source**</span></span>  
 <span data-ttu-id="6a939-234">Gibt den Speicherort des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Pakets an.</span><span class="sxs-lookup"><span data-stu-id="6a939-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="6a939-235">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="6a939-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="6a939-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6a939-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="6a939-237">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="6a939-237">**File system**</span></span>  
  
-   <span data-ttu-id="6a939-238">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="6a939-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="6a939-239">**Server**</span><span class="sxs-lookup"><span data-stu-id="6a939-239">**Server**</span></span>  
 <span data-ttu-id="6a939-240">Geben Sie den Namen des Servers ein, auf dem das [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paket gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6a939-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="6a939-241">Diese Option ist nur verfügbar, wenn **SQL Server** oder **SSIS-Paketspeicher** für **Paketquelle**angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6a939-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="6a939-242">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="6a939-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="6a939-243">Für Anmeldungen bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a939-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="6a939-244">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="6a939-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="6a939-245">Für Anmeldungen an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a939-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="6a939-246">Wenn diese Authentifizierungsmethode ausgewählt wurde, geben Sie entsprechend **Benutzername** und **Kennwort**ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6a939-247">-Authentifizierung wird aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6a939-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="6a939-248">Aus Sicherheitsgründen sollte möglichst die Windows-Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a939-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="6a939-249">**Paket**</span><span class="sxs-lookup"><span data-stu-id="6a939-249">**Package**</span></span>  
 <span data-ttu-id="6a939-250">Geben Sie den Speicherort des Pakets ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6a939-251">Klicken Sie für kennwortgeschützte [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Pakete auf die Registerkarte **Konfigurationen** , um das Kennwort im Dialogfeld **Paketkennwort** einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a939-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="6a939-252">Andernfalls erzeugt der Auftrag des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents, der das kennwortgeschützte Paket ausführt, einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6a939-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="6a939-253">Registerkarte Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="6a939-253">Configurations Tab</span></span>  
 <span data-ttu-id="6a939-254">Gibt Konfigurationsoptionen für das [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paket an.</span><span class="sxs-lookup"><span data-stu-id="6a939-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="6a939-255">Wenn Sie diese Registerkarte auswählen, sind die folgenden Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a939-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="6a939-256">**Konfigurationsdateien**</span><span class="sxs-lookup"><span data-stu-id="6a939-256">**Configuration files**</span></span>  
 <span data-ttu-id="6a939-257">Führt die Konfigurationsdateien für das Paket in einer Liste auf.</span><span class="sxs-lookup"><span data-stu-id="6a939-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="6a939-258">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="6a939-258">**Add**</span></span>  
 <span data-ttu-id="6a939-259">Fügt eine Konfigurationsdatei für das Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a939-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="6a939-260">**Remove**</span><span class="sxs-lookup"><span data-stu-id="6a939-260">**Remove**</span></span>  
 <span data-ttu-id="6a939-261">Entfernt eine Konfigurationsdatei für das Paket.</span><span class="sxs-lookup"><span data-stu-id="6a939-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="6a939-262">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="6a939-262">**Move Up**</span></span>  
 <span data-ttu-id="6a939-263">Verschiebt die ausgewählte Konfigurationsdatei nach oben.</span><span class="sxs-lookup"><span data-stu-id="6a939-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="6a939-264">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="6a939-264">**Move Down**</span></span>  
 <span data-ttu-id="6a939-265">Verschiebt die ausgewählte Konfigurationsdatei nach unten.</span><span class="sxs-lookup"><span data-stu-id="6a939-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="6a939-266">Registerkarte Befehlsdateien</span><span class="sxs-lookup"><span data-stu-id="6a939-266">Command Files Tab</span></span>  
 <span data-ttu-id="6a939-267">Wählt Befehlsdateien für das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="6a939-267">Select command files for the package.</span></span> <span data-ttu-id="6a939-268">Befehlsdateien werden entsprechend ihrer Reihenfolge in der Liste verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6a939-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="6a939-269">Die folgenden Optionen sind verfügbar, wenn Sie diese Registerkarte auswählen.</span><span class="sxs-lookup"><span data-stu-id="6a939-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="6a939-270">**Befehlsdateien**</span><span class="sxs-lookup"><span data-stu-id="6a939-270">**Command files**</span></span>  
 <span data-ttu-id="6a939-271">Führt die Befehlsdateien für das Paket in einer Liste auf.</span><span class="sxs-lookup"><span data-stu-id="6a939-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="6a939-272">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="6a939-272">**Add**</span></span>  
 <span data-ttu-id="6a939-273">Fügt eine Befehlsdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a939-273">Add a command file.</span></span>  
  
 <span data-ttu-id="6a939-274">**Remove**</span><span class="sxs-lookup"><span data-stu-id="6a939-274">**Remove**</span></span>  
 <span data-ttu-id="6a939-275">Entfernt die ausgewählte Befehlsdatei.</span><span class="sxs-lookup"><span data-stu-id="6a939-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="6a939-276">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="6a939-276">**Move Up**</span></span>  
 <span data-ttu-id="6a939-277">Verschiebt die ausgewählte Befehlsdatei nach oben.</span><span class="sxs-lookup"><span data-stu-id="6a939-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="6a939-278">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="6a939-278">**Move Down**</span></span>  
 <span data-ttu-id="6a939-279">Verschiebt die ausgewählte Befehlsdatei nach unten.</span><span class="sxs-lookup"><span data-stu-id="6a939-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="6a939-280">Registerkarte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="6a939-280">Data Sources Tab</span></span>  
 <span data-ttu-id="6a939-281">Zeigt die im Paket angegebenen Datenquellen auf dieser Registerkarte an.</span><span class="sxs-lookup"><span data-stu-id="6a939-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="6a939-282">**Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="6a939-282">**Connection Manager**</span></span>  
 <span data-ttu-id="6a939-283">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="6a939-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="6a939-284">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6a939-284">**Description**</span></span>  
 <span data-ttu-id="6a939-285">Zeigt die Beschreibung der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="6a939-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="6a939-286">**Verbindungs Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="6a939-286">**Connection String**</span></span>  
 <span data-ttu-id="6a939-287">Zeigt die Verbindungszeichenfolge für die Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="6a939-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="6a939-288">Registerkarte Ausführungsoptionen</span><span class="sxs-lookup"><span data-stu-id="6a939-288">Execution Options Tab</span></span>  
 <span data-ttu-id="6a939-289">Zeigt die Ausführungsoptionen für das Paket auf dieser Registerkarte an oder ändert die Werte.</span><span class="sxs-lookup"><span data-stu-id="6a939-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="6a939-290">**Paket bei Überprüfungswarnungen fehlschlagen lassen**</span><span class="sxs-lookup"><span data-stu-id="6a939-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="6a939-291">Wählen Sie diese Option aus, wenn die Paketausführung bei Überprüfungswarnungen fehlschlagen soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="6a939-292">**Paket ohne Ausführung überprüfen**</span><span class="sxs-lookup"><span data-stu-id="6a939-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="6a939-293">Wählen Sie diese Option für den Auftragsschritt aus, wenn das Paket überprüft, nicht jedoch ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="6a939-294">**Maximale Anzahl von gleichzeitig ausführbaren Dateien**</span><span class="sxs-lookup"><span data-stu-id="6a939-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="6a939-295">Die maximale Anzahl der gleichzeitig ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="6a939-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="6a939-296">**Paketprüfpunkte aktivieren**</span><span class="sxs-lookup"><span data-stu-id="6a939-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="6a939-297">Wählen Sie diese Option für den Auftragsschritt aus, wenn Paketprüfpunkte verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a939-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="6a939-298">**Prüfpunktdatei**</span><span class="sxs-lookup"><span data-stu-id="6a939-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="6a939-299">Geben Sie den Namen der Prüfpunktdatei des Pakets ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="6a939-300">**...**</span><span class="sxs-lookup"><span data-stu-id="6a939-300">**...**</span></span>  
 <span data-ttu-id="6a939-301">Sucht nach der Prüfpunktdatei des Pakets.</span><span class="sxs-lookup"><span data-stu-id="6a939-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="6a939-302">**Neustartoptionen überschreiben**</span><span class="sxs-lookup"><span data-stu-id="6a939-302">**Override restart options**</span></span>  
 <span data-ttu-id="6a939-303">Wenn Sie diese Option auswählen, können Sie für diesen Auftragsschritt Neustartoptionen angeben, die von den im Paket angegebenen Optionen abweichen.</span><span class="sxs-lookup"><span data-stu-id="6a939-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="6a939-304">**Neustartoption**</span><span class="sxs-lookup"><span data-stu-id="6a939-304">**Restart option**</span></span>  
 <span data-ttu-id="6a939-305">Wählt die Aktion aus, die bei einem Neustart des Pakets durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a939-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="6a939-306">Registerkarte Protokollierung</span><span class="sxs-lookup"><span data-stu-id="6a939-306">Logging Tab</span></span>  
 <span data-ttu-id="6a939-307">Zeigt die Protokollanbieter für das Paket auf dieser Registerkarte an oder ändert diese.</span><span class="sxs-lookup"><span data-stu-id="6a939-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="6a939-308">**Protokoll Anbieter**</span><span class="sxs-lookup"><span data-stu-id="6a939-308">**Log Provider**</span></span>  
 <span data-ttu-id="6a939-309">Wählt die ClassID für den Protokollanbieter aus.</span><span class="sxs-lookup"><span data-stu-id="6a939-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="6a939-310">**Konfigurationszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="6a939-310">**Configuration String**</span></span>  
 <span data-ttu-id="6a939-311">Geben Sie die Konfigurationszeichenfolge für den Protokollanbieter ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="6a939-312">**Remove**</span><span class="sxs-lookup"><span data-stu-id="6a939-312">**Remove**</span></span>  
 <span data-ttu-id="6a939-313">Entfernt den Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="6a939-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="6a939-314">Registerkarte Werte festlegen</span><span class="sxs-lookup"><span data-stu-id="6a939-314">Set Values Tab</span></span>  
 <span data-ttu-id="6a939-315">Zeigt die Eigenschaftswerte für das Paket auf dieser Registerkarte an oder ändert die Werte.</span><span class="sxs-lookup"><span data-stu-id="6a939-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="6a939-316">**Eigenschaftspfad**</span><span class="sxs-lookup"><span data-stu-id="6a939-316">**Property path**</span></span>  
 <span data-ttu-id="6a939-317">Zeigt einen Pfad für die Eigenschaft an oder ändert diese.</span><span class="sxs-lookup"><span data-stu-id="6a939-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="6a939-318">**Wert**</span><span class="sxs-lookup"><span data-stu-id="6a939-318">**Value**</span></span>  
 <span data-ttu-id="6a939-319">Zeigt einen Wert für die Eigenschaft an oder ändert diesen.</span><span class="sxs-lookup"><span data-stu-id="6a939-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="6a939-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="6a939-320">**Remove**</span></span>  
 <span data-ttu-id="6a939-321">Entfernt die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6a939-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="6a939-322">Registerkarte Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6a939-322">Verification Tab</span></span>  
 <span data-ttu-id="6a939-323">Wählt die Überprüfungsoptionen für den Auftragsschritt auf dieser Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="6a939-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="6a939-324">**Nur signierte Pakete ausführen**</span><span class="sxs-lookup"><span data-stu-id="6a939-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="6a939-325">Führt nur Pakete aus, die signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a939-325">Run only packages that have been signed.</span></span> <span data-ttu-id="6a939-326">Bei Auswahl dieser Option schlägt der Auftragsschritt fehlt, wenn das Paket nicht signiert ist.</span><span class="sxs-lookup"><span data-stu-id="6a939-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="6a939-327">**Paketbuild überprüfen**</span><span class="sxs-lookup"><span data-stu-id="6a939-327">**Verify package build**</span></span>  
 <span data-ttu-id="6a939-328">Führt nur Pakete aus, die eine bestimmte Buildnummer besitzen.</span><span class="sxs-lookup"><span data-stu-id="6a939-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="6a939-329">Bei Auswahl dieser Option schlägt der Auftragsschritt fehl, wenn das Paket nicht die angegebene Buildnummer besitzt.</span><span class="sxs-lookup"><span data-stu-id="6a939-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="6a939-330">**Build**</span><span class="sxs-lookup"><span data-stu-id="6a939-330">**Build**</span></span>  
 <span data-ttu-id="6a939-331">Geben Sie die Buildnummer des Pakets ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="6a939-332">**Paket-ID überprüfen**</span><span class="sxs-lookup"><span data-stu-id="6a939-332">**Verify package ID**</span></span>  
 <span data-ttu-id="6a939-333">Führt nur Pakete aus, die eine bestimmte ID besitzen.</span><span class="sxs-lookup"><span data-stu-id="6a939-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="6a939-334">Bei Auswahl dieser Option schlägt der Auftragsschritt fehl, wenn das Paket nicht die angegebene ID besitzt.</span><span class="sxs-lookup"><span data-stu-id="6a939-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="6a939-335">**Paket-ID**</span><span class="sxs-lookup"><span data-stu-id="6a939-335">**Package ID**</span></span>  
 <span data-ttu-id="6a939-336">Geben Sie die Paket-ID ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="6a939-337">**Versions-ID überprüfen**</span><span class="sxs-lookup"><span data-stu-id="6a939-337">**Verify version ID**</span></span>  
 <span data-ttu-id="6a939-338">Führt nur Pakete mit einer bestimmten Versions-ID aus.</span><span class="sxs-lookup"><span data-stu-id="6a939-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="6a939-339">Bei Auswahl dieser Option schlägt der Auftragsschritt fehl, wenn das Paket nicht die angegebene Versions-ID besitzt.</span><span class="sxs-lookup"><span data-stu-id="6a939-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="6a939-340">**Versions-ID**</span><span class="sxs-lookup"><span data-stu-id="6a939-340">**Version ID**</span></span>  
 <span data-ttu-id="6a939-341">Geben Sie die Versions-ID ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="6a939-342">Registerkarte Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="6a939-342">Command Line Tab</span></span>  
 <span data-ttu-id="6a939-343">Gibt die Befehlszeilenoptionen für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="6a939-343">Specify command-line options for the package.</span></span> <span data-ttu-id="6a939-344">Wenn Sie diese Registerkarte auswählen, sind die folgenden Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a939-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="6a939-345">**Die ursprünglichen Optionen wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="6a939-345">**Restore the original options**</span></span>  
 <span data-ttu-id="6a939-346">Verwendet die in diesem Dialogfeld festgelegten Befehlszeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="6a939-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="6a939-347">**Befehlszeile manuell bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="6a939-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="6a939-348">Gibt die Optionen im Befehlszeilenfenster an.</span><span class="sxs-lookup"><span data-stu-id="6a939-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="6a939-349">**Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="6a939-349">**Command line**</span></span>  
 <span data-ttu-id="6a939-350">Geben Sie die für dieses Paket zu verwendenden Befehlszeilenoptionen ein.</span><span class="sxs-lookup"><span data-stu-id="6a939-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a939-351">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a939-351">See Also</span></span>  
 <span data-ttu-id="6a939-352">[Verwalten von Auftragsschritten](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="6a939-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="6a939-353">[SQL Server-Agent Aufträge für Pakete](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="6a939-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="6a939-354">Replikations-Agent-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="6a939-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
