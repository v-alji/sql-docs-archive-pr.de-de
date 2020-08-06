---
title: Sqlgettypeingefo | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622078"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="673c1-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="673c1-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="673c1-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber meldet den zusätzlichen usertype-Spalten im Resultset von `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="673c1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="673c1-104">USERTYPE gibt die DB-Library-Datentypdefinition aus und ist für Entwickler nützlich, die bestehende DB-Library-Anwendungen nach ODBC portieren.</span><span class="sxs-lookup"><span data-stu-id="673c1-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="673c1-105">behandelt die Identität als Attribut, wohingegen ODBC die Identität als Datentyp behandelt.</span><span class="sxs-lookup"><span data-stu-id="673c1-105">treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="673c1-106">Um diesen Konflikt zu beheben, `SQLGetTypeInfo` gibt die Datentypen zurück: " **initidentity**", " **smallintidentity**", " **tinyintidentity**", " **decibösdentity**" und " **numericidentity**".</span><span class="sxs-lookup"><span data-stu-id="673c1-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="673c1-107">Die `SQLGetTypeInfo` Resultsetspalte AUTO_UNIQUE_VALUE meldet den Wert true für diese Datentypen.</span><span class="sxs-lookup"><span data-stu-id="673c1-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="673c1-108">Für **varchar**, **nvarchar** und **varbinary**wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber weiterhin den Bericht 8000, 4000 und 8000 für den COLUMN_SIZE Wert, auch wenn er tatsächlich unbegrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="673c1-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="673c1-109">Damit soll die Rückwärtskompatibilität sichergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="673c1-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="673c1-110">Für den **XML** -Datentyp [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] meldet der Native Client-ODBC-Treiber SQL_SS_LENGTH_UNLIMITED für COLUMN_SIZE, um eine unbegrenzte Größe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="673c1-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="673c1-111">SQLGetTypeInfo und Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="673c1-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="673c1-112">Der Tabellentyp für Tabellenwert Parameter ist praktisch ein Metatyp, d. h. ein Typ, mit dem andere Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="673c1-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="673c1-113">Daher muss Sie nicht über sqlgettypeingefo verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="673c1-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="673c1-114">Anwendungen müssen SQLTables anstelle von SQLGetTypeInfo verwenden, um Metadaten für Tabellentypen abzurufen, die mit Tabellenwert Parametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="673c1-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="673c1-115">Weitere Informationen zum Abrufen von Diensttyp für Tabellenwert Parameter finden Sie unter [Anweisungs Attribute, die sich auf Tabellenwert Parameter auswirken](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="673c1-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="673c1-116">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="673c1-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="673c1-117">SQLGetTypeInfo-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="673c1-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="673c1-118">Informationen zu den für Datums-/Uhrzeittypen zurückgegebenen Werten finden Sie unter [catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="673c1-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="673c1-119">Weitere allgemeine Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="673c1-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="673c1-120">SQLGetTypeInfo-Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="673c1-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="673c1-121">`SQLGetTypeInfo` unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="673c1-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="673c1-122">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="673c1-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673c1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="673c1-123">See Also</span></span>  
 <span data-ttu-id="673c1-124">[Sqlgettypeingefo-Funktion](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="673c1-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="673c1-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="673c1-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
