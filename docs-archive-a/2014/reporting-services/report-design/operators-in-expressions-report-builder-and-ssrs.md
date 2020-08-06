---
title: Operatoren in Ausdrücken (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617732"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="e6d8b-102">Operatoren in Ausdrücken (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6d8b-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e6d8b-103">Ein Operator ist ein Symbol, das Aktionen darstellt, die auf einen oder mehrere Begriffe in einem Ausdruck angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="e6d8b-104">Die folgenden Operatorkategorien werden in einem Ausdruck unterstützt: Arithmetik, Vergleich, Verkettung, logisch oder bitweise und Bitverschiebung</span><span class="sxs-lookup"><span data-stu-id="e6d8b-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="e6d8b-105">Arithmetik</span><span class="sxs-lookup"><span data-stu-id="e6d8b-105">Arithmetic</span></span>  
 <span data-ttu-id="e6d8b-106">Arithmetische Operatoren führen mathematische Vorgänge für zwei numerische Begriffe in einem Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="e6d8b-107">Operator</span><span class="sxs-lookup"><span data-stu-id="e6d8b-107">Operator</span></span>|<span data-ttu-id="e6d8b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d8b-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="e6d8b-109">Erhebt eine Zahl zur Potenz einer anderen Zahl.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="e6d8b-110">Multipliziert zwei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="e6d8b-111">Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="e6d8b-112">\|Dividiert zwei Zahlen und gibt eine ganze Zahl als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="e6d8b-113">Mod</span><span class="sxs-lookup"><span data-stu-id="e6d8b-113">Mod</span></span>|<span data-ttu-id="e6d8b-114">Gibt den ganzzahligen Rest einer Division zurück.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="e6d8b-115">Beispiel: 7 Mod 5 = 2 (der Rest von 7 geteilt durch 5 ist 2).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="e6d8b-116">Addiert zwei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="e6d8b-117">Gibt die Differenz zwischen zwei Zahlen zurück oder gibt den negativen Wert eines numerischen Begriffs an.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="e6d8b-118">Vergleich</span><span class="sxs-lookup"><span data-stu-id="e6d8b-118">Comparison</span></span>  
 <span data-ttu-id="e6d8b-119">Vergleichsoperatoren testen, ob zwei Ausdrücke gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="e6d8b-120">Operator</span><span class="sxs-lookup"><span data-stu-id="e6d8b-120">Operator</span></span>|<span data-ttu-id="e6d8b-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d8b-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="e6d8b-122">Kleiner als.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="e6d8b-123">Kleiner oder gleich.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="e6d8b-124">Größer als.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="e6d8b-125">Größer oder gleich.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="e6d8b-126">Gleich.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="e6d8b-127">Ungleich.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-127">Not equal to.</span></span>|  
|<span data-ttu-id="e6d8b-128">Wie</span><span class="sxs-lookup"><span data-stu-id="e6d8b-128">Like</span></span>|<span data-ttu-id="e6d8b-129">Bestimmt, ob eine bestimmte Zeichenfolge mit einem angegebenen Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="e6d8b-130">Ein Muster kann normale Zeichen und Platzhalterzeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="e6d8b-131">Bei einem Mustervergleich müssen normale Zeichen exakt mit den angegebenen Zeichen in der Zeichenfolge übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="e6d8b-132">Platzhalterzeichen können jedoch mit beliebigen Teilen der Zeichenfolge übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="e6d8b-133">Das Verwenden der Vergleichsoperatoren für Zeichenfolgen = und != ist nicht so flexibel wie das Verwenden von Platzhalterzeichen mit dem LIKE-Operator.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="e6d8b-134">Im folgenden sind die Zeichen aufgeführt, die als Platzhalter Zeichen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="e6d8b-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="e6d8b-135">**%**: Eine beliebige Zeichenfolge mit NULL oder mehr Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="e6d8b-136">**_**: Beliebiges einzelnes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="e6d8b-137">**[]**: Ein beliebiges einzelnes Zeichen innerhalb des angegebenen Bereichs (z. b. [a-f]) oder der festgelegten Menge (z. b. [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="e6d8b-138">**[^]**: Ein einzelnes Zeichen, das nicht innerhalb des angegebenen Bereichs (z. b. [^ a-f]) oder der festgelegten Menge (z. b. [^ aeiou]) liegt.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="e6d8b-139">Is</span><span class="sxs-lookup"><span data-stu-id="e6d8b-139">Is</span></span>|<span data-ttu-id="e6d8b-140">Vergleicht zwei Objektverweise.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="e6d8b-141">Verketten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e6d8b-141">String Concatenation</span></span>  
 <span data-ttu-id="e6d8b-142">Mit der Zeichenfolgenverkettung wird die zweite Zeichenfolge in einem Ausdruck an die erste Zeichenfolge angefügt.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="e6d8b-143">Verwenden Sie für andere Zeichenfolgenoperationen integrierte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="e6d8b-144">Operator</span><span class="sxs-lookup"><span data-stu-id="e6d8b-144">Operator</span></span>|<span data-ttu-id="e6d8b-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d8b-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="e6d8b-146">Verkettet zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="e6d8b-147">Verkettet zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="e6d8b-148">Logisch und bitweise</span><span class="sxs-lookup"><span data-stu-id="e6d8b-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="e6d8b-149">Logische und bitweise Operatoren führen logische Manipulationen zwischen zwei ganzzahligen Begriffen in einem Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="e6d8b-150">Operator</span><span class="sxs-lookup"><span data-stu-id="e6d8b-150">Operator</span></span>|<span data-ttu-id="e6d8b-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d8b-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e6d8b-152">And</span><span class="sxs-lookup"><span data-stu-id="e6d8b-152">And</span></span>|<span data-ttu-id="e6d8b-153">Führt eine logische Konjunktion zweier boolescher Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="e6d8b-154">Not</span><span class="sxs-lookup"><span data-stu-id="e6d8b-154">Not</span></span>|<span data-ttu-id="e6d8b-155">Führt eine logische Negation eines booleschen Ausdrucks oder eine bitweise Negation eines numerischen Ausdrucks aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="e6d8b-156">oder</span><span class="sxs-lookup"><span data-stu-id="e6d8b-156">Or</span></span>|<span data-ttu-id="e6d8b-157">Führt eine logische Disjunktion zweier boolescher Ausdrücke oder eine bitweise Disjunktion zweier numerischer Werte aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="e6d8b-158">Xor</span><span class="sxs-lookup"><span data-stu-id="e6d8b-158">Xor</span></span>|<span data-ttu-id="e6d8b-159">Führt einen logischen Ausschluss zweier boolescher Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke durch.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="e6d8b-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="e6d8b-160">AndAlso</span></span>|<span data-ttu-id="e6d8b-161">Führt eine logische Konjunktion zweier Ausdrücke durch.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="e6d8b-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="e6d8b-162">OrElse</span></span>|<span data-ttu-id="e6d8b-163">Führt eine logische Disjunktion zweier Ausdrücke durch.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="e6d8b-164">Bitverschiebung</span><span class="sxs-lookup"><span data-stu-id="e6d8b-164">Bit Shift</span></span>  
 <span data-ttu-id="e6d8b-165">Bitweise Operatoren führen Bitmanipulationen zwischen zwei ganzzahligen Begriffen in einem Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="e6d8b-166">Operator</span><span class="sxs-lookup"><span data-stu-id="e6d8b-166">Operator</span></span>|<span data-ttu-id="e6d8b-167">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d8b-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="e6d8b-168">Führt eine arithmetische Verschiebung nach links für ein Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="e6d8b-169">Führt eine arithmetische Verschiebung nach rechts für ein Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6d8b-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6d8b-170">See Also</span></span>  
 <span data-ttu-id="e6d8b-171">[Ausdruck (Dialogfeld)](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8b-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="e6d8b-172">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8b-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6d8b-173">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8b-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6d8b-174">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8b-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e6d8b-175">Dialogfeld „Ausdruck“ (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="e6d8b-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
