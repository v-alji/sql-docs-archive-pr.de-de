---
title: Cursor Verhalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617941"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="fac5e-102">Cursorverhalten</span><span class="sxs-lookup"><span data-stu-id="fac5e-102">Cursor Behaviors</span></span>
  <span data-ttu-id="fac5e-103">ODBC unterstützt die ISO-Optionen für die Definition des Verhaltens von Cursorn durch Angabe ihrer Bildlauffähigkeit und Sensitivität.</span><span class="sxs-lookup"><span data-stu-id="fac5e-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="fac5e-104">Diese Verhaltensweisen werden angegeben, indem die Optionen SQL_ATTR_CURSOR_SCROLLABLE und SQL_ATTR_CURSOR_SENSITIVITY bei einem [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)-Befehl festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fac5e-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="fac5e-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber implementiert diese Optionen, indem er Servercursor mit den folgenden Eigenschaften anfordert.</span><span class="sxs-lookup"><span data-stu-id="fac5e-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="fac5e-106">Einstellungen für das Cursorverhalten</span><span class="sxs-lookup"><span data-stu-id="fac5e-106">Cursor behavior settings</span></span>|<span data-ttu-id="fac5e-107">Angeforderte Servercursoreigenschaften</span><span class="sxs-lookup"><span data-stu-id="fac5e-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="fac5e-108">SQL_SCROLLABLE und SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fac5e-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fac5e-109">Keysetgesteuerter Cursor und versionsbasierte vollständige Parallelität</span><span class="sxs-lookup"><span data-stu-id="fac5e-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fac5e-110">SQL_SCROLLABLE und SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fac5e-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fac5e-111">Statischer Cursor und Parallelität READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="fac5e-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fac5e-112">SQL_SCROLLABLE und SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fac5e-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fac5e-113">Statischer Cursor und Parallelität READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="fac5e-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fac5e-114">SQL_NONSCROLLABLE und SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fac5e-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fac5e-115">Vorwärtscursor und versionsbasierte vollständige Parallelität</span><span class="sxs-lookup"><span data-stu-id="fac5e-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fac5e-116">SQL_NONSCROLLABLE und SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fac5e-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fac5e-117">Standardresultset (Vorwärts, schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="fac5e-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="fac5e-118">SQL_NONSCROLLABLE und SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fac5e-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fac5e-119">Standardresultset (Vorwärts, schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="fac5e-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="fac5e-120">Versions basierte vollständige Parallelität erfordert eine **Zeitstempel** -Spalte in der zugrunde liegenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fac5e-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="fac5e-121">Wenn eine Versions basierte vollständige Parallelitäts Steuerung für eine Tabelle angefordert wird, die keine **Zeitstempel** -Spalte aufweist, verwendet der Server wertebasierte vollständige Parallelität.</span><span class="sxs-lookup"><span data-stu-id="fac5e-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="fac5e-122">Bildlauffähigkeit</span><span class="sxs-lookup"><span data-stu-id="fac5e-122">Scrollability</span></span>  
 <span data-ttu-id="fac5e-123">Wenn SQL_ATTR_CURSOR_SCROLLABLE auf SQL_SCROLLABLE festgelegt ist, unterstützt der Cursor alle unterschiedlichen Werte für den *FetchOrientation* -Parameter von [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="fac5e-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="fac5e-124">Wenn SQL_ATTR_CURSOR_SCROLLABLE auf SQL_NONSCROLLABLE festgelegt ist, unterstützt der Cursor nur einen *FetchOrientation* -Wert von SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="fac5e-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="fac5e-125">Sensitivität</span><span class="sxs-lookup"><span data-stu-id="fac5e-125">Sensitivity</span></span>  
 <span data-ttu-id="fac5e-126">Wenn SQL_ATTR_CURSOR_SENSITIVITY auf SQL_SENSITIVE festgelegt ist, spiegelt der Cursor Datenänderungen wider, die vom aktuellen Benutzer oder über Commitvorgänge anderer Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fac5e-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="fac5e-127">Wenn SQL_ATTR_CURSOR_SENSITIVITY auf SQL_INSENSITIVE festgelegt ist, spiegelt der Cursor keine Datenänderungen wider.</span><span class="sxs-lookup"><span data-stu-id="fac5e-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac5e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fac5e-128">See Also</span></span>  
 [<span data-ttu-id="fac5e-129">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="fac5e-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
