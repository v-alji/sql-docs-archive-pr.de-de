---
title: LOWER (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617200"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="0be84-102">LOWER (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0be84-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="0be84-103">Gibt einen Zeichenausdruck zurück, nachdem Großbuchstaben in Kleinbuchstaben konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0be84-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0be84-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0be84-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0be84-105">Arguments</span></span>  
 <span data-ttu-id="0be84-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="0be84-106">*character_expression*</span></span>  
 <span data-ttu-id="0be84-107">Ein Zeichenausdruck zum Konvertieren in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="0be84-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0be84-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="0be84-108">Result Types</span></span>  
 <span data-ttu-id="0be84-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="0be84-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be84-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0be84-110">Remarks</span></span>  
 <span data-ttu-id="0be84-111">LOWER kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0be84-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="0be84-112">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor LOWER ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0be84-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="0be84-113">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0be84-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="0be84-114">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0be84-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="0be84-115">LOWER gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="0be84-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0be84-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0be84-116">Expression Examples</span></span>  
 <span data-ttu-id="0be84-117">In diesem Beispiel wird ein Zeichenfolgenliteral in Kleinbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0be84-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="0be84-118">Als Ergebnis wird "new york" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0be84-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="0be84-119">In diesem Beispiel werden alle Zeichen in der **Color** -Eingabespalte in Kleinbuchstaben konvertiert, außer dem ersten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0be84-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="0be84-120">Wenn Color gleich YELLOW ist, wird als Ergebnis "Yellow" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0be84-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="0be84-121">Weitere Informationen finden Sie unter [SUBSTRING &#40;SSIS-Ausdruck&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0be84-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="0be84-122">In diesem Beispiel wird der Wert in der **CityName** -Variablen in Kleinbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0be84-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="0be84-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0be84-123">See Also</span></span>  
 <span data-ttu-id="0be84-124">[UPPER &#40;SSIS-Ausdruck&#41;](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0be84-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0be84-125">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="0be84-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
