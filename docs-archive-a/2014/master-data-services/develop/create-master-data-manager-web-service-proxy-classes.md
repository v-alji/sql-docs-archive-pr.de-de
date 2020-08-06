---
title: Erstellen von Proxyklassen für den Master Data Manager-Webdienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630682"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="25552-102">Erstellen von Proxyklassen für den Master Data Manager-Webdienst</span><span class="sxs-lookup"><span data-stu-id="25552-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="25552-103">Der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webdienst ermöglicht die programmgesteuerte Verwendung der Funktionen von [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] an jedem Computer, der auf die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Website zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="25552-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="25552-104">Vor dem Schreiben des Codes für den Zugriff auf den Webdienst sind Proxyklassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25552-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="25552-105">Die Hauptproxyklasse, mit der Sie Webdienstvorgänge ausführen, ist die <xref:Microsoft.MasterDataServices.ServiceClient>-Klasse, welche die <xref:Microsoft.MasterDataServices.IService>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="25552-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="25552-106">Aktivieren der Veröffentlichung von Webdienst-Metadaten</span><span class="sxs-lookup"><span data-stu-id="25552-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="25552-107">Bevor Sie Proxyklassen generieren können, ist die Veröffentlichung der Webdienst-Metadaten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="25552-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="25552-108">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="25552-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="25552-109">Öffnen Sie die Datei „Web.config“ von [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="25552-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="25552-110">Diese Datei befindet sich im Ordner "WebApplication" des [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]-Installationspfads.</span><span class="sxs-lookup"><span data-stu-id="25552-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="25552-111">Suchen Sie den `mdsWsHttpBehavior` Abschnitt unter **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="25552-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="25552-112">Legen Sie für das- **\<serviceMetadata>** Element `httpGetEnabled` auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="25552-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25552-113">Wenn Sie Webdienste über Secure Sockets Layer (SSL) aktivieren möchten, legen Sie im Abschnitt `httpsGetEnabled` der Datei web.config `true` auf `mdsWsHttpBehavior` fest.</span><span class="sxs-lookup"><span data-stu-id="25552-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="25552-114">Sie müssen außerdem `mdsWsHTTPBinding` ändern, damit auch hier eine Konfiguration für SSL vorliegt, und den Nicht-SSL-Abschnitt auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="25552-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="25552-115">Speichern Sie die an der Datei vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="25552-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="25552-116">Testen Sie die Metadaten-Veröffentlichung durch Navigieren zur Dienst-URL, beispielsweise: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="25552-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="25552-117">Ist die Metadaten-Veröffentlichung aktiviert, wird eine Seite angezeigt. Diese beginnt mit:</span><span class="sxs-lookup"><span data-stu-id="25552-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="25552-118">„You have created a service.“ (Sie haben einen Dienst erstellt.)</span><span class="sxs-lookup"><span data-stu-id="25552-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="25552-119">Erstellen von Proxyklassen mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25552-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="25552-120">Ist Visual Studio 2010 installiert, lassen sich Proxyklassen am einfachsten durch das Hinzufügen eines **Dienstverweises** zum Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="25552-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="25552-121">Die Adresse des Dienstverweises ist die URL der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]-Webanwendung, wobei "/service/service.svc" angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="25552-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="25552-122">Beispiel: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="25552-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="25552-123">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen, Aktualisieren oder Entfernen eines Dienstverweises](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="25552-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="25552-124">Erstellen von Proxyklassen mit "Svcutil.exe"</span><span class="sxs-lookup"><span data-stu-id="25552-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="25552-125">Sie müssen entweder [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] oder den [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installiert haben, damit Svcutil.exe auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25552-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="25552-126">Wenn Sie [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] verwenden, müssen Sie den Befehl über die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="25552-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="25552-127">Weitere Informationen finden Sie unter [ServiceModel Metadata Utility-Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) und [Generieren eines WCF-Clients aus Dienstmetadaten](https://go.microsoft.com/fwlink/?LinkId=164821).</span><span class="sxs-lookup"><span data-stu-id="25552-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="25552-128">Verwenden Sie zum Erstellen mehrerer C#-Proxyklassen mit "Svcutil.exe" einen Befehl wie folgt:</span><span class="sxs-lookup"><span data-stu-id="25552-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="25552-129">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="25552-129">Where:</span></span>  
  
-   <span data-ttu-id="25552-130">*servername*:*port* entspricht dem Computernamen und der Portnummer des Computers, auf dem [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="25552-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="25552-131">*virtual_path* ist der virtuelle Pfad von [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in den Internetinformationsdiensten (IIS).</span><span class="sxs-lookup"><span data-stu-id="25552-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="25552-132">*proxy_name* ist der Name für die generierte Proxydatei.</span><span class="sxs-lookup"><span data-stu-id="25552-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25552-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25552-133">See Also</span></span>  
 [<span data-ttu-id="25552-134">Kategorisierte Webdienstvorgänge &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="25552-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
