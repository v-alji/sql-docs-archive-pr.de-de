---
title: Bindungen und Konvertierungen (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621505"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="0dd07-102">Bindungen und Konvertierungen (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0dd07-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="0dd07-103">In diesem Abschnitt wird erläutert, wie zwischen `datetime`- und `datetimeoffset`-Werten konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="0dd07-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="0dd07-104">Die in diesem Abschnitt beschriebenen Konvertierungen werden entweder von OLE DB bereitgestellt oder sind eine konsistente Erweiterung von OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0dd07-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="0dd07-105">Das Format für Literale und Zeichenfolgen für Datums- und Zeitangaben in OLE DB entspricht normalerweise ISO und hängt nicht von der Gebietsschemaeinstellung des Clients ab.</span><span class="sxs-lookup"><span data-stu-id="0dd07-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="0dd07-106">Eine Ausnahme ist DBTYPE_DATE, wo der Standard OLE-Automatisierung ist.</span><span class="sxs-lookup"><span data-stu-id="0dd07-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="0dd07-107">Da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client allerdings nur zwischen Typen konvertiert, wenn Daten vom oder zum Client übertragen werden, kann eine Anwendung [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client nicht dazu zwingen, zwischen DBTYPE_DATE und Zeichenfolgenformaten zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0dd07-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="0dd07-108">Andernfalls verwenden Zeichenfolgen die folgenden Formate (Text in Klammern gibt ein optionales Element an):</span><span class="sxs-lookup"><span data-stu-id="0dd07-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="0dd07-109">Das Format von `datetime`- und `datetimeoffset`-Zeichenfolgen ist:</span><span class="sxs-lookup"><span data-stu-id="0dd07-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="0dd07-110">*JJJJ* - *mm* - *DD*[ *HH*:*mm*:*SS*[.\* 9999999\*] [??</span><span class="sxs-lookup"><span data-stu-id="0dd07-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="0dd07-111">*HH*:*mm*]]</span><span class="sxs-lookup"><span data-stu-id="0dd07-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="0dd07-112">Das Format von `time`-Zeichenfolgen ist:</span><span class="sxs-lookup"><span data-stu-id="0dd07-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="0dd07-113">*hh*:*mm*:*ss*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="0dd07-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="0dd07-114">Das Format von `date`-Zeichenfolgen ist:</span><span class="sxs-lookup"><span data-stu-id="0dd07-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="0dd07-115">*yyyy*-*mm*-*dd*</span><span class="sxs-lookup"><span data-stu-id="0dd07-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dd07-116">Frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client und SQLOLEDB haben OLE-Konvertierungen implementiert, falls Standardkonvertierungen fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="0dd07-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="0dd07-117">Als Ergebnis unterscheiden sich einige von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 sowie höheren Versionen ausgeführte Konvertierungen von der OLE DB-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="0dd07-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="0dd07-118">Konvertierungen von Zeichenfolgen ermöglichen Flexibilität bei Leerstellen- und Feldbreite.</span><span class="sxs-lookup"><span data-stu-id="0dd07-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="0dd07-119">Weitere Informationen finden Sie im Abschnitt "Datenformate: Zeichen folgen und Literale" unter [Datentyp Unterstützung für OLE DB Datums-und Uhrzeit Verbesserungen](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="0dd07-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="0dd07-120">Folgende sind allgemeine Konvertierungsregeln:</span><span class="sxs-lookup"><span data-stu-id="0dd07-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="0dd07-121">Wenn eine Zeichenfolge in einen date/time-Typ konvertiert wird, wird die Zeichenfolge zuerst als ISO-Literal analysiert.</span><span class="sxs-lookup"><span data-stu-id="0dd07-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="0dd07-122">Wenn dies fehlschlägt, wird die Zeichenfolge als OLE-Datumsliteral analysiert, das über Zeitkomponenten verfügt.</span><span class="sxs-lookup"><span data-stu-id="0dd07-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="0dd07-123">Wenn keine Zeit vorhanden ist, der Empfänger aber Zeit speichern kann, wird die Zeit auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0dd07-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="0dd07-124">Wenn kein Datum vorhanden ist, der Empfänger aber ein Datum speichern kann, wird das Datum auf das aktuelle Datum festgelegt, wenn ISO-Konvertierungen verwendet werden, und auf den 30.12.1899, wenn OLE-Konvertierungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0dd07-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="0dd07-125">Wenn im vom Client verwendeten Datentyp keine Zeitzone vorhanden ist, der Server aber eine Zeitzone speichern kann, wird angenommen, dass sich die Daten auf dem Client in der Clientzeitzone befinden.</span><span class="sxs-lookup"><span data-stu-id="0dd07-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="0dd07-126">Wenn auf dem Server keine Zeitzone vorhanden ist, der Client aber über Zeitzoneninformationen verfügt, wird die UTC-Zeitzone angenommen.</span><span class="sxs-lookup"><span data-stu-id="0dd07-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="0dd07-127">Dieses Verhalten unterscheidet sich vom Serververhalten.</span><span class="sxs-lookup"><span data-stu-id="0dd07-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="0dd07-128">Wenn die Zeit vorhanden ist, der Empfänger aber keine Zeit speichern kann, wird die Zeitkomponente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0dd07-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="0dd07-129">Wenn das Datum vorhanden ist, der Empfänger aber kein Datum speichern kann, wird die Datumskomponente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0dd07-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="0dd07-130">Wenn beim Konvertieren vom Client zum Server ein Abschneiden der Sekunden oder Sekundenbruchteile auftritt, wird DB_E_ERRORSOCCURRED zurückgegeben, und als Status wird DBSTATUS_E_DATAOVERFLOW festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0dd07-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="0dd07-131">Wenn beim Konvertieren von Server zu Client ein Abschneiden der Sekunden oder Sekundenbruchteile auftritt, wird DBSTATUS_S_TRUNCATED festgelegt</span><span class="sxs-lookup"><span data-stu-id="0dd07-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dd07-132">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0dd07-132">In This Section</span></span>  
 [<span data-ttu-id="0dd07-133">Client-/Server-Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0dd07-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="0dd07-134">Beschreibt date/time-Konvertierungen, die für eine Clientanwendung durchgeführt werden, die mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB und [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (oder höher) geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="0dd07-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="0dd07-135">Server/Client-Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0dd07-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="0dd07-136">Beschreibt date/time-Konvertierungen, die zwischen [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (oder höher) und einer Clientanwendung durchgeführt werden, die mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="0dd07-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd07-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dd07-137">See Also</span></span>  
 [<span data-ttu-id="0dd07-138">Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="0dd07-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
