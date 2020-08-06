---
title: Cursorrowsetgröße | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620334"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="fb25e-102">Cursorrowsetgröße</span><span class="sxs-lookup"><span data-stu-id="fb25e-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="fb25e-103">ODBC-Cursor sind nicht darauf beschränkt, nur jeweils eine Zeile abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb25e-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="fb25e-104">Sie können mehrere Zeilen in jedem-Befehl von **SQLFetch** oder [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)abrufen.</span><span class="sxs-lookup"><span data-stu-id="fb25e-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="fb25e-105">Bei einer Client-/Serverdatenbank, wie Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ist es effizienter, mehrere Zeilen gleichzeitig abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb25e-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="fb25e-106">Die Anzahl der bei einem Abruf Vorgang zurückgegebenen Zeilen wird als Rowsetgröße bezeichnet und mithilfe der SQL_ATTR_ROW_ARRAY_SIZE von [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="fb25e-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="fb25e-107">Cursor mit einer Rowsetgröße größer als 1 werden als Blockcursor bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb25e-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="fb25e-108">Es gibt zwei Optionen zum Binden von Resultsetspalten für Blockcursor:</span><span class="sxs-lookup"><span data-stu-id="fb25e-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="fb25e-109">Spaltenweises Binden</span><span class="sxs-lookup"><span data-stu-id="fb25e-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="fb25e-110">Jede Spalte wird an ein Array von Variablen gebunden.</span><span class="sxs-lookup"><span data-stu-id="fb25e-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="fb25e-111">Jedes Array verfügt über die gleiche Anzahl Elemente wie die Rowsetgröße.</span><span class="sxs-lookup"><span data-stu-id="fb25e-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="fb25e-112">Zeilen weises binden</span><span class="sxs-lookup"><span data-stu-id="fb25e-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="fb25e-113">Ein Array wird anhand von Strukturen aufgebaut, die die Daten und Indikatoren für alle Spalten in einer Zeile enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb25e-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="fb25e-114">Das Array verfügt über die gleiche Anzahl Strukturen wie die Rowsetgröße.</span><span class="sxs-lookup"><span data-stu-id="fb25e-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="fb25e-115">Wenn entweder eine spaltenweise oder zeilenweise Bindung verwendet wird, füllt jeder-Befehl von **SQLFetch** oder **SQLFetchScroll** die gebundenen Arrays mit Daten aus dem abgerufenen Rowset.</span><span class="sxs-lookup"><span data-stu-id="fb25e-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="fb25e-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) kann auch zum Abrufen von Spaltendaten aus einem Block Cursor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb25e-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="fb25e-117">Da **SQLGetData** jeweils eine Zeile verwendet, müssen **SQLSetPos** aufgerufen werden, um eine bestimmte Zeile im Rowset als aktuelle Zeile festzulegen, bevor **SQLGetData**aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb25e-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="fb25e-118">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber bietet eine Optimierung, bei der mithilfe von Rowsets ein gesamtes Resultset schnell abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb25e-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="fb25e-119">Um diese Optimierung zu verwenden, legen Sie die Cursor Attribute auf ihre Standardwerte fest (vorwärts, schreibgeschützt, Rowsetgröße = 1), wenn **SQLExecDirect** oder **SQLExecute** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb25e-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="fb25e-120">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber richtet ein Standardresultset ein.</span><span class="sxs-lookup"><span data-stu-id="fb25e-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="fb25e-121">Beim Übertragen von Ergebnissen auf den Client ohne Bildlauf ist dies effizienter als Servercursor.</span><span class="sxs-lookup"><span data-stu-id="fb25e-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="fb25e-122">Nachdem die Anweisung ausgeführt wurde, erhöhen Sie die Rowsetgröße und verwenden Sie entweder das spaltenweise oder zeilenweise Binden.</span><span class="sxs-lookup"><span data-stu-id="fb25e-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="fb25e-123">Dadurch [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] kann ein Standardresultset verwendet werden, um Ergebniszeilen effizient an den Client zu senden, während der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber kontinuierlich Zeilen aus den Netzwerkpuffern auf dem Client abruft.</span><span class="sxs-lookup"><span data-stu-id="fb25e-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb25e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb25e-124">See Also</span></span>  
 [<span data-ttu-id="fb25e-125">Cursoreigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb25e-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
