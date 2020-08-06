---
title: SQLPrimaryKeys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622060"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="f7c50-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="f7c50-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="f7c50-103">Eine Tabelle kann über eine Spalte oder Spalten verfügen, die als eindeutige Zeilen Bezeichner fungieren können, und Tabellen, die ohne PRIMARY KEY-Einschränkung erstellt werden, geben ein leeres Resultset an SQLPrimaryKeys zurück.</span><span class="sxs-lookup"><span data-stu-id="f7c50-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="f7c50-104">Die ODBC-Funktion [SQLSpecialColumns meldet Zeilenbezeichnerkandidaten](sqlspecialcolumns.md) für Tabellen ohne Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f7c50-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="f7c50-105">SQLPrimaryKeys gibt SQL_SUCCESS zurück, ob Werte für die Parameter *CatalogName*, Schema Name oder *TableName* *vorhanden sind.*</span><span class="sxs-lookup"><span data-stu-id="f7c50-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="f7c50-106">SQLFetch gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7c50-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="f7c50-107">SQLPrimaryKeys kann in einem statischen Server Cursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7c50-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="f7c50-108">Der Versuch, SQLPrimaryKeys auf einem aktualisierbaren (dynamischen oder Keyset-) Cursor auszuführen, gibt SQL_SUCCESS_WITH_INFO zurück, der angibt, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f7c50-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="f7c50-109">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die Meldung von Informationen für Tabellen auf Verbindungsservern, indem er einen zweiteiligen Namen für den *CatalogName* -Parameter akzeptiert: *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="f7c50-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="f7c50-110">SQLPrimaryKeys und Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="f7c50-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="f7c50-111">Wenn das Anweisungs Attribut SQL_SOPT_SS_NAME_SCOPE den Wert SQL_SS_NAME_SCOPE_TABLE_TYPE anstelle des Standardwerts SQL_SS_NAME_SCOPE_TABLE hat, gibt SQLPrimaryKeys Informationen zu Primärschlüssel Spalten von Tabellentypen zurück.</span><span class="sxs-lookup"><span data-stu-id="f7c50-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="f7c50-112">Weitere Informationen zu SQL_SOPT_SS_NAME_SCOPE finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="f7c50-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="f7c50-113">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f7c50-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c50-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7c50-114">See Also</span></span>  
 <span data-ttu-id="f7c50-115">[SQLPrimaryKeys-Funktion](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="f7c50-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="f7c50-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="f7c50-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
