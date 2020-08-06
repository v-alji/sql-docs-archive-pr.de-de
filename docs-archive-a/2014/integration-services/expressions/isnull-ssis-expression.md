---
title: ISNULL (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701432"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="0de9d-102">ISNULL (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0de9d-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="0de9d-103">Gibt abhängig davon, ob ein Ausdruck NULL ist, ein boolesches Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="0de9d-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de9d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0de9d-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0de9d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0de9d-105">Arguments</span></span>  
 <span data-ttu-id="0de9d-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="0de9d-106">*expression*</span></span>  
 <span data-ttu-id="0de9d-107">Ein gültiger Ausdruck eines beliebigen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="0de9d-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0de9d-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="0de9d-108">Result Types</span></span>  
 <span data-ttu-id="0de9d-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="0de9d-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0de9d-110">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0de9d-110">Expression Examples</span></span>  
 <span data-ttu-id="0de9d-111">In diesem Beispiel wird TRUE zurückgegeben, falls die **DiscontinuedDate** -Spalte einen NULL-Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="0de9d-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="0de9d-112">In diesem Beispiel wird "Unknown last name" zurückgegeben, falls der Wert in der **LastName** -Spalte NULL ist. Andernfalls wird der Wert in der **LastName**-Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0de9d-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="0de9d-113">In diesem Beispiel wird immer TRUE zurückgegeben, falls die **DaysToManufacture** -Spalte NULL ist, unabhängig vom Wert der **AddDays**-Variablen.</span><span class="sxs-lookup"><span data-stu-id="0de9d-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="0de9d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0de9d-114">See Also</span></span>  
 <span data-ttu-id="0de9d-115">[Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0de9d-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0de9d-116">COALESCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0de9d-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
