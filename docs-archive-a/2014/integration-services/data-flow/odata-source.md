---
title: OData-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724818"
---
# <a name="odata-source"></a><span data-ttu-id="50b40-102">OData-Quelle</span><span class="sxs-lookup"><span data-stu-id="50b40-102">OData Source</span></span>
  <span data-ttu-id="50b40-103">Sie verwenden die OData-Quellkomponente in einem SSIS-Paket, um Daten aus den OData (Open Data Protocol)-Diensten zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="50b40-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="50b40-104">Die Komponente unterstützt die OData-Protokolle v2 und v3 sowie die ATOM- und JSON-Datenformate.</span><span class="sxs-lookup"><span data-stu-id="50b40-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50b40-105">Die OData-Quelle kann verwendet werden, um Daten aus SharePoint-Listen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="50b40-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="50b40-106">Um alle Listen auf Ihrem SharePoint-Server anzuzeigen, verwenden Sie die folgende URL: http:// \<server> /_vti_bin/listData.svc.</span><span class="sxs-lookup"><span data-stu-id="50b40-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="50b40-107">Weitere Informationen zu den URL-Konventionen in SharePoint finden Sie unter [SharePoint Foundation-REST-Schnittstelle](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="50b40-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="50b40-108">OData-Format</span><span class="sxs-lookup"><span data-stu-id="50b40-108">OData Format</span></span>  
 <span data-ttu-id="50b40-109">Die meisten OData-Dienste geben Ergebnisse in verschiedenen Formaten zurück.</span><span class="sxs-lookup"><span data-stu-id="50b40-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="50b40-110">Sie können das Format des Resultsets mithilfe der $format-Abfrageoption angeben.</span><span class="sxs-lookup"><span data-stu-id="50b40-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="50b40-111">Formate wie JSON und JSON Light sind effizienter als ATOM/XML und erzielen bei der Übertragung großer Datenmengen möglicherweise eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="50b40-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="50b40-112">In der folgenden Tabelle sind Ergebnisse aus Beispieltests dargestellt.</span><span class="sxs-lookup"><span data-stu-id="50b40-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="50b40-113">Wie Sie erkennen können, ergab der Wechsel von ATOM zu JSON einen Leistungszuwachs von 30-53% und der Wechsel von ATOM zum neuen JSON Light-Format (verfügbar in WCF Data Services 5.1) einen Leistungszuwachs von 67 %.</span><span class="sxs-lookup"><span data-stu-id="50b40-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="50b40-114">Zeilen</span><span class="sxs-lookup"><span data-stu-id="50b40-114">Rows</span></span>|<span data-ttu-id="50b40-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="50b40-115">ATOM</span></span>|<span data-ttu-id="50b40-116">JSON</span><span class="sxs-lookup"><span data-stu-id="50b40-116">JSON</span></span>|<span data-ttu-id="50b40-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="50b40-117">JSON (Light)</span></span>|  
|<span data-ttu-id="50b40-118">10000</span><span class="sxs-lookup"><span data-stu-id="50b40-118">10000</span></span>|<span data-ttu-id="50b40-119">113 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-119">113 seconds</span></span>|<span data-ttu-id="50b40-120">74 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-120">74 seconds</span></span>|<span data-ttu-id="50b40-121">68 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-121">68 seconds</span></span>|  
|<span data-ttu-id="50b40-122">1000000</span><span class="sxs-lookup"><span data-stu-id="50b40-122">1000000</span></span>|<span data-ttu-id="50b40-123">1110 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-123">1110 seconds</span></span>|<span data-ttu-id="50b40-124">853 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-124">853 seconds</span></span>|<span data-ttu-id="50b40-125">665 Sekunden</span><span class="sxs-lookup"><span data-stu-id="50b40-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="50b40-126">Die SSIS OData-Quelle verwendet ODataLib 5.5.0 zum Analysieren von OData-Feeds; sie ist in der Lage, alle von dieser Bibliothek unterstützten Formate zu lesen.</span><span class="sxs-lookup"><span data-stu-id="50b40-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50b40-127">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="50b40-127">In This Section</span></span>  
  
-   [<span data-ttu-id="50b40-128">Installieren und Deinstallieren der OData-Quellkomponente</span><span class="sxs-lookup"><span data-stu-id="50b40-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="50b40-129">Tutorial: Verwenden der odata-Quelle &#91;SSIS-&#93;</span><span class="sxs-lookup"><span data-stu-id="50b40-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="50b40-130">Ändern einer OData-Quellabfrage zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="50b40-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="50b40-131">Quellen-Editor für OData &#40;Seite „Verbindung“&#41;</span><span class="sxs-lookup"><span data-stu-id="50b40-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="50b40-132">Quellen-Editor für OData &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="50b40-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="50b40-133">Quellen-Editor für OData &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="50b40-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="50b40-134">OData-Quelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="50b40-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="50b40-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50b40-135">See Also</span></span>  
 [<span data-ttu-id="50b40-136">OData-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="50b40-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
