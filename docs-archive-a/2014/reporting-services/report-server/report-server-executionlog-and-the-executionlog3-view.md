---
title: Berichts Server-Ausführungs Protokoll und die ExecutionLog3-Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615302"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="bd83e-102">Berichtsserverausführungsprotokoll und die ExecutionLog3-Ansicht</span><span class="sxs-lookup"><span data-stu-id="bd83e-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="bd83e-103">Das Ausführungsprotokoll des Berichtsservers enthält Informationen zu den Berichten, die auf dem Server bzw. auf mehreren Servern in einer Bereitstellung für horizontales Skalieren im einheitlichen Modus oder einer SharePoint-Farm ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="bd83e-104">Anhand des Ausführungsprotokolls des Berichtsservers können Sie feststellen, wie oft ein Bericht angefordert wird, welche Ausgabeformate am meisten verwendet werden und wie viele Millisekunden Verarbeitungszeit für die einzelnen Verarbeitungsphasen aufgewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="bd83e-105">Das Protokoll enthält Informationen über die Zeit, die für die Ausführung der Datasetabfrage eines Berichts aufgewendet wurde, und die Zeit, die für die Verarbeitung der Daten aufgewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bd83e-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="bd83e-106">Wenn Sie Berichtsserveradministrator sind, können Sie die Protokollinformationen überprüfen und Aufgaben mit langer Laufzeit identifizieren sowie den Berichtsautoren zu den Bereichen des Berichts (Dataset oder Verarbeitung) Vorschläge zur Verbesserung machen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="bd83e-107">Für den SharePoint-Modus konfigurierte Berichtsserver können auch die SharePoint-ULS-Protokolle verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="bd83e-108">Weitere Informationen finden Sie unter [Aktivieren von Reporting Services-Ereignissen für das SharePoint-Ablaufverfolgungsprotokoll &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="bd83e-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="bd83e-109">Anzeigen von Protokollinformationen</span><span class="sxs-lookup"><span data-stu-id="bd83e-109">Viewing Log Information</span></span>  
 <span data-ttu-id="bd83e-110">Die Berichtsserverausführung protokolliert Daten zur Berichtsausführung in einer internen Datenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="bd83e-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="bd83e-111">Die Informationen aus der Tabelle sind in SQL Server-Sichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bd83e-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="bd83e-112">Das Berichtsausführungsprotokoll wird in der Berichtsserver-Datenbank gespeichert, die standardmäßig **ReportServer**genannt wird.</span><span class="sxs-lookup"><span data-stu-id="bd83e-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="bd83e-113">Die SQL-Ansichten enthalten die Ausführungsprotokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="bd83e-114">Die Ansichten „2“ und „3“ wurden in aktuelleren Versionen hinzugefügt und enthalten neue Felder, oder sie enthalten Felder mit benutzerfreundlicheren Namen als die vorherigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="bd83e-115">Die älteren Ansichten bleiben im Produkt, sodass es keinerlei Auswirkungen auf benutzerdefinierte Anwendungen, die von ihnen abhängen, gibt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="bd83e-116">Wenn keine Abhängigkeit von einer älteren Sicht vorliegt, z.B. ExecutionLog, wird empfohlen, die neueste Sicht, ExecutionLog**3**, zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="bd83e-117">Inhalte dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="bd83e-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="bd83e-118">Konfigurationseinstellungen für einen Berichtsserver im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="bd83e-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="bd83e-119">Konfigurationseinstellungen für einen Berichtsserver im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="bd83e-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="bd83e-120">Protokollierungsfelder (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="bd83e-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="bd83e-121">Das AdditionalInfo-Feld</span><span class="sxs-lookup"><span data-stu-id="bd83e-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="bd83e-122">Protokollierungsfelder (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="bd83e-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="bd83e-123">Protokollierungsfelder (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="bd83e-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="bd83e-124">Konfigurationseinstellungen für einen Berichtsserver im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="bd83e-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="bd83e-125">Sie können die Berichtsausführungsprotokollierung in den Systemeinstellungen einer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bd83e-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="bd83e-126">Standardmäßig werden Protokolleinträge 60 Tage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd83e-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="bd83e-127">Einträge, die dieses Datum überschreiten, werden um 2.00 Uhr entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="bd83e-128">täglich um 2:00 Uhr entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-128">every day.</span></span> <span data-ttu-id="bd83e-129">Für eine länger vorhandene Installation stehen Informationen jeweils nur 60 Tage lang zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd83e-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="bd83e-130">Sie können keine Beschränkungen für die Anzahl der Zeilen oder die Art der protokollierten Einträge festlegen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="bd83e-131">**So aktivieren Sie die Protokollierung der Ausführung:**</span><span class="sxs-lookup"><span data-stu-id="bd83e-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="bd83e-132">Klicken Sie in der SharePoint-Zentraladministration in der Gruppe **Anwendungsverwaltung** auf **Dienstanwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="bd83e-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="bd83e-133">Klicken Sie auf den Namen der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bd83e-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="bd83e-134">Klicken Sie auf **Systemeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="bd83e-135">Wählen Sie **Protokollierung der Ausführung aktivieren** im Abschnitt **Protokollierung** aus.</span><span class="sxs-lookup"><span data-stu-id="bd83e-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="bd83e-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="bd83e-137">**So aktivieren Sie die ausführliche Protokollierung:**</span><span class="sxs-lookup"><span data-stu-id="bd83e-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="bd83e-138">Sie müssen das Protokollieren wie in den vorherigen Schritten beschrieben aktivieren und anschließend Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="bd83e-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="bd83e-139">Suchen Sie auf der Seite **Systemeinstellungen** Ihrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung den Abschnitt **Benutzerdefiniert** .</span><span class="sxs-lookup"><span data-stu-id="bd83e-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="bd83e-140">Ändern Sie **ExecutionLogLevel** in **Ausführlich**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="bd83e-141">Dieses Feld ist ein Texteingabefeld, und die zwei möglichen Werte sind **Ausführlich** und **Normal**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="bd83e-142">Konfigurationseinstellungen für einen Berichtsserver im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="bd83e-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="bd83e-143">Sie können die Protokollierung der Berichtsausführung auf der Seite "Servereigenschaften" in SQL Server Management Studio aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bd83e-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="bd83e-144">**EnableExecutionLogging** ist eine erweiterte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd83e-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="bd83e-145">Standardmäßig werden Protokolleinträge 60 Tage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd83e-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="bd83e-146">Einträge, die dieses Datum überschreiten, werden um 2.00 Uhr entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="bd83e-147">täglich um 2:00 Uhr entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-147">every day.</span></span> <span data-ttu-id="bd83e-148">Für eine länger vorhandene Installation stehen Informationen jeweils nur 60 Tage lang zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd83e-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="bd83e-149">Sie können keine Beschränkungen für die Anzahl der Zeilen oder die Art der protokollierten Einträge festlegen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="bd83e-150">**So aktivieren Sie die Protokollierung der Ausführung:**</span><span class="sxs-lookup"><span data-stu-id="bd83e-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="bd83e-151">Starten Sie SQL Server Management Studio mit Administratorprivilegien.</span><span class="sxs-lookup"><span data-stu-id="bd83e-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="bd83e-152">Klicken Sie z. B. mit der rechten Maustaste auf das Management Studio-Symbol, und klicken Sie auf „Ausführen als Administrator“.</span><span class="sxs-lookup"><span data-stu-id="bd83e-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="bd83e-153">Stellen Sie eine Verbindung mit dem gewünschten Berichtsserver her.</span><span class="sxs-lookup"><span data-stu-id="bd83e-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="bd83e-154">Klicken Sie mit der rechten Maustaste auf den Servernamen, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="bd83e-155">Wenn die Option "Eigenschaften" deaktiviert ist, überprüfen Sie, dass Sie SQL Server Management Studio mit Administratorprivilegien ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bd83e-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="bd83e-156">Klicken Sie auf die Seite **Protokollierung** .</span><span class="sxs-lookup"><span data-stu-id="bd83e-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="bd83e-157">Wählen Sie **Protokollierung der Berichtsausführung aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="bd83e-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="bd83e-158">**So aktivieren Sie die ausführliche Protokollierung:**</span><span class="sxs-lookup"><span data-stu-id="bd83e-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="bd83e-159">Sie müssen das Protokollieren wie in den vorherigen Schritten beschrieben aktivieren und anschließend Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="bd83e-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="bd83e-160">Klicken Sie im Dialogfeld **Servereigenschaften** auf die Seite **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="bd83e-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="bd83e-161">Ändern Sie im Abschnitt **Benutzerdefiniert** den Wert für **ExecutionLogLevel** in **Ausführlich**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="bd83e-162">Dieses Feld ist ein Texteingabefeld, und die zwei möglichen Werte sind **Ausführlich** und **Normal**.</span><span class="sxs-lookup"><span data-stu-id="bd83e-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="bd83e-163">Protokollierungsfelder (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="bd83e-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="bd83e-164">Dieser Sicht wurde ein zusätzlicher Leitungsdiagnoseknoten in der XML-basierten Spalte **AdditionalInfo** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="bd83e-165">Die Spalte AdditionalInfo enthält eine XML-Struktur von 1:n zusätzlichen Informationsfeldern.</span><span class="sxs-lookup"><span data-stu-id="bd83e-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="bd83e-166">Folgendes ist eine Beispiel-Transact-SQL-Anweisung, um Zeilen aus der Ansicht ExecutionLog3 abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="bd83e-167">Im Beispiel wird davon ausgegangen, dass der Name der Berichtsserver-Datenbank **ReportServer**lautet:</span><span class="sxs-lookup"><span data-stu-id="bd83e-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="bd83e-168">In der folgenden Tabelle werden die Daten beschrieben, die im Berichtsausführungsprotokoll aufgezeichnet werden</span><span class="sxs-lookup"><span data-stu-id="bd83e-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="bd83e-169">Column</span><span class="sxs-lookup"><span data-stu-id="bd83e-169">Column</span></span>|<span data-ttu-id="bd83e-170">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd83e-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bd83e-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="bd83e-171">InstanceName</span></span>|<span data-ttu-id="bd83e-172">Name der Berichtsserverinstanz, die die Anforderung verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="bd83e-173">Wenn die Umgebung mehr als einen Berichtsserver hat, können Sie die zu überwachende InstanceName-Verteilung analysieren und bestimmen, ob der Netzwerklastenausgleich Anforderungen auf der anderen Seite von Berichtsservern wie erwartet verteilt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="bd83e-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="bd83e-174">ItemPath</span></span>|<span data-ttu-id="bd83e-175">Pfad, in dem ein Bericht oder Berichtselement gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="bd83e-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="bd83e-176">UserName</span><span class="sxs-lookup"><span data-stu-id="bd83e-176">UserName</span></span>|<span data-ttu-id="bd83e-177">Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="bd83e-177">User identifier.</span></span>|  
|<span data-ttu-id="bd83e-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="bd83e-178">ExecutionID</span></span>|<span data-ttu-id="bd83e-179">Der interne einer Anforderung zugeordnete Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="bd83e-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="bd83e-180">Anforderungen für die selben Benutzersitzungen besitzen dieselbe Ausführungs-ID.</span><span class="sxs-lookup"><span data-stu-id="bd83e-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="bd83e-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="bd83e-181">RequestType</span></span>|<span data-ttu-id="bd83e-182">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="bd83e-182">Possible Values:</span></span><br /><span data-ttu-id="bd83e-183">**Interactive**</span><span class="sxs-lookup"><span data-stu-id="bd83e-183">**Interactive**</span></span><br /><span data-ttu-id="bd83e-184">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="bd83e-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="bd83e-185">Das Analysieren von nach RequestType=Subscription gefilterten und nach TimeStart sortierten Protokolldaten enthüllt möglicherweise Zeiträume starker Abonnementnutzung und Sie möchten vielleicht einige der Berichtsabonnements in eine andere Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="bd83e-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="bd83e-186">Format</span><span class="sxs-lookup"><span data-stu-id="bd83e-186">Format</span></span>|<span data-ttu-id="bd83e-187">Renderingformat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-187">Rendering format.</span></span>|  
|<span data-ttu-id="bd83e-188">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd83e-188">Parameters</span></span>|<span data-ttu-id="bd83e-189">Parameterwerte, die für die Berichtsausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="bd83e-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="bd83e-190">ItemAction</span></span>|<span data-ttu-id="bd83e-191">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="bd83e-191">Possible values:</span></span><br /><br /> <span data-ttu-id="bd83e-192">**Rendern**</span><span class="sxs-lookup"><span data-stu-id="bd83e-192">**Render**</span></span><br /><br /> <span data-ttu-id="bd83e-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="bd83e-193">**Sort**</span></span><br /><br /> <span data-ttu-id="bd83e-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="bd83e-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="bd83e-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="bd83e-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="bd83e-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="bd83e-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="bd83e-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="bd83e-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="bd83e-198">**Auszuführen**</span><span class="sxs-lookup"><span data-stu-id="bd83e-198">**Execute**</span></span><br /><br /> <span data-ttu-id="bd83e-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="bd83e-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="bd83e-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="bd83e-200">TimeStart</span></span>|<span data-ttu-id="bd83e-201">Anfangs- und Beendigungszeit für die Verarbeitung eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="bd83e-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="bd83e-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="bd83e-202">TimeEnd</span></span>||  
|<span data-ttu-id="bd83e-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="bd83e-203">TimeDataRetrieval</span></span>|<span data-ttu-id="bd83e-204">Anzahl von Millisekunden, die zum Abrufen der Daten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="bd83e-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="bd83e-205">TimeProcessing</span></span>|<span data-ttu-id="bd83e-206">Anzahl von Millisekunden, die zum Verarbeiten des Berichts benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="bd83e-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="bd83e-207">TimeRendering</span></span>|<span data-ttu-id="bd83e-208">Anzahl von Millisekunden, die zum Rendern des Berichts benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="bd83e-209">`Source`</span><span class="sxs-lookup"><span data-stu-id="bd83e-209">Source</span></span>|<span data-ttu-id="bd83e-210">Quelle der Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="bd83e-210">Source of the report execution.</span></span> <span data-ttu-id="bd83e-211">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="bd83e-211">Possible values:</span></span><br /><br /> <span data-ttu-id="bd83e-212">**Live**</span><span class="sxs-lookup"><span data-stu-id="bd83e-212">**Live**</span></span><br /><br /> <span data-ttu-id="bd83e-213">**Cache**: gibt eine zwischengespeicherte Ausführung an, z. b. werden Datasetabfragen nicht Live ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="bd83e-214">**Momentaufnahme**</span><span class="sxs-lookup"><span data-stu-id="bd83e-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="bd83e-215">**History**</span><span class="sxs-lookup"><span data-stu-id="bd83e-215">**History**</span></span><br /><br /> <span data-ttu-id="bd83e-216">**Adhoc** : gibt entweder einen dynamisch generierten Berichts modellbasierten Drillthrough-Bericht oder einen Berichts-Generator Bericht an, der auf einem Client in der Vorschau angezeigt wird, der den Berichts Server für die Verarbeitung und das Rendering verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd83e-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="bd83e-217">**Session**: gibt eine nach Verfolgungs Anforderung in einer bereits eingerichteten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="bd83e-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="bd83e-218">Beispiel: Die ursprüngliche Anforderung besteht im Anzeigen von Seite 1, die Anschlussanforderung ist das Exportieren in Excel mit dem aktuellen Sitzungsstatus.</span><span class="sxs-lookup"><span data-stu-id="bd83e-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="bd83e-219">**RDCE**: gibt eine Anpassungs Erweiterung für die Berichts Definition an.</span><span class="sxs-lookup"><span data-stu-id="bd83e-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="bd83e-220">Eine benutzerdefinierte RDCE-Erweiterung kann eine Berichtsdefinition dynamisch anpassen, bevor sie bei der Berichtsausführung an die Verarbeitungs-Engine übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="bd83e-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="bd83e-221">Status</span><span class="sxs-lookup"><span data-stu-id="bd83e-221">Status</span></span>|<span data-ttu-id="bd83e-222">Status (entweder rsSuccess oder ein Fehlercode; beim Auftreten mehrerer Fehler wird nur der erste Fehler aufgezeichnet).</span><span class="sxs-lookup"><span data-stu-id="bd83e-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="bd83e-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-223">ByteCount</span></span>|<span data-ttu-id="bd83e-224">Größe von gerenderten Berichten in Bytes.</span><span class="sxs-lookup"><span data-stu-id="bd83e-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="bd83e-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-225">RowCount</span></span>|<span data-ttu-id="bd83e-226">Anzahl der von Abfragen zurückgegebenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="bd83e-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="bd83e-227">AdditionalInfo</span></span>|<span data-ttu-id="bd83e-228">Ein XML-Eigenschaftenbehälter, der weitere Informationen zur Ausführung enthält.</span><span class="sxs-lookup"><span data-stu-id="bd83e-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="bd83e-229">Der Inhalt kann für jede Zeile anders sein.</span><span class="sxs-lookup"><span data-stu-id="bd83e-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="bd83e-230">Das AdditionalInfo-Feld</span><span class="sxs-lookup"><span data-stu-id="bd83e-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="bd83e-231">Das AdditionalInfo-Feld ist ein XML-Eigenschaftenbehälter oder eine Struktur, die weitere Informationen zur Ausführung enthält.</span><span class="sxs-lookup"><span data-stu-id="bd83e-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="bd83e-232">Der Inhalt kann für jede Zeile im Protokoll anders sein.</span><span class="sxs-lookup"><span data-stu-id="bd83e-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="bd83e-233">Die folgenden Tabellen sind Beispiele für den Inhalt des AddtionalInfo-Felds für die Standardprotokollierung und die ausführliche Protokollierung:</span><span class="sxs-lookup"><span data-stu-id="bd83e-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="bd83e-234">**Beispiel für die Standardprotokollierung von AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="bd83e-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="bd83e-235">**Beispiel für die ausführliche Protokollierung von AdditionalInfo**</span><span class="sxs-lookup"><span data-stu-id="bd83e-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="bd83e-236">Im folgenden werden einige der Eigenschaften beschrieben, die im Feld AdditionalInfo angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="bd83e-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="bd83e-237">**Processingengine**: 1 = SQL Server 2005, 2 = die neue Bedarfs gesteuerte Verarbeitungs-Engine.</span><span class="sxs-lookup"><span data-stu-id="bd83e-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="bd83e-238">Wenn eine Mehrzahl der Berichte immer noch den Wert 1 anzeigt, können Sie prüfen, wie sie umgestaltet werden sollen, damit sie die neuere und effizientere bedarfsgesteuerte Verarbeitungs-Engine verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="bd83e-239">**Scalabilitytime**: die Anzahl von Millisekunden für die Durchführung von Skalierungs bezogenen Vorgängen in der Verarbeitungs-Engine.</span><span class="sxs-lookup"><span data-stu-id="bd83e-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="bd83e-240">Der Wert 0 gibt an, dass keine zusätzliche Zeit für Skalierungsoperationen aufgebracht wurde. Ein Wert 0 gibt auch an, dass die Anforderung nicht unter unzureichendem Arbeitsspeicher erfolgte.</span><span class="sxs-lookup"><span data-stu-id="bd83e-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="bd83e-241">**Estimatedmemoryusagekb**: eine Schätzung der Höchstmenge an Arbeitsspeicher in Kilobyte, die von jeder Komponente während einer bestimmten Anforderung beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="bd83e-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="bd83e-242">**Dataextension**: die Typen von Daten Erweiterungen oder Datenquellen, die im Bericht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="bd83e-243">Die Zahl ist eine Anzahl von Vorkommen der speziellen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="bd83e-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="bd83e-244">**Externalimages** Der Wert ist in Millisekunden angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd83e-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="bd83e-245">Diese Daten können bei der Diagnose von Leistungsproblemen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="bd83e-246">Die zum Abrufen von Bildern von einem externen Webserver benötigte Zeit verlangsamt möglicherweise die gesamte Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="bd83e-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="bd83e-247">In hinzugefügt [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd83e-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="bd83e-248">**Verbindungen**: eine Struktur mit mehreren Ebenen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="bd83e-249">In hinzugefügt [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd83e-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a> <span data-ttu-id="bd83e-250">Protokollierungsfelder (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="bd83e-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="bd83e-251">Diese Ansicht hat einige neue Felder hinzugefügt und einige andere umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bd83e-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="bd83e-252">Folgendes ist eine Beispiel-Transact-SQL-Anweisung, mit der Sie Zeilen aus der Ansicht ExecutionLog2 abrufen können.</span><span class="sxs-lookup"><span data-stu-id="bd83e-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="bd83e-253">Im Beispiel wird davon ausgegangen, dass der Name der Berichtsserver-Datenbank **ReportServer**lautet:</span><span class="sxs-lookup"><span data-stu-id="bd83e-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="bd83e-254">In der folgenden Tabelle werden die Daten beschrieben, die im Berichtsausführungsprotokoll aufgezeichnet werden</span><span class="sxs-lookup"><span data-stu-id="bd83e-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="bd83e-255">Spalte</span><span class="sxs-lookup"><span data-stu-id="bd83e-255">Column</span></span>|<span data-ttu-id="bd83e-256">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd83e-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bd83e-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="bd83e-257">InstanceName</span></span>|<span data-ttu-id="bd83e-258">Name der Berichtsserverinstanz, die die Anforderung verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="bd83e-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="bd83e-259">ReportPath</span></span>|<span data-ttu-id="bd83e-260">Die Pfadstruktur zum Bericht.</span><span class="sxs-lookup"><span data-stu-id="bd83e-260">The path structure to the report.</span></span>  <span data-ttu-id="bd83e-261">Zum Beispiel würde ein Bericht mit dem Namen „Test“, der der Stammordner im Berichts-Manager ist, den ReportPath „/test“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="bd83e-262">Ein Bericht mit dem Namen „Test“, der im Ordner „Samples“ im Berichts-Manager gespeichert ist, würde den ReportPath „/Samples/test/“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="bd83e-263">UserName</span><span class="sxs-lookup"><span data-stu-id="bd83e-263">UserName</span></span>|<span data-ttu-id="bd83e-264">Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="bd83e-264">User identifier.</span></span>|  
|<span data-ttu-id="bd83e-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="bd83e-265">ExecutionID</span></span>||  
|<span data-ttu-id="bd83e-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="bd83e-266">RequestType</span></span>|<span data-ttu-id="bd83e-267">Anforderungstyp (Benutzer oder System).</span><span class="sxs-lookup"><span data-stu-id="bd83e-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="bd83e-268">Format</span><span class="sxs-lookup"><span data-stu-id="bd83e-268">Format</span></span>|<span data-ttu-id="bd83e-269">Renderingformat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-269">Rendering format.</span></span>|  
|<span data-ttu-id="bd83e-270">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd83e-270">Parameters</span></span>|<span data-ttu-id="bd83e-271">Parameterwerte, die für die Berichtsausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="bd83e-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="bd83e-272">ReportAction</span></span>|<span data-ttu-id="bd83e-273">Mögliche Werte: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="bd83e-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="bd83e-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="bd83e-274">TimeStart</span></span>|<span data-ttu-id="bd83e-275">Anfangs- und Beendigungszeit für die Verarbeitung eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="bd83e-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="bd83e-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="bd83e-276">TimeEnd</span></span>||  
|<span data-ttu-id="bd83e-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="bd83e-277">TimeDataRetrieval</span></span>|<span data-ttu-id="bd83e-278">Zeitaufwand (in Millisekunden) für das Abfragen der Daten, das Verarbeiten des Berichts und das Rendern des Berichts.</span><span class="sxs-lookup"><span data-stu-id="bd83e-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="bd83e-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="bd83e-279">TimeProcessing</span></span>||  
|<span data-ttu-id="bd83e-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="bd83e-280">TimeRendering</span></span>||  
|<span data-ttu-id="bd83e-281">`Source`</span><span class="sxs-lookup"><span data-stu-id="bd83e-281">Source</span></span>|<span data-ttu-id="bd83e-282">Quelle der Berichtsausführung (1=Live, 2=Cache, 3=Snapshot 4=History).</span><span class="sxs-lookup"><span data-stu-id="bd83e-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="bd83e-283">Status</span><span class="sxs-lookup"><span data-stu-id="bd83e-283">Status</span></span>|<span data-ttu-id="bd83e-284">Status (entweder rsSuccess oder ein Fehlercode; beim Auftreten mehrerer Fehler wird nur der erste Fehler aufgezeichnet).</span><span class="sxs-lookup"><span data-stu-id="bd83e-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="bd83e-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-285">ByteCount</span></span>|<span data-ttu-id="bd83e-286">Größe von gerenderten Berichten in Bytes.</span><span class="sxs-lookup"><span data-stu-id="bd83e-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="bd83e-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-287">RowCount</span></span>|<span data-ttu-id="bd83e-288">Anzahl der von Abfragen zurückgegebenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="bd83e-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="bd83e-289">AdditionalInfo</span></span>|<span data-ttu-id="bd83e-290">Ein XML-Eigenschaftenbehälter, der weitere Informationen zur Ausführung enthält.</span><span class="sxs-lookup"><span data-stu-id="bd83e-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a> <span data-ttu-id="bd83e-291">Protokollierungsfelder (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="bd83e-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="bd83e-292">Folgendes ist eine Beispiel-Transact-SQL-Anweisung, mit der Sie Zeilen aus der Ansicht ExecutionLog abrufen können.</span><span class="sxs-lookup"><span data-stu-id="bd83e-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="bd83e-293">Im Beispiel wird davon ausgegangen, dass der Name der Berichtsserver-Datenbank **ReportServer**lautet:</span><span class="sxs-lookup"><span data-stu-id="bd83e-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="bd83e-294">In der folgenden Tabelle werden die Daten beschrieben, die im Berichtsausführungsprotokoll aufgezeichnet werden</span><span class="sxs-lookup"><span data-stu-id="bd83e-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="bd83e-295">Spalte</span><span class="sxs-lookup"><span data-stu-id="bd83e-295">Column</span></span>|<span data-ttu-id="bd83e-296">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd83e-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bd83e-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="bd83e-297">InstanceName</span></span>|<span data-ttu-id="bd83e-298">Name der Berichtsserverinstanz, die die Anforderung verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="bd83e-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="bd83e-299">ReportID</span></span>|<span data-ttu-id="bd83e-300">Berichts-ID.</span><span class="sxs-lookup"><span data-stu-id="bd83e-300">Report identifier.</span></span>|  
|<span data-ttu-id="bd83e-301">UserName</span><span class="sxs-lookup"><span data-stu-id="bd83e-301">UserName</span></span>|<span data-ttu-id="bd83e-302">Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="bd83e-302">User identifier.</span></span>|  
|<span data-ttu-id="bd83e-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="bd83e-303">RequestType</span></span>|<span data-ttu-id="bd83e-304">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="bd83e-304">Possible values:</span></span><br /><br /> <span data-ttu-id="bd83e-305">True = Eine Abonnementanforderung</span><span class="sxs-lookup"><span data-stu-id="bd83e-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="bd83e-306">False = Eine interaktive Anforderung</span><span class="sxs-lookup"><span data-stu-id="bd83e-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="bd83e-307">Format</span><span class="sxs-lookup"><span data-stu-id="bd83e-307">Format</span></span>|<span data-ttu-id="bd83e-308">Renderingformat.</span><span class="sxs-lookup"><span data-stu-id="bd83e-308">Rendering format.</span></span>|  
|<span data-ttu-id="bd83e-309">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd83e-309">Parameters</span></span>|<span data-ttu-id="bd83e-310">Parameterwerte, die für die Berichtsausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd83e-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="bd83e-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="bd83e-311">TimeStart</span></span>|<span data-ttu-id="bd83e-312">Anfangs- und Beendigungszeit für die Verarbeitung eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="bd83e-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="bd83e-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="bd83e-313">TimeEnd</span></span>||  
|<span data-ttu-id="bd83e-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="bd83e-314">TimeDataRetrieval</span></span>|<span data-ttu-id="bd83e-315">Zeitaufwand (in Millisekunden) für das Abfragen der Daten, das Verarbeiten des Berichts und das Rendern des Berichts.</span><span class="sxs-lookup"><span data-stu-id="bd83e-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="bd83e-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="bd83e-316">TimeProcessing</span></span>||  
|<span data-ttu-id="bd83e-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="bd83e-317">TimeRendering</span></span>||  
|<span data-ttu-id="bd83e-318">`Source`</span><span class="sxs-lookup"><span data-stu-id="bd83e-318">Source</span></span>|<span data-ttu-id="bd83e-319">Quelle der Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="bd83e-319">Source of the report execution.</span></span> <span data-ttu-id="bd83e-320">Mögliche Werte: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span><span class="sxs-lookup"><span data-stu-id="bd83e-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="bd83e-321">Status</span><span class="sxs-lookup"><span data-stu-id="bd83e-321">Status</span></span>|<span data-ttu-id="bd83e-322">Mögliche Werte: rsSuccess, rsProcessingAborted oder ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="bd83e-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="bd83e-323">Wenn mehrere Fehler auftreten, wird nur der erste Fehler aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bd83e-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="bd83e-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-324">ByteCount</span></span>|<span data-ttu-id="bd83e-325">Größe von gerenderten Berichten in Bytes.</span><span class="sxs-lookup"><span data-stu-id="bd83e-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="bd83e-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="bd83e-326">RowCount</span></span>|<span data-ttu-id="bd83e-327">Anzahl der von Abfragen zurückgegebenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="bd83e-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd83e-328">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd83e-328">See Also</span></span>  
 <span data-ttu-id="bd83e-329">[Aktivieren von Reporting Services Ereignissen für das SharePoint-Ablauf Verfolgungs Protokoll &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="bd83e-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="bd83e-330">[Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="bd83e-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="bd83e-331">Fehler- und Ereignisreferenz &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd83e-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
