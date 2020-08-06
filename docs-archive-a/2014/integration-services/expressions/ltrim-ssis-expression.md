---
title: LTRIM (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 678d9d93eb1dcd7649d2085b651a08418bbcd6a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617198"
---
# <a name="ltrim-ssis-expression"></a><span data-ttu-id="5b342-102">LTRIM (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="5b342-102">LTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="5b342-103">Gibt einen Zeichenausdruck zurück, nachdem führende Leerzeichen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="5b342-103">Returns a character expression after removing leading spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b342-104">Mit LTRIM werden keine Pseudoleerzeichen, wie z. B. Tabulatoren oder Zeilenvorschubzeichen, entfernt.</span><span class="sxs-lookup"><span data-stu-id="5b342-104">LTRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="5b342-105">Unicode stellt Codeelemente für viele verschiedene Arten von Leerzeichen bereit, diese Funktion erkennt jedoch nur das Unicode-Codeelement 0x0020.</span><span class="sxs-lookup"><span data-stu-id="5b342-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="5b342-106">DBCS-Zeichenfolgen, die in Unicode konvertiert werden, enthalten u. U. andere Leerzeichen als 0x0020. Diese Leerzeichen können von der Funktion nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5b342-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="5b342-107">Zum Entfernen aller Arten von Leerzeichen können Sie die LTrim-Methode von Microsoft Visual Basic .NET in einem Skript verwenden, das aus der Skriptkomponente ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b342-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET LTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b342-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b342-108">Syntax</span></span>  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5b342-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="5b342-109">Arguments</span></span>  
 <span data-ttu-id="5b342-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="5b342-110">*character_expression*</span></span>  
 <span data-ttu-id="5b342-111">Ein Zeichenausdruck, aus dem Leerzeichen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b342-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5b342-112">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="5b342-112">Result Types</span></span>  
 <span data-ttu-id="5b342-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5b342-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b342-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5b342-114">Remarks</span></span>  
 <span data-ttu-id="5b342-115">LTRIM kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b342-115">LTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="5b342-116">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor LTRIM ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b342-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LTRIM performs its operation.</span></span> <span data-ttu-id="5b342-117">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5b342-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="5b342-118">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5b342-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="5b342-119">LTRIM gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="5b342-119">LTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5b342-120">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5b342-120">Expression Examples</span></span>  
 <span data-ttu-id="5b342-121">In diesem Beispiel werden führende Leerzeichen aus einem Zeichenfolgenliteral entfernt.</span><span class="sxs-lookup"><span data-stu-id="5b342-121">This example removes leading spaces from a string literal.</span></span> <span data-ttu-id="5b342-122">Als Ergebnis wird "Hello" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b342-122">The return result is "Hello".</span></span>  
  
```  
LTRIM("    Hello")  
```  
  
 <span data-ttu-id="5b342-123">In diesem Beispiel werden führende Leerzeichen aus der **FirstName** -Spalte entfernt.</span><span class="sxs-lookup"><span data-stu-id="5b342-123">This example removes leading spaces from the **FirstName** column.</span></span>  
  
```  
LTRIM(FirstName)  
```  
  
 <span data-ttu-id="5b342-124">In diesem Beispiel werden führende Leerzeichen aus der **FirstName** -Variablen entfernt.</span><span class="sxs-lookup"><span data-stu-id="5b342-124">This example removes leading spaces from the **FirstName** variable.</span></span>  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b342-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b342-125">See Also</span></span>  
 <span data-ttu-id="5b342-126">[RTRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5b342-126">[RTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="5b342-127">[TRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5b342-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="5b342-128">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="5b342-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
