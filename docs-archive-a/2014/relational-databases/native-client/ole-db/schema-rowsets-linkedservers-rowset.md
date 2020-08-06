---
title: LINKEDSERVERS-Rowset (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609852"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="f82bf-102">LINKEDSERVERS-Rowset (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f82bf-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="f82bf-103">Das **LINKEDSERVERS**-Rowset listet Organisationsdatenquellen auf, die an verteilten [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Abfragen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="f82bf-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="f82bf-104">Das **LINKEDSERVERS** -Rowset enthält die folgenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="f82bf-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="f82bf-105">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f82bf-105">Column name</span></span>|<span data-ttu-id="f82bf-106">Typindikator</span><span class="sxs-lookup"><span data-stu-id="f82bf-106">Type indicator</span></span>|<span data-ttu-id="f82bf-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f82bf-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="f82bf-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="f82bf-108">SVR_NAME</span></span>|<span data-ttu-id="f82bf-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-110">Name eines Verbindungsservers</span><span class="sxs-lookup"><span data-stu-id="f82bf-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="f82bf-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="f82bf-111">SVR_PRODUCT</span></span>|<span data-ttu-id="f82bf-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-113">Hersteller oder ein anderer Name, der den Typ des Datenspeichers identifiziert, der durch den Namen des Verbindungsservers repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="f82bf-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="f82bf-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="f82bf-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="f82bf-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-116">Der Anzeigename des OLE DB-Anbieters, der Daten vom Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82bf-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="f82bf-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="f82bf-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="f82bf-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-119">OLE DB DBPROP_INIT_DATASOURCE-Zeichenfolge, die verwendet wird, um eine Datenquelle vom Anbieter abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f82bf-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="f82bf-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="f82bf-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="f82bf-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-122">OLE DB DBPROP_INIT_PROVIDERSTRING-Wert, der verwendet wird, um eine Datenquelle vom Anbieter abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f82bf-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="f82bf-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="f82bf-123">SVR_LOCATION</span></span>|<span data-ttu-id="f82bf-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="f82bf-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="f82bf-125">OLE DB DBPROP_INIT_LOCATION-Zeichenfolge, die verwendet wird, um eine Datenquelle vom Anbieter abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f82bf-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="f82bf-126">Das Rowset wird nach SRV_NAME sortiert, und eine einzelne Einschränkung wird für SRV_NAME unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f82bf-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82bf-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f82bf-127">See Also</span></span>  
 [<span data-ttu-id="f82bf-128">Schema Rowset Support &#40;OLE DB&#41; (Schemarowset-Unterstützung &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="f82bf-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
