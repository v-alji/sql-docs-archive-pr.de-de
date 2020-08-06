---
title: RowNumber-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617697"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="c33fc-102">RowNumber-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c33fc-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c33fc-103">Gibt eine laufende Zählung der Zeilenanzahl für den angegebenen Bereich zurück.</span><span class="sxs-lookup"><span data-stu-id="c33fc-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="c33fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c33fc-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c33fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c33fc-105">Parameters</span></span>  
 <span data-ttu-id="c33fc-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="c33fc-106">*scope*</span></span>  
 <span data-ttu-id="c33fc-107">(`String`) Der Name eines Datasets, eines Datenbereichs oder einer Gruppe oder NULL (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), der den Kontext angibt, in dem die Zeilenanzahl ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c33fc-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="c33fc-108">Durch `Nothing` wird der äußerste Kontext angegeben, normalerweise das Berichtsdataset.</span><span class="sxs-lookup"><span data-stu-id="c33fc-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c33fc-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c33fc-109">Remarks</span></span>  
 <span data-ttu-id="c33fc-110">`RowNumber`Gibt einen Wert zurück, der die Anzahl der Zeilen innerhalb des angegebenen Bereichs zurückgibt, ebenso wie [RunningValue](report-builder-functions-runningvalue-function.md) den laufenden Wert einer Aggregatfunktion zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c33fc-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="c33fc-111">Wenn Sie einen Bereich angeben, geben Sie an, wann die Zeilenanzahl auf 1 zurückzusetzen ist.</span><span class="sxs-lookup"><span data-stu-id="c33fc-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="c33fc-112">*scope* darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="c33fc-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="c33fc-113">*scope* muss ein Gültigkeitsbereich sein.</span><span class="sxs-lookup"><span data-stu-id="c33fc-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="c33fc-114">Typische Bereiche, von der äußersten bis zur innersten Einkapselung, sind Berichtsdataset, Datenbereich, Zeilengruppen oder Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="c33fc-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="c33fc-115">Um Werte über Spalten hinweg zu inkrementieren, geben Sie einen Bereich an, der dem Namen einer Spaltengruppe enspricht.</span><span class="sxs-lookup"><span data-stu-id="c33fc-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="c33fc-116">Um Zahlen über Zeilen hinweg zu inkrementieren, geben Sie einen Bereich an, der dem Namen einer Zeilengruppe enspricht.</span><span class="sxs-lookup"><span data-stu-id="c33fc-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c33fc-117">Das Einschließen von Aggregaten, die sowohl eine Zeilengruppe als auch eine Spaltengruppe in einem einzelnen Ausdruck angeben, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c33fc-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="c33fc-118">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="c33fc-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="c33fc-119">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="c33fc-119">Code Example</span></span>  
 <span data-ttu-id="c33fc-120">Folgender Ausdruck ist ein Ausdruck, den Sie für die Eigenschaft `BackgroundColor` einer Detailzeile in einem Tablix-Datenbereich verwenden können, um die Farbe der Detailzeilen für jede Gruppe abzuwechseln, wobei stets mit Weiß begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="c33fc-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="c33fc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c33fc-121">See Also</span></span>  
 <span data-ttu-id="c33fc-122">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c33fc-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c33fc-123">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c33fc-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c33fc-124">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c33fc-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c33fc-125">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c33fc-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
