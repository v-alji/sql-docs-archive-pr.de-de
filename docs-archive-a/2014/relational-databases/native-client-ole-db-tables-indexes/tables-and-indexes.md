---
title: Tabellen und Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619080"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="fcdce-102">Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="fcdce-102">Tables and Indexes</span></span>
  <span data-ttu-id="fcdce-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die **IIndexDefinition** -und **ITableDefinition** -Schnittstellen verfügbar und ermöglicht es Consumern, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Tabellen und Indizes zu erstellen, zu ändern und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="fcdce-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="fcdce-104">Gültige Tabellen- und Indexdefinitionen hängen von der Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ab.</span><span class="sxs-lookup"><span data-stu-id="fcdce-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fcdce-105">Die Möglichkeit, Tabellen und Indizes zu erstellen oder zu löschen, hängt von den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zugriffsrechten des Benutzers der Consumeranwendung ab.</span><span class="sxs-lookup"><span data-stu-id="fcdce-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="fcdce-106">Das Löschen einer Tabelle kann durch das Vorhandensein von Beschränkungen der deklarativen referenziellen Integrität oder anderer Faktoren weiter eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="fcdce-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="fcdce-107">Die meisten Anwendungen, die auf abzielen, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwenden SQL-DMO anstelle dieser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieter Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="fcdce-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="fcdce-108">SQL-DMO steht für eine Auflistung von OLE-Automatisierungsobjekten, die alle administrativen Funktionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fcdce-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fcdce-109">Anwendungen, die auf mehrere OLE DB-Anbieter ausgerichtet sind, verwenden diese generischen OLE DB-Schnittstellen, die von den verschiedenen OLE DB-Anbietern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="fcdce-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="fcdce-110">Im anbieterspezifischen Eigenschaftensatz DBPROPSET_SQLSERVERCOLUMN definiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die folgende Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fcdce-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="fcdce-111">Eigenschafts-ID</span><span class="sxs-lookup"><span data-stu-id="fcdce-111">Property ID</span></span>|<span data-ttu-id="fcdce-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fcdce-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fcdce-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="fcdce-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="fcdce-114">Typ: VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="fcdce-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="fcdce-115">R/W: Schreiben</span><span class="sxs-lookup"><span data-stu-id="fcdce-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="fcdce-116">Default: NULL</span><span class="sxs-lookup"><span data-stu-id="fcdce-116">Default: Null</span></span><br /><br /> <span data-ttu-id="fcdce-117">Beschreibung: Diese Eigenschaft wird nur in **ITableDefinition** verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcdce-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="fcdce-118">Die in dieser Eigenschaft angegebene Zeichenfolge wird beim Erstellen einer [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcdce-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="fcdce-119">verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcdce-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="fcdce-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fcdce-120">In This Section</span></span>  
  
-   [<span data-ttu-id="fcdce-121">Erstellen von SQL Server-Tabellen</span><span class="sxs-lookup"><span data-stu-id="fcdce-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="fcdce-122">Hinzufügen einer Spalte zu einer SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="fcdce-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="fcdce-123">Entfernen einer Spalte aus einer SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="fcdce-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="fcdce-124">Löschen einer SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="fcdce-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="fcdce-125">Erstellen von SQL Server-Indizes</span><span class="sxs-lookup"><span data-stu-id="fcdce-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="fcdce-126">Löschen eines SQL Server-Index</span><span class="sxs-lookup"><span data-stu-id="fcdce-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="fcdce-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcdce-127">See Also</span></span>  
 <span data-ttu-id="fcdce-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="fcdce-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="fcdce-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcdce-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="fcdce-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcdce-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="fcdce-131">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fcdce-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
