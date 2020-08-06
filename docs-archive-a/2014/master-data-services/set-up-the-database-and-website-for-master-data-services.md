---
title: Einrichten der Datenbank und Website für Master Data Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622749"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="ecf15-102">Einrichten von Datenbank und Website für Master Data Services</span><span class="sxs-lookup"><span data-stu-id="ecf15-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="ecf15-103">Verwenden Sie den [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] , um die Datenbank und Website für [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS) einzurichten</span><span class="sxs-lookup"><span data-stu-id="ecf15-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="ecf15-104">Um die Datenbank und die Website einzurichten, führen Sie die folgenden Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="ecf15-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="ecf15-105">Erstellen Sie eine Datenbank mithilfe der Seite **Daten Bank Konfiguration** in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecf15-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="ecf15-106">Weitere Informationen finden Sie auf der [Seite Daten Bank Konfiguration &#40;Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) und [Assistent zum Erstellen einer Datenbank &#40;Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ecf15-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="ecf15-107">Erstellen Sie eine neue Website, wählen Sie die Standard Website aus, oder wählen Sie eine andere vorhandene Website mithilfe der Seite **Webkonfiguration** in aus [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecf15-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="ecf15-108">Ordnen Sie dann die MDS-Datenbank der Webanwendung zu, die Sie ausgewählt oder erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ecf15-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="ecf15-109">Weitere Informationen finden Sie unter [webkonfigurationsseite &#40;Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) und [Dialog Feld "Website erstellen" &#40;Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ecf15-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="ecf15-110">Optionale Aktivieren Sie die Integration in Data Quality Services mithilfe der Seite **Webkonfiguration** in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecf15-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="ecf15-111">Weitere Informationen finden Sie unter [Web Configuration page &#40;Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) und [Aktivieren der Data Quality Services-Integration in Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecf15-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="ecf15-112">Alternativ können Sie [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] verwenden, um Einstellungen für die der MDS-Datenbank zugeordneten Webanwendungen und -dienste festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ecf15-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="ecf15-113">Beispielsweise können Sie festlegen, wie häufig Daten geladen werden oder wie oft Überprüfungs-E-Mails gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf15-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="ecf15-114">Weitere Informationen finden Sie unter [Systemeinstellungen &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecf15-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf15-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecf15-115">See Also</span></span>  
 <span data-ttu-id="ecf15-116">[Master Data Services Datenbank](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="ecf15-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 <span data-ttu-id="ecf15-117">[Master Data Manager-Webanwendung [Master Data Services]](../../2014/master-data-services/master-data-manager-web-application.md)</span><span class="sxs-lookup"><span data-stu-id="ecf15-117">[Master Data Manager Web Application](../../2014/master-data-services/master-data-manager-web-application.md)</span></span>  
  
  
