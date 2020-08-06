---
title: Aktivieren der Data Quality Services-Integration in Master Data Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616117"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="43c62-102">Aktivieren der Data Quality Services-Integration in Master Data Services</span><span class="sxs-lookup"><span data-stu-id="43c62-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="43c62-103">Im [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]wird über die Data Quality Services (DQS) eine Abgleichfunktion bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="43c62-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="43c62-104">Diese Funktion muss aktiviert werden, damit sie verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="43c62-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="43c62-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="43c62-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="43c62-106">Es müssen eine [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Webanwendung und eine Datenbank vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="43c62-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="43c62-107">Die Data Quality Services-Funktion und der Data Quality-Client müssen auf der gleichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz installiert sein, auf der die MDS-Datenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="43c62-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="43c62-108">Weitere Informationen finden Sie unter [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="43c62-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="43c62-109">So aktivieren Sie die Data Quality Services-Integration</span><span class="sxs-lookup"><span data-stu-id="43c62-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="43c62-110">Öffnen Sie [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43c62-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="43c62-111">Klicken Sie im linken Bereich auf **Webkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="43c62-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="43c62-112">Wählen Sie auf der Seite **Webkonfiguration** die Website und die Webanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="43c62-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="43c62-113">Klicken Sie im Abschnitt **DQS-Integration aktivieren** auf **Integration in Data Quality Services aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="43c62-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="43c62-114">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43c62-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c62-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43c62-115">See Also</span></span>  
 <span data-ttu-id="43c62-116">[Data Quality-Abgleich im MDS-Add-in für Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="43c62-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="43c62-117">[Master Data Services-Add-In für Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="43c62-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="43c62-118">Installieren von Master Data Services</span><span class="sxs-lookup"><span data-stu-id="43c62-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
