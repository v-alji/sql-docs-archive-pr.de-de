---
title: Festlegen von Verarbeitungsoptionen (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700767"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="dcfa7-102">Festlegen von Verarbeitungsoptionen (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="dcfa7-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="dcfa7-103">Sie können Verarbeitungsoptionen für einen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Bericht festlegen, um den Zeitpunkt der Datenverarbeitung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="dcfa7-104">Sie können auch einen Timeoutwert für die Berichtsverarbeitung und Optionen festlegen, mit denen bestimmt wird, ob der Berichtsverlauf für den aktuellen Bericht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="dcfa7-105">Sie können einen Bericht als Berichtsmomentaufnahme ausführen, um zu verhindern, dass der Bericht zu willkürlichen Zeiten ausgeführt wird (z.B. während einer geplanten Sicherung).</span><span class="sxs-lookup"><span data-stu-id="dcfa7-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="dcfa7-106">Eine Berichtsmomentaufnahme wird gewöhnlich gemäß einem Zeitplan erstellt und später aktualisiert. Auf diese Weise können Sie genau planen, wann der Bericht und die Daten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="dcfa7-107">Falls ein Bericht auf Abfragen basiert, deren Ausführung viel Zeit in Anspruch nimmt oder die Daten von einer Datenquelle verwenden, auf die während eines bestimmten Zeitraums kein Benutzer Zugriff haben soll, sollten Sie den Bericht als Momentaufnahme ausführen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="dcfa7-108">Ein Berichtsserver kann eine Kopie eines verarbeiteten Berichts zwischenspeichern und diese anzeigen, wenn ein Benutzer den Bericht öffnet.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="dcfa7-109">Die Zwischenspeicherung ist eine Technik zur Leistungsoptimierung.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="dcfa7-110">Durch die Zwischenspeicherung kann ein Bericht schneller abgerufen werden, falls der Bericht sehr umfangreich ist oder häufig abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="dcfa7-111">Der Berichtsverlauf enthält eine Auflistung der zuvor ausgeführten Kopien eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="dcfa7-112">Mithilfe des Berichtsverlaufs können Sie eine Aufzeichnung eines Berichts für einen bestimmten Zeitraum verwalten.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="dcfa7-113">Der Berichtsverlauf ist nicht für Berichte mit vertraulichen oder persönlichen Daten gedacht.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="dcfa7-114">Aus diesem Grund kann der Berichtsverlauf nur jene Berichte enthalten, von denen die Abfrage einer Datenquelle mithilfe eines einzigen Satzes von Anmeldeinformationen durchgeführt wird, die für alle einen Bericht ausführenden Benutzer verfügbar sind. (Die Anmeldeinformationen müssen entweder gespeicherte Anmeldeinformationen oder Anmeldeinformationen für die unbeaufsichtigte Berichtsausführung sein.)</span><span class="sxs-lookup"><span data-stu-id="dcfa7-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="dcfa7-115">-Integration in SharePoint werden die Funktionen zum Auschecken und Einchecken in der Inhaltsverwaltung von SharePoint verwendet, um Updates zu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="dcfa7-116">Dies umfasst auch die Erstellung von Berichtsmomentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="dcfa7-117">Wenn Sie die Versionsverwaltung für eine Dokumentbibliothek aktiviert haben, wird die Berichtsversion aktualisiert, wenn eine neue Berichtsverlaufs-Momentaufnahme erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="dcfa7-118">Dies ist eine zusätzliche Auswirkung der Aktualisierung von Momentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="dcfa7-119">Bei der Aktualisierung einer Momentaufnahme wird die LastExecution-Eigenschaft des Berichts geändert, und dadurch erfolgt gleichzeitig eine Änderung in der Version des Berichts.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="dcfa7-120">Mithilfe von Timeoutwerten können Sie Grenzwerte für die Verwendung der Systemressourcen festlegen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="dcfa7-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="dcfa7-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="dcfa7-122">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="dcfa7-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="dcfa7-123">So legen Sie Optionen zum Aktualisieren von Daten fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="dcfa7-124">So legen Sie Zwischenspeicheroptionen für Berichte fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="dcfa7-125">So legen Sie die Verarbeitung von Timeoutwerten fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="dcfa7-126">So legen Sie Verlaufsoptionen und Verlaufsgrenzwerte für Berichte fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="dcfa7-127">Datenbank-Timeout festlegen</span><span class="sxs-lookup"><span data-stu-id="dcfa7-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="dcfa7-128">So legen Sie Daten Aktualisierungs Optionen fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="dcfa7-129">Zeigen Sie auf einen Bericht in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="dcfa7-130">Klicken Sie auf den Pfeil nach unten, und wählen Sie **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="dcfa7-131">Klicken Sie unter **Datenaktualisierungsoptionen**auf **Momentaufnahmedaten verwenden**.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="dcfa7-132">Wenn die Meldung "Dieser Bericht kann nicht über eine Momentaufnahme ausgeführt werden, da mindestens eine Anmeldeinformation für die Datenquellen nicht gespeichert ist" angezeigt wird, bedeutet dies, dass der Bericht nicht für die unbeaufsichtigte Ausführung konfiguriert ist und Sie vor dem Festlegen dieser Option die Datenquellen zum Verwenden gespeicherter Anmeldeinformationen konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="dcfa7-133">Wählen Sie unter **Optionen für Datenmomentaufnahmen**die Option **Datenverarbeitung planen**aus.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="dcfa7-134">Wählen Sie **Nach einem freigegebenen Zeitplan** , wenn Sie über einen vorhandenen freigegebenen Zeitplan verfügen, den Sie verwenden möchten. Wählen Sie andernfalls **Nach einem benutzerdefinierten Zeitplan**, und klicken Sie auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="dcfa7-135">Wählen Sie eine Häufigkeit, einen Zeitplan sowie Werte für das Start- und das Enddatum aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="dcfa7-136">Wählen Sie unter **Optionen für Datenmomentaufnahmen**die Option **Die Momentaufnahme beim Speichern dieser Seite erstellen oder aktualisieren** aus, wenn Sie unmittelbar Momentaufnahmedaten für die Verwendung im Bericht erstellen möchten, ohne auf die Ausführung der geplanten Datenverarbeitung zu warten.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="dcfa7-137">So legen Sie Cache Optionen für Berichte fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="dcfa7-138">Zeigen Sie auf einen Bericht in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="dcfa7-139">Klicken Sie auf den Pfeil nach unten, und wählen Sie **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="dcfa7-140">Klicken Sie unter **Datenaktualisierungsoptionen**auf **Zwischengespeicherte Daten verwenden**.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="dcfa7-141">Wenn die Meldung "Dieser Bericht kann nicht zwischengespeichert werden, da mindestens eine Anmeldeinformation für die Datenquelle nicht gespeichert ist" angezeigt wird, bedeutet dies, dass der Bericht nicht für die unbeaufsichtigte Ausführung konfiguriert ist und Sie vor dem Festlegen dieser Option die Datenquellen zum Verwenden gespeicherter Anmeldeinformationen konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="dcfa7-142">Geben Sie unter **Cacheoptionen**an, wie der Cache abläuft:</span><span class="sxs-lookup"><span data-stu-id="dcfa7-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="dcfa7-143">Geben Sie an, nach wie vielen Minuten der Cache abläuft.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="dcfa7-144">Verwenden Sie einen freigegebenen Zeitplan, um den Cache zu den im Zeitplan angegebenen Zeiten zu leeren.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="dcfa7-145">Erstellen Sie einen benutzerdefinierten Zeitplan, um den Cache zu einem angegebenen Zeitpunkt zu leeren.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="dcfa7-146">So legen Sie Verarbeitungs Timeout Werte fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="dcfa7-147">Zeigen Sie auf einen Bericht in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="dcfa7-148">Klicken Sie auf den Pfeil nach unten, und wählen Sie **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="dcfa7-149">Klicken Sie unter **Verarbeitungstimeout**auf **Die Standardeinstellung für die Site verwenden** , wenn Sie den auf der Berichtsserverebene angegebenen Wert verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="dcfa7-150">Wählen Sie andernfalls **Kein Timeout für die Berichtsverarbeitung festlegen** oder **Berichtsverarbeitungsbeschränkung (in Sekunden)** aus, wenn Sie keinen Timeoutwert angeben oder den Timeoutwert durch einen anderen Wert überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="dcfa7-151">So legen Sie Optionen und Grenzwerte für den Berichts Verlauf fest</span><span class="sxs-lookup"><span data-stu-id="dcfa7-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="dcfa7-152">Zeigen Sie auf einen Bericht in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="dcfa7-153">Klicken Sie auf den Pfeil nach unten, und wählen Sie **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="dcfa7-154">Geben Sie unter **Optionen für Verlaufsmomentaufnahmen**an, wie und wann eine Datenverarbeitung ausgeführt und gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="dcfa7-155">Wählen Sie unter **Grenzwerte für Verlaufsmomentaufnahmen**die Option **Die Standardeinstellung für die Site verwenden** , wenn Sie den auf der Berichtsserverebene angegebenen Wert verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="dcfa7-156">Wählen Sie andernfalls **Die Anzahl von Momentaufnahmen nicht einschränken** , oder geben Sie für **Die Anzahl der Momentaufnahmen auf folgenden Wert beschränken** einen benutzerdefinierten Wert an.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="dcfa7-157">Datenbank-Timeout festlegen</span><span class="sxs-lookup"><span data-stu-id="dcfa7-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="dcfa7-158">Verwenden Sie Windows PowerShell, um das Datenbank-Timeout eines SharePoint-Berichtsservers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dcfa7-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="dcfa7-159">Weitere Informationen finden Sie im Abschnitt zum Abrufen und Festlegen der Eigenschaften der Reporting Services-Dienstanwendungsdatenbank unter [PowerShell-Cmdlets für den SharePoint-Modus von Reporting Services](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa7-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfa7-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcfa7-160">See Also</span></span>  
 <span data-ttu-id="dcfa7-161">[Festlegen von Berichts Verarbeitungseigenschaften](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="dcfa7-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="dcfa7-162">[Zwischenspeichern von Berichten (SSRS)](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dcfa7-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="dcfa7-163">Festlegen von Timeoutwerten für die Verarbeitung von Berichten und freigegebenen Datasets &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dcfa7-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
