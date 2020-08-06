---
title: Importieren von HTML in einen Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697534"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="cfba8-102">Importieren von HTML in einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfba8-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cfba8-103">Sie können ein Textfeld verwenden, um aus einem Feld im Dataset abgerufenen HTML-Text in den Bericht einzufügen.</span><span class="sxs-lookup"><span data-stu-id="cfba8-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="cfba8-104">Der Text kann aus einem einfachen oder komplexen Ausdruck stammen, der zum ordnungsgemäß formatierten HTML evaluiert wird.</span><span class="sxs-lookup"><span data-stu-id="cfba8-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="cfba8-105">Formatierter Text kann in allen unterstützten Ausgabeformaten einschließlich PDF gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="cfba8-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="cfba8-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="cfba8-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="cfba8-107">Diese Abbildung zeigt Text mit HTML-Formatierung in der Berichtsentwurfsansicht und den gleichen Text wie er beim Ausführen des Berichts gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="cfba8-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfba8-108">Beim Importieren von Text mit HTML-Markup müssen die Daten stets zunächst vom Textfeld analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="cfba8-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="cfba8-109">Da nicht alle HTML-Tags unterstützt werden, weicht die HTML-Darstellung im gerenderten Bericht möglicherweise vom ursprünglichen HTML-Text ab.</span><span class="sxs-lookup"><span data-stu-id="cfba8-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="cfba8-110">Eine schnelle Einführung finden Sie unter [Tutorial: Formatieren von Text &#40;Berichts-Generator&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cfba8-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="cfba8-111">Unterstützte HTML-Tags</span><span class="sxs-lookup"><span data-stu-id="cfba8-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="cfba8-112">Nachfolgend finden Sie eine vollständige Liste der Tags, die bei einer Definition als Platzhaltertext als HTML gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="cfba8-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="cfba8-113">Header-, Stil-und Block Elemente: \<H{n}> , \<DIV> , \<SPAN> , \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="cfba8-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="cfba8-114">Alle anderen HTML-Markuptags werden bei der Berichtsverarbeitung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cfba8-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="cfba8-115">Wenn der Ausdruck im Platzhaltertext kein wohlgeformtes HTML aufweist, wird der Platzhalter als Text ohne Formatierung gerendert.</span><span class="sxs-lookup"><span data-stu-id="cfba8-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="cfba8-116">Bei allen HTML-Tags wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="cfba8-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="cfba8-117">Wenn der Text im Textfeld nur aus einem Textabsatz besteht, wird das HTML im Platzhalter, mit dem Blockelemente definiert werden, ordnungsgemäß gerendert.</span><span class="sxs-lookup"><span data-stu-id="cfba8-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="cfba8-118">Wenn das Textfeld hingegen mehrere Textblöcke aufweist, werden die HTML-Tags ignoriert, und die Struktur des Texts wird durch die Textblöcke bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cfba8-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="cfba8-119">Wenn mehrere Tags für den Text definiert wurden und ein Konflikt zwischen HTML und vorhandenen Berichtseinschränkungen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] erkannt wird, werden nur die innersten HTML-Tags als HTML behandelt.</span><span class="sxs-lookup"><span data-stu-id="cfba8-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="cfba8-120">Bei Verwendung der Tags zur Behandlung von Listen werden Schriftart und Stil aller Aufzählungszeichen und Zahlenpräfixe auf Arial schwarz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cfba8-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="cfba8-121">Weitere Informationen finden Sie unter [Hinzufügen von HTML in einem Bericht (Berichts-Generator und SSRS)](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cfba8-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="cfba8-122">Einschränkungen von Cascading Stylesheet-Attributen</span><span class="sxs-lookup"><span data-stu-id="cfba8-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="cfba8-123">Im Hinblick auf die Verwendung von CSS (Cascading Stylesheets)-Attributen wird nur eine Reihe grundlegender Tags definiert.</span><span class="sxs-lookup"><span data-stu-id="cfba8-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="cfba8-124">Nachfolgend finden Sie eine Liste der unterstützten Attribute:</span><span class="sxs-lookup"><span data-stu-id="cfba8-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="cfba8-125">text-align, text-indent</span><span class="sxs-lookup"><span data-stu-id="cfba8-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="cfba8-126">font-family</span><span class="sxs-lookup"><span data-stu-id="cfba8-126">font-family</span></span>  
  
-   <span data-ttu-id="cfba8-127">font-size</span><span class="sxs-lookup"><span data-stu-id="cfba8-127">font-size</span></span>  
  
    -   <span data-ttu-id="cfba8-128">Nur gültige RDL-Größenwerte in absoluten CSS-Längeneinheiten werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cfba8-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="cfba8-129">Unterstützte Einheiten: in, cm, mm, pt, pc.</span><span class="sxs-lookup"><span data-stu-id="cfba8-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="cfba8-130">Relative CSS-Längeneinheiten werden ignoriert und nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cfba8-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="cfba8-131">Nicht unterstützte Einheiten: em, ex, px,%,rem.</span><span class="sxs-lookup"><span data-stu-id="cfba8-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="cfba8-132">color</span><span class="sxs-lookup"><span data-stu-id="cfba8-132">color</span></span>  
  
-   <span data-ttu-id="cfba8-133">padding, padding-bottom, padding-top, padding-right, padding-left</span><span class="sxs-lookup"><span data-stu-id="cfba8-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="cfba8-134">font-weight</span><span class="sxs-lookup"><span data-stu-id="cfba8-134">font-weight</span></span>  
  
 <span data-ttu-id="cfba8-135">Nachfolgend finden Sie einige Überlegungen zur Verwendung von CSS:</span><span class="sxs-lookup"><span data-stu-id="cfba8-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="cfba8-136">CSS-Werte mit ungültigem Format werden ebenso ignoriert wie fehlerhaftes HTML.</span><span class="sxs-lookup"><span data-stu-id="cfba8-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="cfba8-137">Wenn ein Tag sowohl Attribute als auch CSS-Formatattribute enthält, kommt der CSS-Eigenschaft eine höhere Priorität zu.</span><span class="sxs-lookup"><span data-stu-id="cfba8-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="cfba8-138">Wenn Ihr Text beispielsweise ist **\<p style="text-align: right" align="left">** , wird nur das Text-align-Attribut angewendet, und der Text wird rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="cfba8-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="cfba8-139">Wenn eine Eigenschaft bei Attributen oder CSS-Formaten mehrfach angegeben wurde, wird nur die letzte Instanz der Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="cfba8-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="cfba8-140">Wenn Ihr Text beispielsweise ist **\<p align="left" align="right">** , wird der Text rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="cfba8-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfba8-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfba8-141">See Also</span></span>  
 [<span data-ttu-id="cfba8-142">Rendern in das HTML-Format &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cfba8-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
