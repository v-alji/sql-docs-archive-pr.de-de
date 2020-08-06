---
title: TOKEN (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701348"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="22db3-102">TOKEN (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="22db3-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="22db3-103">Gibt ein Token (Teilzeichenfolge) aus einer Zeichenfolge zurück – basierend auf den angegebenen Trennzeichen, die Token in der Zeichenfolge trennen, und der Nummer des Tokens, die festlegt, welcher Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="22db3-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22db3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22db3-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="22db3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="22db3-105">Arguments</span></span>  
 <span data-ttu-id="22db3-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="22db3-106">*character_expression*</span></span>  
 <span data-ttu-id="22db3-107">Eine Zeichenfolge, die durch Trennzeichen getrennte Token enthält.</span><span class="sxs-lookup"><span data-stu-id="22db3-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="22db3-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="22db3-108">*delimiter_string*</span></span>  
 <span data-ttu-id="22db3-109">Eine Zeichenfolge, die Begrenzungszeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="22db3-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="22db3-110">„; ,“ enthält beispielsweise drei Begrenzungszeichen: ein Semikolon, ein Leerzeichen und ein Komma.</span><span class="sxs-lookup"><span data-stu-id="22db3-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="22db3-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="22db3-111">*occurrence*</span></span>  
 <span data-ttu-id="22db3-112">Eine ganze Zahl mit oder ohne Vorzeichen, die angibt, welcher Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="22db3-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="22db3-113">Wenn Sie z. B. 3 als Wert für diesen Parameter angeben, wird das dritte Token in der Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="22db3-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="22db3-114">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="22db3-114">Result Types</span></span>  
 <span data-ttu-id="22db3-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="22db3-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22db3-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="22db3-116">Remarks</span></span>  
 <span data-ttu-id="22db3-117">Diese Funktion teilt die <character_expression>-Zeichenfolge in einen Satz von Token auf, die von den im <delimiter_string> festgelegten Trennzeichen getrennt wurden, und gibt dann das N-te Token zurück, wobei N für die vom \<occurrence>-Parameter festgelegte Anzahl der Vorkommen des Tokens steht.</span><span class="sxs-lookup"><span data-stu-id="22db3-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="22db3-118">Beispiele für die Verwendung dieser Funktion finden Sie im Abschnitt "Beispiele".</span><span class="sxs-lookup"><span data-stu-id="22db3-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="22db3-119">Die folgenden Hinweise gelten für die TOKEN-Funktion:</span><span class="sxs-lookup"><span data-stu-id="22db3-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="22db3-120">Die Trennzeichenfolge kann ein oder mehrere Trennzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="22db3-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="22db3-121">Wenn der Wert des \<occurrence>-Parameters höher als die Gesamtanzahl der Token in der Zeichenfolge ist, gibt die Funktion NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="22db3-122">Führende Trennzeichen werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="22db3-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="22db3-123">TOKEN kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22db3-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="22db3-124">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor TOKEN ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22db3-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="22db3-125">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="22db3-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="22db3-126">TOKEN gibt ein NULL-Ergebnis zurück, wenn der character_expression NULL ist.</span><span class="sxs-lookup"><span data-stu-id="22db3-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="22db3-127">Sie können Variablen und Spalten als Werte für alle Argumente des Ausdrucks verwenden.</span><span class="sxs-lookup"><span data-stu-id="22db3-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="22db3-128">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="22db3-128">Expression Examples</span></span>  
 <span data-ttu-id="22db3-129">Im folgenden Beispiel gibt die TOKEN-Funktion den Wert "ein" zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="22db3-130">Die Zeichenfolge „ein kleiner weißer Hund“ hat 4 durch das Trennzeichen „ “ (Leerzeichen) getrennte Token: „ein“, „kleiner“, „weißer“, „Hund“.</span><span class="sxs-lookup"><span data-stu-id="22db3-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="22db3-131">Das zweite Argument, eine Trennzeichenfolge, gibt nur ein Trennzeichen (das Leerzeichen) an, das beim Teilen der Eingabezeichenfolge in Token verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="22db3-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="22db3-132">Das letzte Argument 1 legt fest, dass das erste Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="22db3-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="22db3-133">In dieser Beispielzeichenfolge ist „ein“ das erste Token.</span><span class="sxs-lookup"><span data-stu-id="22db3-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="22db3-134">Im folgenden Beispiel gibt die TOKEN-Funktion den Wert "Hund" zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="22db3-135">Die Trennzeichenfolge in diesem Beispiel enthält 5 Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="22db3-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="22db3-136">Die Eingabezeichenfolge enthält 4 Token: „a“, „little“, „white“, „dog“.</span><span class="sxs-lookup"><span data-stu-id="22db3-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="22db3-137">Im folgenden Beispiel gibt die TOKEN-Funktion den Wert "" (eine leere Zeichenfolge) zurück, weil es keine 99 Token in der Zeichenfolge gibt.</span><span class="sxs-lookup"><span data-stu-id="22db3-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="22db3-138">Im folgenden Beispiel gibt die TOKEN-Funktion die vollständige Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="22db3-139">Die Funktion analysiert die Eingabezeichenfolge für Trennzeichen, und da es in der Zeichenfolge keine gibt, fügt es die ganze Zeichenfolge als erstes Token hinzu.</span><span class="sxs-lookup"><span data-stu-id="22db3-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="22db3-140">Im folgenden Beispiel gibt die TOKEN-Funktion den Wert "ein" zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="22db3-141">Es ignoriert alle führenden Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="22db3-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="22db3-142">Im folgenden Beispiel gibt die TOKEN-Funktion das Jahr einer Datumszeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="22db3-143">Im folgenden Beispiel gibt die TOKEN-Funktion den Dateinamen des angegebenen Pfads zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="22db3-144">Wenn der Wert von User::Path z. B. „C:\Programme\Daten\MeineDatei.txt“ lautet, gibt die TOKEN-Funktion „MeineDatei.txt“ zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="22db3-145">Die TOKENCOUNT-Funktion gibt 4 zurück, und die TOKEN-Funktion gibt das 4. Token „MeineDatei.txt“ zurück.</span><span class="sxs-lookup"><span data-stu-id="22db3-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="22db3-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22db3-146">See Also</span></span>  
 [<span data-ttu-id="22db3-147">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="22db3-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
