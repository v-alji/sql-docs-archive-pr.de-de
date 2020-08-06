---
title: Arbeiten mit der RollupChildren-Funktion (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721921"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="9a042-102">Arbeiten mit der RollupChildren-Funktion (MDX)</span><span class="sxs-lookup"><span data-stu-id="9a042-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="9a042-103">Die MDX-Funktion (Multidimensional Expressions) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Skript für Search und replace] führt einen Rollup der untergeordneten Elemente eines Members aus, wendet einen anderen unären Operator auf jedes untergeordnete Element an und gibt den Wert dieses Rollups als Zahl zurück.</span><span class="sxs-lookup"><span data-stu-id="9a042-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="9a042-104">Der unäre Operator kann durch eine Elementeigenschaft des untergeordneten Elements bereitgestellt werden, oder der Operator kann ein Zeichenfolgenausdruck sein, der direkt an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9a042-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="9a042-105">Beispiele zur RollupChildren-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a042-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="9a042-106">Die Verwendung der `RollupChildren`-Funktion in MDX-Anweisungen (Multidimensional Expressions) ist einfach zu erklären, die Funktion kann jedoch weit reichende Folgen für MDX-Abfragen haben.</span><span class="sxs-lookup"><span data-stu-id="9a042-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="9a042-107">Der Einfluss der `RollupChildren`-Funktion wird in MDX-Abfragen ersichtlich, die zum Durchführen einer selektiven Analyse der vorhandenen Cubedaten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="9a042-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="9a042-108">Die folgende Tabelle enthält beispielsweise eine Liste untergeordneter Elemente des übergeordneten Elements Net Sales, wobei die unären Operatoren (die durch die `UNARY_OPERATOR`-Elementeigenschaft dargestellt sind) in Klammern angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="9a042-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="9a042-109">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-109">Parent member</span></span>|<span data-ttu-id="9a042-110">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="9a042-111">Nettoumsatz</span><span class="sxs-lookup"><span data-stu-id="9a042-111">Net Sales</span></span>|<span data-ttu-id="9a042-112">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="9a042-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="9a042-113">Domestic Returns (-)</span><span class="sxs-lookup"><span data-stu-id="9a042-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="9a042-114">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="9a042-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="9a042-115">Foreign Returns (-)</span><span class="sxs-lookup"><span data-stu-id="9a042-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="9a042-116">Das übergeordnete Element Net Sales stellt derzeit die Gesamtsumme der in- und ausländischen Bruttoumsatzwerte bereit, wobei in- und ausländische Rücknahmen im Rahmen des Rollups subtrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a042-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="9a042-117">Sie möchten jedoch eine schnelle und einfache Vorhersage des in- und ausländischen Bruttoumsatzes plus 10 % bereitstellen, wobei die in- und ausländischen Rücknahmen ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="9a042-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="9a042-118">Zum Berechnen dieses Wertes können Sie die `RollupChildren`-Funktion auf eine der beiden folgenden Arten verwenden: mit einer benutzerdefinierten Elementeigenschaft oder mit der `IIf`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="9a042-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="9a042-119">Verwenden einer benutzerdefinierten Elementeigenschaft</span><span class="sxs-lookup"><span data-stu-id="9a042-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="9a042-120">Wenn die Rollupberechnung häufig ausgeführt werden soll, besteht die Möglichkeit, eine Elementeigenschaft zu erstellen, in der der Operator gespeichert ist, der für jedes untergeordnete Element für eine bestimmte Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a042-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="9a042-121">Die folgende Tabelle zeigt gültige unäre Operatoren an und beschreibt das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="9a042-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="9a042-122">Operator</span><span class="sxs-lookup"><span data-stu-id="9a042-122">Operator</span></span>|<span data-ttu-id="9a042-123">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="9a042-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="9a042-124">Gesamt = Gesamt + aktuelles untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="9a042-125">Gesamt = Gesamt - aktuelles untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="9a042-126">Gesamt = Gesamt \* aktuelles untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="9a042-127">Gesamt = Gesamt / aktuelles untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="9a042-128">Untergeordnetes Element wird im Rollup nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a042-128">Child is not used in the rollup.</span></span> <span data-ttu-id="9a042-129">Der Wert des untergeordneten Elements wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9a042-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="9a042-130">Beispielsweise könnte eine Elementeigenschaft mit dem Namen `SALES_OPERATOR` erstellt werden, der folgende unäre Operatoren zugewiesen werden (siehe nächste Tabelle).</span><span class="sxs-lookup"><span data-stu-id="9a042-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9a042-131">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-131">Parent member</span></span>|<span data-ttu-id="9a042-132">Untergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9a042-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="9a042-133">Nettoumsatz</span><span class="sxs-lookup"><span data-stu-id="9a042-133">Net Sales</span></span>|<span data-ttu-id="9a042-134">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="9a042-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="9a042-135">Domestic Returns (~)</span><span class="sxs-lookup"><span data-stu-id="9a042-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="9a042-136">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="9a042-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="9a042-137">Foreign Returns (~)</span><span class="sxs-lookup"><span data-stu-id="9a042-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="9a042-138">Mit dieser neuen Elementeigenschaft führt die folgende MDX-Anweisung die Schätzung des Bruttoumsatzes schnell und effizient aus (wobei in- und ausländische Rücknahmen ignoriert werden):</span><span class="sxs-lookup"><span data-stu-id="9a042-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="9a042-139">Beim Aufrufen der Funktion wird der Wert jedes untergeordneten Elements mithilfe des Operators, der in der Elementeigenschaft gespeichert ist, auf das Gesamtergebnis angewendet.</span><span class="sxs-lookup"><span data-stu-id="9a042-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="9a042-140">Die Elemente für in- und ausländische Rücknahmen werden ignoriert, und der von der `RollupChildren`-Funktion zurückgegebene Rollupgesamtwert wird mit 1,1 multipliziert.</span><span class="sxs-lookup"><span data-stu-id="9a042-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="9a042-141">Verwenden der IIf-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a042-141">Using the IIf Function</span></span>  
 <span data-ttu-id="9a042-142">Wenn der Beispiel Vorgang nicht alltäglich ist oder der Vorgang nur auf eine MDX-Abfrage angewendet wird, kann die [IIf](/sql/mdx/iif-mdx) -Funktion mit der-Funktion verwendet werden, `RollupChildren` um dasselbe Ergebnis bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9a042-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="9a042-143">Die folgende MDX-Abfrage stellt dasselbe Ergebnis wie das vorherige MDX-Abfragebeispiel bereit, jedoch ohne die Verwendung einer benutzerdefinierten Elementeigenschaft:</span><span class="sxs-lookup"><span data-stu-id="9a042-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="9a042-144">Die MDX-Anweisung wertet den unären Operator des untergeordneten Elements aus.</span><span class="sxs-lookup"><span data-stu-id="9a042-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="9a042-145">Wird der unäre Operator zur Subtraktion verwendet (wie dies bei den Elementen der in- und ausländischen Rücknahmen der Fall ist), wird der unäre Tildeoperator (~) durch die `IIf`-Funktion ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9a042-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="9a042-146">Andernfalls verwendet die `IIf`-Funktion den unären Operator des untergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="9a042-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="9a042-147">Schließlich wird der zurückgegebene Rollupgesamtwert mit 1,1 multipliziert, um die Vorhersage der in- und ausländischen Bruttoumsätze bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9a042-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a042-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a042-148">See Also</span></span>  
 [<span data-ttu-id="9a042-149">Bearbeiten von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="9a042-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
