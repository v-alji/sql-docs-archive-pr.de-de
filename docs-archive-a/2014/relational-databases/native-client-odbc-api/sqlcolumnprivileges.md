---
title: SQLColumnPrivileges | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609881"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="223a1-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="223a1-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="223a1-103">**SQLColumnPrivileges** gibt SQL_SUCCESS zurück, ob Werte für die Parameter*CatalogName*, Schema Name, *TableName*oder *ColumnName* *vorhanden sind.*</span><span class="sxs-lookup"><span data-stu-id="223a1-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="223a1-104">**SQLFetch** gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="223a1-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="223a1-105">**SQLColumnPrivileges** kann auf einem statischen Server Cursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="223a1-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="223a1-106">Der Versuch, **SQLColumnPrivileges** für einen aktualisierbaren (dynamischen oder Keyset-) Cursor auszuführen, gibt SQL_SUCCESS_WITH_INFO zurück, der angibt, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="223a1-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="223a1-107">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die Meldung von Informationen für Tabellen auf Verbindungsservern, indem er einen zweiteiligen Namen für den *CatalogName* -Parameter akzeptiert: *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="223a1-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223a1-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="223a1-108">See Also</span></span>  
 <span data-ttu-id="223a1-109">[SQLColumnPrivileges-Funktion](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="223a1-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="223a1-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="223a1-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
