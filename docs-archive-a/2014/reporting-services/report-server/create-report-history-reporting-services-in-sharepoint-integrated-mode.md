---
title: Erstellen eines Berichtsverlaufs (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619580"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="06322-102">Erstellen eines Berichtsverlaufs (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="06322-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="06322-103">Der Berichtsverlauf stellt eine Auflistung von Berichtsmomentaufnahmen dar, die Sie im Laufe der Zeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="06322-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="06322-104">Jede Momentaufnahme ist eine Kopie des Berichts in dem Zustand, in dem er zum Zeitpunkt der Momentaufnahme vorlag.</span><span class="sxs-lookup"><span data-stu-id="06322-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="06322-105">Er enthält das Layout und die Daten, die für den Bericht aktuell waren, als die Momentaufnahme erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="06322-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="06322-106">Renderinginformationen werden nicht mit der Momentaufnahme gespeichert.</span><span class="sxs-lookup"><span data-stu-id="06322-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="06322-107">Wenn Sie eine Momentaufnahme im Berichtsverlauf öffnen, wird er in HTML-Code im Berichts-Viewer-Webpart geöffnet.</span><span class="sxs-lookup"><span data-stu-id="06322-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="06322-108">Nachdem er gerendert wurde, können Sie ihn in andere Anwendungsformate exportieren.</span><span class="sxs-lookup"><span data-stu-id="06322-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="06322-109">Damit ein Berichtsverlauf erstellt werden kann, muss der Bericht unbeaufsichtigt ausgeführt werden können (d. h., der Bericht muss vom Berichtsserver ohne Benutzerinteraktion ausgeführt werden können).</span><span class="sxs-lookup"><span data-stu-id="06322-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="06322-110">Sie müssen über die Berechtigung zum Bearbeiten von Elementen für die Bibliothek, die den Bericht beinhaltet, verfügen.</span><span class="sxs-lookup"><span data-stu-id="06322-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="06322-111">Zum Anzeigen und Löschen des Berichtsverlaufs müssen Sie über die Berechtigung zum Anzeigen von Versionen oder zum Löschen von Versionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="06322-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="06322-112">So erstellen Sie eine Momentaufnahme oder den Berichtsverlauf</span><span class="sxs-lookup"><span data-stu-id="06322-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="06322-113">Zeigen Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="06322-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="06322-114">Klicken Sie darauf, um den Pfeil nach unten anzuzeigen, und wählen Sie dann **Berichtsverlauf anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="06322-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="06322-115">Klicken Sie auf **Neue Momentaufnahme**.</span><span class="sxs-lookup"><span data-stu-id="06322-115">Click **New Snapshot**.</span></span> <span data-ttu-id="06322-116">Ist die Schaltfläche nicht sichtbar, sind Sie nicht zum Erstellen von Momentaufnahmen im Berichtsverlauf berechtigt.</span><span class="sxs-lookup"><span data-stu-id="06322-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="06322-117">Wählen Sie die soeben erstellte Momentaufnahme in der Liste aus, um ihn anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06322-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="06322-118">Jede Momentaufnahme wird durch einen Timestamp identifiziert, der angibt, wann die Momentaufnahme erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="06322-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="06322-119">Sie können die Momentaufnahme nicht umbenennen, ihn nicht an eine andere Position verschieben und ihn nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="06322-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="06322-120">So planen Sie den Berichtsverlauf</span><span class="sxs-lookup"><span data-stu-id="06322-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="06322-121">Zeigen Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="06322-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="06322-122">Klicken Sie darauf, um den Pfeil nach unten anzuzeigen, und wählen Sie dann **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="06322-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="06322-123">Klicken Sie unter **Optionen für Verlaufsmomentaufnahmen**auf **Berichtsverlaufs-Momentaufnahmen nach einem Zeitplan erstellen**.</span><span class="sxs-lookup"><span data-stu-id="06322-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="06322-124">Wenn ein freigegebener Zeitplan vorhanden ist, der die gewünschten Zeitplaninformationen enthält, klicken Sie auf **Nach einem freigegebenen Zeitplan** , und wählen Sie den gewünschten Zeitplan aus.</span><span class="sxs-lookup"><span data-stu-id="06322-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="06322-125">Andernfalls klicken Sie auf **Nach einem benutzerdefinierten Zeitplan**, und klicken Sie dann auf **Konfigurieren** , um Optionen zum Erstellen des Berichtsverlaufs nach einem sich wiederholenden Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06322-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="06322-126">So erstellen Sie einen Berichtsverlauf, wenn Daten in einem Bericht aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="06322-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="06322-127">Zeigen Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="06322-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="06322-128">Klicken Sie darauf, um den Pfeil nach unten anzuzeigen, und wählen Sie dann **Verarbeitungsoptionen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="06322-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="06322-129">Klicken Sie unter **Optionen für Verlaufsmomentaufnahmen**auf **Alle Berichtsdaten-Momentaufnahmen im Berichtsverlauf speichern**.</span><span class="sxs-lookup"><span data-stu-id="06322-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06322-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06322-130">See Also</span></span>  
 [<span data-ttu-id="06322-131">Festlegen von Verarbeitungsoptionen &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="06322-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
