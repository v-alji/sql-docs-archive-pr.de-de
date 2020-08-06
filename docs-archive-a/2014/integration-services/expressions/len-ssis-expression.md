---
title: LEN (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616597"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="ef28b-102">LEN (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="ef28b-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="ef28b-103">Gibt die Anzahl von Zeichen in einem Zeichenausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="ef28b-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="ef28b-104">Wenn die Zeichenfolge führende und nachfolgende Leerzeichen enthält, werden sie von der Funktion für die Anzahl berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ef28b-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="ef28b-105">LEN gibt identische Werte für dieselbe Zeichenfolge mit Einzelbyte- und Doppelbytezeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="ef28b-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef28b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef28b-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ef28b-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="ef28b-107">Arguments</span></span>  
 <span data-ttu-id="ef28b-108">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="ef28b-108">*character_expression*</span></span>  
 <span data-ttu-id="ef28b-109">Der auszuwertende Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ef28b-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ef28b-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="ef28b-110">Result Types</span></span>  
 <span data-ttu-id="ef28b-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="ef28b-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef28b-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ef28b-112">Remarks</span></span>  
 <span data-ttu-id="ef28b-113">Das *character_expression* -Argument kann den Datentyp DT_WSTR, DT_TEXT, DT_NTEXT oder DT_IMAGE aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ef28b-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="ef28b-114">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ef28b-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ef28b-115">Wenn *character_expression* ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird dieses bzw. diese implizit in den DT_WSTR-Datentyp umgewandelt, bevor LEN ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef28b-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="ef28b-116">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ef28b-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="ef28b-117">Weitere Informationen finden Sie unter [Umwandlung &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ef28b-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="ef28b-118">Falls das an die LEN-Funktion übergebene Argument einen BLOB-Datentyp (Binary Large Object Block) aufweist, wie z. B. DT_TEXT, DT_NTEXT oder DT_IMAGE, gibt die Funktion die Anzahl der Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="ef28b-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="ef28b-119">LEN gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ef28b-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ef28b-120">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ef28b-120">Expression Examples</span></span>  
 <span data-ttu-id="ef28b-121">In diesem Beispiel wird die Länge eines Zeichenfolgenliterals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef28b-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="ef28b-122">Als Ergebnis wird 12 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef28b-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="ef28b-123">In diesem Beispiel wird die Differenz zwischen der Länge von Werten in den Spalten **FirstName** und **LastName** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef28b-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="ef28b-124">Gibt die Länge eines Computernamens mithilfe der **MachineName**-Systemvariablen zurück.</span><span class="sxs-lookup"><span data-stu-id="ef28b-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef28b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef28b-125">See Also</span></span>  
 [<span data-ttu-id="ef28b-126">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="ef28b-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
