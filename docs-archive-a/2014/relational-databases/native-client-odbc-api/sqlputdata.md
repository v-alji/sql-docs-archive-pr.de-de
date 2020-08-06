---
title: SQLPutData | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622058"
---
# <a name="sqlputdata"></a><span data-ttu-id="a92d7-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="a92d7-102">SQLPutData</span></span>
  <span data-ttu-id="a92d7-103">Die folgenden Einschränkungen gelten, wenn SQLPutData verwendet wird, um mehr als 65.535 Bytes an Daten (für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Version 4.21 a) oder 400 KB an Daten (für SQL Server Version 6,0 und höher) für eine SQL_LONGVARCHAR ( `text` )-, SQL_WLONGVARCHAR ( `ntext` )-oder SQL_LONGVARBINARY ( `image` )-Spalte zu senden:</span><span class="sxs-lookup"><span data-stu-id="a92d7-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="a92d7-104">Der Parameter, auf den verwiesen wird, kann der *insert_Value* in einer INSERT-Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="a92d7-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="a92d7-105">Der Parameter, auf den verwiesen wird, kann ein *Ausdruck* in der SET-Klausel einer Update-Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="a92d7-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="a92d7-106">Das Abbrechen einer Sequenz von SQLPutData-aufrufen, die Daten in Blöcken für einen Server mit bereitstellen, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bewirkt eine partielle Aktualisierung des Spaltenwerts bei Verwendung von Version 6,5 oder früher.</span><span class="sxs-lookup"><span data-stu-id="a92d7-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="a92d7-107">Die- `text` ,-oder-Spalte, auf die `ntext` `image` verwiesen wurde, als SQLCancel aufgerufen wurde, wird auf einen zwischen Platzhalter Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a92d7-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a92d7-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Treiber unterstützt das Herstellen einer Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Version 6.5 und niedriger nicht.</span><span class="sxs-lookup"><span data-stu-id="a92d7-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="a92d7-109">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a92d7-109">Diagnostics</span></span>  
 <span data-ttu-id="a92d7-110">Es gibt einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-spezifischen SQLSTATE für SQLPutData:</span><span class="sxs-lookup"><span data-stu-id="a92d7-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="a92d7-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="a92d7-111">SQLSTATE</span></span>|<span data-ttu-id="a92d7-112">Fehler</span><span class="sxs-lookup"><span data-stu-id="a92d7-112">Error</span></span>|<span data-ttu-id="a92d7-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a92d7-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="a92d7-114">22026</span><span class="sxs-lookup"><span data-stu-id="a92d7-114">22026</span></span>|<span data-ttu-id="a92d7-115">Zeichenfolgendaten, nicht übereinstimmende Länge</span><span class="sxs-lookup"><span data-stu-id="a92d7-115">String data, length mismatch</span></span>|<span data-ttu-id="a92d7-116">Wenn die Länge der zu sendenden Daten in Bytes von einer Anwendung angegeben wurde, z. b. mit SQL_LEN_DATA_AT_EXEC (*n*), wobei *n* größer als 0 ist, muss die Gesamtanzahl der Bytes, die von der Anwendung über SQLPutData angegeben werden, mit der angegebenen Länge identisch sein.</span><span class="sxs-lookup"><span data-stu-id="a92d7-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="a92d7-117">SQLPutData und Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="a92d7-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="a92d7-118">SQLPutData wird von einer Anwendung verwendet, wenn eine Variable Zeilen Bindung mit Tabellenwert Parametern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a92d7-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="a92d7-119">Der *StrLen_Or_Ind* -Parameter gibt an, dass der Treiber zum Sammeln von Daten für die nächste Zeile oder Zeilen von Tabellenwert Parameter-Daten bereit ist, oder dass keine weiteren Zeilen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="a92d7-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="a92d7-120">Ein Wert größer als 0 gibt an, dass der nächste Satz von Zeilenwerten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a92d7-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="a92d7-121">Der Wert 0 gibt an, dass es keine Zeilen mehr gibt, die gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a92d7-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="a92d7-122">Ein Wert unter 0 zeigt einen Fehler an und führt dazu, dass ein Diagnosedatensatz mit SQLState HY090 aufgezeichnet und die Meldung „Ungültige Zeichenfolge oder Pufferlänge“ ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a92d7-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="a92d7-123">Der *DataPtr* -Parameter wird ignoriert, muss jedoch auf einen Wert festgelegt werden, der nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="a92d7-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="a92d7-124">Weitere Informationen finden Sie im Abschnitt zur TVP-Variablen-Zeilen Bindung in [Bindung und Datenübertragung von Tabellenwert Parametern und Spaltenwerten](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="a92d7-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="a92d7-125">Wenn *StrLen_Or_Ind* einen anderen Wert als SQL_DEFAULT_PARAM oder eine Zahl zwischen 0 und dem SQL_PARAMSET_SIZE (d. h. dem *ColumnSize* -Parameter von SQLBindParameter) aufweist, handelt es sich um einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="a92d7-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="a92d7-126">Dieser Fehler bewirkt, dass SQLPutData SQL_ERROR: SQLSTATE=HY090, "Ungültige Zeichenfolge oder Pufferlänge" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a92d7-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="a92d7-127">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a92d7-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a92d7-128">SQLPutData-Unterstützung für verbesserte Funktionen für Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a92d7-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a92d7-129">Parameter Werte von Datums-/Uhrzeittypen werden entsprechend der Beschreibung in [Konvertierungen von C in SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md)konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a92d7-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="a92d7-130">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a92d7-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="a92d7-131">SQLPutData-Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="a92d7-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="a92d7-132">`SQLPutData` unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="a92d7-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="a92d7-133">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a92d7-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a92d7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a92d7-134">See Also</span></span>  
 <span data-ttu-id="a92d7-135">[SQLPutData-Funktion](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="a92d7-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="a92d7-136">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="a92d7-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
