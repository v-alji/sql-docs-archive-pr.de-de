---
title: Veröffentlichen von Datenquellen und Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing data sources [Reporting Services]
- publishing reports [Reporting Services]
- data sources [Reporting Services], managing
ms.assetid: 3a740f8a-1060-4ec3-938b-2305b6887ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 941362afde1cfe5dd3d235c9f243fb17875adadc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696397"
---
# <a name="publishing-data-sources-and-reports"></a><span data-ttu-id="d6fb6-102">Veröffentlichen von Datenquellen und Berichten</span><span class="sxs-lookup"><span data-stu-id="d6fb6-102">Publishing Data Sources and Reports</span></span>
  <span data-ttu-id="d6fb6-103">Vor dem Veröffentlichen Ihres Berichts sollten Sie ihn in der Vorschau anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-103">Before publishing your report, you should preview the report to see how it will look when it is run.</span></span> <span data-ttu-id="d6fb6-104">Sie können die Gestaltung weiter optimieren, bis Sie mit den Ergebnissen zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-104">You can continue to refine the design until you are satisfied with the results.</span></span>  
  
 <span data-ttu-id="d6fb6-105">Nachdem Sie den Bericht entworfen und getestet haben, können Sie ihn für andere Benutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-105">After you design and test your report, you may want to share it with other individuals.</span></span> <span data-ttu-id="d6fb6-106">Um den Bericht freizugeben, müssen Sie ihn auf einem Berichtsserver oder einer SharePoint-Website veröffentlichen bzw. *bereitstellen*.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-106">To share your report, you need to publish, or *deploy*, it to a report server or SharePoint site.</span></span> <span data-ttu-id="d6fb6-107">Nachdem der Bericht veröffentlicht wurde, können Benutzer mit entsprechenden Berechtigungen für den Berichtsserver oder die SharePoint-Website den Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-107">After it has been published, individuals who have permissions to the report server or the SharePoint site can run your report.</span></span> <span data-ttu-id="d6fb6-108">Darüber hinaus kann ein Benutzer mit Administratorberechtigung für den Berichtsserver Abonnements für Ihren Bericht erstellen, sodass der Bericht regelmäßig aktualisiert und an Benutzer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-108">In addition, a person with administrator permissions on the report server can create subscriptions to your report so that the report can be updated and sent to users on a regular schedule.</span></span>  
  
 <span data-ttu-id="d6fb6-109">Wenn Sie den Bericht mithilfe einer freigegebenen Datenquelle erstellt haben, müssen Sie diese an demselben Speicherort veröffentlichen wie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-109">If you used a shared data source to create your report, you need to publish it to the same location as the report.</span></span> <span data-ttu-id="d6fb6-110">Ähnlich wie Berichte können auch freigegebene Datenquellen auf dem Berichtsserver getrennt verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-110">Like reports, shared data sources can be managed separately on the report server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6fb6-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d6fb6-111">In This Section</span></span>  
 [<span data-ttu-id="d6fb6-112">Anzeigen einer Vorschau für Berichte</span><span class="sxs-lookup"><span data-stu-id="d6fb6-112">Previewing Reports</span></span>](previewing-reports.md)  
 <span data-ttu-id="d6fb6-113">Beschreibt, wie der Bericht vor dem Veröffentlichen in der Vorschau angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-113">Describes how to preview a report before you publish it.</span></span>  
  
 [<span data-ttu-id="d6fb6-114">Veröffentlichen von Berichten auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="d6fb6-114">Publishing Reports to a Report Server</span></span>](publishing-reports-to-a-report-server.md)  
 <span data-ttu-id="d6fb6-115">Beschreibt das Veröffentlichen eines Berichts auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-115">Describes how to publish a report to a report server.</span></span>  
  
 [<span data-ttu-id="d6fb6-116">Beispiele für URLs von veröffentlichten Berichtselementen auf einem Berichtsserver im SharePoint-Modus &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6fb6-116">URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;</span></span>](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)  
 <span data-ttu-id="d6fb6-117">Beschreibt das Veröffentlichen eines Berichts auf einer SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="d6fb6-117">Describes how to publish a report to a SharePoint site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6fb6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6fb6-118">See Also</span></span>  
 <span data-ttu-id="d6fb6-119">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-119">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="d6fb6-120">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-120">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="d6fb6-121">[Seiten Layout und Rendering &#40;Berichts-Generator und SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-121">[Page Layout and Rendering &#40;Report Builder and SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6fb6-122">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-122">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="d6fb6-123">[Suchen, anzeigen und Verwalten von Berichten &#40;Berichts-Generator und SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-123">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6fb6-124">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6fb6-124">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d6fb6-125">Drucken von Berichten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6fb6-125">Print Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/print-reports-report-builder-and-ssrs.md)  
  
  
