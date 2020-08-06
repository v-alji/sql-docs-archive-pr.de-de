---
title: SQLSpecialColumns | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617958"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="51f81-102">'SQLSpecialColumns'</span><span class="sxs-lookup"><span data-stu-id="51f81-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="51f81-103">Beim Anfordern von Zeilen bezeichgern (*IdentifierType* SQL_BEST_ROWID) gibt **SQLSpecialColumns** ein leeres Resultset (keine Daten Zeilen) für einen angeforderten Bereich außer SQL_SCOPE_CURROW zurück.</span><span class="sxs-lookup"><span data-stu-id="51f81-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="51f81-104">Das generierte Resultset gibt an, dass die Spalten nur innerhalb dieses Bereichs gültig sind.</span><span class="sxs-lookup"><span data-stu-id="51f81-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="51f81-105">unterstützt keine Pseudospalten für Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="51f81-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="51f81-106">Das **SQLSpecialColumns** -Resultset identifiziert alle Spalten als SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="51f81-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="51f81-107">**SQLSpecialColumns** kann in einem statischen Cursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51f81-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="51f81-108">Der Versuch, **SQLSpecialColumns** für eine aktualisierbare (keysetgesteuerte oder dynamische) auszuführen, gibt SQL_SUCCESS_WITH_INFO zurück, die angibt, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="51f81-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="51f81-109">SQLSpecialColumns-Unterstützung für erweiterte Funktionen zu Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="51f81-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="51f81-110">Informationen zu den Werten, die für die Spalten DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH und DECIMAL_DIGTS für Datums-/Uhrzeittypen zurückgegeben werden, finden Sie unter [catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="51f81-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="51f81-111">Weitere allgemeine Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="51f81-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="51f81-112">SQLSpecialColumns -Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="51f81-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="51f81-113">**SQLSpecialColumns** unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="51f81-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="51f81-114">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="51f81-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f81-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51f81-115">See Also</span></span>  
 <span data-ttu-id="51f81-116">[SQLSpecialColumns-Funktion](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="51f81-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="51f81-117">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="51f81-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
