---
title: DateTime-Datentyp Konvertierungen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620332"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="22e29-102">datetime-Datentypkonvertierungen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="22e29-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="22e29-103">Die folgenden Konvertierungen sind entweder bereits von ODBC definiert oder stellen eine konsistente Erweiterung von ODBC dar.</span><span class="sxs-lookup"><span data-stu-id="22e29-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="22e29-104">Die von den einzelnen Anbietern bereitgestellten Konvertierungen werden vom Benutzerkreis beeinflusst und weisen daher oft Inkonsistenzen untereinander auf.</span><span class="sxs-lookup"><span data-stu-id="22e29-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="22e29-105">Werte in eckigen Klammern sind optional.</span><span class="sxs-lookup"><span data-stu-id="22e29-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="22e29-106">Das Format von datetime-Zeichenfolgen ist 'yyyy-mm-dd[hh:mm:ss[.9999999][Plus/Minus hh:mm]]'</span><span class="sxs-lookup"><span data-stu-id="22e29-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="22e29-107">Das Format von Uhrzeitzeichenfolgen ist 'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="22e29-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="22e29-108">Das Format von Datumszeichenfolgen ist 'yyyy-mm-dd'.</span><span class="sxs-lookup"><span data-stu-id="22e29-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="22e29-109">Konvertierungen von Zeichenfolgen ermöglichen Flexibilität bei Leerstellen- und Feldbreite.</span><span class="sxs-lookup"><span data-stu-id="22e29-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="22e29-110">Weitere Informationen finden Sie im Abschnitt "Datenformate: Zeichen folgen und Literale" unter [Datentyp Unterstützung für ODBC-Datums-und Uhrzeit Verbesserungen](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="22e29-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="22e29-111">Folgende sind allgemeine Konvertierungsregeln:</span><span class="sxs-lookup"><span data-stu-id="22e29-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="22e29-112">Wenn keine Zeit vorhanden ist, der Empfänger aber Zeit speichern kann, wird die Zeit auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="22e29-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="22e29-113">Wenn keine Datumsangabe vorhanden ist, der Empfänger aber das Datum speichern kann, wird das aktuelle Datum verwendet.</span><span class="sxs-lookup"><span data-stu-id="22e29-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="22e29-114">Wenn in dem vom Client verwendeten Datentyp keine Zeitzone vorhanden ist, der Server aber eine Zeitzone speichern kann, wird das Datum in der Clientzeitzone gespeichert.</span><span class="sxs-lookup"><span data-stu-id="22e29-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="22e29-115">Beachten Sie, dass dies vom Server Verhalten abweicht.</span><span class="sxs-lookup"><span data-stu-id="22e29-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="22e29-116">Wenn in dem vom Server verwendeten Datentyp keine Zeitzone vorhanden ist, der Datentyp auf dem Client aber eine Zeitzone aufweist, wird die Zeit in UTC konvertiert, bevor sie auf dem Server gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="22e29-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="22e29-117">Wenn die Zeit vorhanden ist, der Empfänger aber keine Zeit speichern kann, wird die Zeitkomponente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="22e29-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="22e29-118">Wenn ein Datum vorhanden ist, der Empfänger aber kein Datum speichern kann, wird die Datumskomponente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="22e29-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="22e29-119">Wenn es bei der Konvertierung von C in SQL zum Abschneiden von Sekunden oder Sekundenbruchteilen kommt, wird ein Diagnosedatensatz mit SQLSTATE 22008 und der Meldung "Überlauf im Datetime-Feld" generiert.</span><span class="sxs-lookup"><span data-stu-id="22e29-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="22e29-120">Wenn es bei der Konvertierung von SQL in C zum Abschneiden von Sekunden oder Sekundenbruchteilen kommt, wird ein Diagnosedatensatz mit SQLSTATE 01S07 und der Meldung "Teilbereiche wurden abgeschnitten" generiert.</span><span class="sxs-lookup"><span data-stu-id="22e29-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22e29-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="22e29-121">In This Section</span></span>  
 [<span data-ttu-id="22e29-122">Konvertierungen von C in SQL</span><span class="sxs-lookup"><span data-stu-id="22e29-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="22e29-123">Listet Punkte auf, die bei der Konvertierung von C-Typen in Datum-/Uhrzeit-Typen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="22e29-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="22e29-124">Konvertierungen von SQL in C</span><span class="sxs-lookup"><span data-stu-id="22e29-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="22e29-125">Listet Punkte auf, die bei der Konvertierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datum-/Uhrzeit-Typen in C-Typen zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="22e29-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e29-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22e29-126">See Also</span></span>  
 [<span data-ttu-id="22e29-127">Datums-und Uhrzeit Verbesserungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="22e29-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
