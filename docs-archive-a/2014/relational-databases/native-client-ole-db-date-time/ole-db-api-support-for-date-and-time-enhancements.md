---
title: OLE DB-API-Unterstützung für Datums- und Uhrzeit-Erweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620850"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="db5f6-102">OLE DB-API-Unterstützung für Datums- und Uhrzeit-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="db5f6-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="db5f6-103">Die folgenden OLE DB-APIs unterstützen die erweiterten Funktionen für Datum und Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="db5f6-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="db5f6-104">Funktion</span><span class="sxs-lookup"><span data-stu-id="db5f6-104">Function</span></span>|<span data-ttu-id="db5f6-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="db5f6-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="db5f6-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="db5f6-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="db5f6-107">In der DBBINDING-Struktur wird ein Flag hinzugefügt, so dass Anwendungen zwischen den Werten `datetime`, `datetime2` und `smalldatetime` unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="db5f6-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="db5f6-108">Weitere Informationen finden Sie unter [Parameter and Rowset Metadata (Parameter- und Rowsetmetadaten)](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="db5f6-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="db5f6-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="db5f6-110">Weitere Informationen finden Sie unter [Massen Kopier Änderungen für verbesserte Datums-und Uhrzeit Typen &#40;OLE DB und ODBC-&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="db5f6-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="db5f6-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="db5f6-112">Weitere Informationen finden Sie unter [Parameter and Rowset Metadata (Parameter- und Rowsetmetadaten)](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="db5f6-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="db5f6-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="db5f6-114">Weitere Informationen finden Sie unter [Parameter and Rowset Metadata (Parameter- und Rowsetmetadaten)](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="db5f6-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="db5f6-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="db5f6-116">Weitere Informationen finden Sie unter [Parameter and Rowset Metadata (Parameter- und Rowsetmetadaten)](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="db5f6-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="db5f6-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="db5f6-118">Weitere Informationen finden Sie unter [Parameter and Rowset Metadata (Parameter- und Rowsetmetadaten)](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="db5f6-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="db5f6-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="db5f6-120">Ausführliche Informationen zu den betroffenen Schemarowsets finden Sie unter [Date and Time and Schema Rowsets (Datum, Uhrzeit und Schemarowsets)](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="db5f6-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="db5f6-121">IRowsetFastLoad</span></span>|<span data-ttu-id="db5f6-122">Diese Schnittstelle unterstützt ohne Änderungen die neuen Datums-/Uhrzeit-Typen.</span><span class="sxs-lookup"><span data-stu-id="db5f6-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="db5f6-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="db5f6-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="db5f6-124">Weitere Informationen finden Sie unter [Data Type Support for OLE DB Date and Time Improvements (Datentypunterstützung für Verbesserungen von Datum und Uhrzeit in OLE DB)](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="db5f6-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db5f6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db5f6-125">See Also</span></span>  
 [<span data-ttu-id="db5f6-126">Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="db5f6-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
