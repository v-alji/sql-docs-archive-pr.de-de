---
title: Schnelle Vorwärts Cursor (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620347"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="eb79f-102">Schnelle Vorwärtscursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="eb79f-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="eb79f-103">Wenn eine Verbindung mit einer Instanz von besteht [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützt der Native Client-ODBC-Treiber Leistungsoptimierungen für schreibgeschützte Vorwärts Cursor.</span><span class="sxs-lookup"><span data-stu-id="eb79f-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="eb79f-104">Schnelle Vorwärtscursor werden vom Treiber und Server intern auf ganz ähnliche Weise implementiert wie Standardresultsets.</span><span class="sxs-lookup"><span data-stu-id="eb79f-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="eb79f-105">Neben einer hohen Leistungsfähigkeit besitzen schnelle Vorwärtscursor auch folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="eb79f-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="eb79f-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eb79f-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="eb79f-107">Die Resultsetspalten müssen an Programmvariablen gebunden sein.</span><span class="sxs-lookup"><span data-stu-id="eb79f-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="eb79f-108">Wenn der Server auf das Ende des Cursors stößt, wird der Cursor automatisch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="eb79f-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="eb79f-109">Die Anwendung muss weiterhin [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) oder [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE) aufzurufen, aber der Treiber muss nicht die Anforderung zum Schließen an den Server senden.</span><span class="sxs-lookup"><span data-stu-id="eb79f-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="eb79f-110">Damit wird ein Roundtrip durch das Netzwerk zum Server eingespart.</span><span class="sxs-lookup"><span data-stu-id="eb79f-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="eb79f-111">Anwendungen fordern mit dem treiberspezifischen Anweisungsattribut SQL_SOPT_SS_CURSOR_OPTIONS schnelle Vorwärtscursor an.</span><span class="sxs-lookup"><span data-stu-id="eb79f-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="eb79f-112">Wenn dieses auf SQL_CO_FFO festgelegt wird, werden schnelle Vorwärtscursor ohne die automatische Abrufoption aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb79f-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="eb79f-113">Wenn es auf SQL_CO_FFO_AF festgelegt wird, wird auch die automatische Abrufoption aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb79f-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="eb79f-114">Weitere Informationen zu Autofetch finden Sie unter [Verwenden von Autofetch mit ODBC-Cursorn](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="eb79f-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="eb79f-115">Schnelle Vorwärtscursor mit automatischer Abrufoption können eingesetzt werden, um kleine Resultsets mit nur einem Roundtrip zum Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="eb79f-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="eb79f-116">In den folgenden Schritten ist *n* die Anzahl der zurück zugegenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="eb79f-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="eb79f-117">Legen Sie SQL_SOPT_SS_CURSOR_OPTIONS auf SQL_CO_FFO_AF fest.</span><span class="sxs-lookup"><span data-stu-id="eb79f-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="eb79f-118">Legen Sie SQL_ATTR_ROW_ARRAY_SIZE auf *n* + 1 fest.</span><span class="sxs-lookup"><span data-stu-id="eb79f-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="eb79f-119">Binden Sie die Ergebnis Spalten an Arrays von *n* + 1 Elementen (um sicher zu sein, wenn *n* + 1 Zeilen tatsächlich abgerufen werden).</span><span class="sxs-lookup"><span data-stu-id="eb79f-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="eb79f-120">Öffnen Sie den Cursor entweder mit **SQLExecDirect** oder **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="eb79f-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="eb79f-121">Wenn der Rückgabestatus SQL_SUCCESS ist, dann wird **SQLFreeStmt** oder **SQLCloseCursor** aufgerufen, um den Cursor zu schließen.</span><span class="sxs-lookup"><span data-stu-id="eb79f-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="eb79f-122">Alle Daten für die Zeilen sind in den gebundenen Programmvariablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb79f-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="eb79f-123">Mit diesen Schritten sendet **SQLExecDirect** oder **SQLExecute** eine Anforderung zum Öffnen eines Cursors mit aktivierter Autofetch-Option.</span><span class="sxs-lookup"><span data-stu-id="eb79f-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="eb79f-124">Auf diese einzelne Anforderung vom Client, führt der Server Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="eb79f-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="eb79f-125">Er öffnet den Cursor.</span><span class="sxs-lookup"><span data-stu-id="eb79f-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="eb79f-126">Er erstellt das Resultset und sendet die Zeilen an den Client.</span><span class="sxs-lookup"><span data-stu-id="eb79f-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="eb79f-127">Weil die Rowsetgröße auf einen Wert festgelegt wurde, der um 1 größer als die Anzahl der Resultsetzeilen ist, erkennt der Server das Ende des Cursors und schließt den Cursor.</span><span class="sxs-lookup"><span data-stu-id="eb79f-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb79f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb79f-128">See Also</span></span>  
 [<span data-ttu-id="eb79f-129">Details zur Cursor Programmierung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="eb79f-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
