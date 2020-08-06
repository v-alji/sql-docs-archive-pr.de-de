---
title: Verwenden von Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726437"
---
# <a name="using-reports"></a><span data-ttu-id="bdbca-102">Verwenden von Berichten</span><span class="sxs-lookup"><span data-stu-id="bdbca-102">Using Reports</span></span>
  <span data-ttu-id="bdbca-103">Für jede Komponente wird ein separater Bericht generiert und bei Bedarf für jede Instanz, die der Analyse-Assistent des Upgrade Advisors auf einem Server analysiert.</span><span class="sxs-lookup"><span data-stu-id="bdbca-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="bdbca-104">Der Bericht enthält Details über bekannte Probleme, die eine Aktualisierung beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="bdbca-105">Er enthält zudem Links zu Informationen und Maßnahmenvorschlägen zur Behebung der identifizierten Probleme.</span><span class="sxs-lookup"><span data-stu-id="bdbca-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdbca-106">Wenn der Berichts-Viewer des Upgrade Advisors keine Berichte im Standardverzeichnis für Berichte findet, können Sie einen Bericht mithilfe des Links **Bericht öffnen** aus einem anderen Verzeichnis laden.</span><span class="sxs-lookup"><span data-stu-id="bdbca-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="bdbca-107">Anzeigen von Berichten</span><span class="sxs-lookup"><span data-stu-id="bdbca-107">Viewing Reports</span></span>  
 <span data-ttu-id="bdbca-108">Mit dem Berichts-Viewer des Upgrade Advisors zeigen Sie Berichte des Upgrade Advisors an.</span><span class="sxs-lookup"><span data-stu-id="bdbca-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="bdbca-109">Klicken Sie zum Anzeigen von Berichten auf der Startseite des Upgrade Advisors auf Berichts-Viewer des Upgrade **Advisors starten**.</span><span class="sxs-lookup"><span data-stu-id="bdbca-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="bdbca-110">Nachdem Sie einen Bericht für einen Server geladen haben, können Sie eine Komponente wählen, deren Updateprobleme Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="bdbca-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="bdbca-111">Sie können einen Filter aus dem Feld **Filtern nach** anwenden, um Folgendes anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bdbca-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="bdbca-112">Alle Probleme</span><span class="sxs-lookup"><span data-stu-id="bdbca-112">All issues</span></span>  
  
-   <span data-ttu-id="bdbca-113">Alle Ugradeprobleme</span><span class="sxs-lookup"><span data-stu-id="bdbca-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="bdbca-114">Probleme vor dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="bdbca-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="bdbca-115">Alle Migrationsprobleme</span><span class="sxs-lookup"><span data-stu-id="bdbca-115">All migration issues</span></span>  
  
