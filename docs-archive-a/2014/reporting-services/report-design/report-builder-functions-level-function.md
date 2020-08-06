---
title: Dimensionsfunktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617713"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="b4a6c-102">Level-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b4a6c-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b4a6c-103">Gibt die aktuelle Ebene in einer rekursiven Hierarchie zurück.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="b4a6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4a6c-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4a6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4a6c-105">Parameters</span></span>  
 <span data-ttu-id="b4a6c-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="b4a6c-106">*scope*</span></span>  
 <span data-ttu-id="b4a6c-107">(`String`) (optional).</span><span class="sxs-lookup"><span data-stu-id="b4a6c-107">(`String`) (Optional).</span></span> <span data-ttu-id="b4a6c-108">Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="b4a6c-109">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="b4a6c-110">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="b4a6c-110">Return Type</span></span>  
 <span data-ttu-id="b4a6c-111">Gibt einen `Integer` zurück.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-111">Returns an `Integer`.</span></span> <span data-ttu-id="b4a6c-112">Wenn *Scope* ein DataSet oder einen Datenbereich angibt oder eine nicht rekursive Gruppierung (d. h. eine Gruppierung ohne- `Parent` Element) angibt, wird `Level` 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="b4a6c-113">Wenn *scope* weggelassen wird, wird die Ebene des aktuellen Bereichs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4a6c-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4a6c-114">Remarks</span></span>  
 <span data-ttu-id="b4a6c-115">Der von der `Level`-Funktion zurückgegebene Wert ist nullbasiert, d. h., die erste Ebene in einer Hierarchie hat den Wert 0.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="b4a6c-116">Die `Level`-Funktion kann verwendet werden, um den Einzug in einer rekursiven Hierarchie, z. B. einer Mitarbeiterliste, bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4a6c-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="b4a6c-117">Weitere Informationen zu rekursiven Hierarchien finden Sie unter [Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b4a6c-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4a6c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4a6c-118">Example</span></span>  
 <span data-ttu-id="b4a6c-119">Mit dem folgenden Codebeispiel wird die Zeilenebene in der Employees-Gruppe bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="b4a6c-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4a6c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4a6c-120">See Also</span></span>  
 <span data-ttu-id="b4a6c-121">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b4a6c-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b4a6c-122">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b4a6c-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b4a6c-123">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b4a6c-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b4a6c-124">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4a6c-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
