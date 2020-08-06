---
title: SQLFetchScroll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616077"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="87fe7-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="87fe7-102">SQLFetchScroll</span></span>
  <span data-ttu-id="87fe7-103">**SQLFetchScroll** gibt einen Zeilen Satz von Daten an die Anwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="87fe7-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="87fe7-104">Die Größe des Zeilen Satzes wird mithilfe von [SQLSetStmtAttr](sqlsetstmtattr.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87fe7-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="87fe7-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt alle definierten Abruf Anweisungen (z. b. SQL_FETCH_RELATIVE) mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="87fe7-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="87fe7-106">Wenn ein Vorwärtscursor für die Anweisung definiert ist, ist SQL_FETCH_NEXT erforderlich und Versuche, den Abrufvorgang auf eine andere Weise durchzuführen, werden mit einem Fehler quittiert.</span><span class="sxs-lookup"><span data-stu-id="87fe7-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="87fe7-107">SQL_FETCH_BOOKMARK wird nur für statische und keysetgesteuerte Cursor unterstützt.</span><span class="sxs-lookup"><span data-stu-id="87fe7-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="87fe7-108">SQLFetchScroll-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="87fe7-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="87fe7-109">Ergebnis Spaltenwerte von Datums-/Uhrzeittypen werden wie in [Konvertierungen von SQL in C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md)beschrieben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="87fe7-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="87fe7-110">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="87fe7-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="87fe7-111">SQLFetchScroll-Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="87fe7-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="87fe7-112">**SQLFetchScroll** unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="87fe7-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="87fe7-113">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="87fe7-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87fe7-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87fe7-114">See Also</span></span>  
 <span data-ttu-id="87fe7-115">[SQLFetchScroll-Funktion](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="87fe7-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="87fe7-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="87fe7-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
