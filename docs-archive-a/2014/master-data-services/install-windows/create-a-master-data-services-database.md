---
title: Erstellen einer Master Data Services-Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609920"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="b30cf-102">Erstellen einer Master Data Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b30cf-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="b30cf-103">Erstellen Sie eine [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank, wenn Sie zur Unterstützung der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung und des [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Webdiensts eine neuen Datenbank benötigen.</span><span class="sxs-lookup"><span data-stu-id="b30cf-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b30cf-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b30cf-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="b30cf-105">Weitere Informationen zu den Anforderungen für den Computer, auf dem die Datenbank gehostet wird, finden Sie unter [Datenbankanforderungen &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30cf-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="b30cf-106">So erstellen Sie eine Master Data Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b30cf-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="b30cf-107">Öffnen Sie [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b30cf-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="b30cf-108">Klicken Sie im linken Bereich auf **Datenbankkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b30cf-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="b30cf-109">Klicken Sie auf der Seite **Datenbankkonfiguration** auf **Datenbank erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b30cf-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="b30cf-110">Führen Sie die Schritte im Assistenten **Datenbank erstellen** aus, um die Datenbank zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b30cf-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="b30cf-111">Informationen zu den Benutzeroberflächenoptionen im Assistenten finden Sie unter [Datenbank erstellen &#40;Assistent im Konfigurations-Manager für Master Data Services&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b30cf-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b30cf-112">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b30cf-112">Next Steps</span></span>  
  
-   <span data-ttu-id="b30cf-113">Konfigurieren Sie die Systemeinstellungen für die Datenbank und die Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="b30cf-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="b30cf-114">Weitere Informationen finden Sie unter [Systemeinstellungen &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30cf-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b30cf-115">Erstellen Sie eine [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] -Webanwendung, die dieser Datenbank zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b30cf-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="b30cf-116">Weitere Informationen finden Sie unter [Erstellen einer Master Data Manager-Webanwendung &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30cf-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b30cf-117">Konfigurieren Sie einen Wartungsplan, um die Datenbank und Transaktionsprotokolle zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b30cf-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="b30cf-118">Weitere Informationen finden Sie unter [Datenbankanforderungen &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30cf-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30cf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b30cf-119">See Also</span></span>  
 [<span data-ttu-id="b30cf-120">Installieren von Master Data Services</span><span class="sxs-lookup"><span data-stu-id="b30cf-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
