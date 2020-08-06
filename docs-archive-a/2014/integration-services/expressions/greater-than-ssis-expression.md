---
title: '&gt; (Größer als) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- greater than operator (>)
- '> (greater than operator)'
ms.assetid: 2e22efa3-eeb1-4984-a95c-9bccdcf98892
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dfc7ff5d43f85fa16c3a14ff59fb9b8b95299617
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701462"
---
# <a name="gt-greater-than-ssis-expression"></a><span data-ttu-id="5645e-102">&gt; (Größer als) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="5645e-102">&gt; (Greater Than) (SSIS Expression)</span></span>
  <span data-ttu-id="5645e-103">Führt einen Vergleich aus, um zu ermitteln, ob der erste Ausdruck größer ist als der zweite.</span><span class="sxs-lookup"><span data-stu-id="5645e-103">Performs a comparison to determine if the first expression is greater than the second one.</span></span> <span data-ttu-id="5645e-104">Die Ausdrucksauswertung konvertiert viele Datentypen automatisch vor dem Vergleich.</span><span class="sxs-lookup"><span data-stu-id="5645e-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5645e-105">Vergleiche, die die Datentypen DT_TEXT, DT_NTEXT oder DT_IMAGE verwenden, werden von diesem Operator nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5645e-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="5645e-106">Für manche Datentypen muss jedoch der Ausdruck eine explizite Umwandlung einschließen, damit der Ausdruck erfolgreich ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5645e-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="5645e-107">Weitere Informationen zu zulässigen Datentypumwandlungen finden Sie unter [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5645e-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5645e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5645e-108">Syntax</span></span>  
  
```  
  
expression1 > expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5645e-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="5645e-109">Arguments</span></span>  
 <span data-ttu-id="5645e-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="5645e-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="5645e-111">Ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5645e-111">Is any valid expression.</span></span> <span data-ttu-id="5645e-112">Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen.</span><span class="sxs-lookup"><span data-stu-id="5645e-112">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5645e-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="5645e-113">Result Types</span></span>  
 <span data-ttu-id="5645e-114">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="5645e-114">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5645e-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5645e-115">Remarks</span></span>  
 <span data-ttu-id="5645e-116">Wenn einer der Ausdrücke im Vergleich NULL ist, ist das Ergebnis des Vergleichs NULL.</span><span class="sxs-lookup"><span data-stu-id="5645e-116">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="5645e-117">Wenn beide Ausdrücke NULL sind, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="5645e-117">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="5645e-118">Für die Ausdrucksgruppe ( *expression1* und *expression2*) muss eine der folgenden Regeln eingehalten werden:</span><span class="sxs-lookup"><span data-stu-id="5645e-118">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="5645e-119">\**Numerisch\*\*\*expression1* und *expression2* müssen einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5645e-119">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="5645e-120">Die Schnittmenge der Datentypen muss ein numerischer Datentyp gemäß den Regeln zu den impliziten numerischen Konvertierungen sein, die die Ausdrucksauswertung ausführt.</span><span class="sxs-lookup"><span data-stu-id="5645e-120">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="5645e-121">Die Schnittmenge der beiden numerischen Datentypen darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="5645e-121">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="5645e-122">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5645e-122">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="5645e-123">**Zeichen** : *expression1* und *expression2* müssen zu einem der Datentypen DT_STR oder DT_WSTR ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5645e-123">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="5645e-124">Die beiden Ausdrücke können zu verschiedenen Zeichenfolgen-Datentypen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5645e-124">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5645e-125">Bei Zeichenfolgenvergleichen wird nach Groß-/Kleinschreibung, Akzent, Kana und Breite unterschieden.</span><span class="sxs-lookup"><span data-stu-id="5645e-125">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="5645e-126">**Datum, Uhrzeit oder Datum/Uhrzeit** Sowohl *expression1* als auch *expression2* müssen zu einem der folgenden Datentypen ausgewertet werden: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET oder DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="5645e-126">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5645e-127">Das System unterstützt keine Vergleiche zwischen einem Ausdruck, der zu einem Uhrzeitdatentyp ausgewertet wird, und einem Ausdruck, der entweder zu einem Datums- oder zu einem Datums-/Uhrzeitdatentyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="5645e-127">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="5645e-128">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="5645e-128">The system generates an error.</span></span>  
  
     <span data-ttu-id="5645e-129">Beim Vergleich der Ausdrücke werden die folgenden Konvertierungsregeln in der angegebenen Reihenfolge angewendet:</span><span class="sxs-lookup"><span data-stu-id="5645e-129">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="5645e-130">Wenn zwei Ausdrücke zu dem gleichen Datentyp ausgewertet werden, wird der Datentyp verglichen.</span><span class="sxs-lookup"><span data-stu-id="5645e-130">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="5645e-131">Wenn ein Ausdruck den DT_DBTIMESTAMPOFFSET-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMPOFFSET konvertiert, und ein DT_DBTIMESTAMPOFFSET-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5645e-131">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="5645e-132">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5645e-132">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="5645e-133">Wenn ein Ausdruck den DT_DBTIMESTAMP2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIMESTAMP2 konvertiert, und ein DT_DBTIMESTAMP2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5645e-133">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="5645e-134">Wenn ein Ausdruck den DT_DBTIME2-Datentyp aufweist, wird der andere Ausdruck implizit in DT_DBTIME2 konvertiert, und ein DT_DBTIME2-Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5645e-134">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="5645e-135">Wenn ein Ausdruck einen anderen Datentyp als DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 oder DT_DBTIME2 aufweist, werden die Ausdrücke vor dem Vergleichen in den DT_DBTIMESTAMP-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5645e-135">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="5645e-136">Beim Vergleichen der Ausdrücke gelten folgende Annahmen:</span><span class="sxs-lookup"><span data-stu-id="5645e-136">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="5645e-137">Wenn jeder Ausdruck einen Datentyp aufweist, der Millisekunden umfasst, wird angenommen, dass bei dem Datentyp mit der geringsten Anzahl von Ziffern für Millisekunden die verbleibenden Ziffern Nullen sind.</span><span class="sxs-lookup"><span data-stu-id="5645e-137">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="5645e-138">Wenn jeder Ausdruck einen Datumsdatentyp aufweist, jedoch nur ein Ausdruck einen Zeitzonenoffset umfasst, wird angenommen, dass der Datumsdatentyp ohne Zeitzonenoffset in koordinierter Weltzeit (Coordinated Universal Time; UTC) ausgedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="5645e-138">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="5645e-139">Weitere Informationen zu Datentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5645e-139">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5645e-140">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5645e-140">Expression Examples</span></span>  
 <span data-ttu-id="5645e-141">In diesem Beispiel wird zu TRUE ausgewertet, falls das aktuelle Datum der 4. Juli 2003 oder davor ist.</span><span class="sxs-lookup"><span data-stu-id="5645e-141">This example evaluates to TRUE if the current date is earlier than July 4, 2003.</span></span> <span data-ttu-id="5645e-142">Weitere Informationen finden Sie unter [GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5645e-142">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" > GETDATE()  
```  
  
 <span data-ttu-id="5645e-143">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert in der **ListPrice** -Spalte größer als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="5645e-143">This example evaluates to TRUE if the value in the **ListPrice** column is greater than 500.</span></span>  
  
```  
ListPrice > 500  
```  
  
 <span data-ttu-id="5645e-144">In diesem Beispiel wird die **LPrice**-Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="5645e-144">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="5645e-145">Es wird zu TRUE ausgewertet, falls der Wert in der **LPrice** -Spalte größer als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="5645e-145">It evaluates to TRUE if the value of **LPrice** is greater than 500.</span></span> <span data-ttu-id="5645e-146">Der Datentyp der Variablen muss numerisch sein, damit der Ausdruck analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="5645e-146">The data type of the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice > 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="5645e-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5645e-147">See Also</span></span>  
 <span data-ttu-id="5645e-148">[&#60; &#40;Kleiner als&#41; &#40;SSIS-Ausdruck&#41;](less-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5645e-148">[&#60; &#40;Less Than&#41; &#40;SSIS Expression&#41;](less-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="5645e-149">[&#62;= &#40;Größer als oder gleich&#41; &#40;SSIS-Ausdruck&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5645e-149">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="5645e-150">[&#60;= &#40;Kleiner als oder gleich&#41; &#40;SSIS-Ausdruck&#41;](less-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5645e-150">[&#60;= &#40;Less Than or Equal To&#41; &#40;SSIS Expression&#41;](less-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="5645e-151">[== &#40;Gleich, SSIS-Ausdruck&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5645e-151">[== &#40;Equal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="5645e-152">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="5645e-152">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="5645e-153">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="5645e-153">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
