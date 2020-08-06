---
title: Berichte für den Integration Services Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SUMMARY.RENDER.CUSTOM.REPORT.F1
ms.assetid: e976e7c0-a805-4370-bf73-356c8e3becfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3e9510671a290c20edce94baf88200faa0c549
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696949"
---
# <a name="reports-for-the-integration-services-server"></a><span data-ttu-id="6e389-102">Berichte für den Integration Services-Server</span><span class="sxs-lookup"><span data-stu-id="6e389-102">Reports for the Integration Services Server</span></span>
  <span data-ttu-id="6e389-103">In der aktuellen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]sind Standardberichte in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] verfügbar, die zum Überwachen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekten hilfreich sind, die auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-103">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to help you monitor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="6e389-104">Mit diesen Berichten können Sie den Paketstatus und -verlauf anzeigen und ggf. die Ursache von Paketausführungsfehlern identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6e389-104">These reports help you to view package status and history, and, if necessary, identify the cause of package execution failures.</span></span>  
  
 <span data-ttu-id="6e389-105">Im oberen Bereich jeder Berichtsseite werden die folgenden Symbole bereitgestellt: Zurück-Symbol (um zur vorherigen Seite zurückzukehren), Aktualisierungssymbol (um die auf der Seite angezeigten Informationen zu aktualisieren) und Druckersymbol (um die aktuelle Seite zu drucken).</span><span class="sxs-lookup"><span data-stu-id="6e389-105">At the top of each report page, the back icon takes you to the previous page you viewed, the refresh icon refreshes the information displayed on the page, and the print icon allows you to print the current page.</span></span>  
  
 <span data-ttu-id="6e389-106">Weitere Informationen zum Bereitstellen von Paketen auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server, finden Sie unter [Bereitstellen von Projekten auf dem Integration Services-Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="6e389-106">For information on how to deploy packages to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="integration-services-dashboard"></a><span data-ttu-id="6e389-107">Integration Services-Dashboard</span><span class="sxs-lookup"><span data-stu-id="6e389-107">Integration Services Dashboard</span></span>  
 <span data-ttu-id="6e389-108">Der Bericht **Integration Services-Dashboard** bietet eine Übersicht über alle Paketausführungen für die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="6e389-108">The **Integration Services Dashboard** report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="6e389-109">Im Dashboard können Sie die Informationen zu jedem auf dem Server ausgeführten Paket erweitern, um spezifische Details über möglicherweise aufgetretene Paketausführungsfehler zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6e389-109">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span>  
  
 <span data-ttu-id="6e389-110">Der Bericht zeigt die folgenden Abschnitte von Informationen an.</span><span class="sxs-lookup"><span data-stu-id="6e389-110">The report displays the following sections of information.</span></span>  
  
|<span data-ttu-id="6e389-111">`Section`</span><span class="sxs-lookup"><span data-stu-id="6e389-111">Section</span></span>|<span data-ttu-id="6e389-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e389-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e389-113">**Ausführungsinformationen**</span><span class="sxs-lookup"><span data-stu-id="6e389-113">**Execution Information**</span></span>|<span data-ttu-id="6e389-114">Zeigt die Anzahl von Ausführungen an, die in den vergangenen 24 Stunden unterschiedliche Status (fehlerhaft, ausgeführt, erfolgreich, andere) aufgewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="6e389-114">Shows the number of executions that are in different states (failed, running, succeeded, others) in the past 24 hours.</span></span>|  
|<span data-ttu-id="6e389-115">**Paketinformationen**</span><span class="sxs-lookup"><span data-stu-id="6e389-115">**Package Information**</span></span>|<span data-ttu-id="6e389-116">Zeigt die Gesamtanzahl der Pakete, die in den letzten 24 Stunden ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-116">Shows the total number of packages that have been executed in the past 24 hours.</span></span>|  
|<span data-ttu-id="6e389-117">**Verbindungsinformationen**</span><span class="sxs-lookup"><span data-stu-id="6e389-117">**Connection Information**</span></span>|<span data-ttu-id="6e389-118">Zeigt die Verbindungen, die in den letzten 24 Stunden in fehlerhaften Ausführungen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-118">Shows the connections that have been used in failed executions in the past 24 hours.</span></span>|  
|<span data-ttu-id="6e389-119">**Detaillierte Paketinformationen**</span><span class="sxs-lookup"><span data-stu-id="6e389-119">**Package Detailed Information**</span></span>|<span data-ttu-id="6e389-120">Zeigt die Details der abgeschlossenen Ausführungen an, die in den letzten 24 Stunden durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-120">Shows the details of the completed executions that have occurred in the past 24 hours.</span></span> <span data-ttu-id="6e389-121">Dieser Abschnitt zeigt z. B. die Anzahl der fehlerhaften Ausführungen im Vergleich zur Gesamtzahl der Ausführungen, die Dauer der Ausführungen (in Sekunden) und die durchschnittliche Dauer der Ausführungen in den vergangenen drei Monaten an.</span><span class="sxs-lookup"><span data-stu-id="6e389-121">For example, this section shows the number of failed executions versus the total number of executions, the duration of an executions (in seconds), and the average duration of executions for over the past three months.</span></span><br /><br /> <span data-ttu-id="6e389-122">Sie können weitere Informationen für ein Paket anzeigen, indem Sie auf **Übersicht**, **Alle Meldungen**und **Ausführungsleistung**klicken.</span><span class="sxs-lookup"><span data-stu-id="6e389-122">You can view additional information for a package by clicking **Overview**, **All Messages**, and **Execution Performance**.</span></span><br /><br /> <span data-ttu-id="6e389-123">Der Bericht **Ausführungsleistung** zeigt die Dauer der letzten Ausführungsinstanz sowie die Start- und Endzeiten und die Umgebung an, die angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6e389-123">The **Execution Performance** report shows the duration of the last execution instance, as well as the start and end times, and the environment that was applied.</span></span><br /><br /> <span data-ttu-id="6e389-124">Das Diagramm und die zugeordnete Tabelle im Bericht **Ausführungsleistung** zeigen die Dauer der letzten 10 erfolgreichen Ausführungen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="6e389-124">The chart and associated table included in the **Execution Performance** report shows the duration of the past 10 successful executions of the package.</span></span> <span data-ttu-id="6e389-125">In der Tabelle wird auch die durchschnittliche Ausführungsdauer in einem Zeitraum von drei Monaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e389-125">The table also shows the average execution duration over a three-month period.</span></span> <span data-ttu-id="6e389-126">Unterschiedliche Umgebungen und Literalwerte wurden möglicherweise zur Laufzeit für diese 10 erfolgreichen Ausführungen des Pakets angewendet.</span><span class="sxs-lookup"><span data-stu-id="6e389-126">Different environments and different literal values may have been applied at runtime for these 10 successful executions of the package.</span></span><br /><br /> <span data-ttu-id="6e389-127">Schließlich wird im Bericht **Ausführungsleistung** die aktive Zeit und die Gesamtzeit für die Datenflusskomponenten des Pakets angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e389-127">Finally, the **Execution Performance** report shows the Active Time and Total Time for the package data flow components.</span></span> <span data-ttu-id="6e389-128">Die aktive Zeit bezieht sich auf die gesamte Zeit, die für die Ausführung der Komponente in allen Phasen benötigt wurde, und die Gesamtzeit bezieht sich auf die insgesamt verstrichene Zeit für eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="6e389-128">The Active Time refers to the total amount of time that component has spent executing in all phases, and the Total Time refers to the total time elapsed for a component.</span></span> <span data-ttu-id="6e389-129">Der Bericht zeigt nur diese Informationen für Paketkomponenten an, wenn der Protokolliergrad der letzten Paketausführung auf "Leistung" oder "Ausführlich" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6e389-129">The report only displays this information for package components when the logging level of the last package execution was set to Performance or Verbose.</span></span><br /><br /> <span data-ttu-id="6e389-130">Der Bericht **Übersicht** zeigt den Status von Pakettasks an.</span><span class="sxs-lookup"><span data-stu-id="6e389-130">The **Overview** report shows the state of package tasks.</span></span> <span data-ttu-id="6e389-131">Der Bericht **Meldungen** zeigt die Ereignismeldungen und die Fehlermeldungen für das Paket und die Tasks an, beispielsweise das Melden der Start- und Endzeiten sowie die Anzahl der geschriebenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="6e389-131">The **Messages** report shows the event messages and error messages for the package and tasks, such as reporting the start and end times, and the number of rows written.</span></span><br /><br /> <span data-ttu-id="6e389-132">Sie können auch im Bericht **Übersicht** auf **Meldungen anzeigen** klicken, um zum Bericht **Meldungen** zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="6e389-132">You can also click **View Messages** in the **Overview** report to navigate to the **Messages** report.</span></span> <span data-ttu-id="6e389-133">Sie können auch im Bericht **Meldungen** auf **Übersicht anzeigen** klicken, um zum Bericht **Übersicht** zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="6e389-133">You can also click **View Overview** in the **Messages** report to navigate to the **Overview** report.</span></span>|  
  
 <span data-ttu-id="6e389-134">Sie können die auf einer beliebigen Seite angezeigte Tabelle filtern, indem Sie auf **Filtern** klicken und dann im Dialogfeld **Filtereinstellungen** die gewünschten Kriterien auswählen.</span><span class="sxs-lookup"><span data-stu-id="6e389-134">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="6e389-135">Abhängig von den angezeigten Daten sind unterschiedliche Filterkriterien verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e389-135">The filter criteria that are available depend on the data being displayed.</span></span> <span data-ttu-id="6e389-136">Sie können die Sortierreihenfolge des Berichts ändern, indem Sie im Dialogfeld **Filtereinstellungen** auf das Sortiersymbol klicken.</span><span class="sxs-lookup"><span data-stu-id="6e389-136">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
## <a name="all-executions-report"></a><span data-ttu-id="6e389-137">Bericht "Alle Ausführungen"</span><span class="sxs-lookup"><span data-stu-id="6e389-137">All Executions Report</span></span>  
 <span data-ttu-id="6e389-138">Der Bericht **Alle Ausführungen** zeigt eine Zusammenfassung aller [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Ausführungen, die auf dem Server ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-138">The **All Executions Report** displays a summary of all [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="6e389-139">Es kann mehrere Ausführungen des Beispielpakets geben.</span><span class="sxs-lookup"><span data-stu-id="6e389-139">There can be multiple executions of the sample package.</span></span> <span data-ttu-id="6e389-140">Im Gegensatz zum Bericht **Integration Services-Dashboard** können Sie den Bericht **Alle Ausführungen** so konfigurieren, dass Ausführungen angezeigt werden, die während eines Datumsbereichs gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-140">Unlike the **Integration Services Dashboard** report, you can configure the **All Executions** report to show executions that have started during a range of dates.</span></span> <span data-ttu-id="6e389-141">Die Datumsangaben können mehrere Tage, Monate oder Jahre umfassen.</span><span class="sxs-lookup"><span data-stu-id="6e389-141">The dates can span multiple days, months, or years.</span></span>  
  
 <span data-ttu-id="6e389-142">Der Bericht zeigt die folgenden Abschnitte von Informationen an.</span><span class="sxs-lookup"><span data-stu-id="6e389-142">The report displays the following sections of information.</span></span>  
  
|<span data-ttu-id="6e389-143">`Section`</span><span class="sxs-lookup"><span data-stu-id="6e389-143">Section</span></span>|<span data-ttu-id="6e389-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e389-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e389-145">Filtern</span><span class="sxs-lookup"><span data-stu-id="6e389-145">Filter</span></span>|<span data-ttu-id="6e389-146">Zeigt den aktuellen Filter an, der für den Bericht verwendet wird, z. B. der Startzeitraum.</span><span class="sxs-lookup"><span data-stu-id="6e389-146">Shows the current filter applied to the report, such as the Start time range.</span></span>|  
|<span data-ttu-id="6e389-147">Ausführungsinformationen</span><span class="sxs-lookup"><span data-stu-id="6e389-147">Execution Information</span></span>|<span data-ttu-id="6e389-148">Zeigt die Startzeit, die Endzeit und die Dauer für jede Paketausführung an. Sie können eine Liste der Parameterwerte anzeigen, die bei einer Paketausführung verwendet wurden, z. B. Werte, die mit dem Task "Paket ausführen" an ein untergeordnetes Paket übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-148">Shows the start time, end time, and duration for each package execution.You can view a list of the parameter values that were used with a package execution, such as values that were passed to a child package using the Execute Package task.</span></span> <span data-ttu-id="6e389-149">Um die Parameterliste anzuzeigen, klicken Sie auf "Übersicht".</span><span class="sxs-lookup"><span data-stu-id="6e389-149">To view the parameter list, click Overview.</span></span>|  
  
 <span data-ttu-id="6e389-150">Weitere Informationen über das Verwenden des Tasks "Paket ausführen" zum Verfügbarmachen von Werten für untergeordnete Pakete finden Sie unter [Execute Package Task](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="6e389-150">For more information about using the Execute Package task to make values available to a child package, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="6e389-151">Weitere Informationen zu Parametern finden Sie unter [Integration Services-Parameter &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6e389-151">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="all-connections"></a><span data-ttu-id="6e389-152">Alle Verbindungen</span><span class="sxs-lookup"><span data-stu-id="6e389-152">All Connections</span></span>  
 <span data-ttu-id="6e389-153">Der Bericht **Alle Verbindungen** enthält die folgenden Informationen für Verbindungen, die nicht hergestellt werden konnten, und für Ausführungen, die in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="6e389-153">The **All Connections** report provides the following information for connections that have failed, for executions that have occurred on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="6e389-154">Der Bericht zeigt die folgenden Abschnitte von Informationen an.</span><span class="sxs-lookup"><span data-stu-id="6e389-154">The report displays the following sections of information.</span></span>  
  
|<span data-ttu-id="6e389-155">`Section`</span><span class="sxs-lookup"><span data-stu-id="6e389-155">Section</span></span>|<span data-ttu-id="6e389-156">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e389-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e389-157">Filtern</span><span class="sxs-lookup"><span data-stu-id="6e389-157">Filter</span></span>|<span data-ttu-id="6e389-158">Zeigt den aktuellen Filter an, der für den Bericht verwendet wird, z. B. Verbindungen mit einer angegebenen Zeichenfolge und dem Bereich **Uhrzeit des letzten Fehlers** .</span><span class="sxs-lookup"><span data-stu-id="6e389-158">Shows the current filter applied to the report, such as connections with a specified string and the **Last failed time** range.</span></span><br /><br /> <span data-ttu-id="6e389-159">Sie legen den Bereich **Uhrzeit des letzten Fehlers** fest, um lediglich Verbindungsfehler anzuzeigen, die während eines Datumsbereichs aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="6e389-159">You set the **Last failed time** range to display only connection failures that occurred during a range of dates.</span></span> <span data-ttu-id="6e389-160">Der Bereich kann mehrere Tage, Monate oder Jahre umfassen.</span><span class="sxs-lookup"><span data-stu-id="6e389-160">The range can span multiple days, months, or years.</span></span>|  
|<span data-ttu-id="6e389-161">Details</span><span class="sxs-lookup"><span data-stu-id="6e389-161">Details</span></span>|<span data-ttu-id="6e389-162">Zeigt die Verbindungszeichenfolge, die Anzahl der Ausführungen, bei denen eine Verbindung nicht hergestellt werden konnte, und das Datum an, wann die Verbindung zuletzt nicht hergestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="6e389-162">Shows the connection string, number of executions during which a connection failed, and the date when the connection last failed.</span></span>|  
  
## <a name="all-operations-report"></a><span data-ttu-id="6e389-163">Bericht "Alle Vorgänge"</span><span class="sxs-lookup"><span data-stu-id="6e389-163">All Operations Report</span></span>  
 <span data-ttu-id="6e389-164">Der Bericht **Alle Vorgänge** zeigt eine Zusammenfassung aller [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Vorgänge an, die auf dem Server ausgeführt wurden, einschließlich Paketbereitstellung, Validierung und Ausführung sowie anderer administrativer Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="6e389-164">The **All Operations Report** displays a summary of all [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations that have been performed on the server, including package deployment, validation, and execution, as well as other administrative operations.</span></span> <span data-ttu-id="6e389-165">Wie in dem Integration Services-Dashboard können Sie einen Filter auf die Tabelle anwenden, um die angezeigten Informationen einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="6e389-165">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="all-validations-report"></a><span data-ttu-id="6e389-166">Bericht "Alle Überprüfungen"</span><span class="sxs-lookup"><span data-stu-id="6e389-166">All Validations Report</span></span>  
 <span data-ttu-id="6e389-167">Der Bericht **Alle Überprüfungen** zeigt eine Zusammenfassung aller [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Überprüfungen, die auf dem Server ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-167">The **All Validations Report** displays a summary of all [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] validations that have been performed on the server.</span></span> <span data-ttu-id="6e389-168">Die Zusammenfassung enthält Informationen für jede Überprüfungen, z. B. Status, Startzeit und Endzeit.</span><span class="sxs-lookup"><span data-stu-id="6e389-168">The summary displays information for each validation such as status, start time, and end time.</span></span> <span data-ttu-id="6e389-169">Jeder Zusammenfassungseintrag enthält einen Link zu den Meldungen, die während der Überprüfungen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6e389-169">Each summary entry includes a link to messages generated during validation.</span></span> <span data-ttu-id="6e389-170">Wie in dem Integration Services-Dashboard können Sie einen Filter auf die Tabelle anwenden, um die angezeigten Informationen einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="6e389-170">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="custom-reports"></a><span data-ttu-id="6e389-171">Benutzerdefinierte Berichte</span><span class="sxs-lookup"><span data-stu-id="6e389-171">Custom Reports</span></span>  
 <span data-ttu-id="6e389-172">Sie können dem **SSISDB** -Katalogknoten unter dem Knoten **Integration Services-Kataloge** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]einen benutzerdefinierten Bericht (RDL-Datei) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e389-172">You can add a custom report (.rdl file) to the **SSISDB** catalog node under the **Integration Services Catalogs** node in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6e389-173">Stellen Sie vor dem Hinzufügen des Berichts sicher, dass Sie eine Konvention für dreiteilige Namen verwenden, um die Objekte, auf die Sie verweisen, z. B. eine Quelltabelle, vollständig zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="6e389-173">Before adding the report, confirm that you are using a three-part naming convention to fully qualify the objects you reference such as a source table.</span></span> <span data-ttu-id="6e389-174">Andernfalls meldet [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6e389-174">Otherwise, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] will display an error.</span></span> <span data-ttu-id="6e389-175">Die Benennungskonvention ist \<database>.\<owner>.\<object>. Ein Beispiel wäre SSISDB.internal.executions.</span><span class="sxs-lookup"><span data-stu-id="6e389-175">The naming convention is \<database>.\<owner>.\<object>. An example would be SSISDB.internal.executions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e389-176">Wenn Sie dem **SSISDB** -Knoten unter dem Knoten **Datenbanken** benutzerdefinierte Berichte hinzufügen, ist das SSISDB-Präfix nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e389-176">When you add custom reports to the **SSISDB** node under the **Databases** node, the SSISDB prefix is not necessary.</span></span>  
  
 <span data-ttu-id="6e389-177">Anweisungen zum Erstellen und Hinzufügen eines benutzerdefinierten Berichts finden Sie unter [Add a Custom Report to Management Studio](../ssms/object/add-a-custom-report-to-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6e389-177">For instructions on how to create and add a custom report, see [Add a Custom Report to Management Studio](../ssms/object/add-a-custom-report-to-management-studio.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6e389-178">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6e389-178">Related Tasks</span></span>  
 [<span data-ttu-id="6e389-179">Anzeigen von Berichten für den Integration Services-Server</span><span class="sxs-lookup"><span data-stu-id="6e389-179">View Reports for the Integration Services Server</span></span>](../../2014/integration-services/view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="6e389-180">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6e389-180">Related Content</span></span>  
 [<span data-ttu-id="6e389-181">Überwachen von Paketausführungen und anderen Vorgängen</span><span class="sxs-lookup"><span data-stu-id="6e389-181">Monitoring for Package Executions and Other Operations</span></span>](performance/monitor-running-packages-and-other-operations.md)  
  
  