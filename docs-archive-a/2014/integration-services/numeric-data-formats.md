---
title: Numerische Datenformate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618091"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="52017-102">Numerische Datenformate</span><span class="sxs-lookup"><span data-stu-id="52017-102">Numeric Data Formats</span></span>
  <span data-ttu-id="52017-103">Die schnelle Analyse stellt schnelle, einfache und gebietsschemabezogene Routinen zum Analysieren von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="52017-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="52017-104">Nur bestimmte Formate für integer-Datentypen werden von der schnellen Analyse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52017-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="52017-105">Integer-Datentypen</span><span class="sxs-lookup"><span data-stu-id="52017-105">Integer Data Types</span></span>  
 <span data-ttu-id="52017-106">Die integer-Datentypen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sind DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 und DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="52017-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="52017-107">Weitere Informationen finden Sie unter [Integration Services Datentypen](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="52017-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="52017-108">Die schnelle Analyse unterstützt die folgenden Formate für integer-Datentypen:</span><span class="sxs-lookup"><span data-stu-id="52017-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="52017-109">Null oder mehr führende und nachfolgende Leerzeichen oder Tabstopps.</span><span class="sxs-lookup"><span data-stu-id="52017-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="52017-110">Beispielsweise ist der Wert "  123  " gültig.</span><span class="sxs-lookup"><span data-stu-id="52017-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="52017-111">Ein Wert, der nur aus Leerzeichen besteht, wird zu Null ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="52017-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="52017-112">Ein führendes Pluszeichen, Minuszeichen oder keines von beiden.</span><span class="sxs-lookup"><span data-stu-id="52017-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="52017-113">Beispielsweise sind die Werte +123, -123 und 123 gültig.</span><span class="sxs-lookup"><span data-stu-id="52017-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="52017-114">Mindestens eine hindu-arabische Ziffer (0-9).</span><span class="sxs-lookup"><span data-stu-id="52017-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="52017-115">Beispielsweise ist der Wert 345 gültig.</span><span class="sxs-lookup"><span data-stu-id="52017-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="52017-116">Ziffern aus anderen Sprachen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52017-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="52017-117">Folgende Datenformate werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="52017-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="52017-118">Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="52017-118">Special characters.</span></span> <span data-ttu-id="52017-119">Beispielsweise wird das Währungszeichen $ nicht unterstützt, und der Wert $20 kann nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="52017-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="52017-120">Leerzeichen, wie z. B. ein Zeilenvorschub, ein Wagenrücklauf und ein geschütztes Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="52017-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="52017-121">Beispielsweise kann der Wert " 123" nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="52017-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="52017-122">Hexadezimale Darstellungen von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="52017-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="52017-123">Beispielsweise kann der Wert 2EE nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="52017-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="52017-124">Darstellung von ganzen Zahlen in wissenschaftlicher Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="52017-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="52017-125">Beispielsweise kann der Wert 1E+10 nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="52017-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="52017-126">Die folgenden Formate sind Ausgabedatenformate für ganze Zahlen:</span><span class="sxs-lookup"><span data-stu-id="52017-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="52017-127">Ein Minuszeichen für negative Zahlen und kein Zeichen für positive Zahlen.</span><span class="sxs-lookup"><span data-stu-id="52017-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="52017-128">Keine Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="52017-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="52017-129">Mindestens eine hindu-arabische Ziffer (0-9).</span><span class="sxs-lookup"><span data-stu-id="52017-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
