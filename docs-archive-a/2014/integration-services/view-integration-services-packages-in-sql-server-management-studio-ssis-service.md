---
title: Anzeigen von Integration Services Paketen in SQL Server Management Studio (SSIS-Dienst) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695802"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="a32b8-102">Anzeigen von Integration Services-Paketen in SQL Server Management Studio (SSIS-Dienst)</span><span class="sxs-lookup"><span data-stu-id="a32b8-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="a32b8-103">In diesem Thema wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst beschrieben, ein Windows-Dienst zur Verwaltung von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paketen.</span><span class="sxs-lookup"><span data-stu-id="a32b8-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="a32b8-104">unterstützt den Dienst für die Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a32b8-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="a32b8-105">Ab [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]können Sie Objekte, z. B. Pakete, auf dem Integration Services-Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="a32b8-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="a32b8-106">In diesem Verfahren wird beschrieben, wie eine Verbindung mit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] hergestellt und eine Liste der vom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst verwalteten Pakete angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a32b8-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="a32b8-107">So stellen Sie eine Verbindung mit Integration Services her</span><span class="sxs-lookup"><span data-stu-id="a32b8-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="a32b8-108">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft SQL Server**, und klicken Sie dann auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="a32b8-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a32b8-109">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** in der Liste **Servertyp** die Option **Integration Services** aus, geben Sie im Feld **Servername** einen Servernamen an, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a32b8-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a32b8-110">Wenn Sie keine Verbindung mit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]herstellen können, wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst wahrscheinlich nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a32b8-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="a32b8-111">Wenn Sie weitere Informationen zum Status des Diensts erhalten möchten, klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft SQL Server**, zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="a32b8-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="a32b8-112">Klicken Sie im linken Bereich auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="a32b8-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="a32b8-113">Suchen Sie im rechten Bereich den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="a32b8-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="a32b8-114">Starten Sie den Dienst, wenn er nicht bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a32b8-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a32b8-115">wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a32b8-115">opens.</span></span> <span data-ttu-id="a32b8-116">Standardmäßig ist das Fenster des Objekt-Explorers geöffnet und in der unteren linken Ecke des Studios positioniert.</span><span class="sxs-lookup"><span data-stu-id="a32b8-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="a32b8-117">Ist der Objekt-Explorer nicht geöffnet, klicken Sie im Menü **Ansicht** auf **Objekt-Explorer** .</span><span class="sxs-lookup"><span data-stu-id="a32b8-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="a32b8-118">So zeigen Sie die vom Integration Services-Dienst verwalteten Pakete an</span><span class="sxs-lookup"><span data-stu-id="a32b8-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="a32b8-119">Erweitern Sie im Objekt-Explorer den Ordner Gespeicherte Pakete.</span><span class="sxs-lookup"><span data-stu-id="a32b8-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="a32b8-120">Erweitern Sie die Unterordner Gespeicherte Pakete, um die Pakete anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a32b8-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a32b8-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a32b8-121">See Also</span></span>  
 <span data-ttu-id="a32b8-122">[Paketverwaltung &#40;SSIS-Dienst&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="a32b8-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="a32b8-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a32b8-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
