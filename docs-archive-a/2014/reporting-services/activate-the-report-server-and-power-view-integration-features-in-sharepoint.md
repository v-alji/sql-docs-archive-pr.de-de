---
title: Aktivieren des Berichts Servers und Power View von Integrationsfunktionen in SharePoint | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621383"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="e743a-102">Aktivieren der Berichtsserver- und Power View-Integrationsfunktionen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="e743a-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="e743a-103">Die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Website Sammlungs Funktionen werden in der Regel standardmäßig aktiviert, nachdem Sie das [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] -Add-in für SharePoint-Produkte installiert haben.</span><span class="sxs-lookup"><span data-stu-id="e743a-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="e743a-104">In einigen Situationen müssen Sie die Funktionen manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e743a-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="e743a-105">Wenn Sie nach der Installation des SharePoint-Produkts das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint 2010-Produkte installieren, werden die Berichtsserverintegrationsfunktion und die Power View-Integrationsfunktion nur für Stammwebsitesammlungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e743a-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="e743a-106">Für andere Websitesammlungen müssen Sie die Funktionen manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e743a-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="e743a-107">Wenn Sie z. B. eine Websitesammlung von **http://[Mein Servername]/Websites/[Websitesammlungsname]** besitzen, müssen Sie die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Websitesammlungsfunktionen manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e743a-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="e743a-108">Wenn keine Stammwebsitesammlung vorhanden ist, wird vom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In ungefähr folgende Meldung protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e743a-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="e743a-109">"SharePoint Web App 80 besitzt keine Stammwebsitesammlung"</span><span class="sxs-lookup"><span data-stu-id="e743a-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="e743a-110">Die Meldung befindet sich im Add-in-Installationsprotokoll mit dem Namen "RS_SP_ #. log", wobei "#" eine inkrementellen Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="e743a-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="e743a-111">Die Protokolldatei befindet sich im temporären Ordner des aktuellen Benutzers, z. b. c:\Users \\ [Benutzername] \AppData\Local\Temp. Weitere Informationen zu Protokollierungs Optionen mit dem Add-in finden Sie unter [installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="e743a-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="e743a-112">Inhalte dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="e743a-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="e743a-113">So aktivieren Sie die Websitesammlungsfunktion für die Berichtsserver- und Power View-Integration:</span><span class="sxs-lookup"><span data-stu-id="e743a-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="e743a-114">So aktivieren oder deaktivieren Sie die Websitesammlungsfunktion für die Berichtsserver-Zentraladministration:</span><span class="sxs-lookup"><span data-stu-id="e743a-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="e743a-115">So aktivieren Sie die Website Sammlungs Funktionen des Berichts Servers und der Power View-Integration:</span><span class="sxs-lookup"><span data-stu-id="e743a-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="e743a-116">Öffnen Sie den Browser für die Website, auf der die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e743a-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="e743a-117">Klicken Sie auf **Websiteaktionen**.</span><span class="sxs-lookup"><span data-stu-id="e743a-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="e743a-118">Klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e743a-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="e743a-119">Klicken Sie in der Gruppe „Websitesammlungsverwaltung“ auf **Websitesammlungs-Features** .</span><span class="sxs-lookup"><span data-stu-id="e743a-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="e743a-120">Suchen Sie in der Liste **Berichtsserver-Integrationsfunktion** oder **Funktion zur Power View-Integration** .</span><span class="sxs-lookup"><span data-stu-id="e743a-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="e743a-121">Klicken Sie auf **Activate** (Aktivieren).</span><span class="sxs-lookup"><span data-stu-id="e743a-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="e743a-122">Verwenden Sie zum Deaktivieren der Funktionen die gleiche Prozedur, klicken Sie jedoch auf **Deaktivieren** statt auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e743a-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="e743a-123">So aktivieren oder deaktivieren Sie die Website Sammlungs Funktion für Reporting Services zentral Administration:</span><span class="sxs-lookup"><span data-stu-id="e743a-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="e743a-124">Öffnen Sie den Browser für die SharePoint-Zentraladministration.</span><span class="sxs-lookup"><span data-stu-id="e743a-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="e743a-125">Klicken Sie auf **Websiteaktionen**.</span><span class="sxs-lookup"><span data-stu-id="e743a-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="e743a-126">Klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e743a-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="e743a-127">Klicken Sie in der Gruppe „Websitesammlungsverwaltung“ auf **Websitesammlungs-Features** .</span><span class="sxs-lookup"><span data-stu-id="e743a-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="e743a-128">Suchen Sie in der Liste die Funktion **Berichtsserver-Zentraladministration** .</span><span class="sxs-lookup"><span data-stu-id="e743a-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="e743a-129">Klicken Sie auf **Activate** (Aktivieren).</span><span class="sxs-lookup"><span data-stu-id="e743a-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="e743a-130">Verwenden Sie zum Deaktivieren der Funktion die gleiche Prozedur, klicken Sie jedoch auf **Deaktivieren** statt **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e743a-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e743a-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e743a-131">Next Steps</span></span>  
 <span data-ttu-id="e743a-132">Nachdem die Funktion aktiviert wurde, können Sie die Serverintegration fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="e743a-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e743a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e743a-133">See Also</span></span>  
 [<span data-ttu-id="e743a-134">Installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="e743a-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
