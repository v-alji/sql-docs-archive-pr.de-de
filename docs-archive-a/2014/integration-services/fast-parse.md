---
title: Schnelle Analyse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720251"
---
# <a name="fast-parse"></a><span data-ttu-id="2a915-102">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="2a915-102">Fast Parse</span></span>
  <span data-ttu-id="2a915-103">Die schnelle Analyse stellt schnelle, einfache Routinen zum Analysieren von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="2a915-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="2a915-104">Diese Routinen sind nicht gebietsschemaspezifisch und unterstützen nur eine Teilmenge von Datums-, Uhrzeit- und Ganzzahlformaten.</span><span class="sxs-lookup"><span data-stu-id="2a915-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="2a915-105">Anforderungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2a915-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="2a915-106">Durch Implementieren der schnellen Analyse ist das Interpretieren von Datum, Uhrzeit und numerischen Daten in gebietsschemaspezifischen Formaten sowie in häufig verwendeten ISO 8601-Basisformaten und erweiterten Formaten über ein Paket nicht möglich. Jedoch trägt dies zur Leistungssteigerung des Pakets bei.</span><span class="sxs-lookup"><span data-stu-id="2a915-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="2a915-107">Beispielsweise unterstützt die schnelle Analyse nur die gängigsten Datumsformatdarstellungen, wie z. B. YYYYMMDD und YYYY-MM-DD, führt keine gebietsschemaspezifische Analyse durch, erkennt keine Sonderzeichen in Währungsdaten und kann die hexadezimale oder wissenschaftliche Darstellung von ganzen Zahlen nicht konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2a915-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="2a915-108">Die schnelle Analyse ist nur bei Verwenden der Flatfilequelle oder der Transformation für Datenkonvertierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2a915-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="2a915-109">Die Leistungssteigerung kann sehr erheblich sein. Daher sollten Sie nach Möglichkeit die schnelle Analyse in diesen Datenflusskomponenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a915-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="2a915-110">Wenn der Datenfluss im Paket eine gebietsschemabezogene Analyse erfordert, wird stattdessen die Standardanalyse empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2a915-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="2a915-111">So erkennt die schnelle Analyse beispielsweise keine gebietsschemabezogenen Daten mit Dezimalsymbolen wie dem Komma, anderen Datenformaten als dem Jahr-Monat-Datum-Format und Währungssymbolen.</span><span class="sxs-lookup"><span data-stu-id="2a915-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="2a915-112">Abgeschnittene Darstellungen, die mindestens ein Datumsteil implizieren, wie z. B. ein Jahrhundert, ein Jahr oder ein Monat, werden von der schnellen Analyse nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="2a915-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="2a915-113">Die schnelle Analyse erkennt z.B. weder das Format **-JJMM**, das ein Jahr und einen Monat in einem implizierten Jahrhundert angibt, noch **--MM**, das einen Monat in einem implizierten Jahr angibt.</span><span class="sxs-lookup"><span data-stu-id="2a915-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="2a915-114">Bestimmte Darstellungen mit reduzierter Genauigkeit werden jedoch erkannt.</span><span class="sxs-lookup"><span data-stu-id="2a915-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="2a915-115">Beispielsweise erkennt die schnelle Analyse das Format 'hhmm;', das nur die Stunde und die Minute angibt, sowie '**YYYY**', das nur das Jahr angibt.</span><span class="sxs-lookup"><span data-stu-id="2a915-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="2a915-116">Die schnelle Analyse wird auf Spaltenebene angegeben.</span><span class="sxs-lookup"><span data-stu-id="2a915-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="2a915-117">In der Flatfilequelle und der Transformation für Datenkonvertierung können Sie die schnelle Analyse für Ausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="2a915-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="2a915-118">Eingaben und Ausgaben können gebietsschemabezogene und gebietsschemaneutrale Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a915-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="2a915-119">Weitere Informationen zu den von der schnellen Analyse unterstützten Datenformaten finden Sie unter [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) und [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="2a915-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="2a915-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2a915-120">Related Tasks</span></span>  
 [<span data-ttu-id="2a915-121">Festlegen der schnellen Analyse</span><span class="sxs-lookup"><span data-stu-id="2a915-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
