---
title: Berichts-Manager-URL (einheitlicher SSRS-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619558"
---
# <a name="report-manager-url-ssrs-native-mode"></a><span data-ttu-id="0ed1a-102">Berichts-Manager-URL (einheitlicher SSRS-Modus)</span><span class="sxs-lookup"><span data-stu-id="0ed1a-102">Report Manager URL (SSRS Native Mode)</span></span>
  <span data-ttu-id="0ed1a-103">Auf der Seite der Berichts-Manager-URL können Sie die URL, mit der auf den Berichts-Manager zugegriffen wird, konfigurieren bzw. ändern.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-103">Use the Report Manager URL page to configure or modify the URL used to access Report Manager.</span></span> <span data-ttu-id="0ed1a-104">Standardmäßig übernimmt die URL des Berichts-Manager das Präfix, die IP-Adresse und den Port der URL des Report Server-Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-104">By default, the Report Manager URL inherits the prefix, IP address, and port of the Report Server Web service URL.</span></span> <span data-ttu-id="0ed1a-105">Dies ist darauf zurückzuführen, dass der Berichts-Manager Front-End-Zugriff auf den Webdienst bietet, der innerhalb desselben Berichtsserver-Diensts ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-105">This is because Report Manager provides front-end access to the Web service that runs within the same Report Server service.</span></span> <span data-ttu-id="0ed1a-106">Wenn Sie die Dienstanwendungen isolieren und den Berichts-Manager für den Zugriff auf einen Report Server-Webdienst auf einem anderen Computer verwenden, müssen Sie die Datei RSReportServer.config ändern, damit der Berichts-Manager auf eine andere Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-106">If you are isolating the service applications and using Report Manager to access a Report Server Web service on a different computer, you must edit RSReportServer.config file to point Report Manager to a different instance.</span></span> <span data-ttu-id="0ed1a-107">Weitere Informationen zum Konfigurieren einer Berichts-Manager Verbindung mit einem Remote Berichts Server finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0ed1a-107">For more information about configuring a Report Manager connection to a remote report server, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="0ed1a-108">Einheitlicher [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modus.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="0ed1a-109">Wenn Sie den Berichtsserver so konfigurieren, dass er im integrierten SharePoint-Modus ausgeführt wird, erstellen Sie keine URL für den Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-109">If you are configuring the report server to run in SharePoint integrated mode, do not create a Report Manager URL.</span></span> <span data-ttu-id="0ed1a-110">Der Berichts-Manager wird auf einem Berichtsserver, der im integrierten SharePoint-Modus ausgeführt wird, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-110">Report Manager is not supported on a report server that runs in SharePoint integrated mode.</span></span> <span data-ttu-id="0ed1a-111">Wenn für den Berichts-Manager bereits eine URL vorhanden ist, ist diese nicht mehr verfügbar, sobald Sie den Berichtsserver für den integrierten SharePoint-Modus konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-111">If a URL already exists for Report Manager, it will become unavailable after you configure the report server to run in SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="0ed1a-112">Um diese Seite zu öffnen, starten Sie den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurations-Manager, und klicken Sie im Navigationsbereich auf **Berichts-Manager-URL** .</span><span class="sxs-lookup"><span data-stu-id="0ed1a-112">To open this page, start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and click **Report Manager URL** in the navigation pane.</span></span> <span data-ttu-id="0ed1a-113">Weitere Informationen zum Starten des Configuration Manager finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0ed1a-113">For more information about how to start the Configuration Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ed1a-114">Wenn der Berichts-Manager nicht aktiviert ist, können Sie auf dieser Seite keine Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-114">If Report Manager is not enabled, you cannot set options on this page.</span></span> <span data-ttu-id="0ed1a-115">Weitere Informationen zum Aktivieren von Berichts-Manager finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0ed1a-115">For more information about enabling Report Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ed1a-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="0ed1a-116">Options</span></span>  
 <span data-ttu-id="0ed1a-117">**Virtuelles Verzeichnis**</span><span class="sxs-lookup"><span data-stu-id="0ed1a-117">**Virtual Directory**</span></span>  
 <span data-ttu-id="0ed1a-118">Gibt den Namen des virtuellen Verzeichnisses für den Berichts-Manager an.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-118">Specifies the virtual directory name for Report Manager.</span></span> <span data-ttu-id="0ed1a-119">Auf einem Computer kann nur jeweils ein Name eines virtuellen Verzeichnisses für jede Instanz des Berichts-Managers vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-119">You can only have one virtual directory name for each Report Manager instance on the same computer.</span></span>  
  
 <span data-ttu-id="0ed1a-120">**URLs**</span><span class="sxs-lookup"><span data-stu-id="0ed1a-120">**URLs**</span></span>  
 <span data-ttu-id="0ed1a-121">Zeigt die für die aktuelle Berichts-Manager-Instanz definierte URL an.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-121">Displays the URL defined for the current Report Manager instance.</span></span>  
  
 <span data-ttu-id="0ed1a-122">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="0ed1a-122">**Advanced**</span></span>  
 <span data-ttu-id="0ed1a-123">Zeigt eine zusätzliche URL für die aktuelle Berichts-Manager-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="0ed1a-123">Add an additional URL for the current Report Manager instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed1a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ed1a-124">See Also</span></span>  
 <span data-ttu-id="0ed1a-125">[Konfigurieren einer URL &#40;SSRS-Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0ed1a-125">[Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0ed1a-126">[URLs in Konfigurationsdateien &#40;SSRS-Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0ed1a-126">[URLs in Configuration Files  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="0ed1a-127">Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="0ed1a-127">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
