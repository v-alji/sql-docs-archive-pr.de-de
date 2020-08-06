---
title: Implementierung von Cursorn | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616074"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="5f905-102">Implementieren von Cursorn</span><span class="sxs-lookup"><span data-stu-id="5f905-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="5f905-103">ODBC-Anwendungen steuern das Cursorverhalten, indem mindestens ein Anweisungsattribut festgelegt wird, bevor eine SQL-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f905-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="5f905-104">ODBC bietet zwei verschiedene Möglichkeiten, die Merkmale eines Cursors anzugeben:</span><span class="sxs-lookup"><span data-stu-id="5f905-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="5f905-105">Cursortyp</span><span class="sxs-lookup"><span data-stu-id="5f905-105">Cursor type</span></span>  
  
     <span data-ttu-id="5f905-106">Cursor Typen werden mit dem SQL_ATTR_CURSOR_TYPE-Attribut von [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f905-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="5f905-107">Die ODBC-Cursortypen sind vorwärts, statisch, keysetgesteuert, gemischt und dynamisch.</span><span class="sxs-lookup"><span data-stu-id="5f905-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="5f905-108">Durch Festlegen des Cursortyps wurden Cursor in ODBC ursprünglich angegeben.</span><span class="sxs-lookup"><span data-stu-id="5f905-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="5f905-109">Cursor Verhalten</span><span class="sxs-lookup"><span data-stu-id="5f905-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="5f905-110">Das Cursor Verhalten wird mithilfe der Attribute "SQL_ATTR_CURSOR_SCROLLABLE" und "SQL_ATTR_CURSOR_SENSITIVITY" von **SQLSetStmtAttr**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f905-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="5f905-111">Diese Attribute werden anhand der Schlüsselwörter SCROLL und SENSITIVE modelliert, die für die DECLARE CURSOR-Anweisung in ISO-Standards definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5f905-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="5f905-112">Diese beiden ISO-Optionen wurden in ODBC Version 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5f905-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="5f905-113">Die Merkmale eines ODBC-Cursors sollten mit einer der beiden Methoden angegeben werden, wobei die ODBC-Cursortypen vorzuziehen sind.</span><span class="sxs-lookup"><span data-stu-id="5f905-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="5f905-114">Neben dem Cursortyp legen ODBC-Anwendungen noch andere Optionen fest, z. B. die Anzahl der bei jedem Abruf zurückgegebenen Zeilen, Parallelitätsoptionen und Transaktionsisolationsstufen.</span><span class="sxs-lookup"><span data-stu-id="5f905-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="5f905-115">Diese Optionen können entweder für ODBC-Cursor (vorwärts, statisch, keysetgesteuert, gemischt und dynamisch) oder ISO-Cursor (Bildlauffähigkeit und Sensitivität) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5f905-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="5f905-116">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt mehrere Möglichkeiten, die verschiedenen Cursor Typen physisch zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="5f905-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="5f905-117">Der Treiber implementiert einige Cursortypen mit einem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Standardresultset und andere als Servercursor oder mit der ODBC-Cursorbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5f905-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f905-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5f905-118">In This Section</span></span>  
  
-   [<span data-ttu-id="5f905-119">Verwenden von SQL Server-Standardresultsets</span><span class="sxs-lookup"><span data-stu-id="5f905-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="5f905-120">Verwenden von Servercursorn</span><span class="sxs-lookup"><span data-stu-id="5f905-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="5f905-121">ODBC-Cursorbibliothek</span><span class="sxs-lookup"><span data-stu-id="5f905-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f905-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f905-122">See Also</span></span>  
 [<span data-ttu-id="5f905-123">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="5f905-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
