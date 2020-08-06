---
title: TRIM (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701330"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="47e3d-102">TRIM (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="47e3d-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="47e3d-103">Gibt einen Zeichenausdruck zurück, nachdem führende und nachfolgende Leerzeichen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="47e3d-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47e3d-104">Mit TRIM werden keine Leerzeichen entfernt, wie z. B. Tabulatoren oder Zeilenvorschubzeichen.</span><span class="sxs-lookup"><span data-stu-id="47e3d-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="47e3d-105">Unicode stellt Codeelemente für viele verschiedene Arten von Leerzeichen bereit, diese Funktion erkennt jedoch nur das Unicode-Codeelement 0x0020.</span><span class="sxs-lookup"><span data-stu-id="47e3d-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="47e3d-106">DBCS-Zeichenfolgen, die in Unicode konvertiert werden, enthalten u. U. andere Leerzeichen als 0x0020. Diese Leerzeichen können von der Funktion nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="47e3d-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="47e3d-107">Zum Entfernen aller Arten von Leerzeichen können Sie die Trim-Methode von Microsoft Visual Basic .NET in einem Skript verwenden, das aus der Skriptkomponente ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47e3d-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47e3d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="47e3d-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="47e3d-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="47e3d-109">Arguments</span></span>  
 <span data-ttu-id="47e3d-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="47e3d-110">*character_expression*</span></span>  
 <span data-ttu-id="47e3d-111">Ein Zeichenausdruck, aus dem Leerzeichen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="47e3d-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="47e3d-112">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="47e3d-112">Result Types</span></span>  
 <span data-ttu-id="47e3d-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="47e3d-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47e3d-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="47e3d-114">Remarks</span></span>  
 <span data-ttu-id="47e3d-115">TRIM gibt ein NULL-Ergebnis zurück, wenn das Element NULL ist.</span><span class="sxs-lookup"><span data-stu-id="47e3d-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="47e3d-116">TRIM kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47e3d-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="47e3d-117">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor TRIM ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47e3d-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="47e3d-118">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="47e3d-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="47e3d-119">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="47e3d-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="47e3d-120">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="47e3d-120">Expression Examples</span></span>  
 <span data-ttu-id="47e3d-121">In diesem Beispiel werden führende und nachfolgende Leerzeichen aus einem Zeichenfolgenliteral entfernt.</span><span class="sxs-lookup"><span data-stu-id="47e3d-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="47e3d-122">Als Ergebnis wird "New York" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47e3d-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="47e3d-123">In diesem Beispiel werden führende und nachfolgende Leerzeichen aus dem Ergebnis der Verkettung der Spalten **FirstName** und **LastName** entfernt.</span><span class="sxs-lookup"><span data-stu-id="47e3d-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="47e3d-124">Die leere Zeichenfolge zwischen **FirstName** und **LastName** wird nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="47e3d-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="47e3d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47e3d-125">See Also</span></span>  
 <span data-ttu-id="47e3d-126">[LTRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="47e3d-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="47e3d-127">[RTRIM &#40;SSIS-Ausdruck&#41;](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="47e3d-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="47e3d-128">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="47e3d-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
