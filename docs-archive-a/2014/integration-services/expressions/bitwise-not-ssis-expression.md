---
title: ~ (Bitweises NOT) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619964"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="2afc4-102">~ (Bitweises NOT) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2afc4-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="2afc4-103">Führt eine bitweise Negation einer ganzen Zahl aus.</span><span class="sxs-lookup"><span data-stu-id="2afc4-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="2afc4-104">Dieser Operator kann auf integer-Datentypen mit und ohne Vorzeichen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2afc4-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2afc4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2afc4-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2afc4-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="2afc4-106">Arguments</span></span>  
 <span data-ttu-id="2afc4-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="2afc4-107">*integer_expression*</span></span>  
 <span data-ttu-id="2afc4-108">Ein beliebiger gültiger Ausdruck eines integer-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="2afc4-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="2afc4-109">*integer*_*expression* ist eine ganze Zahl, die für die bitweise Operation in eine binäre Zahl transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="2afc4-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="2afc4-110">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2afc4-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2afc4-111">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="2afc4-111">Result Types</span></span>  
 <span data-ttu-id="2afc4-112">Gibt den Datentyp von *integer_expression*zurück.</span><span class="sxs-lookup"><span data-stu-id="2afc4-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2afc4-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2afc4-113">Remarks</span></span>  
 <span data-ttu-id="2afc4-114">Keine</span><span class="sxs-lookup"><span data-stu-id="2afc4-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2afc4-115">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2afc4-115">Expression Examples</span></span>  
 <span data-ttu-id="2afc4-116">In diesem Beispiel wird eine bitweise ~ (NOT)-Operation für die Zahl 170 (0000 0000 1010 1010) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2afc4-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="2afc4-117">Diese Zahl ist eine ganze Zahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="2afc4-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="2afc4-118">Der Ausdruck wird zu -170 (1111111101010101) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2afc4-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="2afc4-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="2afc4-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="2afc4-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="2afc4-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afc4-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2afc4-121">See Also</span></span>  
 <span data-ttu-id="2afc4-122">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="2afc4-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="2afc4-123">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="2afc4-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
