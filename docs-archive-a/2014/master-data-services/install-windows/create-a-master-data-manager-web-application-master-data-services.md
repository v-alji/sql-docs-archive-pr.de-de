---
title: Erstellen einer Master Data Manager-Webanwendung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609921"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="50842-102">Erstellen einer Master Data Manager-Webanwendung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="50842-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="50842-103">Die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung stellt eine Oberfläche für Benutzer für das Arbeiten mit Masterdaten und für Administratoren für das Konfigurieren und Verwalten von MDS bereit.</span><span class="sxs-lookup"><span data-stu-id="50842-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="50842-104">Eine Webanwendung muss immer in einer Website enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="50842-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="50842-105">Um eine Webanwendung zu erstellen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="50842-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="50842-106">Verwenden Sie die Standardwebsite, und erstellen Sie dann die Webanwendung,</span><span class="sxs-lookup"><span data-stu-id="50842-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="50842-107">Verwenden Sie eine vorhandene Website, und erstellen Sie dann die Webanwendung, oder</span><span class="sxs-lookup"><span data-stu-id="50842-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="50842-108">Erstellen Sie eine neue Website, die automatisch eine Webanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="50842-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="50842-109">Nachdem Sie die Webanwendung erstellt haben, ordnen Sie die [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank der Webanwendung zu.</span><span class="sxs-lookup"><span data-stu-id="50842-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50842-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="50842-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="50842-111">Weitere Informationen zu den Anforderungen für den Computer, auf dem die Webanwendung gehostet wird, finden Sie unter [Anforderungen für die Webanwendung &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="50842-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="50842-112">So erstellen Sie eine Master Data Manager-Webanwendung in einer neuen Website</span><span class="sxs-lookup"><span data-stu-id="50842-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="50842-113">Wenn Sie eine neue Website erstellen, ist die Stammwebanwendung die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="50842-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="50842-114">Die Webanwendung wird auch einem neuen Anwendungspool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="50842-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50842-115">Bei diesem Verfahren können Sie keinen virtuellen Pfad und Alias der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="50842-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="50842-116">Wenn Sie einen virtuellen Pfad und Alias für [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]angeben möchten, müssen Sie eine Webanwendung in einer vorhandenen Website erstellen, die noch nicht als [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="50842-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="50842-117">Darüber hinaus unterstützt [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] das Erstellen von Websites, die nur HTTP-Bindungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="50842-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="50842-118">Um eine HTTPS-Bindung hinzuzufügen, erstellen Sie eine neue Website und eine Anwendung in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] . Weitere Informationen finden Sie dann unter [Schützen einer Master Data Manager-Webanwendung](secure-a-master-data-manager-web-application.md) .</span><span class="sxs-lookup"><span data-stu-id="50842-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="50842-119">So erstellen Sie eine Master Data Manager-Webanwendung in einer neuen Website</span><span class="sxs-lookup"><span data-stu-id="50842-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="50842-120">Öffnen Sie [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50842-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="50842-121">Klicken Sie im linken Bereich auf **Webkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="50842-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="50842-122">Wählen Sie auf der Seite **Webkonfiguration** in der Liste Website die Option **Neue Website erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="50842-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="50842-123">Geben Sie im Dialogfeld **Website erstellen** Informationen für eine neue Website an.</span><span class="sxs-lookup"><span data-stu-id="50842-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="50842-124">Weitere Informationen zu den Benutzeroberflächenoptionen im Dialogfeld finden Sie unter [Website erstellen (Dialogfeld) &#40;Konfigurations-Manager für Master Data Services&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="50842-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="50842-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="50842-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="50842-126">So erstellen Sie eine Master Data Manager-Webanwendung in einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="50842-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="50842-127">Wenn Sie in einer vorhandenen Website eine Webanwendung erstellen, können Sie den virtuellen Pfad und Alias der Webanwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="50842-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="50842-128">Die Webanwendung wird einem neuen Anwendungspool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="50842-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="50842-129">So erstellen Sie eine Master Data Manager-Webanwendung in einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="50842-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="50842-130">Öffnen Sie [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50842-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="50842-131">Klicken Sie im linken Bereich auf **Webkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="50842-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="50842-132">Wählen Sie auf der Seite **Webkonfiguration** aus der Dropdownliste **Website** die Website aus, in der Sie die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="50842-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="50842-133">Klicken Sie auf **Anwendung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="50842-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="50842-134">Geben Sie im Dialogfeld **Webanwendung erstellen** Informationen für eine neue Webanwendung an.</span><span class="sxs-lookup"><span data-stu-id="50842-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="50842-135">Weitere Informationen zu den Benutzeroberflächenoptionen im Dialogfeld finden Sie unter [Webanwendung erstellen (Dialogfeld) &#40;Konfigurations-Manager für Master Data Services&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="50842-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="50842-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="50842-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="50842-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="50842-137">Next Steps</span></span>  
  
-   <span data-ttu-id="50842-138">Ordnen Sie die Webanwendung einer [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank zu.</span><span class="sxs-lookup"><span data-stu-id="50842-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="50842-139">Weitere Informationen finden Sie unter [Zuordnen einer Master Data Services-Datenbank und -Webanwendung](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="50842-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="50842-140">Wenn Sie den Inhalt mit Secure Sockets Layer (SSL) verschlüsseln möchten, können Sie die Website, die die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung hostet, optional so konfigurieren, dass diese eine HTTPS-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="50842-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="50842-141">Konfigurieren Sie das Serverzertifikat für den Webserver, eine HTTPS-Bindung und die SSL-Einstellungen für die Website mithilfe eines IIS (Internet Information Services)-Tools, z. B. IIS-Manager.</span><span class="sxs-lookup"><span data-stu-id="50842-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="50842-142">Weitere Informationen finden Sie unter [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="50842-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50842-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50842-143">See Also</span></span>  
 [<span data-ttu-id="50842-144">Installieren von Master Data Services</span><span class="sxs-lookup"><span data-stu-id="50842-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
