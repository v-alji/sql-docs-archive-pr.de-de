---
title: Aktivieren der Berichts Server-Dateisynchronisierung Funktion in der SharePoint-zentral Administration | Microsoft-Dokumentation
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619664"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="08a2b-102">Aktivieren des Features zur Berichtsserver-Dateisynchronisierung in der SharePoint-Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="08a2b-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="08a2b-103">Das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]-Feature zur Berichtsserver-Dateisynchronisierung verwendet SharePoint-Ereignishandler, um den Berichtsserverkatalog mit Elementen in Dokumentbibliotheken zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="08a2b-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="08a2b-104">Diese Funktion ist nützlich, wenn Benutzer veröffentlichte Berichtselemente häufig direkt in die SharePoint-Dokumentbibliotheken hochladen.</span><span class="sxs-lookup"><span data-stu-id="08a2b-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="08a2b-105">Wenn die Datei Synchronisierungs Funktion nicht aktiviert ist, werden die Inhalte weiterhin synchronisiert, aber nicht so häufig.</span><span class="sxs-lookup"><span data-stu-id="08a2b-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="08a2b-106">Das Feature zur Dateisynchronisierung kann in der SharePoint-Websiteverwaltung aktiviert werden, nachdem Sie das [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]-Add-In für SharePoint-Produkte installiert haben.</span><span class="sxs-lookup"><span data-stu-id="08a2b-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="08a2b-107">Die Funktion kann für einzelne Websites manuell aktiviert und deaktiviert werden, jedoch nicht auf Ebene der Websitesammlung.</span><span class="sxs-lookup"><span data-stu-id="08a2b-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="08a2b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="08a2b-108">Prerequisites</span></span>  
 <span data-ttu-id="08a2b-109">Das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="08a2b-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="08a2b-110">Wenn das Add-in nicht installiert ist, wird die Datei Synchronisierungs Funktion nicht in der Funktionsliste der Website angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a2b-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="08a2b-111">Um die Installation zu überprüfen, zeigen Sie die Liste der installierten Anwendungen in der [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows- **Systemsteuerung**an.</span><span class="sxs-lookup"><span data-stu-id="08a2b-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="08a2b-112">Wenn das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]-Add-In installiert ist, folgen Sie den Anweisungen in diesem Thema, um das Feature zur Berichtsserver-Dateisynchronisierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="08a2b-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="08a2b-113">So aktivieren oder deaktivieren Sie das Feature zur Berichtsserver-Dateisynchronisierung auf einer Website</span><span class="sxs-lookup"><span data-stu-id="08a2b-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="08a2b-114">Klicken Sie auf der Hauptseite der Website auf das Menü **Website Aktionen** , und klicken Sie dann auf **Website Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="08a2b-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="08a2b-115">Klicken Sie in den **Website Aktionen**auf **Website Funktionen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="08a2b-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="08a2b-116">Suchen Sie **Berichtsserver-Dateisynchronisierung** in der Liste.</span><span class="sxs-lookup"><span data-stu-id="08a2b-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="08a2b-117">Klicken Sie auf **Activate** (Aktivieren).</span><span class="sxs-lookup"><span data-stu-id="08a2b-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08a2b-118">Gehen Sie auf die gleiche Weise vor, um das Feature zur Berichtsserver-Dateisynchronisierung zu deaktivieren. Klicken Sie jedoch auf **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="08a2b-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a2b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08a2b-119">See Also</span></span>  
 <span data-ttu-id="08a2b-120">[Problembehandlung bei Berichts teilen &#40;Berichts-Generator und SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="08a2b-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="08a2b-121">[Aktivieren des Berichts Servers und Power View von Integrationsfunktionen in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="08a2b-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="08a2b-122">[Installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="08a2b-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="08a2b-123">Installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="08a2b-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
