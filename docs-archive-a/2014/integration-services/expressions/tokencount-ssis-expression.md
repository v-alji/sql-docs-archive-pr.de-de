---
title: TOKENCOUNT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701336"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="d60ea-102">TOKENCOUNT (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d60ea-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="d60ea-103">Gibt die Anzahl der Token in einer Zeichenfolge zurück, die durch die angegebenen Trennzeichen getrennte Token enthält.</span><span class="sxs-lookup"><span data-stu-id="d60ea-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d60ea-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d60ea-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d60ea-105">Arguments</span></span>  
 <span data-ttu-id="d60ea-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="d60ea-106">*character_expression*</span></span>  
 <span data-ttu-id="d60ea-107">Eine Zeichenfolge, die durch Trennzeichen getrennte Token enthält.</span><span class="sxs-lookup"><span data-stu-id="d60ea-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="d60ea-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="d60ea-108">*delimiter_string*</span></span>  
 <span data-ttu-id="d60ea-109">Eine Zeichenfolge, die Begrenzungszeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="d60ea-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="d60ea-110">„; ,“ enthält beispielsweise drei Begrenzungszeichen: ein Semikolon, ein Leerzeichen und ein Komma.</span><span class="sxs-lookup"><span data-stu-id="d60ea-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d60ea-111">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="d60ea-111">Result Types</span></span>  
 <span data-ttu-id="d60ea-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="d60ea-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d60ea-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d60ea-113">Remarks</span></span>  
 <span data-ttu-id="d60ea-114">Die folgenden Hinweise gelten für die TOKEN-Funktion:</span><span class="sxs-lookup"><span data-stu-id="d60ea-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="d60ea-115">Die Trennzeichenfolge kann ein oder mehrere Trennzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d60ea-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="d60ea-116">Führende Trennzeichen werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="d60ea-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="d60ea-117">TOKENCOUNT kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d60ea-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="d60ea-118">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor TOKEN ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d60ea-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="d60ea-119">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d60ea-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="d60ea-120">TOKENCOUNT gibt 0 (null) zurück, wenn character_expression NULL ist.</span><span class="sxs-lookup"><span data-stu-id="d60ea-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="d60ea-121">Sie können Variablen und Spalten als Argumente für diesen Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="d60ea-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="d60ea-122">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d60ea-122">Expression Examples</span></span>  
 <span data-ttu-id="d60ea-123">Im folgenden Beispiel gibt die TOKENCOUNT-Funktion „3“ zurück, da die Zeichenfolge drei Token enthält: „01“, „12“, „2011“.</span><span class="sxs-lookup"><span data-stu-id="d60ea-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="d60ea-124">Im darauf folgenden Beispiel gibt die TOKENCOUNT-Funktion „4“ zurück, da vier Token („a“, „little“, „white“, „dog“) vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d60ea-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="d60ea-125">Im folgenden Beispiel gibt die TOKENCOUNT-Funktion 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="d60ea-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="d60ea-126">Die Funktion analysiert die Eingabezeichenfolge für Trennzeichen, und da es in der Zeichenfolge keine gibt, fügt es die ganze Zeichenfolge als erstes Token hinzu.</span><span class="sxs-lookup"><span data-stu-id="d60ea-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="d60ea-127">Im folgenden Beispiel gibt die TOKENCOUNT-Funktion 4 zurück.</span><span class="sxs-lookup"><span data-stu-id="d60ea-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="d60ea-128">Die Trennzeichenfolge in diesem Beispiel enthält 5 Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="d60ea-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="d60ea-129">Die Eingabezeichenfolge enthält 4 Token: „a“, „little“, „white“, „dog“.</span><span class="sxs-lookup"><span data-stu-id="d60ea-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="d60ea-130">Im folgenden Beispiel gibt die TOKENCOUNT-Funktion 4 zurück.</span><span class="sxs-lookup"><span data-stu-id="d60ea-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="d60ea-131">Es ignoriert alle führenden Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="d60ea-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="d60ea-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d60ea-132">See Also</span></span>  
 [<span data-ttu-id="d60ea-133">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="d60ea-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
