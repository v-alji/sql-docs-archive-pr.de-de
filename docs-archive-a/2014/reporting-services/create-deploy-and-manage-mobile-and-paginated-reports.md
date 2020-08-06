---
title: Reporting Services (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695445"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="259b8-102">Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="259b8-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="259b8-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]bietet eine umfassende Palette an gebrauchsfertigen Tools und Diensten, die Sie beim Erstellen, bereitstellen und Verwalten von Berichten für Ihre Organisation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="259b8-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="259b8-104">umfasst Programmierfunktionen, mit denen die Berichtsfunktionen erweitert und angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="259b8-104">includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="259b8-105">ist eine serverbasierte Berichterstattungs Plattform, die umfassende Berichterstattungs Funktionen für eine Vielzahl von Datenquellen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="259b8-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="259b8-106">enthält einen umfassenden Satz von Tools zum Erstellen, verwalten und Übermitteln von Berichten und APIs, mit denen Entwickler die Daten-und Berichts Verarbeitung in benutzerdefinierte Anwendungen integrieren oder erweitern können.</span><span class="sxs-lookup"><span data-stu-id="259b8-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="259b8-107">Tools funktionieren in der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] -Umgebung und sind vollständig in- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Tools und-Komponenten integriert.</span><span class="sxs-lookup"><span data-stu-id="259b8-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="259b8-108">Mit [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] können Sie interaktive, tabellarische, grafische oder Freiformberichte aus relationalen, multidimensionalen oder XML-basierten Datenquellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="259b8-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="259b8-109">Berichte können eine umfangreiche Datenvisualisierung umfassen, einschließlich Diagrammen, Karten und Sparklines.</span><span class="sxs-lookup"><span data-stu-id="259b8-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="259b8-110">Sie können Berichte veröffentlichen, die Berichtsverarbeitung planen oder bedarfsgesteuert auf Berichte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="259b8-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="259b8-111">Zudem haben Sie die Möglichkeit, aus einer Vielzahl von Anzeigeformaten eine Auswahl zu treffen, Berichte in andere Anwendungen wie [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] zu exportieren und veröffentlichte Berichte zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="259b8-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="259b8-112">Die von Ihnen erstellten Berichte können über eine webbasierte Verbindung, über eine [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Anwendung oder eine SharePoint-Website angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="259b8-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="259b8-113">Sie können auch Datenwarnungen für Berichte erstellen, die auf einer SharePoint-Website veröffentlicht werden, und E-Mails bei Berichtsdatenänderungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="259b8-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="259b8-114">Weitere Informationen zu den neuen Funktionen in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] finden Sie unter [What es New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="259b8-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="259b8-115">Weitere Informationen zu anderen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Komponenten, -Tools und -Ressourcen finden Sie in der [SQL Server-Onlinedokumentation](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="259b8-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="259b8-116">Symbol " **Inhalt nach Bereichs** ![Ordner](media/hlp-16folder.gif "Ordnersymbol") Durchsuchen" [Reporting Services Berichts Server](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="259b8-117">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Reporting Services Berichte &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="259b8-118">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Berichtsdaten &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="259b8-119">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="259b8-120">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Berichts Teile in Berichts-Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="259b8-121">[Zeitpläne](subscriptions/schedules.md) für ![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol")</span><span class="sxs-lookup"><span data-stu-id="259b8-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="259b8-122">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Abonnements und Übermittlungs &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="259b8-123">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Reporting Services Daten Warnungen](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="259b8-124">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="259b8-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="259b8-125">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Reporting Services Sicherheit und Schutz](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="259b8-126">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [URL-Zugriff &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="259b8-127">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Erweiterungen &#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="259b8-128">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Reporting Services Tools](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="259b8-129">![Folder icon](media/hlp-16folder.gif "Ordnersymbol") [Fehler-und Ereignis Referenz des Ordner Symbols &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="259b8-130">![Ordnersymbol](media/hlp-16folder.gif "Ordnersymbol") [Funktionsreferenz &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="259b8-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="259b8-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="259b8-131">See Also</span></span>
 [<span data-ttu-id="259b8-132">SQL Server-Ressourcencenter</span><span class="sxs-lookup"><span data-stu-id="259b8-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


