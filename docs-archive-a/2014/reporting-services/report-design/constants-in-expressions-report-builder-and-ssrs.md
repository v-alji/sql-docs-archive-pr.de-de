---
title: Konstanten in Ausdrücken (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616445"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="c2d77-102">Konstanten in Ausdrücken (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c2d77-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c2d77-103">Eine Konstante besteht aus Literaltext oder vordefiniertem Text.</span><span class="sxs-lookup"><span data-stu-id="c2d77-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="c2d77-104">Der Berichtsprozessor hat Zugriff auf die vordefinierten Konstanten. Wenn Sie die Konstanten in einen Ausdruck einschließen, werden die Werte, die sie darstellen, daher im Ausdruck ersetzt, bevor dieser ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c2d77-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="c2d77-105">Literaltext</span><span class="sxs-lookup"><span data-stu-id="c2d77-105">Literal Text</span></span>  
 <span data-ttu-id="c2d77-106">In einem Ausdruck ist Literaltext Text, der in doppelten Anführungszeichen steht.</span><span class="sxs-lookup"><span data-stu-id="c2d77-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="c2d77-107">Sie können Text auch direkt ohne doppelte Anführungszeichen in ein Textfeld eingeben, wenn er nicht Teil eines Ausdrucks ist.</span><span class="sxs-lookup"><span data-stu-id="c2d77-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="c2d77-108">Wenn der Textfeldwert nicht mit einem Gleichheitszeichen (=) beginnt, wird der Text als Literaltext behandelt.</span><span class="sxs-lookup"><span data-stu-id="c2d77-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="c2d77-109">In der folgenden Tabelle werden mehrere Beispiele für Literaltext in einem Ausdruck angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2d77-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="c2d77-110">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="c2d77-110">Constant</span></span>|<span data-ttu-id="c2d77-111">Anzeigetext</span><span class="sxs-lookup"><span data-stu-id="c2d77-111">Display text</span></span>|<span data-ttu-id="c2d77-112">Ausdruckstext</span><span class="sxs-lookup"><span data-stu-id="c2d77-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="c2d77-113">Bericht ausgeführt um:</span><span class="sxs-lookup"><span data-stu-id="c2d77-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="c2d77-114">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="c2d77-114">Adventure Works Cycles</span></span>|<span data-ttu-id="c2d77-115">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="c2d77-115">Adventure Works Cycles</span></span>|<span data-ttu-id="c2d77-116">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="c2d77-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="c2d77-117">[Anzeigetext in Klammern]</span><span class="sxs-lookup"><span data-stu-id="c2d77-117">[Bracketed display text]</span></span>|<span data-ttu-id="c2d77-118">\\[Anzeigetext in Klammern\\]</span><span class="sxs-lookup"><span data-stu-id="c2d77-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="c2d77-119">[Anzeigetext in Klammern]</span><span class="sxs-lookup"><span data-stu-id="c2d77-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="c2d77-120">RDL-Konstanten</span><span class="sxs-lookup"><span data-stu-id="c2d77-120">RDL Constants</span></span>  
 <span data-ttu-id="c2d77-121">Sie können in der Berichtsdefinitionssprache (RDL) definierte Konstanten in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2d77-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="c2d77-122">Im Dialogfeld **Ausdruck** werden Konstanten angezeigt, wenn Sie einen Ausdruck für eine Berichtseigenschaft erstellen, der nur bestimmte gültige Werte akzeptiert. Diese Werte werden auch als Enumerationstypen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c2d77-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="c2d77-123">Die folgende Tabelle enthält zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c2d77-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="c2d77-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c2d77-124">Property</span></span>|<span data-ttu-id="c2d77-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c2d77-125">Description</span></span>|<span data-ttu-id="c2d77-126">Werte</span><span class="sxs-lookup"><span data-stu-id="c2d77-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="c2d77-127">Textausrichtung</span><span class="sxs-lookup"><span data-stu-id="c2d77-127">TextAlign</span></span>|<span data-ttu-id="c2d77-128">Gültige Werte zum Ausrichten von Text in einem Textfeld.</span><span class="sxs-lookup"><span data-stu-id="c2d77-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="c2d77-129">Allgemein, Links, Zentriert, Rechts</span><span class="sxs-lookup"><span data-stu-id="c2d77-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="c2d77-130">Rahmenart</span><span class="sxs-lookup"><span data-stu-id="c2d77-130">BorderStyle</span></span>|<span data-ttu-id="c2d77-131">Gültige Werte für eine einem Bericht hinzugefügte Zeile.</span><span class="sxs-lookup"><span data-stu-id="c2d77-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="c2d77-132">Standard, Keine, Gepunktet, Gestrichelt, Einfarbig, Doppelt, Strich-Punkt, Strich-Punkt-Punkt</span><span class="sxs-lookup"><span data-stu-id="c2d77-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="c2d77-133">Visual Basic-Konstanten</span><span class="sxs-lookup"><span data-stu-id="c2d77-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="c2d77-134">Sie können in einem Ausdruck in der [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Laufzeitbibliothek definierte Konstanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2d77-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="c2d77-135">Beispielsweise kann die Konstante `DateInterval.Day` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2d77-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="c2d77-136">Für das Datum 10. Januar 2008 gibt der folgende Ausdruck beispielsweise die Zahl 10 zurück:</span><span class="sxs-lookup"><span data-stu-id="c2d77-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="c2d77-137">CLR-Konstanten</span><span class="sxs-lookup"><span data-stu-id="c2d77-137">CLR Constants</span></span>  
 <span data-ttu-id="c2d77-138">Sie können in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Common Language Runtime-Klassen (CLR) definierte Konstanten in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2d77-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="c2d77-139">In der folgenden Tabelle wird ein Beispiel für eine systemdefinierte Farbe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2d77-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="c2d77-140">Konstante</span><span class="sxs-lookup"><span data-stu-id="c2d77-140">Constant</span></span>|<span data-ttu-id="c2d77-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2d77-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c2d77-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="c2d77-142">MistyRose</span></span>|<span data-ttu-id="c2d77-143">Beim Erstellen eines Ausdrucks für eine Berichtseigenschaft, die auf der Hintergrundfarbe basiert, können Sie eine Farbe mit Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="c2d77-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="c2d77-144">Gültige Namen werden im Dialogfeld **Ausdruck** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c2d77-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2d77-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2d77-145">See Also</span></span>  
 <span data-ttu-id="c2d77-146">[Dialog Feld ' Ausdruck '](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="c2d77-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="c2d77-147">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2d77-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2d77-148">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2d77-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2d77-149">[Datentypen in Ausdrücken &#40;Berichts-Generator und SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2d77-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c2d77-150">Dialogfeld „Ausdruck“ (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="c2d77-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
