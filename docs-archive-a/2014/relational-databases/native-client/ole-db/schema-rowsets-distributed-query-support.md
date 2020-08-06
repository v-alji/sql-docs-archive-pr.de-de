---
title: Verteilte Abfrageunterstützung für Schemarowsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609854"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="f2956-102">Verteilte Abfrageunterstützung für Schemarowsets</span><span class="sxs-lookup"><span data-stu-id="f2956-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="f2956-103">Zur Unterstützung [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verteilter Abfragen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gibt die **IDBSchemaRowset** -Schnittstelle von Native Client OLE DB-Anbieter Metadaten auf Verbindungs Servern zurück.</span><span class="sxs-lookup"><span data-stu-id="f2956-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="f2956-104">Wenn die DBPROPSET_SQLSERVERSESSION-Eigenschaft SSPROP_QUOTEDCATALOGNAMES auf VARIANT_TRUE festgelegt wurde, kann für den Katalognamen ein Bezeichner in Anführungszeichen angegeben werden (beispielsweise "my.catalog").</span><span class="sxs-lookup"><span data-stu-id="f2956-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="f2956-105">Wenn die Schemarowset-Ausgabe nach Katalog eingeschränkt wird, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erkennt der Native Client OLE DB-Anbieter einen zweiteiligen Namen, der den Verbindungs Server und den Katalognamen enthält.</span><span class="sxs-lookup"><span data-stu-id="f2956-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="f2956-106">Geben Sie für die Schemarowsets in der folgenden Tabelle einen zweiteiligen Katalognamen als _linked_server_an **.** der _Katalog_ schränkt die Ausgabe in den entsprechenden Katalog des benannten Verbindungs Servers ein.</span><span class="sxs-lookup"><span data-stu-id="f2956-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="f2956-107">Schemarowset</span><span class="sxs-lookup"><span data-stu-id="f2956-107">Schema rowset</span></span>|<span data-ttu-id="f2956-108">Katalogeinschränkung</span><span class="sxs-lookup"><span data-stu-id="f2956-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="f2956-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="f2956-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="f2956-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="f2956-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="f2956-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f2956-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="f2956-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="f2956-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="f2956-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="f2956-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="f2956-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="f2956-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="f2956-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="f2956-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="f2956-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="f2956-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="f2956-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f2956-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="f2956-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="f2956-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2956-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f2956-125">Zur Beschränkung eines Schemarowsets auf alle Kataloge eines Verbindungsservers, verwenden Sie die Syntax *linked_server* (wobei der Punkt als Trennzeichen Teil der Namensangabe ist).</span><span class="sxs-lookup"><span data-stu-id="f2956-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="f2956-126">Diese Syntax ist gleichbedeutend mit der Angabe von NULL für die Katalognamensbeschränkung und wird auch verwendet, wenn der Verbindungsserver eine Datenquelle angibt, die Kataloge nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2956-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="f2956-127">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter definiert das Schemarowset LINKEDSERVERS und gibt eine Liste der OLE DB Datenquellen zurück, die als Verbindungs Server registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f2956-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2956-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2956-128">See Also</span></span>  
 <span data-ttu-id="f2956-129">[Schemarowset-Unterstützung &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="f2956-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="f2956-130">LINKEDSERVERS-Rowset &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f2956-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
