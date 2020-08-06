---
title: Zuordnen einer Master Data Services-Datenbank und -Webanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696910"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="da217-102">Zuordnen einer Master Data Services-Datenbank und -Webanwendung</span><span class="sxs-lookup"><span data-stu-id="da217-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="da217-103">Ordnen Sie die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung einer [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank zu, um die für Webvorgänge verwendete Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="da217-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da217-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="da217-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="da217-105">muss auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="da217-105">must be installed on the local computer.</span></span> <span data-ttu-id="da217-106">Weitere Informationen finden Sie unter [Installieren von Master Data Services](install-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="da217-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="da217-107">Eine lokale [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="da217-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="da217-108">Weitere Informationen finden Sie unter [Erstellen einer Master Data Manager-Webanwendung &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="da217-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="da217-109">Eine lokale oder eine [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Remotedatenbank muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="da217-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="da217-110">Weitere Informationen finden Sie unter [Erstellen einer Master Data Services-Datenbank](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="da217-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="da217-111">So ordnen Sie eine Master Data Services-Datenbank und -Webanwendung zu</span><span class="sxs-lookup"><span data-stu-id="da217-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="da217-112">Öffnen Sie [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da217-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="da217-113">Klicken Sie im linken Bereich auf **Webkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="da217-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="da217-114">Wählen Sie auf der Seite **Webkonfiguration** unter **Webanwendung**aus der Liste **Website** die Website aus, in der die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="da217-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="da217-115">Wählen Sie im Feld **Webanwendung** die Webanwendung aus, die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]hostet.</span><span class="sxs-lookup"><span data-stu-id="da217-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="da217-116">Klicken Sie unter **Anwendung einer Datenbank zuordnen**auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="da217-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="da217-117">Das Dialogfeld **Verbindung mit Datenbank herstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="da217-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="da217-118">Geben Sie Verbindungsinformationen für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an, die die [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank hostet, und klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="da217-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="da217-119">Wählen Sie aus der Liste **Master Data Services-Datenbank** die Datenbank aus, der Sie die Webanwendung zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da217-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="da217-120">Überprüfen Sie unter **Anwendung einer Datenbank zuordnen**, ob die Instanz- und Datenbankinformationen korrekt sind, und klicken Sie dann auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="da217-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="da217-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="da217-121">Next Steps</span></span>  
  
-   <span data-ttu-id="da217-122">Beim Erstellen der Webanwendung wird automatisch der programmgesteuerte Zugriff auf die [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Webdienste aktiviert.</span><span class="sxs-lookup"><span data-stu-id="da217-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="da217-123">Damit Entwickler Zugriff auf die Dienstmetadaten erhalten, um auf einfache Weise Proxyklassen für den programmgesteuerten Zugriff zu generieren, sollten Sie die Veröffentlichung von Metadaten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="da217-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="da217-124">Weitere Informationen finden Sie unter [Erstellen von Proxyklassen für den Master Data Manager-Webdienst](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="da217-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="da217-125">Fügen Sie [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]Benutzer und Gruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="da217-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="da217-126">Wenn keinen Benutzern oder Gruppen Zugriff auf [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]gewährt wurde, müssen Sie [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] mithilfe der Anmeldeinformationen für den [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Systemadministrator öffnen.</span><span class="sxs-lookup"><span data-stu-id="da217-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="da217-127">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../administrators-master-data-services.md) und [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md) (Benutzer und Gruppen [Master Data Services]).</span><span class="sxs-lookup"><span data-stu-id="da217-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da217-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da217-128">See Also</span></span>  
 <span data-ttu-id="da217-129">[Installieren von Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="da217-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="da217-130">Webkonfiguration &#40;Seite im Konfigurations-Manager für Master Data Sevices&#41;</span><span class="sxs-lookup"><span data-stu-id="da217-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
