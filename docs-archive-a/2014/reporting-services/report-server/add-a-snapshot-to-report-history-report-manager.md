---
title: Hinzufügen einer Momentaufnahme zum Berichtsverlauf (Berichts-Manager) | Microsoft-Dokumentation
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619626"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="1af84-102">Hinzufügen einer Momentaufnahme zum Berichtsverlauf (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="1af84-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="1af84-103">Der Berichtsverlauf stellt eine Auflistung von Berichtsmomentaufnahmen dar, die Sie im Laufe der Zeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="1af84-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="1af84-104">Ein Berichtsmomentaufnahme ist ein Bericht, der Layoutinformationen und Abfrageergebnisse enthält, die zu einem bestimmten Zeitpunkt abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="1af84-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="1af84-105">Während für bedarfsgesteuerte Berichte aktuelle Abfrageergebnisse abgerufen werden, wenn Sie den Bericht auswählen, werden Berichtsmomentaufnahmen anhand eines Zeitplans verarbeitet und anschließend auf einem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1af84-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="1af84-106">Wenn Sie eine Berichtsmomentaufnahme zum Anzeigen auswählen, ruft der Berichtsserver den gespeicherten Bericht aus der Berichtsserver-Datenbank ab und zeigt die Daten und das Layout an, die zum Zeitpunkt der Momentaufnahmeerstellung für den Bericht aktuell waren.</span><span class="sxs-lookup"><span data-stu-id="1af84-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="1af84-107">Berichtsmomentaufnahmen werden in keinem speziellen Renderingformat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1af84-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="1af84-108">Stattdessen werden Berichtsmomentaufnahmen erst dann in einem endgültigen Anzeigeformat (wie HTML) gerendert, wenn sie von einem Benutzer oder einer Anwendung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="1af84-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="1af84-109">Durch das verzögerte Rendering wird eine Momentaufnahme portabel.</span><span class="sxs-lookup"><span data-stu-id="1af84-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="1af84-110">Der Bericht kann jeweils im richtigen Format für das anfordernde Gerät oder den anfordernden Webbrowser gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="1af84-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="1af84-111">So fügen Sie dem Berichtsverlauf manuell Momentaufnahmen hinzu</span><span class="sxs-lookup"><span data-stu-id="1af84-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="1af84-112">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und zeigen Sie auf das Element, dessen Verlauf angezeigt werden soll, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="1af84-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="1af84-113">Klicken Sie im Dropdownmenü auf **Berichtsverlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1af84-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="1af84-114">Klicken Sie auf **Neue Momentaufnahme**.</span><span class="sxs-lookup"><span data-stu-id="1af84-114">Click **New Snapshot**.</span></span> <span data-ttu-id="1af84-115">In der Spalte **Ausführungszeitpunkt** wird eine neue Momentaufnahme erstellt.</span><span class="sxs-lookup"><span data-stu-id="1af84-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1af84-116">Dazu muss der Berichtsverlauf vom Administrator auf **Verlauf kann manuell erstellt werden**konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="1af84-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="1af84-117">Weitere Informationen finden Sie unter [Einschränken des Berichtsverlaufs &#40;Berichts-Manager&#41;](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1af84-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="1af84-118">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="1af84-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="1af84-119">So fügen Sie dem Berichtsverlauf automatisch alle Momentaufnahmen hinzu</span><span class="sxs-lookup"><span data-stu-id="1af84-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="1af84-120">Für einen Bericht, der bereits für die Ausführung als Berichtsausführungs-Momentaufnahme konfiguriert ist, können Sie zusätzliche Eigenschaften festlegen, um bei jeder Aktualisierung der Momentaufnahme eine Kopie der Momentaufnahme im Berichtsverlauf zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1af84-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="1af84-121">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , zeigen Sie auf das Element, dessen Verlauf angezeigt werden soll, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="1af84-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="1af84-122">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="1af84-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="1af84-123">Klicken Sie auf **Momentaufnahmeoptionen**.</span><span class="sxs-lookup"><span data-stu-id="1af84-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="1af84-124">Aktivieren Sie das Kontrollkästchen **Alle Berichtsausführungs-Momentaufnahmen im Verlauf speichern**.</span><span class="sxs-lookup"><span data-stu-id="1af84-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="1af84-125">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="1af84-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="1af84-126">So fügen Sie basierend auf einem Zeitplan automatisch Momentaufnahmen zum Berichtsverlauf hinzu</span><span class="sxs-lookup"><span data-stu-id="1af84-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="1af84-127">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und zeigen Sie auf das Element, dessen Verlauf angezeigt werden soll, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="1af84-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="1af84-128">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="1af84-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="1af84-129">Klicken Sie auf **Momentaufnahmeoptionen**.</span><span class="sxs-lookup"><span data-stu-id="1af84-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="1af84-130">Aktivieren Sie das Kontrollkästchen für **Folgenden Zeitplan verwenden, um dem Berichtsverlauf Momentaufnahmen hinzuzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1af84-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="1af84-131">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1af84-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="1af84-132">Wählen Sie **Berichtsspezifischer Zeitplan**aus.</span><span class="sxs-lookup"><span data-stu-id="1af84-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="1af84-133">Geben Sie die Zeitplandetails ein, wählen Sie Start- und Enddatum für den Zeitplan aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1af84-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="1af84-134">Wählen Sie **Freigegebener Zeitplan**aus.</span><span class="sxs-lookup"><span data-stu-id="1af84-134">Select **Shared schedule**.</span></span> <span data-ttu-id="1af84-135">Wählen Sie aus der Liste den gewünschten Zeitplan aus.</span><span class="sxs-lookup"><span data-stu-id="1af84-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="1af84-136">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="1af84-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af84-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1af84-137">See Also</span></span>

- [<span data-ttu-id="1af84-138">Konfigurieren von Ausführungseigenschaften für einen Bericht &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="1af84-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="1af84-139">Öffnen und Schließen eines Berichts (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="1af84-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="1af84-140">Einschränken des Berichtsverlaufs (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="1af84-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="1af84-141">Zeitpläne</span><span class="sxs-lookup"><span data-stu-id="1af84-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="1af84-142">Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="1af84-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)