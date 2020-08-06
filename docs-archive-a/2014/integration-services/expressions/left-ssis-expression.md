---
title: LEFT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621063"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="b2de1-102">LEFT (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b2de1-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="b2de1-103">Gibt die angegebene Anzahl von Zeichen ab der äußersten linken Position des angegebenen Zeichenausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="b2de1-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2de1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2de1-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2de1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b2de1-105">Arguments</span></span>  
 <span data-ttu-id="b2de1-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="b2de1-106">*character_expression*</span></span>  
 <span data-ttu-id="b2de1-107">Ein Zeichenausdruck, von dem Zeichen extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2de1-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="b2de1-108">*Zahl*</span><span class="sxs-lookup"><span data-stu-id="b2de1-108">*number*</span></span>  
 <span data-ttu-id="b2de1-109">Ein ganzzahliger Ausdruck, der die Anzahl der zurückzugebenden Zeichen angibt.</span><span class="sxs-lookup"><span data-stu-id="b2de1-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b2de1-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="b2de1-110">Result Types</span></span>  
 <span data-ttu-id="b2de1-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="b2de1-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2de1-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b2de1-112">Remarks</span></span>  
 <span data-ttu-id="b2de1-113">Wenn *number* größer ist als die Länge von *character_expression*, gibt die Funktion *character_expression*zurück.</span><span class="sxs-lookup"><span data-stu-id="b2de1-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="b2de1-114">Falls *number* gleich Null ist, gibt die Funktion eine leere Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="b2de1-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="b2de1-115">Falls *number* eine negative Zahl ist, gibt die Funktion einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="b2de1-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="b2de1-116">Für das *number* -Argument sind Variablen und Spalten möglich.</span><span class="sxs-lookup"><span data-stu-id="b2de1-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="b2de1-117">LEFT kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2de1-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="b2de1-118">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor LEFT ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b2de1-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="b2de1-119">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b2de1-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="b2de1-120">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b2de1-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="b2de1-121">LEFT gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="b2de1-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b2de1-122">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="b2de1-122">Expression Examples</span></span>  
 <span data-ttu-id="b2de1-123">Im folgenden Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2de1-123">The following example uses a string literal.</span></span> <span data-ttu-id="b2de1-124">Als Ergebnis wird `"Mountain"`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b2de1-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2de1-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2de1-125">See Also</span></span>  
 <span data-ttu-id="b2de1-126">[RIGHT &#40;SSIS-Ausdruck&#41;](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b2de1-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b2de1-127">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="b2de1-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
