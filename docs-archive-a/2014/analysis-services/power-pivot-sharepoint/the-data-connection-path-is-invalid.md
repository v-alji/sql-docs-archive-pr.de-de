---
title: 'Der Datenverbindungspfad in der Arbeitsmappe verweist auf eine Datei auf dem lokalen Laufwerk oder entspricht einem ungültigen URI. Die folgenden Verbindungen wurden nicht aktualisiert: Power Pivot-Daten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd22e41a-0931-4d32-888a-633a3046fc5e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3349af08290e2ff659db1441d849b2afef51e95b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617309"
---
# <a name="the-data-connection-path-in-the-workbook-points-to-a-file-on-the-local-drive-or-is-an-invalid-uri-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="d9479-103">Der Datenverbindungspfad in der Arbeitsmappe verweist auf eine Datei auf dem lokalen Laufwerk oder entspricht einem ungültigen URI.</span><span class="sxs-lookup"><span data-stu-id="d9479-103">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="d9479-104">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="d9479-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="d9479-105">Für Excel-Arbeitsmappen, die PowerPivot-Daten enthalten, gibt Excel Services diesen Fehler zurück, wenn keine Verbindung mit eingebetteten Datenquellen hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9479-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9479-106">Details</span><span class="sxs-lookup"><span data-stu-id="d9479-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9479-107">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="d9479-107">Applies to</span></span>|<span data-ttu-id="d9479-108">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="d9479-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="d9479-109">Produktversion</span><span class="sxs-lookup"><span data-stu-id="d9479-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d9479-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9479-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="d9479-111">Ursache</span><span class="sxs-lookup"><span data-stu-id="d9479-111">Cause</span></span>|<span data-ttu-id="d9479-112">Excel Services werden dafür konfiguriert, nur Datenverbindungen von ODC-Dateien zuzulassen, die sich in einer vertrauenswürdigen Datenverbindungsbibliothek befinden.</span><span class="sxs-lookup"><span data-stu-id="d9479-112">Excel Services is configured to only allow data connections from .odc files that are in a trusted data connection library.</span></span>|  
|<span data-ttu-id="d9479-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d9479-113">Message Text</span></span>|<span data-ttu-id="d9479-114">Der Datenverbindungspfad in der Arbeitsmappe verweist auf eine Datei auf dem lokalen Laufwerk oder entspricht einem ungültigen URI.</span><span class="sxs-lookup"><span data-stu-id="d9479-114">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="d9479-115">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="d9479-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9479-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d9479-116">Explanation</span></span>  
 <span data-ttu-id="d9479-117">PowerPivot-Arbeitsmappen enthalten eingebettete Datenverbindungen.</span><span class="sxs-lookup"><span data-stu-id="d9479-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="d9479-118">Um die Interaktion mit Arbeitsmappen über Slicer und Filter zu unterstützen, müssen Excel Services so konfiguriert sein, dass der externe Datenzugriff über eingebettete Verbindungsinformationen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d9479-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="d9479-119">Externer Datenzugriff ist zum Abrufen von PowerPivot-Daten erforderlich, die auf PowerPivot-Server in der Farm geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="d9479-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9479-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d9479-120">User Action</span></span>  
 <span data-ttu-id="d9479-121">Ändern Sie die Konfigurationseinstellungen, um eingebettete Datenquellenverbindungen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="d9479-121">Change the configuration settings to allow embedded data source connections.</span></span>  
  
1.  <span data-ttu-id="d9479-122">Klicken Sie in der Zentraladministration unter Anwendungsverwaltung auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d9479-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="d9479-123">Klicken Sie auf **Excel Services-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="d9479-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="d9479-124">Klicken Sie auf **Vertrauenswürdiger Dateispeicherort**.</span><span class="sxs-lookup"><span data-stu-id="d9479-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="d9479-125">Klicken Sie auf **http://** oder den Speicherort, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d9479-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="d9479-126">Klicken Sie unter Externe Daten in **Externe Daten zulassen**auf Vertrauenswürdige Datenverbindungsbibliotheken und eingebettete Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="d9479-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="d9479-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9479-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="d9479-128">Alternativ können Sie einen neuen vertrauenswürdigen Speicherort für Websites erstellen, die PowerPivot-Arbeitsmappen enthalten, und dann die Konfigurationseinstellungen nur für diese Website ändern.</span><span class="sxs-lookup"><span data-stu-id="d9479-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="d9479-129">Weitere Informationen finden Sie unter [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="d9479-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
