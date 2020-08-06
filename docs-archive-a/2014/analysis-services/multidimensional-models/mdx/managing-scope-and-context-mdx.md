---
title: Verwalten von Gültigkeitsbereich und Kontext (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616741"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="dc97c-102">Verwalten von Gültigkeitsbereich und Kontext (MDX)</span><span class="sxs-lookup"><span data-stu-id="dc97c-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="dc97c-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] kann ein MDX-Skript (Multidimensional Expressions) für den gesamten Cube oder bestimmte Teile des Cubes an bestimmten Punkten innerhalb der Ausführung des Skripts angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc97c-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="dc97c-104">Ein MDX-Skript kann, indem Berechnungsdurchläufe verwendet werden, einen mehrstufigen Ansatz für Berechnungen in einem Cube haben.</span><span class="sxs-lookup"><span data-stu-id="dc97c-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc97c-105">Weitere Informationen über die Auswirkungen von Berechnungsdurchläufe auf Berechnungen finden Sie unter [Grundlegendes zu Durchlauf- und Lösungsreihenfolge &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="dc97c-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="dc97c-106">Um den Berechnungsdurchlauf, den Gültigkeitsbereich und den Kontext in einem MDX-Skript zu steuern, verwenden Sie speziell die CACULATE-Anweisung, die `This`-Funktion und die SCOPE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dc97c-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="dc97c-107">Verwenden der CALCULATE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dc97c-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="dc97c-108">Die CALCULATE-Anweisung füllt jede Zelle im Cube mit aggregierten Daten auf.</span><span class="sxs-lookup"><span data-stu-id="dc97c-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="dc97c-109">Im MDX-Standardskript gibt es z. B. eine einzelne CALCULATE-Anweisung am Anfang des Skripts.</span><span class="sxs-lookup"><span data-stu-id="dc97c-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="dc97c-110">Weitere Informationen zur Syntax der CALCULATE-Anweisung finden Sie unter [CALCULATE-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="dc97c-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc97c-111">Enthält das Skript eine SCOPE-Anweisung, die eine CALCULATE-Anweisung enthält, wertet MDX die CALCULATE-Anweisung nicht für den gesamten Cube, sondern im Kontext des Teilcubes aus, der durch die SCOPE-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dc97c-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="dc97c-112">Verwenden der This-Funktion</span><span class="sxs-lookup"><span data-stu-id="dc97c-112">Using the This Function</span></span>  
 <span data-ttu-id="dc97c-113">Mit der `This`-Funktion können Sie in einem MDX-Skript den aktuellen Teilcube abrufen.</span><span class="sxs-lookup"><span data-stu-id="dc97c-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="dc97c-114">Sie können die `This`-Funktion dazu verwenden, die Werte von Zellen im aktuellen Teilcube auf einen MDX-Ausdruck festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dc97c-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="dc97c-115">Die `This`-Funktion wird häufig zusammen mit der SCOPE-Anweisung verwendet, um den Inhalt eines bestimmten Teilcubes im Verlauf eines bestimmten Berechnungsdurchlaufs zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dc97c-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc97c-116">Enthält das Skript eine SCOPE-Anweisung, die eine `This`-Funktion enthält, wertet MDX die `This`-Funktion nicht für den gesamten Cube, sondern im Kontext des Teilcubes aus, der durch die SCOPE-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dc97c-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="dc97c-117">Beispiel zur This-Funktion</span><span class="sxs-lookup"><span data-stu-id="dc97c-117">This Function Example</span></span>  
 <span data-ttu-id="dc97c-118">Im folgenden Beispiel eines MDX-Skriptbefehls wird die `This`-Funktion dazu verwendet, den Wert des Amount-Measures (in der Finance-Measuregruppe des [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)]-Beispielcubes) für die untergeordneten Elemente des Redmond-Elements in der Customer-Dimension um 10 % zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="dc97c-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="dc97c-119">Weitere Informationen zur Syntax der- `This` Funktion finden Sie in [dieser &#40;MDX-&#41;](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="dc97c-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="dc97c-120">Verwenden der SCOPE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dc97c-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="dc97c-121">Die SCOPE-Anweisung definiert in einem MDX-Skript den aktuellen Teilcube, der weitere MDX-Ausdrücke und -Anweisungen enthält sowie deren Gültigkeitsbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="dc97c-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="dc97c-122">MDX wertet diese weiteren MDX-Ausdrücke und -Anweisungen einschließlich der `This`-Funktion und der CALCULATE-Anweisung im Kontext des Teilcubes aus.</span><span class="sxs-lookup"><span data-stu-id="dc97c-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="dc97c-123">Eine SCOPE-Anweisung ist dynamisch, aber nicht iterativ.</span><span class="sxs-lookup"><span data-stu-id="dc97c-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="dc97c-124">Die Anweisungen, die in einer SCOPE-Anweisung enthalten sind, werden einmal ausgeführt, der Teilcube selbst kann aber dynamisch festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dc97c-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="dc97c-125">Angenommen, Sie haben einen Teilcube mit dem Namen SampleCube.</span><span class="sxs-lookup"><span data-stu-id="dc97c-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="dc97c-126">Sie führen die folgende SCOPE-Anweisung für den SampleCube-Cube aus, um einen Teilcube zu definieren, der den Kontext als ALLMEMBERS in der Measures-Dimension definiert:</span><span class="sxs-lookup"><span data-stu-id="dc97c-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="dc97c-127">Die Anweisungen und Ausdrücke in dieser SCOPE-Anweisung werden einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc97c-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="dc97c-128">Jetzt führt ein Anwender im geschäftlichen Bereich die folgende MDX-Abfrage, die ein Measure mit dem Namen ExistingMeasure enthält, für den SampleCube-Cube aus:</span><span class="sxs-lookup"><span data-stu-id="dc97c-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="dc97c-129">Das von der Abfrage zurückgegebene Cellset sieht in etwa so aus, wie die in der folgenden Tabelle gezeigte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="dc97c-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="dc97c-130">[ExistingMeasure]</span><span class="sxs-lookup"><span data-stu-id="dc97c-130">[ExistingMeasure]</span></span>|<span data-ttu-id="dc97c-131">[NewMeasure]</span><span class="sxs-lookup"><span data-stu-id="dc97c-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="dc97c-132">[Customer].[All]</span><span class="sxs-lookup"><span data-stu-id="dc97c-132">[Customer].[All]</span></span>|<span data-ttu-id="dc97c-133">2</span><span class="sxs-lookup"><span data-stu-id="dc97c-133">2</span></span>|<span data-ttu-id="dc97c-134">2</span><span class="sxs-lookup"><span data-stu-id="dc97c-134">2</span></span>|  
  
 <span data-ttu-id="dc97c-135">Anhand des zurückgegebenen Cellsets können Sie sehen, wie der ExistingMeasure-Wert, der im MDX-Skript in der SCOPE-Anweisung enthalten ist, dynamisch aktualisiert wird, nachdem das NewMeasure-Measure definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dc97c-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="dc97c-136">SCOPE-Anweisungen können ineinander geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="dc97c-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="dc97c-137">Da die SCOPE-Anweisung aber nicht iterativ ist, besteht der Hauptzweck für das Schachteln von SCOPE-Anweisungen darin, einen Teilcube für eine spezielle Bearbeitung weiter zu unterteilen.</span><span class="sxs-lookup"><span data-stu-id="dc97c-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="dc97c-138">Beispiel für die SCOPE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dc97c-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="dc97c-139">Im folgenden MDX-Skriptbeispiel wird eine SCOPE-Anweisung dazu verwendet, den Wert des Amount-Measures (in der Finance-Measuregruppe des [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] -Beispielcubes) für die untergeordneten Elemente des Redmond-Elements in der Customer-Dimension um 10 % zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dc97c-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="dc97c-140">Eine weitere SCOPE-Anweisung ändert allerdings den Teilcube so, dass er das Amount-Measure für die untergeordneten Elemente des Kalenderjahres 2002 enthält.</span><span class="sxs-lookup"><span data-stu-id="dc97c-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="dc97c-141">Schließlich wird das Amount-Measure nur für diesen Teilcube aggregiert, sodass die aggregierten Werte für das Amount-Measure für andere Kalenderjahre nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dc97c-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="dc97c-142">Weitere Informationen zur Syntax der SCOPE-Anweisung finden Sie unter [SCOPE-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="dc97c-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc97c-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc97c-143">See Also</span></span>  
 <span data-ttu-id="dc97c-144">[MDX-Sprachreferenz &#40;MDX-&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="dc97c-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="dc97c-145">[Das grundlegende MDX-Skript &#40;MDX-&#41;](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="dc97c-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="dc97c-146">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dc97c-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
