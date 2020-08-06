---
title: Cast (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721673"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="30ef5-102">CAST (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="30ef5-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="30ef5-103">Konvertiert einen Ausdruck explizit in einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="30ef5-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="30ef5-104">Der Umwandlungsoperator kann auch als Operator zum Abschneiden dienen.</span><span class="sxs-lookup"><span data-stu-id="30ef5-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="30ef5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="30ef5-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="30ef5-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="30ef5-106">Arguments</span></span>
 <span data-ttu-id="30ef5-107">*type_spec* Ein gültiger- [!INCLUDE[ssIS](../../includes/ssis-md.md)] Datentyp.</span><span class="sxs-lookup"><span data-stu-id="30ef5-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="30ef5-108">*Ausdruck* Ein gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="30ef5-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="30ef5-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="30ef5-109">Result Types</span></span>
 <span data-ttu-id="30ef5-110">Der Datentyp von *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="30ef5-110">The data type of *type_spec*.</span></span> <span data-ttu-id="30ef5-111">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="30ef5-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="30ef5-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30ef5-112">Remarks</span></span>
 <span data-ttu-id="30ef5-113">Im folgenden Diagramm werden zulässige Umwandlungsvorgänge dargestellt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="30ef5-114">![Zulässige und unzulässige Umwandlungen zwischen Datentypen](../media/data-conversion.gif "Zulässige und unzulässige Umwandlungen zwischen Datentypen")</span><span class="sxs-lookup"><span data-stu-id="30ef5-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="30ef5-115">Für die Umwandlung in bestimmte Datentypen sind Parameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30ef5-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="30ef5-116">In der folgenden Tabelle sind diese Datentypen und die zugehörigen Parameter aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="30ef5-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="30ef5-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30ef5-117">Data type</span></span>|<span data-ttu-id="30ef5-118">Parameter</span><span class="sxs-lookup"><span data-stu-id="30ef5-118">Parameter</span></span>|<span data-ttu-id="30ef5-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30ef5-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="30ef5-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="30ef5-120">DT_STR</span></span>|<span data-ttu-id="30ef5-121">*charcount*</span><span class="sxs-lookup"><span data-stu-id="30ef5-121">*charcount*</span></span><br /><br /> <span data-ttu-id="30ef5-122">*Codepage*</span><span class="sxs-lookup"><span data-stu-id="30ef5-122">*codepage*</span></span>|<span data-ttu-id="30ef5-123">(DT_STR,30,1252) wandelt 30 Bytes, oder 30 einzelne Zeichen, mithilfe der 1252-Codepage in den DT_STR-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="30ef5-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="30ef5-124">DT_WSTR</span></span>|<span data-ttu-id="30ef5-125">*CharCount*</span><span class="sxs-lookup"><span data-stu-id="30ef5-125">*Charcount*</span></span>|<span data-ttu-id="30ef5-126">(DT_WSTR,20) wandelt 20 Bytepaare, oder 20 Unicode-Zeichen, in den DT_WSTR-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="30ef5-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="30ef5-127">DT_BYTES</span></span>|<span data-ttu-id="30ef5-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="30ef5-128">*Bytecount*</span></span>|<span data-ttu-id="30ef5-129">(DT_BYTES,50) wandelt 50 Bytes in den DT_BYTES-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="30ef5-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="30ef5-130">DT_DECIMAL</span></span>|<span data-ttu-id="30ef5-131">*Skalierung*</span><span class="sxs-lookup"><span data-stu-id="30ef5-131">*Scale*</span></span>|<span data-ttu-id="30ef5-132">(DT_DECIMAL,2) wandelt einen numerischen Wert mithilfe von 2 Dezimalstellen in den DT_DECIMAL-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="30ef5-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="30ef5-133">DT_NUMERIC</span></span>|<span data-ttu-id="30ef5-134">*Genauigkeit*</span><span class="sxs-lookup"><span data-stu-id="30ef5-134">*Precision*</span></span><br /><br /> <span data-ttu-id="30ef5-135">*Skalierung*</span><span class="sxs-lookup"><span data-stu-id="30ef5-135">*Scale*</span></span>|<span data-ttu-id="30ef5-136">(DT_NUMERIC,10,3) wandelt einen numerischen Wert mithilfe einer Genauigkeit von 10 und 3 Dezimalstellen in den DT_NUMERIC-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="30ef5-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="30ef5-137">DT_TEXT</span></span>|<span data-ttu-id="30ef5-138">*Codepage*</span><span class="sxs-lookup"><span data-stu-id="30ef5-138">*Codepage*</span></span>|<span data-ttu-id="30ef5-139">(DT_TEXT,1252) wandelt einen Wert mithilfe der 1252-Codepage in den DT_TEXT-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="30ef5-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="30ef5-140">Wenn eine Zeichenfolge in einen DT_DATE-Datentyp umgewandelt wird, oder umgekehrt, wird das Gebietsschema der Transformation verwendet.</span><span class="sxs-lookup"><span data-stu-id="30ef5-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="30ef5-141">Allerdings weist das Datum das ISO-Format YYYY-MM-DD auf, und zwar unabhängig davon, ob für das Gebietsschema das ISO-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30ef5-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="30ef5-142">Informationen zum Konvertieren einer Zeichenfolge in einen anderen Datumsdatentyp als DT_DATE finden Sie unter [SQL Server Integration Services-Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="30ef5-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="30ef5-143">Falls die Codepage eine Multibytezeichen-Codepage ist, kann die Anzahl der Bytes und Zeichen abweichen.</span><span class="sxs-lookup"><span data-stu-id="30ef5-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="30ef5-144">Durch das Umwandeln von DT_WSTR in DT_STR mit dem gleichen *charcount* -Wert können die letzten Zeichen in der konvertierten Zeichenfolge abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="30ef5-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="30ef5-145">Falls in der Spalte der Zieltabelle ausreichend Speicherplatz vorhanden ist, legen Sie für den Wert des *charcount* -Parameters die Anzahl der Bytes fest, die die Multibytecodepage erfordert.</span><span class="sxs-lookup"><span data-stu-id="30ef5-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="30ef5-146">Wenn Sie z.B. Zeichendaten mithilfe der 936-Codepage in einen DT_STR-Datentyp umwandeln, sollten Sie für *charcount* einen Wert festlegen, der bis zu zweimal größer als die Anzahl von Zeichen ist, die die Daten erwartungsgemäß enthalten. Falls Sie Zeichendaten mithilfe der UTF-8-Codepage umwandeln, sollten Sie für *charcount* einen Wert festlegen, der bis zu viermal größer ist.</span><span class="sxs-lookup"><span data-stu-id="30ef5-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="30ef5-147">Weitere Informationen zur Struktur von Datumsdatentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="30ef5-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="30ef5-148">Beispiele für SSIS-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="30ef5-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="30ef5-149">In diesem Beispiel wird ein numerischer Wert in eine ganze Zahl umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="30ef5-150">In diesem Beispiel wird eine ganze Zahl mithilfe der 1252-Codepage in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="30ef5-151">In diesem Beispiel wird eine aus drei Zeichen bestehende Zeichenfolge in Doppelbytezeichen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="30ef5-152">In diesem Beispiel wird eine ganze Zahl in eine Dezimalzahl mit zwei Dezimalstellen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="30ef5-153">In diesem Beispiel wird eine ganze Zahl in einen numerischen Wert mit einer Genauigkeit von 7 und drei Dezimalstellen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="30ef5-154">In diesem Beispiel werden Werte in der **FirstName** -Spalte, für die ein **nvarchar** -Datentyp und eine Länge von 50 definiert ist, mithilfe der 1252-Codepage in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="30ef5-155">In diesem Beispiel werden Werte in der Spalte **DateFirstPurchase** des Typs DT_DBDATE in eine Unicode-Zeichenfolge mit einer Länge von 20 Zeichen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="30ef5-156">In diesem Beispiel wird das Zeichenfolgenliteral "True" in einen booleschen Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="30ef5-157">In diesem Beispiel wird ein Zeichenfolgenliteral in DT_DBDATE umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="30ef5-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="30ef5-158">In diesem Beispiel wird ein Zeichenfolgenliteral in den DT_DBTIME2-Datentyp umgewandelt, bei dem fünf Ziffern für Millisekunden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30ef5-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="30ef5-159">(Beim DT_DBTIME2-Datentyp können null bis sieben Ziffern für Millisekunden angegeben werden.)</span><span class="sxs-lookup"><span data-stu-id="30ef5-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="30ef5-160">In diesem Beispiel wird ein Zeichenfolgenliteral in den DT_DBTIMESTAMP2-Datentyp umgewandelt, bei dem vier Ziffern für Millisekunden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30ef5-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="30ef5-161">(Beim DT_DBTIMESTAMP2-Datentyp können null bis sieben Ziffern für Millisekunden angegeben werden.)</span><span class="sxs-lookup"><span data-stu-id="30ef5-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="30ef5-162">In diesem Beispiel wird ein Zeichenfolgenliteral in den DT_DBTIMESTAMPOFFSET-Datentyp umgewandelt, bei dem sieben Ziffern für Millisekunden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30ef5-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="30ef5-163">(Beim DT_DBTIMESTAMPOFFSET-Datentyp können null bis sieben Ziffern für Millisekunden angegeben werden.)</span><span class="sxs-lookup"><span data-stu-id="30ef5-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="30ef5-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30ef5-164">See Also</span></span>
 <span data-ttu-id="30ef5-165">[Operator Rangfolge und Assoziativität-](operator-precedence-and-associativity.md) [Operatoren &#40;SSIS-Ausdruck&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS-&#41; Ausdrücke](integration-services-ssis-expressions.md) [Integration Services-Datentypen in Ausdrücken](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="30ef5-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


