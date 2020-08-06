---
title: 'Auftrags Schritt-Eigenschaften: neuer Auftrags Schritt (Seite "Erweitert") | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722181"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="2cc1e-102">Auftragsschritteigenschaften: Neuer Auftragsschritt (Seite „Erweitert“)</span><span class="sxs-lookup"><span data-stu-id="2cc1e-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="2cc1e-103">Mithilfe dieser Seite können Sie die Eigenschaften eines-Agent- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Auftrags Schritts anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2cc1e-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2cc1e-104">Options</span></span>  
 <span data-ttu-id="2cc1e-105">**Aktion bei Erfolg**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-105">**On success action**</span></span>  
 <span data-ttu-id="2cc1e-106">Legt fest, welche Aktion der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent bei erfolgreicher Auftragsausführung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="2cc1e-107">**Wiederholungsversuche**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-107">**Retry attempts**</span></span>  
 <span data-ttu-id="2cc1e-108">Legt fest, wie oft vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent versucht werden soll, einen fehlgeschlagenen Auftragsschritt erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="2cc1e-109">**Wiederholungsintervall (Min)**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="2cc1e-110">Legt fest, wie lange der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent bis zum nächsten Wiederholungsversuch warten soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="2cc1e-111">**Aktion bei Fehler**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-111">**On failure action**</span></span>  
 <span data-ttu-id="2cc1e-112">Legt fest, welche Aktion der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent bei Fehlschlagen des Auftrags ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="2cc1e-113">Optionen für Transact-SQL-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="2cc1e-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="2cc1e-114">**Ausgabedatei**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-114">**Output file**</span></span>  
 <span data-ttu-id="2cc1e-115">Legt fest, welche Datei für die Ausgabe aus dem Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="2cc1e-116">Diese Option ist nur für Mitglieder der festen Serverrolle **sysadmin** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="2cc1e-117">**...**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-117">**...**</span></span>  
 <span data-ttu-id="2cc1e-118">Nach der Datei, die für die Ausgabe aus dem Auftragsschritt verwendet werden soll, können Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-119">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-119">**View**</span></span>  
 <span data-ttu-id="2cc1e-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ist diese Schaltfläche für die Anzeige von Ausgabedateien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2cc1e-121">Nutzen Sie stattdessen den Editor für die Anzeige von Auftragsschritt-Ausgabedateien.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2cc1e-122">**Ausgabe an vorhandene Datei anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="2cc1e-123">Fügt die Ausgabe an den vorhandenen Inhalt der Datei an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="2cc1e-124">Andernfalls wird der vorige Inhalt der Datei bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-125">**In Tabelle protokollieren**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-125">**Log to table**</span></span>  
 <span data-ttu-id="2cc1e-126">Protokolliert die Ausgabedaten des Auftragsschritts in der **sysjobstepslogs** -Tabelle der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2cc1e-127">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-127">**View**</span></span>  
 <span data-ttu-id="2cc1e-128">Klicken Sie nach Ausführung des Auftragsschritts auf **Anzeigen** , um seine Ausgabe in der Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2cc1e-129">**Ausgabe an vorhandenen Eintrag in Tabelle anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2cc1e-130">Fügt die Ausgabe an den vorhandenen Inhalt der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2cc1e-131">Andernfalls wird der vorige Inhalt der Tabelle bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-132">**Schrittausgabe in Verlauf einschließen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-132">**Include step output in history**</span></span>  
 <span data-ttu-id="2cc1e-133">Wählen Sie diese Option aus, wenn die Ausgabe des Auftragsschritts in den Auftragsverlauf aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="2cc1e-134">**Ausführen als Benutzer**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-134">**Run as user**</span></span>  
 <span data-ttu-id="2cc1e-135">Wenn Sie Mitglied der festen Serverrolle **sysadmin** sind, können Sie für die Ausführung dieses Auftragsschritts einen anderen SQL-Anmeldenamen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="2cc1e-136">Optionen für Auftragsschritte des Betriebssystems (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="2cc1e-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="2cc1e-137">**Ausgabedatei**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-137">**Output file**</span></span>  
 <span data-ttu-id="2cc1e-138">Legt fest, welche Datei für die Ausgabe aus dem Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-139">**...**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-139">**...**</span></span>  
 <span data-ttu-id="2cc1e-140">Nach der Datei, die für die Ausgabe aus dem Auftragsschritt verwendet werden soll, können Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-141">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-141">**View**</span></span>  
 <span data-ttu-id="2cc1e-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ist diese Schaltfläche für die Anzeige von Ausgabedateien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2cc1e-143">Nutzen Sie stattdessen den Editor für die Anzeige von Auftragsschritt-Ausgabedateien.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2cc1e-144">**Ausgabe an vorhandene Datei anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="2cc1e-145">Fügt die Auftragsschrittausgabe bei jeder Ausführung des Schritts an den vorhandenen Inhalt der Datei an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="2cc1e-146">**In Tabelle protokollieren**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-146">**Log to table**</span></span>  
 <span data-ttu-id="2cc1e-147">Protokolliert die Ausgabedaten des Auftragsschritts in der **sysjobstepslogs** -Tabelle der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2cc1e-148">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-148">**View**</span></span>  
 <span data-ttu-id="2cc1e-149">Klicken Sie nach Ausführung des Auftragsschritts auf **Anzeigen** , um seine Ausgabe in der Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2cc1e-150">**Ausgabe an vorhandenen Eintrag in Tabelle anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2cc1e-151">Fügt die Ausgabe an den vorhandenen Inhalt der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2cc1e-152">Andernfalls wird der vorige Inhalt der Tabelle bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-153">**Schrittausgabe in Verlauf einschließen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-153">**Include step output in history**</span></span>  
 <span data-ttu-id="2cc1e-154">Wählen Sie diese Option aus, wenn die Ausgabe des Auftragsschritts in den Auftragsverlauf aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="2cc1e-155">Optionen für PowerShell-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="2cc1e-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="2cc1e-156">**Ausgabedatei**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-156">**Output file**</span></span>  
 <span data-ttu-id="2cc1e-157">Legt fest, welche Datei für die Ausgabe aus dem Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-158">**...**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-158">**...**</span></span>  
 <span data-ttu-id="2cc1e-159">Nach der Datei, die für die Ausgabe aus dem Auftragsschritt verwendet werden soll, können Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-160">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-160">**View**</span></span>  
 <span data-ttu-id="2cc1e-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ist diese Schaltfläche für die Anzeige von Ausgabedateien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2cc1e-162">Nutzen Sie stattdessen den Editor für die Anzeige von Auftragsschritt-Ausgabedateien.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2cc1e-163">**Ausgabe an vorhandene Datei anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="2cc1e-164">Fügt die Auftragsschrittausgabe bei jeder Ausführung des Schritts an den vorhandenen Inhalt der Datei an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="2cc1e-165">**In Tabelle protokollieren**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-165">**Log to table**</span></span>  
 <span data-ttu-id="2cc1e-166">Protokolliert die Ausgabedaten des Auftragsschritts in der **sysjobstepslogs** -Tabelle der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2cc1e-167">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-167">**View**</span></span>  
 <span data-ttu-id="2cc1e-168">Klicken Sie nach Ausführung des Auftragsschritts auf **Anzeigen** , um seine Ausgabe in der Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2cc1e-169">**Ausgabe an vorhandenen Eintrag in Tabelle anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2cc1e-170">Fügt die Ausgabe an den vorhandenen Inhalt der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2cc1e-171">Andernfalls wird der vorige Inhalt der Tabelle bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-172">**Schrittausgabe in Verlauf einschließen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-172">**Include step output in history**</span></span>  
 <span data-ttu-id="2cc1e-173">Wählen Sie diese Option aus, wenn die Ausgabe des Auftragsschritts in den Auftragsverlauf aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="2cc1e-174">Optionen für Auftragsschritte des Replikation-Warteschlangenlesers</span><span class="sxs-lookup"><span data-stu-id="2cc1e-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="2cc1e-175">**Server**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-175">**Server**</span></span>  
 <span data-ttu-id="2cc1e-176">Legt fest, welcher Server für einen Auftragsschritt des Replikation-Warteschlangenlesers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="2cc1e-177">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-177">**Database**</span></span>  
 <span data-ttu-id="2cc1e-178">Legt fest, welche Datenbank für einen Auftragsschritt des Replikation-Warteschlangenlesers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="2cc1e-179">Optionen für Auftragsschritte von SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2cc1e-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="2cc1e-180">**Ausgabedatei**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-180">**Output file**</span></span>  
 <span data-ttu-id="2cc1e-181">Legt fest, welche Datei für die Ausgabe aus dem Auftragsschritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="2cc1e-182">Diese Option ist nur für Mitglieder der festen Serverrolle **sysadmin** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="2cc1e-183">**...**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-183">**...**</span></span>  
 <span data-ttu-id="2cc1e-184">Nach der Datei, die für die Ausgabe aus dem Auftragsschritt verwendet werden soll, können Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="2cc1e-185">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-185">**View**</span></span>  
 <span data-ttu-id="2cc1e-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]ist diese Schaltfläche für die Anzeige von Ausgabedateien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="2cc1e-187">Nutzen Sie stattdessen den Editor für die Anzeige von Auftragsschritt-Ausgabedateien.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="2cc1e-188">**Ausgabe an vorhandene Datei anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="2cc1e-189">Fügt die Ausgabe an den vorhandenen Inhalt der Datei an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="2cc1e-190">Andernfalls wird der vorige Inhalt der Datei bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-191">**In Tabelle protokollieren**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-191">**Log to table**</span></span>  
 <span data-ttu-id="2cc1e-192">Protokolliert die Ausgabedaten des Auftragsschritts in der **sysjobstepslogs** -Tabelle der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="2cc1e-193">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-193">**View**</span></span>  
 <span data-ttu-id="2cc1e-194">Klicken Sie nach Ausführung des Auftragsschritts auf **Anzeigen** , um seine Ausgabe in der Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="2cc1e-195">**Ausgabe an vorhandenen Eintrag in Tabelle anfügen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="2cc1e-196">Fügt die Ausgabe an den vorhandenen Inhalt der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="2cc1e-197">Andernfalls wird der vorige Inhalt der Tabelle bei jeder Ausführung des Auftragsschritts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="2cc1e-198">**Schrittausgabe in Verlauf einschließen**</span><span class="sxs-lookup"><span data-stu-id="2cc1e-198">**Include step output in history**</span></span>  
 <span data-ttu-id="2cc1e-199">Wählen Sie diese Option aus, wenn die Ausgabe des Auftragsschritts in den Auftragsverlauf aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc1e-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cc1e-200">See Also</span></span>  
 [<span data-ttu-id="2cc1e-201">Verwalten von Auftragsschritten</span><span class="sxs-lookup"><span data-stu-id="2cc1e-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
