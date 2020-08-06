---
title: Konfigurieren von Ausführungseigenschaften für einen Bericht (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630513"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="18b06-102">Konfigurieren von Ausführungseigenschaften für einen Bericht (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="18b06-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="18b06-103">Sie können Berichtsverarbeitungsoptionen festlegen, um anzugeben, wann Daten für einen Bericht abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18b06-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="18b06-104">Es ist hilfreich, die Datenverarbeitung für einen Bericht zu planen, wenn die externe Datenquelle zu bestimmten Zeiten aktualisiert wird (beispielsweise bei einem Data Warehouse, das täglich oder wöchentlich aktualisiert wird) und Sie vermeiden wollen, dass bei jeder Berichtsanforderung dieselben Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="18b06-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="18b06-105">Das Planen der Datenverarbeitung ist außerdem hilfreich, wenn Sie die Verarbeitungslast für den externen Datenbankserver steuern möchten oder wenn Sie einheitliche Ergebnisse für verschiedene Benutzer bereitstellen möchten, die mit identischen Datensätzen arbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="18b06-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="18b06-106">Bei flüchtigen Daten kann ein bedarfsgesteuerter Bericht von einer Minute zur nächsten unterschiedliche Ergebnisse liefern.</span><span class="sxs-lookup"><span data-stu-id="18b06-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="18b06-107">Dagegen können Sie mit einer Berichtsmomentaufnahme gültige Vergleiche mit anderen Berichten oder Analysetools ausführen, die Daten desselben Zeitpunkts enthalten.</span><span class="sxs-lookup"><span data-stu-id="18b06-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="18b06-108">Eine Berichtsmomentaufnahme ist ein Bericht, der Layoutanweisungen und Abfrageergebnisse enthält, die zu einem bestimmten Zeitpunkt abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="18b06-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="18b06-109">Während für bedarfsgesteuerte Berichte aktuelle Abfrageergebnisse abgerufen werden, wenn Sie den Bericht auswählen, werden Berichtsmomentaufnahmen anhand eines Zeitplans verarbeitet und anschließend auf einem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="18b06-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="18b06-110">Wenn Sie eine Berichtsmomentaufnahme zum Anzeigen auswählen, ruft der Berichtsserver den gespeicherten Bericht aus der Berichtsserver-Datenbank ab und zeigt die Daten und das Layout an, die zum Zeitpunkt der Momentaufnahmeerstellung für den Bericht aktuell waren.</span><span class="sxs-lookup"><span data-stu-id="18b06-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="18b06-111">Berichtsmomentaufnahmen werden in keinem speziellen Renderingformat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="18b06-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="18b06-112">Stattdessen werden Berichtsmomentaufnahmen erst dann in einem endgültigen Anzeigeformat (wie HTML) gerendert, wenn sie von einem Benutzer oder einer Anwendung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="18b06-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="18b06-113">Durch das verzögerte Rendering wird eine Momentaufnahme portabel.</span><span class="sxs-lookup"><span data-stu-id="18b06-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="18b06-114">Der Bericht kann jeweils im richtigen Format für das anfordernde Gerät oder den anfordernden Webbrowser gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="18b06-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="18b06-115">So konfigurieren Sie Berichtsverarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="18b06-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="18b06-116">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="18b06-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="18b06-117">Navigieren Sie zu dem Bericht, für den Sie Berichtsverarbeitungsoptionen festlegen möchten, und öffnen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="18b06-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="18b06-118">Zeigen Sie auf den Bericht, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="18b06-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="18b06-119">Klicken Sie im Dropdownmenü auf **Verwalten** , und wählen Sie dann die Registerkarte **Verarbeitungsoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="18b06-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="18b06-120">Klicken Sie auf **Diesen Bericht aus einer Berichtsausführungs-Momentaufnahme rendern**, und wählen Sie dann eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="18b06-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="18b06-121">Falls Sie eine Momentaufnahme erstellen möchten, wählen Sie **Berichtsausführungs-Momentaufnahmen entsprechend diesem Zeitplan erstellen**aus, und definieren Sie anschließend einen berichtsspezifischen Zeitplan, oder wählen Sie aus der Liste **Freigegebener Zeitplan** einen Zeitplan aus.</span><span class="sxs-lookup"><span data-stu-id="18b06-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="18b06-122">Wenn Sie sofort eine Momentaufnahme erstellen möchten, wählen Sie **Erstellen Sie eine Momentaufnahme des Berichts, wenn Sie auf dieser Seite auf die Schaltfläche "Anwenden" klicken**aus.</span><span class="sxs-lookup"><span data-stu-id="18b06-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="18b06-123">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="18b06-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b06-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18b06-124">See Also</span></span>  
 <span data-ttu-id="18b06-125">[Festlegen von Berichts Verarbeitungseigenschaften](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="18b06-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="18b06-126">[Öffnen und schließen Sie einen Bericht &#40;Berichts-Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18b06-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="18b06-127">[Inhalt &#40;Seite, Berichts-Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18b06-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="18b06-128">[Verwalten von Berichtsserverinhalten &#40;einheitlicher SSRS-Modus&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="18b06-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="18b06-129">Verarbeitungsoptionen (Eigenschaftenseite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="18b06-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
