---
title: DISCOVER_XEVENT_TRACE_DEFINITION-Rowset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: e1ce2d2d-f994-4318-801a-ee0385aecd84
author: minewiskan
ms.author: owend
ms.openlocfilehash: bedd6ec66a188738ac9a522b4802b3b431e82f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718886"
---
# <a name="discover_xevent_trace_definition-rowset"></a><span data-ttu-id="3e38d-102">DISCOVER_XEVENT_TRACE_DEFINITION-Rowset</span><span class="sxs-lookup"><span data-stu-id="3e38d-102">DISCOVER_XEVENT_TRACE_DEFINITION Rowset</span></span>
  <span data-ttu-id="3e38d-103">Stellt Informationen über die derzeit aktiven XEvent-Ablaufverfolgungen auf dem Server bereit.</span><span class="sxs-lookup"><span data-stu-id="3e38d-103">Provides information about XEvent traces that are currently active on the server.</span></span>  
  
 <span data-ttu-id="3e38d-104">**Gilt für:** tabellarische und mehrdimensionale Modelle</span><span class="sxs-lookup"><span data-stu-id="3e38d-104">**Applies to:** tabular models, multidimensional models</span></span>  
  
## <a name="rowset-columns"></a><span data-ttu-id="3e38d-105">Rowsetspalten</span><span class="sxs-lookup"><span data-stu-id="3e38d-105">Rowset Columns</span></span>  
 <span data-ttu-id="3e38d-106">Das `DISCOVER_XEVENT_TRACE_DEFINITION`-Rowset enthält die folgenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="3e38d-106">The `DISCOVER_XEVENT_TRACE_DEFINITION` rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="3e38d-107">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3e38d-107">Column name</span></span>|<span data-ttu-id="3e38d-108">Typindikator</span><span class="sxs-lookup"><span data-stu-id="3e38d-108">Type indicator</span></span>|<span data-ttu-id="3e38d-109">Länge</span><span class="sxs-lookup"><span data-stu-id="3e38d-109">Length</span></span>|<span data-ttu-id="3e38d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e38d-110">Description</span></span>|  
|-----------------|--------------------|------------|-----------------|  
|`Data`|`DBTYPE_WSTR`||<span data-ttu-id="3e38d-111">Die XML-Definition der XEvent-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="3e38d-111">The XML definition of the XEvent trace.</span></span>|  
  
 <span data-ttu-id="3e38d-112">Dieses Schemarowset ist nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="3e38d-112">This schema rowset is not sorted.</span></span>  
  
## <a name="using-adomdnet-to-return-the-rowset"></a><span data-ttu-id="3e38d-113">Verwenden von ADOMD.NET zum Zurückgeben des Rowsets</span><span class="sxs-lookup"><span data-stu-id="3e38d-113">Using ADOMD.NET to return the rowset</span></span>  
 <span data-ttu-id="3e38d-114">Wenn Sie Metadaten mithilfe von ADOMD.NET und des Schemarowsets abrufen, können Sie entweder die GUID verwenden oder eine Referenz für ein Schemarowsetobjekt in der GetSchemaDataSet-Methode herstellen.</span><span class="sxs-lookup"><span data-stu-id="3e38d-114">When using ADOMD.NET and the schema rowset to retrieve metadata, you can use either the GUID or string to reference a schema rowset object in the GetSchemaDataSet method.</span></span> <span data-ttu-id="3e38d-115">Weitere Informationen finden Sie unter [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span><span class="sxs-lookup"><span data-stu-id="3e38d-115">For more information, see [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span></span>  
  
 <span data-ttu-id="3e38d-116">Die folgende Tabelle enthält die GUID und die Zeichenfolgenwerte, die dieses Rowset identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3e38d-116">The following table provides the GUID and string values that identify this rowset.</span></span>  
  
|<span data-ttu-id="3e38d-117">Argument</span><span class="sxs-lookup"><span data-stu-id="3e38d-117">Argument</span></span>|<span data-ttu-id="3e38d-118">Wert</span><span class="sxs-lookup"><span data-stu-id="3e38d-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="3e38d-119">GUID</span><span class="sxs-lookup"><span data-stu-id="3e38d-119">GUID</span></span>|<span data-ttu-id="3e38d-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span><span class="sxs-lookup"><span data-stu-id="3e38d-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span></span>|  
|<span data-ttu-id="3e38d-121">String</span><span class="sxs-lookup"><span data-stu-id="3e38d-121">String</span></span>|<span data-ttu-id="3e38d-122">DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e38d-122">DISCOVER_XEVENT_TRACE_DEFINITION</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e38d-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e38d-123">See Also</span></span>  
 <span data-ttu-id="3e38d-124">[XML for Analysis Schemarowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span><span class="sxs-lookup"><span data-stu-id="3e38d-124">[XML for Analysis Schema Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span></span>  
 <span data-ttu-id="3e38d-125">[Verwenden Sie SQL Server erweiterte Ereignisse &#40;xevents-&#41; zum Überwachen von Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="3e38d-125">[Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span></span>  
 [<span data-ttu-id="3e38d-126">Verwenden von dynamischen Verwaltungssichten &#40;DMVs&#41; zum Überwachen von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3e38d-126">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
  
