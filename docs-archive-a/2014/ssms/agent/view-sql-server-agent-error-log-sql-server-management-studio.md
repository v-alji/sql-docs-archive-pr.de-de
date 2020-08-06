---
title: Anzeigen des SQL Server-Agent-Fehlerprotokolls (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719387"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="a37a8-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a37a8-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a37a8-103">In diesem Thema wird das Anzeigen des  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokolls in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a37a8-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a37a8-104">Im Protokolldatei-Viewer können Protokollinformationen aus einer Vielzahl von Komponenten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a37a8-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="a37a8-105">Wählen Sie im geöffneten Protokolldatei-Viewer im Bereich **Protokolle auswählen** die Protokolle aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a37a8-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="a37a8-106">In jedem Protokoll werden dem Protokolltyp entsprechende Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a37a8-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="a37a8-107">Welche Protokolle verfügbar sind, ist davon abhängig, wie der Protokolldatei-Viewer geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="a37a8-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="a37a8-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a37a8-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a37a8-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a37a8-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a37a8-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a37a8-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a37a8-111">Security</span><span class="sxs-lookup"><span data-stu-id="a37a8-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="a37a8-112">So zeigen Sie ein SQL Server-Agent-Fehlerprotokoll mithilfe von SQL Server Management Studio an</span><span class="sxs-lookup"><span data-stu-id="a37a8-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a37a8-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a37a8-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a37a8-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a37a8-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a37a8-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a37a8-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a37a8-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a37a8-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a37a8-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a37a8-117">Permissions</span></span>  
 <span data-ttu-id="a37a8-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a37a8-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a37a8-119">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="a37a8-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="a37a8-120">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="a37a8-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="a37a8-121">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a37a8-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="a37a8-122">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a37a8-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="a37a8-123">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a37a8-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="a37a8-124">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a37a8-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a37a8-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a37a8-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="a37a8-126">So zeigen Sie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll an</span><span class="sxs-lookup"><span data-stu-id="a37a8-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="a37a8-127">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll enthält, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a37a8-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="a37a8-128">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a37a8-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a37a8-129">Klicken Sie auf das Pluszeichen, um den Ordner **Fehlerprotokolle** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a37a8-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="a37a8-130">Klicken Sie mit der rechten Maustaste auf das Fehlerprotokoll, das Sie anzeigen möchten, und wählen Sie **Agentprotokoll anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="a37a8-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="a37a8-131">Die folgenden Optionen sind im Dialogfeld **Protokolldatei-Viewer-**_server_name_ verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a37a8-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="a37a8-132">**Protokoll laden**</span><span class="sxs-lookup"><span data-stu-id="a37a8-132">**Load Log**</span></span>  
     <span data-ttu-id="a37a8-133">Öffnen Sie ein Dialogfeld, in dem Sie eine zu ladende Protokolldatei angeben können.</span><span class="sxs-lookup"><span data-stu-id="a37a8-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="a37a8-134">**Export**</span><span class="sxs-lookup"><span data-stu-id="a37a8-134">**Export**</span></span>  
     <span data-ttu-id="a37a8-135">Öffnen Sie ein Dialogfeld, in dem Sie die im Raster **Protokolldateizusammenfassung** angezeigten Informationen in eine Textdatei exportieren können.</span><span class="sxs-lookup"><span data-stu-id="a37a8-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="a37a8-136">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="a37a8-136">**Refresh**</span></span>  
     <span data-ttu-id="a37a8-137">Aktualisieren Sie die Anzeige der ausgewählten Protokolle.</span><span class="sxs-lookup"><span data-stu-id="a37a8-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="a37a8-138">Beim Übernehmen von Filtereinstellungen werden mithilfe der Schaltfläche **Aktualisieren** die ausgewählten Protokolle erneut vom Zielserver gelesen.</span><span class="sxs-lookup"><span data-stu-id="a37a8-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="a37a8-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="a37a8-139">**Filter**</span></span>  
     <span data-ttu-id="a37a8-140">Öffnen Sie ein Dialogfeld, in dem Sie zum Filtern der Protokolldatei verwendete Einstellungen angeben können, z.B. Filterkriterien wie **Verbindung**, **Datum**oder **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="a37a8-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="a37a8-141">**Suchen,**</span><span class="sxs-lookup"><span data-stu-id="a37a8-141">**Search**</span></span>  
     <span data-ttu-id="a37a8-142">Durchsuchen Sie die Protokolldatei nach bestimmtem Text.</span><span class="sxs-lookup"><span data-stu-id="a37a8-142">Search the log file for specific text.</span></span> <span data-ttu-id="a37a8-143">Das Suchen mit Platzhalterzeichen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a37a8-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="a37a8-144">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="a37a8-144">**Stop**</span></span>  
     <span data-ttu-id="a37a8-145">Beendet das Laden der Protokolldateieinträge.</span><span class="sxs-lookup"><span data-stu-id="a37a8-145">Stops loading the log file entries.</span></span> <span data-ttu-id="a37a8-146">Diese Option können Sie z. B. verwenden, wenn das Laden einer Remote- oder Offline-Protokolldatei eine lange Zeit in Anspruch nimmt und Sie nur die zuletzt erstellten Einträge anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a37a8-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="a37a8-147">**Protokolldateizusammenfassung**</span><span class="sxs-lookup"><span data-stu-id="a37a8-147">**Log file summary**</span></span>  
     <span data-ttu-id="a37a8-148">In diesem Informationsbereich wird eine Zusammenfassung der Protokolldateifilterung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a37a8-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="a37a8-149">Wenn die Datei nicht gefiltert wurde, wird folgender Text angezeigt: **Kein Filter angewendet**.</span><span class="sxs-lookup"><span data-stu-id="a37a8-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="a37a8-150">Nach Anwendung eines Filters auf das Protokoll wird folgender Text angezeigt: **Filter log entries where:** \<filter criteria> (Protokolleinträge nach folgenden Kriterien filtern:).</span><span class="sxs-lookup"><span data-stu-id="a37a8-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="a37a8-151">**Details für die ausgewählte Zeile**</span><span class="sxs-lookup"><span data-stu-id="a37a8-151">**Selected row details**</span></span>  
     <span data-ttu-id="a37a8-152">Wählen Sie eine Zahl aus, um am unteren Rand der Seite zusätzliche Details zu der ausgewählten Ereigniszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a37a8-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="a37a8-153">Die Spalten können durch Ziehen an neue Positionen im Raster neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a37a8-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="a37a8-154">Die Breite der Spalten kann durch Ziehen der Spaltentrennbalken in der Kopfzeile des Rasters nach links oder rechts geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a37a8-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="a37a8-155">Wenn Sie auf die Spaltentrennbalken in der Kopfzeile des Rasters doppelklicken, wird die Breite der Spalte automatisch an die Breite des Inhalts angepasst.</span><span class="sxs-lookup"><span data-stu-id="a37a8-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="a37a8-156">**Instanz**</span><span class="sxs-lookup"><span data-stu-id="a37a8-156">**Instance**</span></span>  
     <span data-ttu-id="a37a8-157">Der Name der Instanz, bei der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a37a8-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="a37a8-158">Dieser wird im Format *Computername*\\*Instanzname*.</span><span class="sxs-lookup"><span data-stu-id="a37a8-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="a37a8-159">**Date**</span><span class="sxs-lookup"><span data-stu-id="a37a8-159">**Date**</span></span>  
     <span data-ttu-id="a37a8-160">Zeigt das Datum des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="a37a8-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="a37a8-161">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="a37a8-161">**Source**</span></span>  
     <span data-ttu-id="a37a8-162">Zeigt die Ausgangsfunktion an, mit dem das Ereignis erstellt wurde, z. B. den Namen des Diensts (z. B. MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="a37a8-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="a37a8-163">Dies wird nicht für alle Protokolltypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a37a8-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="a37a8-164">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="a37a8-164">**Message**</span></span>  
     <span data-ttu-id="a37a8-165">Zeigt die Meldungen an, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a37a8-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="a37a8-166">**Protokolltyp**</span><span class="sxs-lookup"><span data-stu-id="a37a8-166">**Log Type**</span></span>  
     <span data-ttu-id="a37a8-167">Zeigt den Typ des Protokolls an, zu dem das Ereignis gehört.</span><span class="sxs-lookup"><span data-stu-id="a37a8-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="a37a8-168">Alle ausgewählten Protokolle werden im Fenster für die Protokolldateizusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a37a8-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="a37a8-169">**Protokollquelle**</span><span class="sxs-lookup"><span data-stu-id="a37a8-169">**Log Source**</span></span>  
     <span data-ttu-id="a37a8-170">Zeigt eine Beschreibung des Quellprotokolls an, in dem das Ereignis aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a37a8-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="a37a8-171">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a37a8-171">When finished, click **Close**.</span></span>  
  
  
