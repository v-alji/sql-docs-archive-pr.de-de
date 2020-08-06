---
title: CountRows-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617722"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="a1ae8-102">CountRows-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1ae8-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a1ae8-103">Gibt die Anzahl der Zeilen im angegebenen Bereich zurück, einschließlich der Zeilen mit NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="a1ae8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1ae8-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1ae8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1ae8-105">Parameters</span></span>  
 <span data-ttu-id="a1ae8-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="a1ae8-106">*scope*</span></span>  
 <span data-ttu-id="a1ae8-107">(`String`) Der Name eines Datasets, eines Datenbereichs oder einer Gruppe mit den zu zählenden Berichtselementen.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="a1ae8-108">*recursive*</span><span class="sxs-lookup"><span data-stu-id="a1ae8-108">*recursive*</span></span>  
 <span data-ttu-id="a1ae8-109">(**Enumerationstyp**) Optional.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="a1ae8-110">`Simple` (Standardwert) oder `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="a1ae8-111">Gibt an, ob die Aggregation rekursiv auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="a1ae8-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="a1ae8-112">Return Type</span></span>  
 <span data-ttu-id="a1ae8-113">Gibt einen `Integer` zurück.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1ae8-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a1ae8-114">Remarks</span></span>  
 <span data-ttu-id="a1ae8-115">`CountRows` zählt alle Zeilen im angegebenen Bereich, einschließlich der Zeilen mit NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="a1ae8-116">Der Wert *scope* darf kein Ausdruck sein und muss auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="a1ae8-117">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a1ae8-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="a1ae8-118">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a1ae8-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ae8-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1ae8-119">Example</span></span>  
 <span data-ttu-id="a1ae8-120">Das folgende Codebeispiel zeigt einen Ausdruck, der die Anzahl der Zeilen in einer Zeilengruppe mit dem Namen `GroupbyCategory` (basierend auf dem Ausdruck `[Category]`) berechnet.</span><span class="sxs-lookup"><span data-stu-id="a1ae8-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1ae8-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1ae8-121">See Also</span></span>  
 <span data-ttu-id="a1ae8-122">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1ae8-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a1ae8-123">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1ae8-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a1ae8-124">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1ae8-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a1ae8-125">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a1ae8-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
