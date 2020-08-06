---
title: Datums-und Uhrzeit Verbesserungen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617939"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="e515a-102">Verbesserungen bei Datum und Zeit (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e515a-102">Date and Time Improvements (ODBC)</span></span>
  <span data-ttu-id="e515a-103">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] wurden neue Datums- und Uhrzeitdatentypen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e515a-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduced new date and time data types.</span></span> <span data-ttu-id="e515a-104">In diesem Abschnitt wird beschrieben, wie diese neuen Typen als Erweiterungen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e515a-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="e515a-105">Eine Übersicht über [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Native Client-Unterstützung für die neuen Datums-und Uhrzeit Datentypen finden Sie unter [Verbesserungen bei Datum und Uhrzeit](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="e515a-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="e515a-106">Ein Beispiel für die ODBC-Datums-/Uhrzeitunterstützung finden Sie unter [Verwenden von Datums-und Uhrzeit Typen](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="e515a-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="e515a-107">Allgemeine Informationen über Datums- und Uhrzeitdatentypen finden Sie unter [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e515a-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e515a-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e515a-108">In This Section</span></span>  
 [<span data-ttu-id="e515a-109">Datentypunterstützung für ODBC-Verbesserungen bei Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e515a-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="e515a-110">Liefert Informationen über ODBC-Typen, die Datums- und Uhrzeitdatentypen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e515a-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="e515a-111">Metadaten &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="e515a-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="e515a-112">Beschreibt Informationen, die in den IPD- und IRD-Feldern (Implementierungsparameterdeskriptor, Implementierungszeilendeskriptor) zurückgegeben werden, sowie Spaltenmetadaten, die von `SQLColumns` und `SQLProcedureColumns` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e515a-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="e515a-113">Beschreibt auch die von `SQLGetTypeInfo` zurückgegebenen Datentyp-Metadaten.</span><span class="sxs-lookup"><span data-stu-id="e515a-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="e515a-114">DateTime-Datentyp Konvertierungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="e515a-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="e515a-115">Beschreibt die Konvertierung zwischen datetime- und datetimeoffset-Werten.</span><span class="sxs-lookup"><span data-stu-id="e515a-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="e515a-116">sql_variant-Unterstützung für Datum- und Uhrzeit-Typen</span><span class="sxs-lookup"><span data-stu-id="e515a-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="e515a-117">Beschreibt die Unterstützung der SQL_VARIANT-Funktion für die verbesserte Datums- und Uhrzeitfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="e515a-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="e515a-118">Massen Kopier Änderungen für verbesserte Datums-und Uhrzeittypen &#40;OLE DB und ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="e515a-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="e515a-119">Beschreibt Datums-/Uhrzeitverbesserungen zur Unterstützung von Massenkopiervorgängen.</span><span class="sxs-lookup"><span data-stu-id="e515a-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="e515a-120">Verbessertes Verhalten des Datums-und Uhrzeittyps mit früheren Versionen von SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e515a-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="e515a-121">Beschreibt das erwartete Verhalten, wenn eine Client Anwendung, die verbesserte Datums-und Uhrzeit Funktionen verwendet, mit einer älteren Version von kommuniziert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und wenn ein Client, der mit einer älteren Version von Native Client kompiliert wurde, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Befehle an einen Server sendet, der erweiterte Datums-und Uhrzeit Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e515a-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="e515a-122">ODBC API-Unterstützung für verbesserte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e515a-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="e515a-123">Listet die ODBC-Funktionen auf, die die verbesserte Datums- und Uhrzeitfunktionalität unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e515a-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e515a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e515a-124">See Also</span></span>  
 [<span data-ttu-id="e515a-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e515a-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
