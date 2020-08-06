---
title: Sichern einer Master Data Manager-Webanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722894"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="d2dc6-102">Schützen einer Master Data Manager-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="d2dc6-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="d2dc6-103">Sie können die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung per HTTPS schützen.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2dc6-104">Für die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung kann entweder HTTP oder HTTPS verwendet werden, jedoch nicht beides.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d2dc6-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d2dc6-105">Prerequisites</span></span>  
 <span data-ttu-id="d2dc6-106">So führen Sie die Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d2dc6-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="d2dc6-107">Sie müssen Administrator auf dem Webserver sein, auf dem [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="d2dc6-108">Auf dem Webserver muss MDS installiert sein, und es muss eine Webanwendung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="d2dc6-109">Weitere Informationen finden Sie unter [Installieren von Master Data Services](install-master-data-services.md) und [Erstellen einer Master Data Manager-Webanwendung &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d2dc6-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="d2dc6-110">So schützen Sie die Master Data Manager-Webanwendung per HTTPS</span><span class="sxs-lookup"><span data-stu-id="d2dc6-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="d2dc6-111">Nachdem Sie sich vergewissert haben, dass die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung per HTTP ordnungsgemäß konfiguriert wurde, erstellen Sie in IIS ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="d2dc6-112">Weitere Informationen finden Sie unter [Konfigurieren von Serverzertifikaten in IIS 7.0](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d2dc6-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="d2dc6-113">Klicken Sie im Bereich **Verbindungen** unter **Websites**auf die Website, auf der die [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="d2dc6-114">Klicken Sie im Bereich **Aktionen** auf **Bindungen**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="d2dc6-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="d2dc6-116">Wählen Sie in der Liste die Option **https**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="d2dc6-117">Wählen Sie das SSL-Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="d2dc6-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="d2dc6-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-119">Optional.</span></span> <span data-ttu-id="d2dc6-120">Um HTTP zu entfernen, damit Benutzer nur per HTTPS auf die Website zugreifen können, klicken Sie in der Liste auf die Zeile mit **http**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="d2dc6-121">Klicken Sie auf **Entfernen** , und klicken Sie im Bestätigungsdialogfeld auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d2dc6-122">Nachdem HTTP entfernt wurde, müssen die basicHttp- und wsHttpBinding-Konfiguration geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="d2dc6-123">Klicken Sie zum Schließen des Dialogfelds **Sitebindungen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="d2dc6-124">Öffnen Sie nun die Datei web.config von *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\webapplication.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="d2dc6-125">Suchen Sie nach der Zeichenfolge `<security mode="Message">` , und ändern Sie diese in `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="d2dc6-126">Speichern und schließen Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-126">Save and close the file.</span></span> <span data-ttu-id="d2dc6-127">Wenn Sie einen Fehler erhalten, kann dies daran liegen, dass Sie die Benutzerkontensteuerung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="d2dc6-128">Weitere Informationen finden Sie unter [Deaktivieren der Benutzerkontensteuerung](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d2dc6-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="d2dc6-129">Benutzer sollten jetzt per HTTPS auf die Website zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d2dc6-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2dc6-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2dc6-130">See Also</span></span>  
 [<span data-ttu-id="d2dc6-131">Erstellen einer Master Data Manager-Webanwendung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2dc6-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
