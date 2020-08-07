---
title: 'Der vertrauenswürdige Speicherort, an dem die Arbeitsmappe gespeichert wird, lässt keine externen Datenverbindungen zu. Die folgenden Verbindungen wurden nicht aktualisiert: Power Pivot-Daten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dc0cedfd-a7d0-40ef-bdd6-ea508130640a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b7f6d335eac0bec0f67012cc413f3917c50348b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608008"
---
# <a name="the-trusted-location-where-the-workbook-is-stored-does-not-allow-external-data-connections-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="3e158-103">Der vertrauenswürdige Speicherort, an dem die Arbeitsmappe gespeichert wird, lässt keine externen Datenverbindungen zu.</span><span class="sxs-lookup"><span data-stu-id="3e158-103">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="3e158-104">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="3e158-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="3e158-105">Für Excel-Arbeitsmappen, die PowerPivot-Daten enthalten, gibt Excel Services diesen Fehler zurück, wenn keine Verbindung mit eingebetteten Datenquellen hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e158-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e158-106">Details</span><span class="sxs-lookup"><span data-stu-id="3e158-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e158-107">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="3e158-107">Applies to</span></span>|<span data-ttu-id="3e158-108">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="3e158-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="3e158-109">Produktversion</span><span class="sxs-lookup"><span data-stu-id="3e158-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="3e158-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e158-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="3e158-111">Ursache</span><span class="sxs-lookup"><span data-stu-id="3e158-111">Cause</span></span>|<span data-ttu-id="3e158-112">Excel Services sind dafür konfiguriert, den externen Datenzugriff zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="3e158-112">Excel Services is configured to deny external data access.</span></span>|  
|<span data-ttu-id="3e158-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3e158-113">Message Text</span></span>|<span data-ttu-id="3e158-114">Der vertrauenswürdige Speicherort, an dem die Arbeitsmappe gespeichert wird, lässt keine externen Datenverbindungen zu.</span><span class="sxs-lookup"><span data-stu-id="3e158-114">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="3e158-115">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="3e158-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e158-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3e158-116">Explanation</span></span>  
 <span data-ttu-id="3e158-117">PowerPivot-Arbeitsmappen enthalten eingebettete Datenverbindungen.</span><span class="sxs-lookup"><span data-stu-id="3e158-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="3e158-118">Um die Interaktion mit Arbeitsmappen über Slicer und Filter zu unterstützen, müssen Excel Services so konfiguriert sein, dass der externe Datenzugriff über eingebettete Verbindungsinformationen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="3e158-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="3e158-119">Externer Datenzugriff ist zum Abrufen von PowerPivot-Daten erforderlich, die auf PowerPivot-Server in der Farm geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="3e158-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e158-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3e158-120">User Action</span></span>  
 <span data-ttu-id="3e158-121">Ändern Sie die Konfigurationseinstellungen, um eingebettete Datenquellen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="3e158-121">Change the configuration settings to allow embedded data sources.</span></span>  
  
1.  <span data-ttu-id="3e158-122">Klicken Sie in der Zentraladministration unter Anwendungsverwaltung auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="3e158-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="3e158-123">Klicken Sie auf **Excel Services-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="3e158-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="3e158-124">Klicken Sie auf **Vertrauenswürdiger Dateispeicherort**.</span><span class="sxs-lookup"><span data-stu-id="3e158-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="3e158-125">Klicken Sie auf **http://** oder den Speicherort, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3e158-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="3e158-126">Klicken Sie unter Externe Daten in **Externe Daten zulassen**auf Vertrauenswürdige Datenverbindungsbibliotheken und eingebettete Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="3e158-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="3e158-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e158-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="3e158-128">Alternativ können Sie einen neuen vertrauenswürdigen Speicherort für Websites erstellen, die PowerPivot-Arbeitsmappen enthalten, und dann die Konfigurationseinstellungen nur für diese Website ändern.</span><span class="sxs-lookup"><span data-stu-id="3e158-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="3e158-129">Weitere Informationen finden Sie unter [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="3e158-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