-   <span data-ttu-id="bdbca-116">Behobene Probleme</span><span class="sxs-lookup"><span data-stu-id="bdbca-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="bdbca-117">Ungelöste Probleme</span><span class="sxs-lookup"><span data-stu-id="bdbca-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="bdbca-118">Wenn für den Bericht mehr als 20 Probleme vorliegen, können Sie zur nächsten oder vorherigen Gruppe von Problemen wechseln, indem Sie oben oder unten in der Liste Probleme auf **weiter 20** oder **vorherige 20** klicken.</span><span class="sxs-lookup"><span data-stu-id="bdbca-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="bdbca-119">Sie können bis zu fünf gespeicherte Berichte anzeigen, indem Sie im Dropdown-Listenfeld **Bericht** die Berichte auswählen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="bdbca-120">Die Berichte werden nach dem Zeitstempel für ihren Generierungszeitpunkt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bdbca-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="bdbca-121">Berichtformat</span><span class="sxs-lookup"><span data-stu-id="bdbca-121">Report Format</span></span>  
 <span data-ttu-id="bdbca-122">Der Berichts-Viewer zeigt Berichtsprobleme in drei Spalten an.</span><span class="sxs-lookup"><span data-stu-id="bdbca-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="bdbca-123">Jedes Problem ist reduzierbar, damit Sie die Beschreibung ausblenden können, um nur die Schlüsselinformationen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="bdbca-124">Die erste Spalte ist die Spalte **Wichtigkeit** .</span><span class="sxs-lookup"><span data-stu-id="bdbca-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="bdbca-125">Symbole geben die Wichtigkeit jedes Problems an: Ein roter Kreis mit einem X steht für blockierende oder wichtige Probleme und ein gelbes Dreieck mit einem Ausrufungszeichen für Warnungen oder Informationen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="bdbca-126">Die zweite Spalte gibt **an**, wann das Problem behoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="bdbca-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="bdbca-127">Sie können den Bericht entweder nach der **Wichtigkeit** oder **nach dem Zeitpunkt der Korrektur** der Spalte sortieren.</span><span class="sxs-lookup"><span data-stu-id="bdbca-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="bdbca-128">In der dritten Spalte, **Beschreibung**, wird der Titel des Problems aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bdbca-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="bdbca-129">Sie können die Anzeige eines Problems erweitern, um zusätzliche Informationen, einen Link zu detaillierten Informationen über Abhilfe und einen Link zu Problemdetails einzublenden.</span><span class="sxs-lookup"><span data-stu-id="bdbca-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="bdbca-130">Wenn Sie den Link anklicken, um detaillierte Informationen über das Problem zu erhalten, wird ein Hilfethema mit Informationen darüber und Anweisungen zur Behebung des Problems angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdbca-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="bdbca-131">Nachdem Sie ein Problem behoben oder die Aktions Elemente verwaltet haben, können Sie die Probleme als abgeschlossen markieren, indem Sie das Kontrollkästchen **dieses Problem wurde gelöst** auswählen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="bdbca-132">Wenn Sie die aufgelösten Probleme aus der Liste der Upgradeprobleme entfernen möchten, klicken Sie auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="bdbca-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="bdbca-133">Das Problem wird erst wieder angezeigt, wenn Sie den Analyse-Assistenten des Upgrade Advisors für dieselbe Komponente ausführen oder den Filter für **aufgelöste Probleme** aus der Option **Filtern nach** anwenden.</span><span class="sxs-lookup"><span data-stu-id="bdbca-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="bdbca-134">Berichtsdateien</span><span class="sxs-lookup"><span data-stu-id="bdbca-134">Report Files</span></span>  
 <span data-ttu-id="bdbca-135">Der Analyse-Assistent des Upgrade Advisors erstellt Berichte im Verzeichnis My Documents \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade advisor\110\reports und erstellt ein Unterverzeichnis für jeden Server, den Sie analysieren.</span><span class="sxs-lookup"><span data-stu-id="bdbca-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="bdbca-136">Die Berichtdateien sind XML-Dateien, die einer bestimmten Benennungskonvention entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bdbca-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="bdbca-137">Wenn Sie den Berichts-Viewer des Upgrade Advisors starten, werden die Berichtsdateien im Standardverzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdbca-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="bdbca-138">Wenn Sie Berichtsdateien in diesen Ordner kopieren, müssen sie der Benennungskonvention entsprechen, da der Berichts-Viewer sie sonst nicht automatisch anzeigt.</span><span class="sxs-lookup"><span data-stu-id="bdbca-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="bdbca-139">Wenn Sie die Informationen an andere Personen weitergeben möchten, können Sie ihnen den XML-Bericht senden.</span><span class="sxs-lookup"><span data-stu-id="bdbca-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="bdbca-140">Wenn Sie eine andere Anwendung verwenden möchten, können Sie den Bericht alternativ in eine Datei im CSV-Format exportieren, anhand derer Sie eine Kalkulationstabelle, eine Textdatei oder eine E-Mail-Nachricht erstellen können.</span><span class="sxs-lookup"><span data-stu-id="bdbca-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbca-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdbca-141">See Also</span></span>  
 <span data-ttu-id="bdbca-142">[Vorgehensweise: Anzeigen eines Berichts des Upgrade Advisors](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="bdbca-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="bdbca-143">[Vorgehensweise: Exportieren von Berichten](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="bdbca-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="bdbca-144">[Vorgehensweise: Filtern von Berichten](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="bdbca-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="bdbca-145">[Beheben von Upgradeproblemen](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="bdbca-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="bdbca-146">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="bdbca-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
