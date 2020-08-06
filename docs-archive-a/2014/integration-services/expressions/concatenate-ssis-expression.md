---
title: + (Verketten) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701486"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="6f28f-102">+ (Verketten) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="6f28f-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="6f28f-103">Verkettet zwei Ausdrücke zu einem einzelnen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6f28f-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f28f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f28f-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f28f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6f28f-105">Arguments</span></span>  
 <span data-ttu-id="6f28f-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="6f28f-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="6f28f-107">Ein gültiger Ausdruck vom Datentyp DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT oder DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="6f28f-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6f28f-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="6f28f-108">Result Types</span></span>  
 <span data-ttu-id="6f28f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="6f28f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f28f-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6f28f-110">Remarks</span></span>  
 <span data-ttu-id="6f28f-111">Für den Ausdruck können die Datentypen DT_STR und/oder DT_WSTR verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="6f28f-112">Die Verkettung der Datentypen DT_STR und DT_WSTR gibt ein Ergebnis vom DT_WSTR-Datentyp zurück.</span><span class="sxs-lookup"><span data-stu-id="6f28f-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="6f28f-113">Die Länge der Zeichenfolge ist die Summe der Längen der ursprünglichen Zeichenfolgen, ausgedrückt in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6f28f-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="6f28f-114">Nur Daten mit den Zeichenfolgen-Datentypen DT_STR und DT_WSTR oder den BLOB-Datentypen (Binary Large Object Block) DT_TEXT, DT_NTEXT und DT_IMAGE können verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="6f28f-115">Andere Datentypen müssen vor der Verkettung explizit in einen dieser Datentypen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="6f28f-116">Weitere Informationen zu zulässigen Datentypumwandlungen finden Sie unter [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="6f28f-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="6f28f-117">Beide Ausdrücke müssen vom gleichen Datentyp sein, oder es muss möglich sein, einen Ausdruck implizit in den Datentyp des anderen Ausdrucks zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6f28f-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="6f28f-118">Wenn z. B. die Zeichenfolge "Order date is " und die **OrderDate** -Spalte verkettet werden, werden die Werte in **OrderDate** implizit in einen Zeichenfolgen-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6f28f-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="6f28f-119">Um zwei numerische Werte zu verketten, müssen beide numerischen Werte explizit in einen Zeichenfolgen-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="6f28f-120">In einer Verkettung kann nur ein BLOB-Datentyp verwendet werden: DT_TEXT, DT_NTEXT oder DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="6f28f-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="6f28f-121">Wenn eines der Elemente NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="6f28f-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="6f28f-122">Zeichenfolgenliterale müssen in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6f28f-123">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6f28f-123">Expression Examples</span></span>  
 <span data-ttu-id="6f28f-124">In diesem Beispiel werden die Werte in den Spalten **FirstName** und **LastName** verkettet und ein Leerzeichen dazwischen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6f28f-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="6f28f-125">In diesem Beispiel werden die Variablen **ZIPCode** und **ZIPCode+4**verkettet.</span><span class="sxs-lookup"><span data-stu-id="6f28f-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="6f28f-126">Beide Variablen weisen einen Zeichenfolgen-Datentyp auf.</span><span class="sxs-lookup"><span data-stu-id="6f28f-126">Both variables have a string data type.</span></span> <span data-ttu-id="6f28f-127">**ZIPCode+4** muss in eckige Klammern eingeschlossen werden, weil der Variablenname das Zeichen + enthält.</span><span class="sxs-lookup"><span data-stu-id="6f28f-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f28f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f28f-128">See Also</span></span>  
 <span data-ttu-id="6f28f-129">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="6f28f-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="6f28f-130">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="6f28f-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
