---
title: Verbindungen (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607876"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="4da29-102">Verbindungen (MDS-Add-I für Excel)</span><span class="sxs-lookup"><span data-stu-id="4da29-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="4da29-103">Um Daten in den [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]herunterzuladen, müssen Sie zuerst eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="4da29-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="4da29-104">Eine Verbindung ist, wie der [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Webdienst weiß, mit welcher MDS-Datenbank eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4da29-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="4da29-105">Die Verbindungszeichenfolge ist normalerweise die URL der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]-Webanwendung, z.B. http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="4da29-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="4da29-106">Jedes Mal, wenn Sie Excel starten, müssen Sie eine Verbindung mit einem MDS-Repository herstellen.</span><span class="sxs-lookup"><span data-stu-id="4da29-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="4da29-107">Die einzige Ausnahme ist, wenn das aktive Arbeitsblatt bereits von MDS verwaltete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="4da29-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="4da29-108">In diesem Fall wird jedes Mal automatisch eine Verbindung hergestellt, wenn Sie Daten im Blatt aktualisieren oder veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4da29-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="4da29-109">Sie können mehrere Verbindungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="4da29-109">You can create multiple connections.</span></span> <span data-ttu-id="4da29-110">Die Verbindung, auf die zuletzt zugegriffen wurde, wird als Standard angesehen.</span><span class="sxs-lookup"><span data-stu-id="4da29-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="4da29-111">Es können gleichzeitig mehrere Benutzer verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="4da29-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="4da29-112">Konflikte können jedoch entstehen, wenn mehrere Benutzer versuchen, die gleichen Daten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4da29-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="4da29-113">Weitere Informationen finden Sie unter [Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4da29-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="4da29-114">Herstellen einer automatischen Verbindung und Laden von häufig verwendeten Daten</span><span class="sxs-lookup"><span data-stu-id="4da29-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="4da29-115">Wenn Sie immer eine Verbindung mit dem gleichen Server herstellen und den gleichen Satz Daten laden möchten, können Sie Shortcutabfragedateien erstellen, die Verbindungs- und Filterinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4da29-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="4da29-116">Weitere Informationen zu Abfragedateien finden Sie unter [Shortcutabfragedateien &#40;MDS-Add-In für Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4da29-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="4da29-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="4da29-117">Data Quality Services</span></span>  
 <span data-ttu-id="4da29-118">Der [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] hat die Data Quality Services-Funktionalität, mit der Sie Daten vor dem Veröffentlichen im MDS-Repository zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="4da29-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="4da29-119">Wenn Sie eine Verbindung herstellen und eine DQS-Datenbank auf der gleichen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wie die MDS-Datenbank installiert wird, können Sie DQS-Schaltflächen im Menüband anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4da29-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="4da29-120">Wenn die Datenbank DQS_Main nicht in der Instanz vorhanden ist, werden diese Schaltflächen nicht angezeigt und die Datenqualitätsfunktionalität ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da29-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="4da29-121">Fehlerbehandlung von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4da29-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="4da29-122">Wenn Sie eine Verbindung mit MDS herstellen, finden Sie unter [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) Tipps zur Problembehandlung Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4da29-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4da29-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4da29-123">Related Tasks</span></span>  
  
|<span data-ttu-id="4da29-124">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4da29-124">Task Description</span></span>|<span data-ttu-id="4da29-125">Thema</span><span class="sxs-lookup"><span data-stu-id="4da29-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4da29-126">Herstellen einer Verbindung mit einer [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank</span><span class="sxs-lookup"><span data-stu-id="4da29-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="4da29-127">Herstellen einer Verbindung mit einem MDS-Repository &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4da29-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="4da29-128">Laden Sie MDS-Daten in Excel.</span><span class="sxs-lookup"><span data-stu-id="4da29-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="4da29-129">Laden von Daten aus MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="4da29-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="4da29-130">Filtern Sie MDS-Daten, bevor Sie sie in Excel laden.</span><span class="sxs-lookup"><span data-stu-id="4da29-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="4da29-131">Daten vor dem Laden &#40;MDS-Add-in für Excel Filtern&#41;</span><span class="sxs-lookup"><span data-stu-id="4da29-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="4da29-132">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4da29-132">Related Content</span></span>  
  
-   [<span data-ttu-id="4da29-133">Daten &#40;MDS-Add-in für Excel werden geladen&#41;</span><span class="sxs-lookup"><span data-stu-id="4da29-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="4da29-134">Shortcutabfragedateien &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4da29-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="4da29-135">Master Data Services-Add-In für Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="4da29-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
