---
title: InScope-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617715"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="caed3-102">InScope-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="caed3-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="caed3-103">Gibt an, ob sich die aktuelle Instanz eines Elements innerhalb des angegebenen Bereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="caed3-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="caed3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="caed3-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="caed3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="caed3-105">Parameters</span></span>  
 <span data-ttu-id="caed3-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="caed3-106">*scope*</span></span>  
 <span data-ttu-id="caed3-107">(`String`) Der Name eines Datasets, eines Datenbereichs oder einer Gruppe, die einen Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="caed3-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="caed3-108">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="caed3-108">Return Type</span></span>  
 <span data-ttu-id="caed3-109">Gibt einen Wert vom Typ `Boolean` zurück.</span><span class="sxs-lookup"><span data-stu-id="caed3-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caed3-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="caed3-110">Remarks</span></span>  
 <span data-ttu-id="caed3-111">Die- `InScope` Funktion testet den Bereich der aktuellen Instanz eines Berichts Elements auf die Mitgliedschaft in dem durch den *Scope*-Parameter angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="caed3-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="caed3-112">*Scope* darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="caed3-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="caed3-113">Die `InScope`-Funktion wird üblicherweise in Datenbereichen mit dynamischer Bereichsdefinierung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="caed3-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="caed3-114">So kann `InScope` beispielsweise in einem Drillthroughlink in einer Datenbereichszelle verwendet werden, um unterschiedliche Berichtsnamen und unterschiedliche Parametersätze bereitzustellen, je nach Zelle, auf die Sie klicken.</span><span class="sxs-lookup"><span data-stu-id="caed3-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="caed3-115">Dies wird im folgenden Beispiel verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="caed3-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="caed3-116">Mit dem folgenden Ausdruck, der in einem Drillthroughlink als Berichtsname verwendet wird, wird der `ProductDetail` -Bericht geöffnet, wenn sich die angeklickte Zelle in der `Month` -Gruppierung befindet; andernfalls wird der `ProductSummary` -Bericht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="caed3-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="caed3-117">Mit dem folgenden Ausdruck, der in der `Omit`-Eigenschaft eines Drillthroughberichts-Parameters verwendet wird, wird der Parameter nur dann an den Zielbericht übergeben, wenn sich die angeklickte Zelle in der `Product`-Gruppierung befindet.</span><span class="sxs-lookup"><span data-stu-id="caed3-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="caed3-118">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="caed3-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="caed3-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="caed3-119">Example</span></span>  
 <span data-ttu-id="caed3-120">Im folgenden Codebeispiel wird angezeigt, ob sich die aktuelle Instanz des Elements innerhalb des `Product` -Datasets, -Datenbereichs oder -Gruppenbereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="caed3-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="caed3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="caed3-121">See Also</span></span>  
 <span data-ttu-id="caed3-122">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="caed3-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="caed3-123">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="caed3-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="caed3-124">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="caed3-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="caed3-125">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="caed3-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
