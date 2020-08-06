---
title: SQLTables | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617949"
---
# <a name="sqltables"></a><span data-ttu-id="56acb-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="56acb-102">SQLTables</span></span>
  <span data-ttu-id="56acb-103">SQLTables kann auf einem statischen Server Cursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="56acb-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="56acb-104">Der Versuch, SQLTables für einen aktualisierbaren (dynamischen oder Keyset-) Cursor auszuführen, gibt SQL_SUCCESS_WITH_INFO zurück, der angibt, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="56acb-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="56acb-105">SQLTables meldet Tabellen aus allen Datenbanken, wenn der *CatalogName* -Parameter SQL_ALL_CATALOGS und alle anderen Parameter Standardwerte (null-Zeiger) enthalten.</span><span class="sxs-lookup"><span data-stu-id="56acb-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="56acb-106">SQLTables verwendet zum Melden von verfügbaren Katalogen, Schemas und Tabellentypen eine besondere Verwendung leerer Zeichen folgen (Byte Zeiger der Länge 0 (null)).</span><span class="sxs-lookup"><span data-stu-id="56acb-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="56acb-107">Leere Zeichenfolgen sind keine Standardwerte (NULL-Zeiger).</span><span class="sxs-lookup"><span data-stu-id="56acb-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="56acb-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die Meldung von Informationen für Tabellen auf Verbindungsservern, indem er einen zweiteiligen Namen für den *CatalogName* -Parameter akzeptiert: *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="56acb-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="56acb-109">SQLTables gibt Informationen zu allen Tabellen zurück, deren Namen *TableName* entsprechen und deren Besitzer der aktuelle Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="56acb-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="56acb-110">'SQLTables'- und Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="56acb-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="56acb-111">Wenn das Anweisungs Attribut SQL_SOPT_SS_NAME_SCOPE den Wert SQL_SS_NAME_SCOPE_TABLE_TYPE anstelle des Standardwerts SQL_SS_NAME_SCOPE_TABLE enthält, gibt SQLTables Informationen zu Tabellentypen zurück.</span><span class="sxs-lookup"><span data-stu-id="56acb-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="56acb-112">Der TABLE_TYPE Wert, der für einen Tabellentyp in Spalte 4 des von SQLTables zurückgegebenen Resultsets zurückgegeben wird, ist der Tabellentyp.</span><span class="sxs-lookup"><span data-stu-id="56acb-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="56acb-113">Weitere Informationen zu SQL_SOPT_SS_NAME_SCOPE finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="56acb-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="56acb-114">Tabellen, Sichten und Synonyme nutzen einen gemeinsamen Namespace, der sich von dem Namespace unterscheidet, den Tabellentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="56acb-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="56acb-115">Wenngleich ein und derselbe Namespace nicht eine Tabelle und eine Sicht enthalten kann, ist es hingegen möglich, dass ein Namespace im selben Katalog und Schema eine Tabelle und einen Tabellentypen enthält.</span><span class="sxs-lookup"><span data-stu-id="56acb-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="56acb-116">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="56acb-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56acb-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56acb-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="56acb-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56acb-118">See Also</span></span>  
 <span data-ttu-id="56acb-119">[SQLTables-Funktion](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="56acb-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="56acb-120">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="56acb-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
