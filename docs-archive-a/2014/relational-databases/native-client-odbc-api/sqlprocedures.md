---
title: SQLProcedures | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622059"
---
# <a name="sqlprocedures"></a><span data-ttu-id="e2ece-102">'SQLProcedures'</span><span class="sxs-lookup"><span data-stu-id="e2ece-102">SQLProcedures</span></span>
  <span data-ttu-id="e2ece-103">Alle gespeicherten Prozeduren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] geben einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="e2ece-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="e2ece-104">**SQLProcedures** gibt SQL_PT_FUNCTION für die Resultsetspalte PROCEDURE_TYPE aus.</span><span class="sxs-lookup"><span data-stu-id="e2ece-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="e2ece-105">**SQLProcedures** gibt SQL_SUCCESS zurück, unabhängig davon, ob Werte für die Parameter *CatalogName, SchemaName* oder *ProcName* vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e2ece-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="e2ece-106">**SQLFetch** gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2ece-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="e2ece-107">**SQLProcedures** kann in einem statischen Servercursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2ece-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="e2ece-108">Wenn versucht wird, **SQLProcedures** in einem aktualisierbaren (dynamischen oder Keyset-)Cursor auszuführen, gibt der Cursor SQL_SUCCESS_WITH_INFO zurück. Das bedeutet, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2ece-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="e2ece-109">**SQLProcedures** gibt Informationen zu allen Prozeduren zurück, deren Name *ProcName* entspricht und die vom aktuellen Benutzer ausgeführt werden können bzw. für die der Benutzer die VIEW DEFINITION-Berechtigung erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="e2ece-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ece-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2ece-110">See Also</span></span>  
 <span data-ttu-id="e2ece-111">[SQLProcedures-Funktion](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="e2ece-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="e2ece-112">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="e2ece-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
