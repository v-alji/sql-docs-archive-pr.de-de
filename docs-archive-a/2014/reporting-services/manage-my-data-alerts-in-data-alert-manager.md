---
title: Verwalten meiner Datenwarnungen im Datenwarnungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721223"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="e2dcb-102">Verwalten meiner Datenwarnungen im Datenwarnungs-Manager</span><span class="sxs-lookup"><span data-stu-id="e2dcb-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="e2dcb-103">SharePoint-Benutzer können eine Liste der Datenwarnungen, die sie erstellt haben, und Informationen zu den Warnungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="e2dcb-104">Zudem haben Benutzer die Möglichkeit, ihre Warnungen zu löschen, Warnungsdefinitionen zur Bearbeitung im Datenwarnungs-Designer zu öffnen und ihre Warnungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="e2dcb-105">Das folgende Bild zeigt die für Benutzer verfügbaren Funktionen in Datenwarnungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="e2dcb-106">![Warnungs-Manager-Funktionen für SharePoint-Benutzer](media/rs-alertmanageriw.gif "Warnungs-Manager-Funktionen für SharePoint-Benutzer")</span><span class="sxs-lookup"><span data-stu-id="e2dcb-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="e2dcb-107">So zeigen Sie eine Liste Ihrer Warnungen an</span><span class="sxs-lookup"><span data-stu-id="e2dcb-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="e2dcb-108">Wechseln Sie zur SharePoint-Bibliothek. Hier haben Sie die Berichte gespeichert, für die Sie Datenwarnungen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="e2dcb-109">Klicken Sie auf das Symbol für das Dropdownmenü zum Erweitern in einem Bericht, und klicken Sie auf **Datenwarnungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="e2dcb-110">Das folgende Bild zeigt das Dropdownmenü.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="e2dcb-111">![Öffnen des Warnungs-Managers über das Berichtskontextmenü](media/rs-openalertmanager.gif "Öffnen des Warnungs-Managers über das Berichtskontextmenü")</span><span class="sxs-lookup"><span data-stu-id="e2dcb-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="e2dcb-112">Der Datenwarnungs-Manager wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-112">Data Alert Manager opens.</span></span> <span data-ttu-id="e2dcb-113">Standardmäßig listet er die Warnungen für den in der Bibliothek ausgewählten Bericht auf.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="e2dcb-114">Klicken Sie neben der Liste **Warnungen anzeigen für folgenden Bericht** auf den Pfeil nach unten, und wählen Sie einen Bericht aus, um die zugehörigen Warnungen anzuzeigen. Klicken Sie alternativ auf **Alle anzeigen** , um alle Warnungen aufzuführen.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2dcb-115">Verfügt der ausgewählte Bericht über keine Warnungen, müssen Sie nicht zur SharePoint-Bibliothek zurückkehren, um einen Bericht mit Warnungen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="e2dcb-116">Klicken Sie stattdessen auf **Alle anzeigen** , um eine Liste mit allen Warnungen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="e2dcb-117">In einer Tabelle werden der Warnungsname, Berichtsname, Ihr Name als Ersteller der Warnung, die Nummer, mit der die Warnung gesendet wurde, die letzte Änderung der Warnungsdefinition und der Status der Warnung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="e2dcb-118">Wenn die Warnung nicht generiert oder gesendet werden kann, enthält die Statusspalte Informationen zum Fehler und hilft Ihnen bei der Behebung des Problems.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="e2dcb-119">So bearbeiten Sie eine Warnungsdefinition</span><span class="sxs-lookup"><span data-stu-id="e2dcb-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="e2dcb-120">Klicken Sie mit der rechten Maustaste auf die Datenwarnung, deren Warnungsdefinition Sie bearbeiten möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="e2dcb-121">Die Warnungsdefinition wird im Datenwarnungs-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="e2dcb-122">Weitere Informationen finden Sie unter [Bearbeiten einer Datenwarnung im Warnungs-Designer](edit-a-data-alert-in-alert-designer.md) und [Datenwarnungs-Designer](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e2dcb-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2dcb-123">Nur der Benutzer, der die Datenwarnungsdefinition erstellt hat, kann sie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2dcb-124">Wenn der Bericht und die aus dem Bericht generierten Datenfeeds geändert wurden, ist die Warnungsdefinition möglicherweise nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="e2dcb-125">Dies ist der Fall, wenn eine Spalte, auf die die Warnung in ihren Regeln verweist, aus dem Bericht gelöscht wird, der Datentyp geändert wird, die Spalte in einem anderen Datenfeed enthalten ist, oder wenn der Bericht gelöscht oder verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="e2dcb-126">Sie können eine ungültige Warnungsdefinition öffnen. Sie können sie jedoch nicht erneut speichern, sofern sie nicht gemäß der aktuellen Version des Berichtsdatenfeeds gültig ist, auf dem sie basiert.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="e2dcb-127">Weitere Informationen dazu, wie Datenfeeds aus Berichten generiert werden, finden Sie unter [Generieren von Datenfeeds aus Berichten (Berichts-Generator und SSRS)](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2dcb-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="e2dcb-128">So löschen Sie eine Warnungsdefinition</span><span class="sxs-lookup"><span data-stu-id="e2dcb-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="e2dcb-129">Klicken Sie mit der rechten Maustaste auf die zu löschende Datenwarnung, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="e2dcb-130">Wenn Sie die Warnung löschen, werden keine weiteren Warnmeldungen gesendet.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="e2dcb-131">So führen Sie eine Warnung aus</span><span class="sxs-lookup"><span data-stu-id="e2dcb-131">To run an alert</span></span>  
  
-   <span data-ttu-id="e2dcb-132">Klicken Sie mit der rechten Maustaste auf die auszuführende Datenwarnung, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="e2dcb-133">Die Warnungsinstanz wird erstellt, und die Datenwarnmeldung wird sofort gesendet – unabhängig von den Zeitplanoptionen, die Sie im Datenwarnungs-Designer angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="e2dcb-134">Beispielsweise wird eine Warnung gesendet, die so konfiguriert ist, dass sie wöchentlich und nur im Fall von Ergebnisänderungen zu senden ist.</span><span class="sxs-lookup"><span data-stu-id="e2dcb-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dcb-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2dcb-135">See Also</span></span>  
 <span data-ttu-id="e2dcb-136">[Datenwarnungs-Manager für Warnungsadministratoren](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="e2dcb-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="e2dcb-137">Reporting Services-Datenwarnungen</span><span class="sxs-lookup"><span data-stu-id="e2dcb-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
