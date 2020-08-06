---
title: Lesezeichen für Zeilen in ODBC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723845"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="23c0a-102">Kennzeichnen von Zeilen in ODBC</span><span class="sxs-lookup"><span data-stu-id="23c0a-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="23c0a-103">Ein Lesezeichen ist ein Wert, der verwendet wird, um eine Zeile mit Daten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="23c0a-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="23c0a-104">Die Bedeutung des Lesezeichenwerts ist nur dem Treiber oder der Datenquelle bekannt.</span><span class="sxs-lookup"><span data-stu-id="23c0a-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="23c0a-105">Der Wert kann so einfach wie eine Zeilennummer oder so komplex wie eine Datenträgeradresse sein.</span><span class="sxs-lookup"><span data-stu-id="23c0a-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="23c0a-106">In ODBC fordert die Anwendung ein Lesezeichen für bestimmte Zeilen an, speichert es und gibt es an den Cursor für die Rückgabe an die Zeile zurück.</span><span class="sxs-lookup"><span data-stu-id="23c0a-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="23c0a-107">Beim Abrufen von Zeilen mit [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)kann eine Anwendung ein Lesezeichen als Grundlage für die Auswahl der Anfangs Zeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="23c0a-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="23c0a-108">Dies ist eine Form der absoluten Adressierung, da sie nicht von der aktuellen Cursorposition abhängt.</span><span class="sxs-lookup"><span data-stu-id="23c0a-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="23c0a-109">Um einen Bildlauf zu einer mit einem Lesezeichen markierten Zeile durchführen zu können, ruft die Anwendung **SQLFetchScroll** mit der *FetchOrientation* SQL_FETCH_BOOKMARK auf.</span><span class="sxs-lookup"><span data-stu-id="23c0a-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="23c0a-110">Dieser Vorgang verwendet das Lesezeichen, auf das das SQL_ATTR_FETCH_BOOKMARK_PTR-Optionsattribut zeigt.</span><span class="sxs-lookup"><span data-stu-id="23c0a-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="23c0a-111">Es gibt das Rowset zurück, das mit der Zeile beginnt, die von diesem Lesezeichen identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="23c0a-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="23c0a-112">Eine Anwendung kann einen Offset für diesen Vorgang im *FetchOffset* -Argument des Aufrufens von **SQLFetchScroll**angeben.</span><span class="sxs-lookup"><span data-stu-id="23c0a-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="23c0a-113">Wenn ein Offset angegeben ist, wird die erste Zeile des zurückgegebenen Rowsets durch Hinzufügen der Zahl im FetchOffset-Argument zu der Zahl der Zeile, die vom Lesezeichen identifiziert wird, bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23c0a-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="23c0a-114">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Native Client-ODBC-Treiber unterstützt nur Lesezeichen auf statischen und Keysetcursorn.</span><span class="sxs-lookup"><span data-stu-id="23c0a-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="23c0a-115">Wenn beim Festlegen von Lesezeichen ein dynamischer Cursor angefordert wird, wird stattdessen ein Keysetcursor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="23c0a-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="23c0a-116">Lesezeichen können auch mit der **SQLBulkOperations** -Funktion verwendet werden, um Vorgänge für eine Reihe von Zeilen ab dem Lesezeichen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="23c0a-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c0a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23c0a-117">See Also</span></span>  
 [<span data-ttu-id="23c0a-118">Bildläufe und Abrufen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="23c0a-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
