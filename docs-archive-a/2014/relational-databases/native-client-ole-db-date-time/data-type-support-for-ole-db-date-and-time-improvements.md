---
title: Datentypunterstützung für Verbesserungen von OLE DB-Datum und -Uhrzeit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722734"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="43def-102">Datentypunterstützung für Verbesserungen von OLE DB-Datum und -Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="43def-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="43def-103">Dieses Thema liefert Informationen über OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client)-Typen, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datums- und Uhrzeitdatentypen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="43def-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="43def-104">Datentypzuordnung zu Rowsets und Parametern</span><span class="sxs-lookup"><span data-stu-id="43def-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="43def-105">OLE DB stellt zwei neue Datentypen bereit, um die neuen Servertypen zu unterstützen: DBTYPE_DBTIME2 und DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="43def-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="43def-106">Die folgende Tabelle zeigt die vollständige Servertypzuordnung:</span><span class="sxs-lookup"><span data-stu-id="43def-106">The following table shows the complete server type mapping:</span></span>  
  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="43def-107">-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43def-107">data type</span></span>|<span data-ttu-id="43def-108">OLE DB-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43def-108">OLE DB data type</span></span>|<span data-ttu-id="43def-109">Wert</span><span class="sxs-lookup"><span data-stu-id="43def-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="43def-110">datetime</span><span class="sxs-lookup"><span data-stu-id="43def-110">datetime</span></span>|<span data-ttu-id="43def-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="43def-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="43def-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="43def-113">smalldatetime</span></span>|<span data-ttu-id="43def-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="43def-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="43def-116">date</span><span class="sxs-lookup"><span data-stu-id="43def-116">date</span></span>|<span data-ttu-id="43def-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="43def-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="43def-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="43def-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="43def-119">time</span><span class="sxs-lookup"><span data-stu-id="43def-119">time</span></span>|<span data-ttu-id="43def-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="43def-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="43def-121">145 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="43def-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="43def-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="43def-122">datetimeoffset</span></span>|<span data-ttu-id="43def-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="43def-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="43def-124">146 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="43def-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="43def-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="43def-125">datetime2</span></span>|<span data-ttu-id="43def-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="43def-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="43def-128">Datenformate: Zeichenfolgen und Literale</span><span class="sxs-lookup"><span data-stu-id="43def-128">Data Formats: Strings and Literals</span></span>  
  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="43def-129">-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43def-129">data type</span></span>|<span data-ttu-id="43def-130">OLE DB-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43def-130">OLE DB data type</span></span>|<span data-ttu-id="43def-131">Zeichenfolgenformat für Clientkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="43def-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="43def-132">datetime</span><span class="sxs-lookup"><span data-stu-id="43def-132">datetime</span></span>|<span data-ttu-id="43def-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-134">'yyyy-mm-dd hh:mm:ss[.999]'</span><span class="sxs-lookup"><span data-stu-id="43def-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="43def-135">unterstützt bis zu drei Sekundenbruchteilziffern für Datetime.</span><span class="sxs-lookup"><span data-stu-id="43def-135">supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="43def-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="43def-136">smalldatetime</span></span>|<span data-ttu-id="43def-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-138">'yyyy-mm-dd hh:mm:ss'</span><span class="sxs-lookup"><span data-stu-id="43def-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="43def-139">Dieser Datentyp verfügt über eine Genauigkeit von einer Minute.</span><span class="sxs-lookup"><span data-stu-id="43def-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="43def-140">Die zweite Komponente ist 0 (null) auf Ausgabe und wird auf Eingabe vom Server gerundet.</span><span class="sxs-lookup"><span data-stu-id="43def-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="43def-141">date</span><span class="sxs-lookup"><span data-stu-id="43def-141">date</span></span>|<span data-ttu-id="43def-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="43def-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="43def-143">'yyyy-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="43def-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="43def-144">time</span><span class="sxs-lookup"><span data-stu-id="43def-144">time</span></span>|<span data-ttu-id="43def-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="43def-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="43def-146">'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="43def-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="43def-147">Sekundenbruchteile können optional mit bis zu sieben Ziffern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43def-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="43def-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="43def-148">datetime2</span></span>|<span data-ttu-id="43def-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span><span class="sxs-lookup"><span data-stu-id="43def-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="43def-151">Sekundenbruchteile können optional mit bis zu sieben Ziffern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43def-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="43def-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="43def-152">datetimeoffset</span></span>|<span data-ttu-id="43def-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="43def-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="43def-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span><span class="sxs-lookup"><span data-stu-id="43def-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="43def-155">Sekundenbruchteile können optional mit bis zu sieben Ziffern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43def-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="43def-156">Für Datums-/Uhrzeitliterale gibt es keine Änderungen der Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="43def-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="43def-157">Sekundenbruchteile in Ergebnissen verwenden immer einen Punkt (.) anstelle eines Doppelpunkts (:).</span><span class="sxs-lookup"><span data-stu-id="43def-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="43def-158">An Anwendungen zurückgegebene Zeichenfolgenwerte haben immer die gleiche Länge für eine bestimmte Spalte.</span><span class="sxs-lookup"><span data-stu-id="43def-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="43def-159">Die Komponenten Jahr, Monat, Tag, Stunde, Minute und Sekunde werden mit führenden Nullen bis zur maximalen Breite aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="43def-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="43def-160">Zwischen Datum und Uhrzeit und zwischen Zeit und Zeitzonenoffset ist jeweils genau eine Leerstelle.</span><span class="sxs-lookup"><span data-stu-id="43def-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="43def-161">Ein Zeitzonenoffset wird immer mit einem Zeichen eingeleitet.</span><span class="sxs-lookup"><span data-stu-id="43def-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="43def-162">Dieses Zeichen ist ein Plus (+), wenn der Offset 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="43def-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="43def-163">Es gibt keine Leerstellen zwischen dem Zeichen und dem Offsetwert.</span><span class="sxs-lookup"><span data-stu-id="43def-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="43def-164">Sekundenbruchteile werden bei Bedarf bis zur definierten Genauigkeit für die Spalte mit nachfolgenden Nullen aufgefüllt, jedoch nicht weiter.</span><span class="sxs-lookup"><span data-stu-id="43def-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="43def-165">Für datetime-Spalten gibt es drei Ziffern für Sekundenbruchteile.</span><span class="sxs-lookup"><span data-stu-id="43def-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="43def-166">Für smalldatetime-Spalten gibt es, keine Ziffern für Sekundenbruchteile und die Sekunden sind immer 0 (null).</span><span class="sxs-lookup"><span data-stu-id="43def-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="43def-167">Konvertierungen aus Zeichenfolgenwerten, die von der Anwendung bereitgestellt werden, sind flexibler und erlauben Komponentenwerte, die unter der maximalen Breite liegen.</span><span class="sxs-lookup"><span data-stu-id="43def-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="43def-168">Jahre können aus 1-4 Ziffern bestehen.</span><span class="sxs-lookup"><span data-stu-id="43def-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="43def-169">Monate, Tage, Stunden, Minuten und Sekunden können 1 oder 2 Ziffern haben.</span><span class="sxs-lookup"><span data-stu-id="43def-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="43def-170">Es kann beliebig viele Leerstellen zwischen Datum-/Uhrzeit und Zeit-/Zeitzonenoffsets geben.</span><span class="sxs-lookup"><span data-stu-id="43def-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="43def-171">Das Zeichen eines Offsets mit 0 (null) Stunden und 0 (null) Minuten kann Plus oder Minus sein.</span><span class="sxs-lookup"><span data-stu-id="43def-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="43def-172">Nachfolgende Nullen sind bis zu einem Maximum von 9 Ziffern für Sekundenbruchteile zugelassen.</span><span class="sxs-lookup"><span data-stu-id="43def-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="43def-173">Eine Zeitkomponente kann mit einem Dezimaltrennzeichen und keinen Ziffern für Sekundenbruchteile enden.</span><span class="sxs-lookup"><span data-stu-id="43def-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="43def-174">Eine leere Zeichenfolge ist kein gültiges Datum-/Uhrzeitliteral und stellt keinen NULL-Wert dar.</span><span class="sxs-lookup"><span data-stu-id="43def-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="43def-175">Der Versuch, eine leere Zeichenfolge in einen Datum-/Uhrzeitwert zu konvertieren, führt Fehlern mit SQLSTATE 22018 und der Meldung „Ungültiger Zeichenwert für Konvertierungsangabe“.</span><span class="sxs-lookup"><span data-stu-id="43def-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="43def-176">Datenformate: Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="43def-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="43def-177">In den unten beschriebenen OLE DB-spezifischen Strukturen entspricht OLE DB den gleichen Einschränkungen wie ODBC.</span><span class="sxs-lookup"><span data-stu-id="43def-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="43def-178">Diese werden vom gregorianischen Kalender genommen:</span><span class="sxs-lookup"><span data-stu-id="43def-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="43def-179">Der Bereich für den Monat liegt zwischen 1 und 12.</span><span class="sxs-lookup"><span data-stu-id="43def-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="43def-180">Der Bereich für das Tagfeld liegt zwischen 1 und der Anzahl Tage in dem Monat und muss mit den Feldern für Jahr und Monat konsistent sein unter Berücksichtigung von Schaltjahren.</span><span class="sxs-lookup"><span data-stu-id="43def-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="43def-181">Der Bereich für die Stunden liegt zwischen 0 und 23.</span><span class="sxs-lookup"><span data-stu-id="43def-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="43def-182">Der Bereich für die Minuten liegt zwischen 0 und 59.</span><span class="sxs-lookup"><span data-stu-id="43def-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="43def-183">Der Bereich für die Sekunden liegt zwischen 0 und 59.</span><span class="sxs-lookup"><span data-stu-id="43def-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="43def-184">Es sind bis zu zwei Schaltsekunden erlaubt, um die Synchronisierung mit der Sternzeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="43def-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="43def-185">Implementierungen für die folgenden bestehenden OLE DB-Strukturen wurden geändert, um die Unterstützung der neuen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datum-/Uhrzeitdatentypen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="43def-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="43def-186">Die Definitionen haben sich jedoch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="43def-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="43def-187">DBTYPE_DATE (Dies ist ein Automatisierung-DATE-Typ.</span><span class="sxs-lookup"><span data-stu-id="43def-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="43def-188">Er wird intern als `double` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="43def-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="43def-189">Der ganzzahlige Teil gibt die Anzahl von Tagen seit dem 30. Dezember 1899 wieder und der Bruchteil den Teil eines Tages.</span><span class="sxs-lookup"><span data-stu-id="43def-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="43def-190">Dieser Typ hat eine Genauigkeit von 1 Sekunde und hat daher eine effektive Dezimalstelle von 0.)</span><span class="sxs-lookup"><span data-stu-id="43def-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="43def-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="43def-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="43def-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="43def-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="43def-193">DBTYPE_DBTIMESTAMP (das Bruchteilfeld wird von OLE DB als der milliardste Teil einer Sekunde (Nanosekunde) definiert, und der gültige Bereich liegt zwischen 0-999.999.999)</span><span class="sxs-lookup"><span data-stu-id="43def-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="43def-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="43def-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="43def-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="43def-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="43def-196">Diese Struktur wird auf beiden Betriebssystemen (32 Bit und 64 Bit) bis 12 Byte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="43def-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="43def-197">DBTYPE_ DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="43def-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="43def-198">Wenn `timezone_hour` negativ ist, muss `timezone_minute` negativ oder 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="43def-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="43def-199">Wenn `timezone_hour` positiv ist, muss `timezone minute` positiv oder 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="43def-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="43def-200">Wenn `timezone_hour` 0 (null) ist, kann `timezone minute` einen Wert zwischen -59 und +59 haben.</span><span class="sxs-lookup"><span data-stu-id="43def-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="43def-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="43def-201">SSVARIANT</span></span>  
 <span data-ttu-id="43def-202">Dieses struct enthält jetzt die neuen Strukturen DBTYPE_DBTIME2 und DBTYPE_DBTIMESTAMPOFFSET und fügt Sekundenbruchteile für entsprechende Typen hinzu.</span><span class="sxs-lookup"><span data-stu-id="43def-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="43def-203">Ferner wird die Enumeration, die dem SSVARIANT-Typ zugewiesen ist und den Enumerationstyp bestimmt, folgendermaßen erweitert:</span><span class="sxs-lookup"><span data-stu-id="43def-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="43def-204">Anwendungen, die zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client migriert werden, `sql_variant` verwenden und auf der eingeschränkten Genauigkeit von `datetime` beruhen, müssen aktualisiert werden, wenn des zugrunde liegende Schema auf die Verwendung von `datetime2` anstelle von `datetime` aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="43def-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="43def-205">Die Zugriffsmakros für SSVARIANT wurden durch Hinzufügen von Folgendem ebenfalls erweitert:</span><span class="sxs-lookup"><span data-stu-id="43def-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="43def-206">Datentypzuordnung zu ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="43def-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="43def-207">Die folgende Typzuordnung wird mit DBCOLUMNDESC-Strukturen verwendet, die von ITableDefinition::CreateTable verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="43def-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="43def-208">OLE DB-Datentyp (*wType*)</span><span class="sxs-lookup"><span data-stu-id="43def-208">OLE DB data type (*wType*)</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="43def-209">-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43def-209">data type</span></span>|<span data-ttu-id="43def-210">Notizen</span><span class="sxs-lookup"><span data-stu-id="43def-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="43def-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="43def-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="43def-212">date</span><span class="sxs-lookup"><span data-stu-id="43def-212">date</span></span>||  
|<span data-ttu-id="43def-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43def-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="43def-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="43def-214">`datetime2`(p)</span></span>|<span data-ttu-id="43def-215">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter überprüft das DBCOLUMDESC *bScale* -Element, um die Genauigkeit der Sekundenbruchteile zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="43def-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="43def-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="43def-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="43def-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="43def-217">`time`(p)</span></span>|<span data-ttu-id="43def-218">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter überprüft das DBCOLUMDESC *bScale* -Element, um die Genauigkeit der Sekundenbruchteile zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="43def-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="43def-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="43def-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="43def-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="43def-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="43def-221">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter überprüft das DBCOLUMDESC *bScale* -Element, um die Genauigkeit der Sekundenbruchteile zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="43def-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="43def-222">Wenn eine Anwendung DBTYPE_DBTIMESTAMP in *wType*angibt, kann Sie die Zuordnung zu überschreiben, `datetime2` indem Sie einen Typnamen in *pwsztytzame*bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="43def-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="43def-223">Wenn `datetime` angegeben wird, muss *bScale* 3 sein.</span><span class="sxs-lookup"><span data-stu-id="43def-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="43def-224">Wenn `smalldatetime` angegeben wird, muss *bScale* den Wert 0 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="43def-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="43def-225">Wenn *bScale* nicht mit *wType* und *pwsztykame*konsistent ist, wird DB_E_BADSCALE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43def-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43def-226">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43def-226">See Also</span></span>  
 [<span data-ttu-id="43def-227">Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="43def-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
