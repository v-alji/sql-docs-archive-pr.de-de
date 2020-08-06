---
title: '&lt; (Kleiner als) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- less than (<)
- < (less than operator)
ms.assetid: 8674afdc-4276-46cb-be08-5aadfe8b9624
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d8367e337fe92667d5bdc39638d03af390797b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720278"
---
# <a name="lt-less-than-ssis-expression"></a><span data-ttu-id="bba8b-102">&lt; (Kleiner als) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="bba8b-102">&lt; (Less Than) (SSIS Expression)</span></span>
  <span data-ttu-id="bba8b-103">Führt einen Vergleich aus, um zu ermitteln, ob der erste Ausdruck kleiner ist als der zweite.</span><span class="sxs-lookup"><span data-stu-id="bba8b-103">Performs a comparison to determine if the first expression is less than the second one.</span></span> <span data-ttu-id="bba8b-104">Die Ausdrucksauswertung konvertiert viele Datentypen automatisch vor dem Vergleich.</span><span class="sxs-lookup"><span data-stu-id="bba8b-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bba8b-105">Vergleiche, die die Datentypen DT_TEXT, DT_NTEXT oder DT_IMAGE verwenden, werden von diesem Operator nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bba8b-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="bba8b-106">Für manche Datentypen muss jedoch der Ausdruck eine explizite Umwandlung einschließen, damit der Ausdruck erfolgreich ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bba8b-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="bba8b-107">Weitere Informationen zu zulässigen Datentypumwandlungen finden Sie unter [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="bba8b-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba8b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="bba8b-108">Syntax</span></span>  
  
```  
  
expression1 < expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="bba8b-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="bba8b-109">Arguments</span></span>  
 <span data-ttu-id="bba8b-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="bba8b-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="bba8b-111">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bba8b-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bba8b-112">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="bba8b-112">Result Types</span></span>  
 <span data-ttu-id="bba8b-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="bba8b-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bba8b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bba8b-114">Remarks</span></span>  
 <span data-ttu-id="bba8b-115">Wenn einer der Ausdrücke im Vergleich NULL ist, ist das Ergebnis des Vergleichs NULL.</span><span class="sxs-lookup"><span data-stu-id="bba8b-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="bba8b-116">Wenn beide Ausdrücke NULL sind, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="bba8b-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="bba8b-117">Für die Ausdrucksgruppe ( *expression1* und *expression2*) muss eine der folgenden Regeln eingehalten werden:</span><span class="sxs-lookup"><span data-stu-id="bba8b-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="bba8b-118">\**Numerisch\*\*\*expression1* und *expression2* müssen einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bba8b-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="bba8b-119">Die Schnittmenge der Datentypen muss ein numerischer Datentyp gemäß den Regeln zu den impliziten numerischen Konvertierungen sein, die die Ausdrucksauswertung ausführt.</span><span class="sxs-lookup"><span data-stu-id="bba8b-119">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="bba8b-120">Die Schnittmenge der beiden numerischen Datentypen darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="bba8b-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="bba8b-121">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bba8b-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="bba8b-122">**Zeichen** : *expression1* und *expression2* müssen zu einem der Datentypen DT_STR oder DT_WSTR ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="bba8b-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="bba8b-123">Die beiden Ausdrücke können zu verschiedenen Zeichenfolgen-Datentypen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="bba8b-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bba8b-124">Bei Zeichenfolgenvergleichen wird nach Groß-/Kleinschreibung, Akzent, Kana und Breite unterschieden.</span><span class="sxs-lookup"><span data-stu-id="bba8b-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="bba8b-125">**Datum, Uhrzeit oder Datum/Uhrzeit** Sowohl *expression1* als auch *expression2* müssen zu einem der folgenden Datentypen ausgewertet werden: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET oder DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="bba8b-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bba8b-126">Das System unterstützt keine Vergleiche zwischen einem Ausdruck, der zu einem Uhrzeitdatentyp ausgewertet wird, und einem Ausdruck, der entweder zu einem Datums- oder zu einem Datums-/Uhrzeitdatentyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="bba8b-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="bba8b-127">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="bba8b-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="bba8b-128">Beim Vergleich der Ausdrücke werden die folgenden Konvertierungsregeln in der angegebenen Reihenfolge angewendet:</span><span class="sxs-lookup"><span data-stu-id="bba8b-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="bba8b-129">Wenn zwei Ausdrücke zu dem gleichen Datentyp ausgewertet werden, wird der Datentyp verglichen.</span><span class="sxs-lookup"><span data-stu-id="bba8b-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="bba8b-130">Wenn ein Ausdruck den DT_DBTIMESTAMPOFFSET-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMPOFFSET konvertiert, und ein DT_DBTIMESTAMPOFFSET-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bba8b-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="bba8b-131">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bba8b-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="bba8b-132">Wenn ein Ausdruck den DT_DBTIMESTAMP2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMP2 konvertiert, und ein DT_DBTIMESTAMP2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bba8b-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="bba8b-133">Wenn ein Ausdruck den DT_DBTIME2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIME2 konvertiert, und ein DT_DBTIME2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bba8b-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="bba8b-134">Wenn ein Ausdruck einen anderen Datentyp als DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 oder DT_DBTIME2 aufweist, werden die Ausdrücke vor dem Vergleichen in den DT_DBTIMESTAMP-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="bba8b-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="bba8b-135">Beim Vergleichen der Ausdrücke gelten folgende Annahmen:</span><span class="sxs-lookup"><span data-stu-id="bba8b-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="bba8b-136">Wenn jeder Ausdruck einen Datentyp aufweist, der Millisekunden umfasst, wird angenommen, dass bei dem Datentyp mit der geringsten Anzahl von Ziffern für Millisekunden die verbleibenden Ziffern Nullen sind.</span><span class="sxs-lookup"><span data-stu-id="bba8b-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="bba8b-137">Wenn jeder Ausdruck einen Datumsdatentyp aufweist, jedoch nur ein Ausdruck einen Zeitzonenoffset umfasst, wird angenommen, dass der Datumsdatentyp ohne Zeitzonenoffset in koordinierter Weltzeit (Coordinated Universal Time; UTC) ausgedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="bba8b-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="bba8b-138">Weitere Informationen zu Datentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="bba8b-138">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="bba8b-139">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="bba8b-139">Expression Examples</span></span>  
 <span data-ttu-id="bba8b-140">In diesem Beispiel wird zu TRUE ausgewertet, falls das aktuelle Datum der 4. Juli 2003 oder danach ist.</span><span class="sxs-lookup"><span data-stu-id="bba8b-140">This example evaluates to TRUE if the current date is later than July 4, 2003.</span></span> <span data-ttu-id="bba8b-141">Weitere Informationen finden Sie unter [GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="bba8b-141">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" < GETDATE()  
```  
  
 <span data-ttu-id="bba8b-142">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert in der **ListPrice** -Spalte kleiner als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="bba8b-142">This example evaluates to TRUE if the value in the **ListPrice** column is less than 500.</span></span>  
  
```  
ListPrice < 500  
```  
  
 <span data-ttu-id="bba8b-143">In diesem Beispiel wird die **LPrice**-Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="bba8b-143">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="bba8b-144">Es wird zu TRUE ausgewertet, falls der Wert in der **LPrice** -Spalte kleiner als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="bba8b-144">It evaluates to TRUE if the value of **LPrice** is less than 500.</span></span> <span data-ttu-id="bba8b-145">Der Datentyp der Variablen muss numerisch sein, damit der Ausdruck analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="bba8b-145">The data type of the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice < 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="bba8b-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bba8b-146">See Also</span></span>  
 <span data-ttu-id="bba8b-147">[&#62; &#40;Größer als&#41; &#40;SSIS-Ausdruck&#41;](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="bba8b-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="bba8b-148">[&#62;= &#40;Größer als oder gleich&#41; &#40;SSIS-Ausdruck&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="bba8b-148">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="bba8b-149">[&#60;= &#40;Kleiner als oder gleich&#41; &#40;SSIS-Ausdruck&#41;](less-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="bba8b-149">[&#60;= &#40;Less Than or Equal To&#41; &#40;SSIS Expression&#41;](less-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="bba8b-150">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="bba8b-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="bba8b-151">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="bba8b-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
