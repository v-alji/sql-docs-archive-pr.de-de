---
title: '!= (Ungleich) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- unequal operator (!=)
- '!= (not equal to)'
ms.assetid: fad20e85-c0e6-42bf-af70-2bc80ee09be5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be3eadbac77d76a2b3aac9555d9f40cb56e38949
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701319"
---
# <a name="-unequal-ssis-expression"></a><span data-ttu-id="43ef6-102">!= (Ungleich) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43ef6-102">!= (Unequal) (SSIS Expression)</span></span>
  <span data-ttu-id="43ef6-103">Führt einen Vergleich aus, um zu ermitteln, ob zwei Ausdrücke mit kompatiblen Datentypen ungleich sind.</span><span class="sxs-lookup"><span data-stu-id="43ef6-103">Performs a comparison to determine if two expressions with compatible data types are not equal.</span></span> <span data-ttu-id="43ef6-104">Die Ausdrucksauswertung konvertiert viele Datentypen automatisch vor dem Vergleich.</span><span class="sxs-lookup"><span data-stu-id="43ef6-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
 <span data-ttu-id="43ef6-105">Für manche Datentypen muss jedoch der Ausdruck eine explizite Umwandlung einschließen, damit der Ausdruck erfolgreich ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="43ef6-105">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="43ef6-106">Weitere Informationen zu zulässigen Datentypumwandlungen finden Sie unter [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-106">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ef6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="43ef6-107">Syntax</span></span>  
  
```  
  
expression1 != expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="43ef6-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="43ef6-108">Arguments</span></span>  
 <span data-ttu-id="43ef6-109">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="43ef6-109">*expression1, expression2*</span></span>  
 <span data-ttu-id="43ef6-110">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="43ef6-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="43ef6-111">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="43ef6-111">Result Types</span></span>  
 <span data-ttu-id="43ef6-112">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="43ef6-112">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43ef6-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="43ef6-113">Remarks</span></span>  
 <span data-ttu-id="43ef6-114">Wenn einer der Ausdrücke im Vergleich NULL ist, ist das Ergebnis des Vergleichs NULL.</span><span class="sxs-lookup"><span data-stu-id="43ef6-114">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="43ef6-115">Wenn beide Ausdrücke NULL sind, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="43ef6-115">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="43ef6-116">Für die Ausdrucksgruppe ( *expression1* und *expression2*) muss eine der folgenden Regeln eingehalten werden:</span><span class="sxs-lookup"><span data-stu-id="43ef6-116">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="43ef6-117">\**Numerisch\*\*\*expression1* und *expression2* müssen einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="43ef6-117">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="43ef6-118">Die Schnittmenge der Datentypen muss ein numerischer Datentyp gemäß der Regeln zu den impliziten numerischen Konvertierungen sein, die die Ausdrucksauswertung ausführt.</span><span class="sxs-lookup"><span data-stu-id="43ef6-118">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="43ef6-119">Die Schnittmenge der beiden numerischen Datentypen darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="43ef6-119">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="43ef6-120">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-120">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="43ef6-121">**Zeichen** : *expression1* und *expression2* müssen zu einem der Datentypen DT_STR oder DT_WSTR ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-121">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="43ef6-122">Die beiden Ausdrücke können zu verschiedenen Zeichenfolgen-Datentypen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-122">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43ef6-123">Bei Zeichenfolgenvergleichen wird nach Groß-/Kleinschreibung, Akzent, Kana und Breite unterschieden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-123">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="43ef6-124">**Datum, Uhrzeit oder Datum/Uhrzeit** Sowohl *expression1* als auch *expression2* müssen zu einem der folgenden Datentypen ausgewertet werden: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET oder DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="43ef6-124">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43ef6-125">Das System unterstützt keine Vergleiche zwischen einem Ausdruck, der zu einem Uhrzeitdatentyp ausgewertet wird, und einem Ausdruck, der entweder zu einem Datums- oder zu einem Datums-/Uhrzeitdatentyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="43ef6-125">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="43ef6-126">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="43ef6-126">The system generates an error.</span></span>  
  
     <span data-ttu-id="43ef6-127">Beim Vergleich der Ausdrücke werden die folgenden Konvertierungsregeln in der angegebenen Reihenfolge angewendet:</span><span class="sxs-lookup"><span data-stu-id="43ef6-127">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="43ef6-128">Wenn zwei Ausdrücke zu dem gleichen Datentyp ausgewertet werden, wird der Datentyp verglichen.</span><span class="sxs-lookup"><span data-stu-id="43ef6-128">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="43ef6-129">Wenn ein Ausdruck den DT_DBTIMESTAMPOFFSET-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMPOFFSET konvertiert, und ein DT_DBTIMESTAMPOFFSET-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43ef6-129">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="43ef6-130">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="43ef6-131">Wenn ein Ausdruck den DT_DBTIMESTAMP2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMP2 konvertiert, und ein DT_DBTIMESTAMP2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43ef6-131">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="43ef6-132">Wenn ein Ausdruck den DT_DBTIME2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIME2 konvertiert, und ein DT_DBTIME2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43ef6-132">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="43ef6-133">Wenn ein Ausdruck einen anderen Datentyp als DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 oder DT_DBTIME2 aufweist, werden die Ausdrücke vor dem Vergleichen in den DT_DBTIMESTAMP-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="43ef6-133">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="43ef6-134">Beim Vergleichen der Ausdrücke gelten folgende Annahmen:</span><span class="sxs-lookup"><span data-stu-id="43ef6-134">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="43ef6-135">Wenn jeder Ausdruck einen Datentyp aufweist, der Millisekunden umfasst, wird angenommen, dass bei dem Datentyp mit der geringsten Anzahl von Ziffern für Millisekunden die verbleibenden Ziffern Nullen sind.</span><span class="sxs-lookup"><span data-stu-id="43ef6-135">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="43ef6-136">Wenn jeder Ausdruck einen Datumsdatentyp aufweist, jedoch nur ein Ausdruck einen Zeitzonenoffset umfasst, wird angenommen, dass der Datumsdatentyp ohne Zeitzonenoffset in koordinierter Weltzeit (Coordinated Universal Time; UTC) ausgedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="43ef6-136">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="43ef6-137">\**Logisch\*\*\*expression1* und *expression2* müssen zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-137">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="43ef6-138">**GUID:** *expression1* und *expression2* müssen zum Datentyp DT_GUID ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-138">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="43ef6-139">**Binary:** *expression1* und *expression2* müssen zum Datentyp DT_BYTES ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="43ef6-139">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="43ef6-140">**BLOB:** *expression1* und *expression2* müssen zum gleichen BLOB-Datentyp (Binary Large Object Block) ausgewertet werden: DT_TEXT, DT_NTEXT oder DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="43ef6-140">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="43ef6-141">Weitere Informationen zu Datentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-141">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="43ef6-142">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="43ef6-142">Expression Examples</span></span>  
 <span data-ttu-id="43ef6-143">In diesem Beispiel wird nur zu TRUE ausgewertet, falls das aktuelle Datum nicht der 4. Juli 2003 ist.</span><span class="sxs-lookup"><span data-stu-id="43ef6-143">This example evaluates to TRUE only if the current date is not July 4, 2003.</span></span> <span data-ttu-id="43ef6-144">Weitere Informationen finden Sie unter [GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-144">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" != GETDATE()  
```  
  
 <span data-ttu-id="43ef6-145">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert in der **ListPrice** -Spalte nicht 500 ist.</span><span class="sxs-lookup"><span data-stu-id="43ef6-145">This example evaluates to TRUE if the value in the **ListPrice** column is not 500.</span></span>  
  
```  
ListPrice != 500  
```  
  
 <span data-ttu-id="43ef6-146">In diesem Beispiel wird die **LPrice**-Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="43ef6-146">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="43ef6-147">Es wird zu TRUE ausgewertet, falls der Wert in der **LPrice** -Spalte nicht 500 entspricht.</span><span class="sxs-lookup"><span data-stu-id="43ef6-147">It evaluates to TRUE if the value of **LPrice** is not 500.</span></span> <span data-ttu-id="43ef6-148">Der Datentyp der Variablen muss numerisch sein, damit der Ausdruck analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="43ef6-148">The data type on the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice != 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="43ef6-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43ef6-149">See Also</span></span>  
 <span data-ttu-id="43ef6-150">[== &#40;Gleich, SSIS-Ausdruck&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="43ef6-150">[== &#40;Equal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="43ef6-151">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="43ef6-151">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="43ef6-152">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="43ef6-152">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
