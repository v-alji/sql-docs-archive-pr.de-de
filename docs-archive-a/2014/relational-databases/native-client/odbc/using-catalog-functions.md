---
title: Verwenden von Katalog Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621478"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="f7b92-102">Verwenden von Katalogfunktionen</span><span class="sxs-lookup"><span data-stu-id="f7b92-102">Using Catalog Functions</span></span>
  <span data-ttu-id="f7b92-103">Alle Datenbanken verfügen über eine Struktur, die die in der Datenbank gespeicherten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="f7b92-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="f7b92-104">Eine Definition dieser Struktur ist zusammen mit anderen Informationen, wie beispielsweise Berechtigungen, in einem Katalog gespeichert, der als Satz Systemtabellen implementiert und auch als Datenwörterbuch bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f7b92-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="f7b92-105">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber ermöglicht einer Anwendung die Bestimmung der Datenbankstruktur durch Aufrufe von ODBC-Katalog Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f7b92-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="f7b92-106">Katalogfunktionen geben Informationen in Resultsets zurück und werden mithilfe von gespeicherten Katalogprozeduren implementiert, um die Systemtabellen im Katalog abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f7b92-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="f7b92-107">Beispielsweise könnte eine Anwendung ein Resultset mit Informationen über alle Tabellen im System oder alle Spalten in einer bestimmten Tabelle anfordern.</span><span class="sxs-lookup"><span data-stu-id="f7b92-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="f7b92-108">Die standardmäßigen ODBC-Katalogfunktionen dienen dazu, Kataloginformationen von der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz abzurufen, mit der die Anwendung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f7b92-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f7b92-109">unterstützt verteilte Abfragen, in denen auf Daten aus mehreren heterogenen OLE DB-Datenquellen in einer einzigen Abfrage zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="f7b92-109">supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="f7b92-110">Eine Methode des Zugriffs auf eine OLE DB-Datenquelle ist die Definition der Datenquelle als Verbindungsserver.</span><span class="sxs-lookup"><span data-stu-id="f7b92-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="f7b92-111">Dies kann mit [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f7b92-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="f7b92-112">Nachdem der Verbindungsserver definiert wurde, kann in Transact-SQL-Anweisungen auf Objekte dieses Servers verwiesen werden. Dazu wird ein vierteiliger Name verwendet:</span><span class="sxs-lookup"><span data-stu-id="f7b92-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="f7b92-113">*linked_server_name. catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="f7b92-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="f7b92-114">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber unterstützt zwei treiberspezifische Funktionen, die dazu dienen, Kataloginformationen von Verbindungsservern abzurufen:</span><span class="sxs-lookup"><span data-stu-id="f7b92-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="f7b92-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="f7b92-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="f7b92-116">Gibt eine Liste der auf den lokalen Servern definierten Verbindungsserver zurück.</span><span class="sxs-lookup"><span data-stu-id="f7b92-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="f7b92-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="f7b92-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="f7b92-118">Gibt eine Liste der in einem Verbindungsserver enthaltenen Kataloge zurück.</span><span class="sxs-lookup"><span data-stu-id="f7b92-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="f7b92-119">Nachdem Sie einen Verbindungs Servernamen und einen Katalognamen haben, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützt der Native Client-ODBC-Treiber das erhalten von Informationen aus dem Katalog mithilfe eines zweiteiligen namens _linked_server_name_**.** _Katalog_ für *CatalogName* in den folgenden ODBC-Katalog Funktionen:</span><span class="sxs-lookup"><span data-stu-id="f7b92-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="f7b92-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="f7b92-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="f7b92-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="f7b92-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="f7b92-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="f7b92-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="f7b92-123">**'SQLStatistics'**</span><span class="sxs-lookup"><span data-stu-id="f7b92-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="f7b92-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="f7b92-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="f7b92-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="f7b92-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="f7b92-126">Der zweiteilige _linked_server_name_**.** _catalog_ wird auch für " *f-CatalogName* " und " *PKCatalogName* " in " [sqlfremdnkeys](../../native-client-odbc-api/sqlforeignkeys.md)" unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f7b92-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="f7b92-127">Zur Verwendung von SQLLinkedServers und SQLLinkedCatalogs sind die folgenden Dateien erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f7b92-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="f7b92-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="f7b92-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="f7b92-129">Enthält Funktionsprototypen und Konstantendefinitionen für die Verbindungsserverkatalogfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f7b92-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="f7b92-130">sqlncli.h muss in der ODBC-Anwendung enthalten sein und im Includepfad angegeben werden, wenn die Anwendung kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="f7b92-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="f7b92-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="f7b92-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="f7b92-132">Muss im Bibliothekspfad des Linkers enthalten sein und als zu verknüpfende Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7b92-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="f7b92-133">sqlncli11.lib wird zusammen mit dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7b92-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="f7b92-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="f7b92-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="f7b92-135">Muss zur Ausführungszeit verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="f7b92-135">Must be present at execution time.</span></span> <span data-ttu-id="f7b92-136">sqlncli11.dll wird mit dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ODBC-Treiber von Native Client verteilt.</span><span class="sxs-lookup"><span data-stu-id="f7b92-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b92-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7b92-137">See Also</span></span>  
 <span data-ttu-id="f7b92-138">[SQL Server Native Client &#40;ODBC-&#41;](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="f7b92-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="f7b92-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="f7b92-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="f7b92-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="f7b92-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="f7b92-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="f7b92-144">'SQLStatistics'</span><span class="sxs-lookup"><span data-stu-id="f7b92-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  
