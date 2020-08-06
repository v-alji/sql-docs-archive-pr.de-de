---
title: Abschneiden von Daten (SSIS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622228"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="65661-102">Abschneiden von Daten (SSIS)</span><span class="sxs-lookup"><span data-stu-id="65661-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="65661-103">Ein Ausdruck kann versehentlich bewirken, dass Daten abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="65661-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="65661-104">Dies ist in folgenden Situationen möglich:</span><span class="sxs-lookup"><span data-stu-id="65661-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="65661-105">Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="65661-105">Strings.</span></span> <span data-ttu-id="65661-106">Beispielsweise gehen durch das Übersetzen von Zeichenfolgendaten mit dem DT_WSTR-Datentyp in eine Zeichenfolge mit der gleichen Länge (gemessen in Zeichen) und dem DT_STR-Datentyp Daten verloren, wenn die ursprüngliche Zeichenfolge Doppelbytezeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="65661-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="65661-107">Signifikante Ziffern.</span><span class="sxs-lookup"><span data-stu-id="65661-107">Significant digits.</span></span> <span data-ttu-id="65661-108">Beispielsweise das Umwandeln einer ganzen Zahl vom DT_I4-Datentyp in den DT_I2-Datentyp oder einer ganzen Zahl ohne Vorzeichen in eine ganze Zahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="65661-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="65661-109">Insignifikante Ziffern.</span><span class="sxs-lookup"><span data-stu-id="65661-109">Insignificant digits.</span></span> <span data-ttu-id="65661-110">Beispielsweise das Umwandeln einer reellen Zahl vom DT_R8-Datentyp in den DT_R4-Datentyp oder einer ganzen Zahl vom DT_I4-Datentyp in den DT_R4-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="65661-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="65661-111">Die Ausdrucksauswertung identifiziert explizite Umwandlungen, durch die Daten abgeschnitten werden könnten und gibt eine Warnung aus, wenn der Ausdruck analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="65661-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="65661-112">Beispielsweise werden Sie von der Ausdrucksauswertung gewarnt, falls eine Zeichenfolge mit 30 Zeichen in eine Zeichenfolge mit 20 Zeichen umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="65661-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65661-113">Zur Laufzeit wird nicht überprüft, ob Daten abgeschnitten werden. Die Daten werden ohne Warnung abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="65661-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="65661-114">Die meisten Datenadapter und Transformationen unterstützen jedoch Fehlerausgaben, die mit der Disposition von Fehlerzeilen umgehen können.</span><span class="sxs-lookup"><span data-stu-id="65661-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="65661-115">Weitere Informationen zur Behandlung von Daten abkürzen finden Sie unter [Fehlerbehandlung in Daten](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="65661-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
