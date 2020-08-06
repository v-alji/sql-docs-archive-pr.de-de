---
title: ROUND (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701397"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="608c9-102">ROUND (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="608c9-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="608c9-103">Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde.</span><span class="sxs-lookup"><span data-stu-id="608c9-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="608c9-104">Der length-Parameter muss zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="608c9-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="608c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="608c9-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="608c9-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="608c9-106">Arguments</span></span>  
 <span data-ttu-id="608c9-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="608c9-107">*numeric_expression*</span></span>  
 <span data-ttu-id="608c9-108">Ein Ausdruck eines gültigen numerischen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="608c9-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="608c9-109">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="608c9-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="608c9-110">*length*</span><span class="sxs-lookup"><span data-stu-id="608c9-110">*length*</span></span>  
 <span data-ttu-id="608c9-111">Ein ganzzahliger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="608c9-111">Is an integer expression.</span></span> <span data-ttu-id="608c9-112">Dies ist die Genauigkeit, auf die *numeric_expression* gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="608c9-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="608c9-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="608c9-113">Result Types</span></span>  
 <span data-ttu-id="608c9-114">Der Typ entspricht dem Typ von *numeric*_*expression*.</span><span class="sxs-lookup"><span data-stu-id="608c9-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="608c9-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="608c9-115">Remarks</span></span>  
 <span data-ttu-id="608c9-116">Das *length* -Argument muss zu einer positiven ganzen Zahl oder 0 (null) ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="608c9-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="608c9-117">ROUND gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="608c9-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="608c9-118">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="608c9-118">Expression Examples</span></span>  
 <span data-ttu-id="608c9-119">Diese Beispiele runden numerische Literale auf eine Länge von drei.</span><span class="sxs-lookup"><span data-stu-id="608c9-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="608c9-120">Als erstes Ergebnis wird 137.1570 zurückgegeben und als zweites Ergebnis 137.1580.</span><span class="sxs-lookup"><span data-stu-id="608c9-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="608c9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="608c9-121">See Also</span></span>  
 [<span data-ttu-id="608c9-122">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="608c9-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
