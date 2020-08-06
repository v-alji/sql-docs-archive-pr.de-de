---
title: Aktivieren der Power Pivot-Funktions Integration für Website Sammlungen in der zentral Administration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698577"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="340d6-102">Aktivieren der PowerPivot-Funktionsintegration für Websitesammlungen in der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="340d6-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="340d6-103">Die Integration der PowerPivot-Funktion für bestimmte Websitesammlungen muss aktiviert werden, wenn Sie die Installationsoption Vorhandene Farm zur Installation von SQL Server PowerPivot für SharePoint verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="340d6-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="340d6-104">Wenn Sie PowerPivot für SharePoint mit der Option "Neuer Server" installiert haben, können Sie diese Aufgabe überspringen, da SQL Server-Setup bereits die Funktion zur PowerPivot-Integration für die Stammwebsitesammlung aktiviert hat, als die Bereitstellung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="340d6-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="340d6-105">Die Funktionsaktivierung auf der Ebene der Websitesammlung ist erforderlich, um Ihren Websites Anwendungsseiten und Vorlagen zur Verfügung zu stellen,  einschließlich Konfigurationsseiten für geplante Datenaktualisierungen und Anwendungsseiten für PowerPivot-Katalog- und Datenfeed-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="340d6-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="340d6-106">Sie müssen die PowerPivot-Integration für jede Websitesammlung aktivieren, die die PowerPivot-Abfrageverarbeitung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="340d6-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="340d6-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="340d6-107">Prerequisites</span></span>  
 <span data-ttu-id="340d6-108">Sie müssen Administrator einer Websitesammlung sein.</span><span class="sxs-lookup"><span data-stu-id="340d6-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="340d6-109">Power Pivot-Funktionen aktivieren</span><span class="sxs-lookup"><span data-stu-id="340d6-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="340d6-110">Klicken Sie auf einer SharePoint-Website auf **Websiteaktionen**.</span><span class="sxs-lookup"><span data-stu-id="340d6-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="340d6-111">Standardmäßig wird auf SharePoint-Webanwendungen über Port 80 zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="340d6-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="340d6-112">Dies bedeutet, dass Sie häufig auf eine SharePoint-Website zugreifen können, indem Sie http://\<computer name> eingeben, um die Stammwebsitesammlung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="340d6-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="340d6-113">Klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="340d6-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="340d6-114">Klicken Sie unter Websitesammlungsverwaltung auf **Websitesammlungsfeatures**.</span><span class="sxs-lookup"><span data-stu-id="340d6-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="340d6-115">Scrollen Sie auf der Seite nach unten, bis Sie die **Funktion zur Power Pivot-Integration-Website Sammlung**</span><span class="sxs-lookup"><span data-stu-id="340d6-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="340d6-116">Klicken Sie auf **Activate** (Aktivieren).</span><span class="sxs-lookup"><span data-stu-id="340d6-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="340d6-117">Wiederholen Sie den Schritt für zusätzliche Websitesammlungen, indem Sie jede Website öffnen und auf **Websiteaktionen**klicken.</span><span class="sxs-lookup"><span data-stu-id="340d6-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340d6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="340d6-118">See Also</span></span>  
 <span data-ttu-id="340d6-119">[Power Pivot-Server Verwaltung und-Konfiguration in der zentral Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="340d6-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="340d6-120">[Anfängliche Konfiguration &#40;PowerPivot für SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="340d6-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="340d6-121">PowerPivot für SharePoint 2010-Installation</span><span class="sxs-lookup"><span data-stu-id="340d6-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
