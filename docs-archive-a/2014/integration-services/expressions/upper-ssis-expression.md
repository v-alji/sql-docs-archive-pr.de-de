---
title: UPPER (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701318"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="33465-102">UPPER (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="33465-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="33465-103">Gibt einen Zeichenausdruck zurück, nachdem Kleinbuchstaben in Großbuchstaben konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33465-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33465-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33465-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="33465-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="33465-105">Arguments</span></span>  
 <span data-ttu-id="33465-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="33465-106">*character_expression*</span></span>  
 <span data-ttu-id="33465-107">Ein Zeichenausdruck zum Konvertieren in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="33465-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="33465-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="33465-108">Result Types</span></span>  
 <span data-ttu-id="33465-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="33465-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33465-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="33465-110">Remarks</span></span>  
 <span data-ttu-id="33465-111">UPPER kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33465-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="33465-112">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor UPPER ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33465-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="33465-113">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="33465-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="33465-114">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="33465-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="33465-115">UPPER gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="33465-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="33465-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="33465-116">Expression Examples</span></span>  
 <span data-ttu-id="33465-117">In diesem Beispiel wird ein Zeichenfolgenliteral in Großbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="33465-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="33465-118">Als Ergebnis wird "HELLO" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="33465-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="33465-119">In diesem Beispiel wird das erste Zeichen in der **FirstName** -Spalte in einen Großbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="33465-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="33465-120">Wenn **FirstName** gleich anna ist, wird als Ergebnis "A" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="33465-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="33465-121">Weitere Informationen finden Sie unter [SUBSTRING &#40;SSIS-Ausdruck&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="33465-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="33465-122">In diesem Beispiel wird der Wert in der **PostalCode** -Variablen in Großbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="33465-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="33465-123">Wenn **PostalCode** gleich k4b1s2 ist, wird als Ergebnis "K4B1S2" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="33465-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="33465-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33465-124">See Also</span></span>  
 <span data-ttu-id="33465-125">[LOWER &#40;SSIS-Ausdruck&#41;](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="33465-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="33465-126">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="33465-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
