---
title: Protokolldatei-Viewer (F1-Hilfe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616540"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="ccb07-102">Protokolldatei-Viewer (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="ccb07-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="ccb07-103">Im Protokolldatei-Viewer können Protokollinformationen aus einer Vielzahl von Komponenten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ccb07-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="ccb07-104">Wählen Sie im geöffneten Protokolldatei-Viewer im Bereich **Protokolle auswählen** die Protokolle aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ccb07-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="ccb07-105">In jedem Protokoll werden dem Protokolltyp entsprechende Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccb07-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="ccb07-106">Welche Protokolle verfügbar sind, ist davon abhängig, wie der Protokolldatei-Viewer geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="ccb07-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="ccb07-107">Weitere Informationen finden Sie unter [Öffnen des Protokolldatei-Viewers](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="ccb07-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="ccb07-108">Die Anzahl der angezeigten Zeilen für Überwachungsprotokolle kann auf der Seite **SQL Server Objekt-Explorer/Befehle** im Dialogfeld **Extras/Optionen** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ccb07-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="ccb07-109">Beschreibungen der Spalten, die für Überwachungsprotokolle angezeigt werden, finden Sie unter [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccb07-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ccb07-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ccb07-110">Options</span></span>  
 <span data-ttu-id="ccb07-111">**Protokoll laden**</span><span class="sxs-lookup"><span data-stu-id="ccb07-111">**Load Log**</span></span>  
 <span data-ttu-id="ccb07-112">Öffnen Sie ein Dialogfeld, in dem Sie eine zu ladende Protokolldatei angeben können.</span><span class="sxs-lookup"><span data-stu-id="ccb07-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="ccb07-113">**Export**</span><span class="sxs-lookup"><span data-stu-id="ccb07-113">**Export**</span></span>  
 <span data-ttu-id="ccb07-114">Öffnen Sie ein Dialogfeld, in dem Sie die im Raster **Protokolldateizusammenfassung** angezeigten Informationen in eine Textdatei exportieren können.</span><span class="sxs-lookup"><span data-stu-id="ccb07-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="ccb07-115">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="ccb07-115">**Refresh**</span></span>  
 <span data-ttu-id="ccb07-116">Aktualisieren Sie die Anzeige der ausgewählten Protokolle.</span><span class="sxs-lookup"><span data-stu-id="ccb07-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="ccb07-117">Beim Übernehmen von Filtereinstellungen werden mithilfe der Schaltfläche **Aktualisieren** die ausgewählten Protokolle erneut vom Zielserver gelesen.</span><span class="sxs-lookup"><span data-stu-id="ccb07-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="ccb07-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="ccb07-118">**Filter**</span></span>  
 <span data-ttu-id="ccb07-119">Öffnen Sie ein Dialogfeld, in dem Sie zum Filtern der Protokolldatei verwendete Einstellungen angeben können, z.B. Filterkriterien wie **Verbindung**, **Datum**oder **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="ccb07-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="ccb07-120">**Suchen,**</span><span class="sxs-lookup"><span data-stu-id="ccb07-120">**Search**</span></span>  
 <span data-ttu-id="ccb07-121">Durchsuchen Sie die Protokolldatei nach bestimmtem Text.</span><span class="sxs-lookup"><span data-stu-id="ccb07-121">Search the log file for specific text.</span></span> <span data-ttu-id="ccb07-122">Das Suchen mit Platzhalterzeichen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ccb07-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="ccb07-123">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="ccb07-123">**Stop**</span></span>  
 <span data-ttu-id="ccb07-124">Beendet das Laden der Protokolldateieinträge.</span><span class="sxs-lookup"><span data-stu-id="ccb07-124">Stops loading the log file entries.</span></span> <span data-ttu-id="ccb07-125">Diese Option können Sie z. B. verwenden, wenn das Laden einer Remote- oder Offline-Protokolldatei eine lange Zeit in Anspruch nimmt und Sie nur die zuletzt erstellten Einträge anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ccb07-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="ccb07-126">**Protokolldateizusammenfassung**</span><span class="sxs-lookup"><span data-stu-id="ccb07-126">**Log file summary**</span></span>  
 <span data-ttu-id="ccb07-127">In diesem Informationsbereich wird eine Zusammenfassung der Protokolldateifilterung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccb07-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="ccb07-128">Wenn die Datei nicht gefiltert wurde, wird folgender Text angezeigt: **Kein Filter angewendet**.</span><span class="sxs-lookup"><span data-stu-id="ccb07-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="ccb07-129">Nach Anwendung eines Filters auf das Protokoll wird folgender Text angezeigt: **Filter log entries where:** \<filter criteria> (Protokolleinträge nach folgenden Kriterien filtern:).</span><span class="sxs-lookup"><span data-stu-id="ccb07-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="ccb07-130">**Details für die ausgewählte Zeile**</span><span class="sxs-lookup"><span data-stu-id="ccb07-130">**Selected row details**</span></span>  
 <span data-ttu-id="ccb07-131">Wählen Sie eine Zahl aus, um am unteren Rand der Seite zusätzliche Details zu der ausgewählten Ereigniszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccb07-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="ccb07-132">Die Spalten können durch Ziehen an neue Positionen im Raster neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ccb07-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="ccb07-133">Die Breite der Spalten kann durch Ziehen der Spaltentrennbalken in der Kopfzeile des Rasters nach links oder rechts geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ccb07-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="ccb07-134">Wenn Sie auf die Spaltentrennbalken in der Kopfzeile des Rasters doppelklicken, wird die Breite der Spalte automatisch an die Breite des Inhalts angepasst.</span><span class="sxs-lookup"><span data-stu-id="ccb07-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="ccb07-135">**Instanz**</span><span class="sxs-lookup"><span data-stu-id="ccb07-135">**Instance**</span></span>  
 <span data-ttu-id="ccb07-136">Der Name der Instanz, bei der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ccb07-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="ccb07-137">Dieser wird im Format *Computername*\\*Instanzname*.</span><span class="sxs-lookup"><span data-stu-id="ccb07-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="ccb07-138">Häufig angezeigte Spalten</span><span class="sxs-lookup"><span data-stu-id="ccb07-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="ccb07-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="ccb07-139">**Date**</span></span>  
 <span data-ttu-id="ccb07-140">Zeigt das Datum des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="ccb07-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="ccb07-141">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="ccb07-141">**Source**</span></span>  
 <span data-ttu-id="ccb07-142">Zeigt die Ausgangsfunktion an, mit dem das Ereignis erstellt wurde, z. B. den Namen des Diensts (z. B. MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="ccb07-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="ccb07-143">Dies wird nicht für alle Protokolltypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccb07-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="ccb07-144">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="ccb07-144">**Message**</span></span>  
 <span data-ttu-id="ccb07-145">Zeigt die Meldungen an, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ccb07-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="ccb07-146">**Protokolltyp**</span><span class="sxs-lookup"><span data-stu-id="ccb07-146">**Log Type**</span></span>  
 <span data-ttu-id="ccb07-147">Zeigt den Typ des Protokolls an, zu dem das Ereignis gehört.</span><span class="sxs-lookup"><span data-stu-id="ccb07-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="ccb07-148">Alle ausgewählten Protokolle werden im Fenster für die Protokolldateizusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccb07-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="ccb07-149">**Protokollquelle**</span><span class="sxs-lookup"><span data-stu-id="ccb07-149">**Log Source**</span></span>  
 <span data-ttu-id="ccb07-150">Zeigt eine Beschreibung des Quellprotokolls an, in dem das Ereignis aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ccb07-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="ccb07-151">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ccb07-151">Permissions</span></span>  
 <span data-ttu-id="ccb07-152">Zum Zugreifen auf Protokolldateien für Onlineinstanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] müssen Sie Mitglied der festen Serverrolle „securityadmin“ sein.</span><span class="sxs-lookup"><span data-stu-id="ccb07-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="ccb07-153">Zum Zugreifen auf Protokolldateien für Offlineinstanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] müssen Sie über Lesezugriff für den WMI-Namespace **Root\Microsoft\SqlServer\ComputerManagement10** und den Ordner mit den Protokolldateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="ccb07-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="ccb07-154">Weitere Informationen finden Sie im Abschnitt „Sicherheit“ des Themas [Anzeigen von Offlineprotokolldateien](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="ccb07-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb07-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb07-155">See Also</span></span>  
 <span data-ttu-id="ccb07-156">[Protokolldatei-Viewer](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ccb07-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="ccb07-157">[Öffnen des Protokolldatei-Viewers](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ccb07-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="ccb07-158">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="ccb07-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
