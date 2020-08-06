---
title: REPLACE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701421"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="aff78-102">REPLACE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="aff78-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="aff78-103">Gibt einen Zeichenausdruck zurück, nachdem eine Zeichenfolge im Ausdruck durch eine andere Zeichenfolge oder durch eine leere Zeichenfolge ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="aff78-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aff78-104">Von der REPLACE-Funktion werden häufig lange Zeichenfolgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aff78-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="aff78-105">Die Folgen der Kürzung können unauffällig behandelt werden oder eine Warnung oder einen Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="aff78-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="aff78-106">Weitere Informationen finden Sie unter [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff78-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aff78-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="aff78-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="aff78-108">Arguments</span></span>  
 <span data-ttu-id="aff78-109">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="aff78-109">*character_expression*</span></span>  
 <span data-ttu-id="aff78-110">Ein gültiger Zeichenausdruck, den die Funktion durchsucht.</span><span class="sxs-lookup"><span data-stu-id="aff78-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="aff78-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="aff78-111">*searchstring*</span></span>  
 <span data-ttu-id="aff78-112">Ein gültiger Zeichenausdruck, nach dem die Funktion sucht.</span><span class="sxs-lookup"><span data-stu-id="aff78-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="aff78-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="aff78-113">*replacementstring*</span></span>  
 <span data-ttu-id="aff78-114">Ein gültiger Zeichenausdruck, der den zu ersetzenden Ausdruck darstellt.</span><span class="sxs-lookup"><span data-stu-id="aff78-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="aff78-115">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="aff78-115">Result Types</span></span>  
 <span data-ttu-id="aff78-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="aff78-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aff78-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="aff78-117">Remarks</span></span>  
 <span data-ttu-id="aff78-118">Die Länge von *searchstring* darf nicht Null sein.</span><span class="sxs-lookup"><span data-stu-id="aff78-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="aff78-119">Die Länge von *replacementstring* darf Null sein.</span><span class="sxs-lookup"><span data-stu-id="aff78-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="aff78-120">Für die Argumente *searchstring* und *replacementstring* sind Variablen und Spalten möglich.</span><span class="sxs-lookup"><span data-stu-id="aff78-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="aff78-121">REPLACE kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff78-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="aff78-122">Das*character_expression1, character_expression2,* -Argument und das *character_expression3* -Argument, die Zeichenfolgenliterale oder Datenspalten mit dem DT_STR-Datentyp sind, werden implizit in den DT_WSTR-Datentyp umgewandelt, bevor REPLACE die Operation ausführt.</span><span class="sxs-lookup"><span data-stu-id="aff78-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="aff78-123">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="aff78-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="aff78-124">Weitere Informationen finden Sie unter [Umwandlung &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="aff78-125">REPLACE gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="aff78-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="aff78-126">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="aff78-126">Expression Examples</span></span>  
 <span data-ttu-id="aff78-127">In diesem Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="aff78-127">This example uses a string literal.</span></span> <span data-ttu-id="aff78-128">Als Ergebnis wird "All Terrain Bike" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aff78-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="aff78-129">In diesem Beispiel wird die Zeichenfolge "Bike" aus der **Product** -Spalte entfernt.</span><span class="sxs-lookup"><span data-stu-id="aff78-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="aff78-130">In diesem Beispiel werden Werte in der **DaysToManufacture** -Spalte ersetzt.</span><span class="sxs-lookup"><span data-stu-id="aff78-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="aff78-131">Die Spalte weist einen Integer-Datentyp auf, und der Ausdruck enthält die Umwandlung von **DaysToManufacture** in den DT_WSTR-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="aff78-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="aff78-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aff78-132">See Also</span></span>  
 <span data-ttu-id="aff78-133">[SUBSTRING &#40;SSIS-Ausdruck&#41;](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="aff78-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="aff78-134">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="aff78-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
