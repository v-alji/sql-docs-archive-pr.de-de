---
title: Hinzufügen von MSOLAP. 5 als vertrauenswürdiger Datenanbieter in Excel Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621216"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="53abc-102">Hinzufügen von MSOLAP.5 als vertrauenswürdigen Datenanbieter in Excel Services</span><span class="sxs-lookup"><span data-stu-id="53abc-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="53abc-103">MSOLAP.5 bezieht sich auf den Analysis Services OLE DB-Anbieter für SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="53abc-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="53abc-104">Excel Services müssen diesem Anbieter vertrauen, bevor es die Verbindunganforderung ermöglicht, wodurch die PowerPivot-Daten auf dem Server verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="53abc-105">Wenn Sie PowerPivot für SharePoint mithilfe des PowerPivot-Konfigurationstools konfiguriert haben, ist MSOLAP.5 möglicherweise ein vertrauenswürdiger Anbieter, da das Tool eine Aktion bietet, die diese Anforderung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="53abc-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="53abc-106">Wenn Sie jedoch die PowerShell-Zentraladministration verwenden oder die Aktion für den vertrauenswürdigen Anbieter im Konfigurationstool ausgeschlossen haben, fehlt möglicherweise der Anbieter, und Sie müssen den Anbieter jetzt bei der Konfiguration der Farm für den PowerPivot-Datenzugriff hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53abc-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="53abc-107">Sie müssen diesen Schritt für jede Excel Services-Dienstanwendung nur einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="53abc-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="53abc-108">Für jeden physischen Server, der eine PowerPivot-Datenanforderung behandelt, z. B. ein PowerPivot für SharePoint-Server oder ein Excel Services-Server, muss auf dem Computer der OLE DB-Anbieter installiert sein.</span><span class="sxs-lookup"><span data-stu-id="53abc-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="53abc-109">Eine PowerPivot für SharePoint-Installation umfasst immer den OLE DB-Anbieter. Wenn Sie die Excel Services jedoch auf einem Computer ausführen, auf dem PowerPivot für SharePoint nicht vorhanden ist, müssen Sie den Anbieter manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="53abc-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="53abc-110">Weitere Informationen finden Sie unter [Installieren des OLE DB-Anbieters für Analysis Services auf SharePoint-Servern](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="53abc-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="53abc-111">Hinzufügen eines vertrauenswürdigen Anbieters zu Excel Services</span><span class="sxs-lookup"><span data-stu-id="53abc-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="53abc-112">Klicken Sie in der Zentraladministration auf **Dienstanwendungen verwalten**und dann auf die Excel Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="53abc-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="53abc-113">Klicken Sie auf **Vertrauenswürdige Dienstanbieter**.</span><span class="sxs-lookup"><span data-stu-id="53abc-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="53abc-114">Überprüfen Sie, dass MSOLAP.5 in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="53abc-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="53abc-115">Je nach der Art der Konfiguration von PowerPivot für SharePoint wird MSOLAP.5 möglicherweise bereits vertraut.</span><span class="sxs-lookup"><span data-stu-id="53abc-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="53abc-116">Falls nicht aufgeführt, klicken Sie auf **Vertrauenswürdigen Datenanbieter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="53abc-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="53abc-117">Geben Sie unter Anbieter-ID `MSOLAP.5` ein.</span><span class="sxs-lookup"><span data-stu-id="53abc-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="53abc-118">Stellen Sie sicher, dass für den Anbietertyp OLE DB ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="53abc-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="53abc-119">Geben Sie als Anbieterbeschreibung **Microsoft OLE DB-Anbieter für OLAP Services 11.0**ein.</span><span class="sxs-lookup"><span data-stu-id="53abc-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
