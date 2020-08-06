---
title: Konfiguration und Verwaltung eines Berichts Servers (Reporting Services SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723602"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="aaf1f-102">Konfiguration und Verwaltung eines Berichtsservers (SharePoint-Modus von Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="aaf1f-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="aaf1f-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ist eine serverbasierte Berichts Plattform, die eine vollständige Palette an gebrauchsfertigen Tools und Diensten bereitstellt, mit denen Sie Berichte für Ihre Organisation erstellen, bereitstellen und verwalten können, sowie Programmierfunktionen, mit denen Sie Ihre Berichterstattungs Funktionen erweitern und anpassen können.</span><span class="sxs-lookup"><span data-stu-id="aaf1f-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="aaf1f-104">Sie können die Berichtsumgebung in ein SharePoint-Produkt integrieren, um die Vorteile der Zusammenarbeitsumgebung zu nutzen, die von SharePoint-Websites bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aaf1f-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aaf1f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aaf1f-105">In this section</span></span>  
 <span data-ttu-id="aaf1f-106">Die folgenden Abschnitte enthalten Informationen zu Konzepten, Bereitstellungsszenarios, Verfahren usw. zum Integrieren der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Umgebung in ein SharePoint-Produkt oder eine SharePoint-Technologie:</span><span class="sxs-lookup"><span data-stu-id="aaf1f-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="aaf1f-107">Menüoptionen in einer SharePoint-Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="aaf1f-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="aaf1f-108">Datenwarnungs-Manager für SharePoint-Benutzer</span><span class="sxs-lookup"><span data-stu-id="aaf1f-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="aaf1f-109">Erstellen und Verwalten von Abonnements für Berichtsserver im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="aaf1f-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="aaf1f-110">Aktualisieren von Anmeldeinformationen in Berichtsdatenquellen von einer SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="aaf1f-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="aaf1f-111">Verwalten von freigegebenen Datasets</span><span class="sxs-lookup"><span data-stu-id="aaf1f-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="aaf1f-112">Festlegen von Parametern für einen veröffentlichten Bericht &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="aaf1f-113">Festlegen von Verarbeitungsoptionen &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="aaf1f-114">Optionen zur Cacheaktualisierung &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="aaf1f-115">Funktion zur Reporting Services-Websitesammlung</span><span class="sxs-lookup"><span data-stu-id="aaf1f-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="aaf1f-116">Aktivieren der Berichtsserver- und Power View-Integrationsfunktionen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="aaf1f-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="aaf1f-117">Einstellungen und Funktionen für Reporting Services-Websites &#40;SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="aaf1f-118">Aktivieren des Features zur Berichtsserver-Dateisynchronisierung in der SharePoint-Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="aaf1f-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="aaf1f-119">Hinzufügen von Berichts Server-Inhaltstypen zu einer Bibliothek &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="aaf1f-120">Berichte im lokalen Modus im Vergleich mit Berichte im verbundenen Modus im Berichts-Viewer &#40;Reporting Services im SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="aaf1f-121">Hochladen von Dokumenten in eine SharePoint-Bibliothek (Reporting Services im SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="aaf1f-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="aaf1f-122">Festlegen von Verarbeitungsoptionen &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf1f-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="aaf1f-123">Allgemeinere Informationen zu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] finden Sie unter [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="aaf1f-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="aaf1f-124">Weitere Informationen zu anderen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Komponenten, -Tools und -Ressourcen finden Sie in der [SQL Server-Onlinedokumentation](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="aaf1f-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
