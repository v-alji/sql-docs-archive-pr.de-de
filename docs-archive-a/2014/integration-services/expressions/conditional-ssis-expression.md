---
title: '? : (Bedingt) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622229"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="a32ff-103">?</span><span class="sxs-lookup"><span data-stu-id="a32ff-103">?</span></span> <span data-ttu-id="a32ff-104">: (Bedingt) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="a32ff-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="a32ff-105">Gibt einen von zwei Ausdrücken basierend auf der Auswertung eines booleschen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="a32ff-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="a32ff-106">Falls der boolesche Ausdruck zu TRUE ausgewertet wird, wird der erste Ausdruck ausgewertet, und das Ergebnis ist das Ausdrucksergebnis.</span><span class="sxs-lookup"><span data-stu-id="a32ff-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="a32ff-107">Falls der boolesche Ausdruck zu FALSE ausgewertet wird, wird der zweite Ausdruck ausgewertet, und das Ergebnis ist das Ausdrucksergebnis.</span><span class="sxs-lookup"><span data-stu-id="a32ff-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a32ff-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a32ff-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a32ff-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="a32ff-109">Arguments</span></span>  
 <span data-ttu-id="a32ff-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="a32ff-110">*boolean_expression*</span></span>  
 <span data-ttu-id="a32ff-111">Ein gültiger Ausdruck, der zu TRUE, FALSE oder NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="a32ff-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="a32ff-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="a32ff-112">*expression1*</span></span>  
 <span data-ttu-id="a32ff-113">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a32ff-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="a32ff-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="a32ff-114">*expression2*</span></span>  
 <span data-ttu-id="a32ff-115">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a32ff-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a32ff-116">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="a32ff-116">Result Types</span></span>  
 <span data-ttu-id="a32ff-117">Der Datentyp von *expression1* oder *expression2*.</span><span class="sxs-lookup"><span data-stu-id="a32ff-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a32ff-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a32ff-118">Remarks</span></span>  
 <span data-ttu-id="a32ff-119">Falls *boolean_expression* zu NULL ausgewertet wird, lautet das Ergebnis des Ausdrucks NULL.</span><span class="sxs-lookup"><span data-stu-id="a32ff-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="a32ff-120">Wenn ein ausgewählter Ausdruck, *expression1* oder *expression2* , NULL ist, lautet das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="a32ff-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="a32ff-121">Wenn ein ausgewählter Ausdruck ungleich NULL ist, aber der nicht ausgewählte Ausdruck NULL ist, besitzt das Ergebnis den Wert des ausgewählten Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a32ff-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="a32ff-122">Falls *expression1* und *expression2* vom gleichen Datentyp sind, gehört auch das Ergebnis zu diesem Datentyp.</span><span class="sxs-lookup"><span data-stu-id="a32ff-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="a32ff-123">Die folgenden zusätzlichen Regeln sind auch auf Ergebnistypen anwendbar:</span><span class="sxs-lookup"><span data-stu-id="a32ff-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="a32ff-124">Für den DT_TEXT-Datentyp müssen *expression1* und *expression2* die gleiche Codepage aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a32ff-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="a32ff-125">Die Länge eines Ergebnisses mit dem DT_BYTES-Datentyp ist die Länge des längeren Arguments.</span><span class="sxs-lookup"><span data-stu-id="a32ff-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="a32ff-126">Die Ausdrucksgruppe, *expression1* und *expression2*, muss zu gültigen Datentypen ausgewertet werden und eine der folgenden Regeln einhalten:</span><span class="sxs-lookup"><span data-stu-id="a32ff-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="a32ff-127">\**Numerisch\*\*\*expression1* und *expression2* müssen einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a32ff-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="a32ff-128">Die Schnittmenge der Datentypen muss ein numerischer Datentyp gemäß den Regeln zu den impliziten numerischen Konvertierungen sein, die die Ausdrucksauswertung ausführt.</span><span class="sxs-lookup"><span data-stu-id="a32ff-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="a32ff-129">Die Schnittmenge der beiden numerischen Datentypen darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a32ff-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="a32ff-130">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a32ff-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="a32ff-131">**Zeichenfolge:** *expression1* und *expression2* müssen einen Zeichenfolgen-Datentyp aufweisen, d.h. DT_STR oder DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a32ff-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="a32ff-132">Die beiden Ausdrücke können zu verschiedenen Zeichenfolgen-Datentypen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a32ff-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="a32ff-133">Das Ergebnis weist den DT_WSTR-Datentyp und die Länge des längeren Arguments auf.</span><span class="sxs-lookup"><span data-stu-id="a32ff-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="a32ff-134">**Datum, Uhrzeit oder Datum/Uhrzeit** Sowohl *expression1* als auch *expression2* müssen zu einem der folgenden Datentypen ausgewertet werden: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET oder DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="a32ff-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a32ff-135">Das System unterstützt keine Vergleiche zwischen einem Ausdruck, der zu einem Uhrzeitdatentyp ausgewertet wird, und einem Ausdruck, der entweder zu einem Datums- oder zu einem Datums-/Uhrzeitdatentyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="a32ff-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="a32ff-136">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="a32ff-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="a32ff-137">Beim Vergleich der Ausdrücke werden die folgenden Konvertierungsregeln in der angegebenen Reihenfolge angewendet:</span><span class="sxs-lookup"><span data-stu-id="a32ff-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="a32ff-138">Wenn zwei Ausdrücke zu dem gleichen Datentyp ausgewertet werden, wird der Datentyp verglichen.</span><span class="sxs-lookup"><span data-stu-id="a32ff-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="a32ff-139">Wenn ein Ausdruck den DT_DBTIMESTAMPOFFSET-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMPOFFSET konvertiert, und ein DT_DBTIMESTAMPOFFSET-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a32ff-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="a32ff-140">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a32ff-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="a32ff-141">Wenn ein Ausdruck den DT_DBTIMESTAMP2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMP2 konvertiert, und ein DT_DBTIMESTAMP2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a32ff-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="a32ff-142">Wenn ein Ausdruck den DT_DBTIME2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIME2 konvertiert, und ein DT_DBTIME2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a32ff-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="a32ff-143">Wenn ein Ausdruck einen anderen Datentyp als DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 oder DT_DBTIME2 aufweist, werden die Ausdrücke vor dem Vergleichen in den DT_DBTIMESTAMP-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a32ff-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="a32ff-144">Beim Vergleichen der Ausdrücke gelten folgende Annahmen:</span><span class="sxs-lookup"><span data-stu-id="a32ff-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="a32ff-145">Wenn jeder Ausdruck einen Datentyp aufweist, der Millisekunden umfasst, wird angenommen, dass bei dem Datentyp mit der geringsten Anzahl von Ziffern für Millisekunden die verbleibenden Ziffern Nullen sind.</span><span class="sxs-lookup"><span data-stu-id="a32ff-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="a32ff-146">Wenn jeder Ausdruck einen Datumsdatentyp aufweist, jedoch nur ein Ausdruck einen Zeitzonenoffset umfasst, wird angenommen, dass der Datumsdatentyp ohne Zeitzonenoffset in koordinierter Weltzeit (Coordinated Universal Time; UTC) ausgedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="a32ff-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="a32ff-147">Weitere Informationen zu Datentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a32ff-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a32ff-148">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="a32ff-148">Expression Examples</span></span>  
 <span data-ttu-id="a32ff-149">In diesem Beispiel wird ein Ausdruck gezeigt, der bedingt zu `savannah` oder `unknown`ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="a32ff-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="a32ff-150">Dieses Beispiel zeigt einen Ausdruck, der auf eine **ListPrice** -Spalte verweist.</span><span class="sxs-lookup"><span data-stu-id="a32ff-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="a32ff-151">**ListPrice** weist den DT_CY-Datentyp auf.</span><span class="sxs-lookup"><span data-stu-id="a32ff-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="a32ff-152">Der Ausdruck multipliziert **ListPrice** bedingt mit 0,2 oder 0,1.</span><span class="sxs-lookup"><span data-stu-id="a32ff-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="a32ff-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a32ff-153">See Also</span></span>  
 <span data-ttu-id="a32ff-154">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="a32ff-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="a32ff-155">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="a32ff-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
