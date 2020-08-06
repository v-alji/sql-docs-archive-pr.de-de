---
title: Verwalten aller Datenwarnungen auf einer SharePoint-Website im Datenwarnungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721220"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="50e69-102">Verwalten aller Datenwarnungen auf einer SharePoint-Website im Datenwarnungs-Manager</span><span class="sxs-lookup"><span data-stu-id="50e69-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="50e69-103">SharePoint-Warnungsadministratoren können eine Liste der von allen Benutzern der Website erstellten Datenwarnungen und Informationen zu den Warnungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50e69-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="50e69-104">Warnungsadministratoren können auch Warnungen löschen.</span><span class="sxs-lookup"><span data-stu-id="50e69-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="50e69-105">Das folgende Bild zeigt Warnungsadministratoren die verfügbaren Funktionen im Datenwarnungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="50e69-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="50e69-106">![Warnungs-Manager für SharePoint-Websiteadministratoren](media/rs-alertmanagersite.gif "Warnungs-Manager für SharePoint-Websiteadministratoren")</span><span class="sxs-lookup"><span data-stu-id="50e69-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="50e69-107">So zeigen Sie eine Liste der von einem Websitebenutzer erstellten Warnungen an</span><span class="sxs-lookup"><span data-stu-id="50e69-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="50e69-108">Wechseln Sie zur SharePoint-Website, auf der Datenwarnungsdefinitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="50e69-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="50e69-109">Klicken Sie auf der Startseite auf **Websiteaktionen**.</span><span class="sxs-lookup"><span data-stu-id="50e69-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="50e69-110">Führen Sie einen Bildlauf zum Ende der Liste durch, und klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="50e69-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="50e69-111">Klicken Sie unter **Reporting Services**auf **Datenwarnungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="50e69-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="50e69-112">Klicken Sie neben der Liste **Warnungen anzeigen für folgenden Benutzer** auf den Pfeil nach unten, und wählen Sie den Benutzer aus, dessen Warnungen Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="50e69-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="50e69-113">Klicken Sie neben der Liste **Warnungen anzeigen für folgenden Bericht** auf den Pfeil nach unten, und wählen Sie eine bestimmte anzuzeigende Warnung aus, oder klicken Sie auf **Alle anzeigen** , um alle vom ausgewählten Benutzer erstellten Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50e69-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="50e69-114">Eine Tabelle umfasst den Namen, Berichtsnamen, Namen der Person, die die Datenwarnung erstellt hat, die Häufigkeit der Übermittlungen einer Datenwarnung, die letzte Änderung der Datenwarnungsdefinition und den Status der Datenwarnung.</span><span class="sxs-lookup"><span data-stu-id="50e69-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="50e69-115">Wenn die Datenwarnung nicht generiert oder gesendet werden kann, enthält die Statusspalte Informationen zum Fehler und hilft Ihnen bei der Behebung des Problems.</span><span class="sxs-lookup"><span data-stu-id="50e69-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="50e69-116">So löschen Sie eine Warnungsdefinition</span><span class="sxs-lookup"><span data-stu-id="50e69-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="50e69-117">Klicken Sie mit der rechten Maustaste auf die zu löschende Datenwarnung, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="50e69-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50e69-118">Nach dem Löschen der Warnung werden keine weiteren Warnmeldungen gesendet.</span><span class="sxs-lookup"><span data-stu-id="50e69-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="50e69-119">Wenn Sie jedoch die Warnungsdatenbank abfragen, stellen Sie möglicherweise fest, dass die Warnungsdefinition immer noch vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="50e69-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="50e69-120">Der Warndienst führt den Cleanup nach einem Zeitplan durch. Die Warnungsdefinition wird beim nächsten Cleanup dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="50e69-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="50e69-121">Das Standardintervall für den Cleanup beträgt 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="50e69-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="50e69-122">Dieses und andere Cleanupintervalle sind konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="50e69-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="50e69-123">Weitere Informationen finden Sie unter [Reporting Services-Datenwarnungen](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="50e69-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e69-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50e69-124">See Also</span></span>  
 <span data-ttu-id="50e69-125">[Datenwarnungs-Manager für Warnungsadministratoren](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="50e69-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="50e69-126">Reporting Services-Datenwarnungen</span><span class="sxs-lookup"><span data-stu-id="50e69-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
