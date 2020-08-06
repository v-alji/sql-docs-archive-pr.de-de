---
title: Hinzufügen eines Ausdrucks (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696414"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="6d3e6-102">Hinzufügen eines Ausdrucks (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6d3e6-103">Ausdrücke werden überall in einem Bericht zum Definieren von Berichtselementeigenschaften, Filtern, Gruppen, Sortierreihenfolgen, Verbindungszeichenfolgen und Parameterwerten verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="6d3e6-104">Ausdrücke beginnen mit einem Gleichheitszeichen (=) und werden in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="6d3e6-105">Sie werden zur Laufzeit vom Berichtsprozessor ausgewertet, der das Auswertungsergebnis mit den Berichtslayoutelementen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="6d3e6-106">Ausdrücke können einfach oder komplex sein.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="6d3e6-107">Einfache Ausdrücke verweisen auf ein einzelnes Element in einer integrierten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="6d3e6-108">Komplexe Ausdrücke können Konstanten, Operatoren, globale Auflistungselemente und Funktionsaufrufe enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="6d3e6-109">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6d3e6-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="6d3e6-110">So fügen Sie einem Textfeld einen Ausdruck hinzu</span><span class="sxs-lookup"><span data-stu-id="6d3e6-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="6d3e6-111">Klicken Sie in der Ansicht **Entwurf** auf das Textfeld auf der Entwurfsoberfläche, dem Sie einen Ausdruck hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="6d3e6-112">Geben Sie den Anzeigetext für den Ausdruck in das Textfeld ein, um einen einfachen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="6d3e6-113">Geben Sie zum Beispiel für das Datasetfeld Sales den Text `[Sales]`ein.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="6d3e6-114">Klicken Sie mit der rechten Maustaste auf das Textfeld, und wählen Sie den Befehl **Ausdruck**aus, um einen komplexen Ausdruck einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="6d3e6-115">Das Dialogfeld **Ausdruck** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="6d3e6-116">Geben Sie den Ausdruck im Ausdrucksbereich hinter '=' ein, bzw. erstellen Sie den Ausdruck interaktiv, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="6d3e6-117">Der Ausdruck wird auf der Entwurfsoberfläche als `<<Expr>>`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3e6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d3e6-118">See Also</span></span>  
 <span data-ttu-id="6d3e6-119">[Formatieren von Text und Platzhaltern &#40;Berichts-Generator und SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d3e6-120">[Textfelder &#40;Berichts-Generator und SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d3e6-121">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d3e6-122">[Beispiele für Filtergleichungen &#40;Berichts-Generator und SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d3e6-123">[Beispiele für Gruppierungsausdrücke (Berichts-Generator und SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d3e6-124">[Dialogfeld „Ausdruck“ (Berichts-Generator)](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="6d3e6-125">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d3e6-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6d3e6-126">Hinzufügen von Code zu einem Bericht (SSRS)</span><span class="sxs-lookup"><span data-stu-id="6d3e6-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
