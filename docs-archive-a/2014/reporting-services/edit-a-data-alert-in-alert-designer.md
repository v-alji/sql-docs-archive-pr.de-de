---
title: Bearbeiten einer Datenwarnung im Warnungs-Designer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719642"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="17819-102">Bearbeiten einer Datenwarnung im Warnungs-Designer</span><span class="sxs-lookup"><span data-stu-id="17819-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="17819-103">Öffnen Sie die mit dem Datenwarnungs-Manager zu bearbeitende Datenwarnungsdefinition.</span><span class="sxs-lookup"><span data-stu-id="17819-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="17819-104">Nur der Benutzer, der die Warnungsdefinition erstellt hat, kann sie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="17819-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="17819-105">Weitere Informationen zum Öffnen des Datenwarnungs-Managers finden Sie unter [Verwalten meiner Datenwarnungen im Datenwarnungs-Manager](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="17819-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="17819-106">Das folgende Bild zeigt das Kontextmenü einer Datenwarnung im Datenwarnungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="17819-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="17819-107">![Öffnen des Datenwarnungs-Designers durch Klicken auf „Edit“ (Bearbeiten)](media/rs-alertmanageriwopendesigner.gif "Öffnen des Datenwarnungs-Designers durch Klicken auf „Edit“ (Bearbeiten)")</span><span class="sxs-lookup"><span data-stu-id="17819-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="17819-108">Die folgende Prozedur enthält die Schritte zum Öffnen der Warnungsdefinition im Datenwarnungs-Designer über den Datenwarnungs-Manager, um sie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="17819-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="17819-109">So bearbeiten Sie eine Datenwarnungsdefinition mit dem Datenwarnungs-Designer</span><span class="sxs-lookup"><span data-stu-id="17819-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="17819-110">Klicken Sie im Datenwarnungs-Manager mit der rechten Maustaste auf die zu bearbeitende Datenwarnungsdefinition, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="17819-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="17819-111">Die Warnungsdefinition wird im Datenwarnungs-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="17819-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="17819-112">Aktualisieren Sie die Regeln, Zeitplaneinstellungen und E-Mail-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="17819-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="17819-113">Weitere Informationen finden Sie unter [Datenwarnungs-Designer](../../2014/reporting-services/data-alert-designer.md) und [Erstellen einer Datenwarnung im Datenwarnungs-Designer](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="17819-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="17819-114">Sie können keinen anderen Datenfeed auswählen.</span><span class="sxs-lookup"><span data-stu-id="17819-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="17819-115">Um einen anderen Datenfeed zu verwenden, erstellen Sie eine neue Datenwarnungsdefinition.</span><span class="sxs-lookup"><span data-stu-id="17819-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="17819-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="17819-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="17819-117">Wenn der Bericht und die aus dem Bericht generierten Datenfeeds geändert wurden, ist die Warnungsdefinition möglicherweise nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="17819-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="17819-118">Dies tritt auf, wenn eine Spalte, auf die die Warnungsdefinition in ihren Regeln verweist, vom Bericht gelöscht wird, den Datentyp ändert, oder wenn der Bericht gelöscht oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="17819-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="17819-119">Sie können eine ungültige Warnungsdefinition öffnen. Sie können sie jedoch nicht erneut speichern, sofern sie nicht gemäß der aktuellen Version des Berichtsdatenfeeds gültig ist, auf dem sie basiert.</span><span class="sxs-lookup"><span data-stu-id="17819-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="17819-120">Weitere Informationen dazu, wie Datenfeeds aus Berichten generiert werden, finden Sie unter [Generieren von Datenfeeds aus Berichten (Berichts-Generator und SSRS)](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="17819-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17819-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17819-121">See Also</span></span>
 <span data-ttu-id="17819-122">[Datenwarnungs-Manager für Warnungs Administratoren](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Daten Warnungen](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="17819-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


