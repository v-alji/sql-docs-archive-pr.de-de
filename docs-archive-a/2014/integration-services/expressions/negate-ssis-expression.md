---
title: '- (Negation) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720269"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="5b194-102">- (Negation) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="5b194-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="5b194-103">Negiert einen numerischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5b194-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b194-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b194-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5b194-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5b194-105">Arguments</span></span>  
 <span data-ttu-id="5b194-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="5b194-106">*numeric_expression*</span></span>  
 <span data-ttu-id="5b194-107">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="5b194-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="5b194-108">Nur numerische Datentypen mit Vorzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b194-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="5b194-109">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5b194-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5b194-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="5b194-110">Result Types</span></span>  
 <span data-ttu-id="5b194-111">Gibt den Datentyp von *numeric_expression*zurück.</span><span class="sxs-lookup"><span data-stu-id="5b194-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5b194-112">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5b194-112">Expression Examples</span></span>  
 <span data-ttu-id="5b194-113">In diesem Beispiel wird der Wert der **Counter** -Variablen negiert und das numerische Literal 50 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b194-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b194-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b194-114">See Also</span></span>  
 <span data-ttu-id="5b194-115">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="5b194-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="5b194-116">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="5b194-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
