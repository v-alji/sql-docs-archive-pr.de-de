---
title: () (Klammern) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724001"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="0f9b0-102">() (Klammern) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0f9b0-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="0f9b0-103">Identifiziert die Auswertungsreihenfolge von Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="0f9b0-104">Ausdrücke in Klammern haben die höchste Auswertungsrangfolge.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="0f9b0-105">Geschachtelte Ausdrücke, die in Klammern eingeschlossen sind, werden von innen nach außen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="0f9b0-106">Durch Klammern werden außerdem komplexe Ausdrücke verständlicher.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f9b0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f9b0-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f9b0-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="0f9b0-108">Arguments</span></span>  
 <span data-ttu-id="0f9b0-109">*expression*</span><span class="sxs-lookup"><span data-stu-id="0f9b0-109">*expression*</span></span>  
 <span data-ttu-id="0f9b0-110">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0f9b0-111">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="0f9b0-111">Result Types</span></span>  
 <span data-ttu-id="0f9b0-112">Der Datentyp von *expression*.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-112">The data type of *expression*.</span></span> <span data-ttu-id="0f9b0-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f9b0-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0f9b0-114">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0f9b0-114">Expression Examples</span></span>  
 <span data-ttu-id="0f9b0-115">Dieses Beispiel zeigt, wie die Rangfolge von Operatoren durch die Verwendung von Klammern geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="0f9b0-116">Der erste Ausdruck wird zu 100 ausgewertet, der zweite zu 31.</span><span class="sxs-lookup"><span data-stu-id="0f9b0-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f9b0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f9b0-117">See Also</span></span>  
 <span data-ttu-id="0f9b0-118">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="0f9b0-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="0f9b0-119">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="0f9b0-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
