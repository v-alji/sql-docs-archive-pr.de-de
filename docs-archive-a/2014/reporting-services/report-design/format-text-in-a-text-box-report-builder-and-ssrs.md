---
title: Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616385"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="72325-102">Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="72325-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72325-103">Sie können beliebige Teile des Texts in einem Textfeld unabhängig voneinander formatieren und Platzhaltertext und statischen Text in einem Textfeld mischen.</span><span class="sxs-lookup"><span data-stu-id="72325-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="72325-104">Durch das Mischen von Formaten und Hinzufügen von Platzhaltertext können Sie im Bericht Seriendrucke oder Vorlagen für Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="72325-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="72325-105">Jeder Ausdruck kann mithilfe eines Platzhalters getrennt definiert und formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="72325-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="72325-106">So kombinieren Sie mehrere Formatierungen in einem Textfeld</span><span class="sxs-lookup"><span data-stu-id="72325-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="72325-107">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="72325-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="72325-108">Klicken Sie auf die Entwurfsoberfläche, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Größe.</span><span class="sxs-lookup"><span data-stu-id="72325-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="72325-109">Wählen Sie im Textfeld den Text aus, der formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="72325-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="72325-110">Klicken Sie mit der rechten Maustaste auf den markierten Text, und klicken Sie dann auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="72325-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="72325-111">Legen Sie die Formatierungsoptionen fest.</span><span class="sxs-lookup"><span data-stu-id="72325-111">Set formatting options.</span></span> <span data-ttu-id="72325-112">Beispielsweise auf der Registerkarte **Allgemein** :</span><span class="sxs-lookup"><span data-stu-id="72325-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="72325-113">**QuickInfo:** Geben Sie Text ein oder einen Ausdruck, der zu einer QuickInfo ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="72325-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="72325-114">Die QuickInfo wird angezeigt, wenn der Benutzer den Mauszeiger über das Element in einem Bericht hält.</span><span class="sxs-lookup"><span data-stu-id="72325-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="72325-115">**Markuptyp:** Wählen Sie eine Option aus, um anzugeben, wie der markierte Text gerendert wird:</span><span class="sxs-lookup"><span data-stu-id="72325-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="72325-116">**Nur Text:** Zeigt den markierten Text als einfachen Text an.</span><span class="sxs-lookup"><span data-stu-id="72325-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="72325-117">HTML wird als Literaltext behandelt.</span><span class="sxs-lookup"><span data-stu-id="72325-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="72325-118">**HTML**  Zeigt den markierten Text als HTML an.</span><span class="sxs-lookup"><span data-stu-id="72325-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="72325-119">Wenn der Ausdruckswert des Platzhalters gültige HTML-Tags enthält, werden diese Tags als HTML gerendert.</span><span class="sxs-lookup"><span data-stu-id="72325-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="72325-120">Weitere Informationen finden Sie unter [Importieren von HTML in einen Bericht (Berichts-Generator und SSRS)](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72325-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="72325-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72325-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="72325-122">Wiederholen Sie die Schritte 2 bis 5 für den übrigen zu formatierenden Text.</span><span class="sxs-lookup"><span data-stu-id="72325-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="72325-123">So formatieren Sie Text und Platzhalter im gleichen Textfeld unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="72325-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="72325-124">Klicken Sie auf der Registerkarte **Einfügen** auf **Liste**.</span><span class="sxs-lookup"><span data-stu-id="72325-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="72325-125">Klicken Sie auf die Entwurfsoberfläche, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Größe.</span><span class="sxs-lookup"><span data-stu-id="72325-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="72325-126">Das Dialogfeld **Dataseteigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72325-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="72325-127">Sie können ein freigegebenes Dataset oder ein im Bericht eingebettetes Dataset verwenden.</span><span class="sxs-lookup"><span data-stu-id="72325-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="72325-128">Weitere Informationen finden Sie unter [Dataseteigenschaften (Dialogfeld), Abfrage (Berichts-Generator)](../report-data/dataset-properties-dialog-box-query-report-builder.md) oder [Dataseteigenschaften (Dialogfeld), Abfrage](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="72325-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="72325-129">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="72325-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="72325-130">Klicken Sie in die Liste, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Größe.</span><span class="sxs-lookup"><span data-stu-id="72325-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="72325-131">Geben Sie im Textfeld eine Bezeichnung ein, z. B. **Mein Feld**.</span><span class="sxs-lookup"><span data-stu-id="72325-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="72325-132">Ziehen Sie ein Feld aus dem Dataset in das Textfeld.</span><span class="sxs-lookup"><span data-stu-id="72325-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="72325-133">Es wird ein Platzhalter für das Feld erstellt.</span><span class="sxs-lookup"><span data-stu-id="72325-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="72325-134">Wählen Sie für einfache Formatierung den Platzhaltertext aus, und klicken Sie dann auf der Registerkarte **Home** in der Gruppe **Schriftart** auf eine der Formatierungsoptionen. Klicken Sie z.B. auf die Schaltfläche **Bold** (Fett).</span><span class="sxs-lookup"><span data-stu-id="72325-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="72325-135">Klicken Sie mit der rechten Maustaste auf den Platzhaltertext, und klicken Sie dann auf **Platzhaltereigenschaften**, um weitere Formatierungsoptionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72325-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="72325-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72325-136">Click **OK**.</span></span> <span data-ttu-id="72325-137">Das Textfeld in der Berichtsentwurfsansicht sollte „**Mein Feld**: [*Feldname*]“ enthalten, wobei *Feldname* der Name des Felds ist.</span><span class="sxs-lookup"><span data-stu-id="72325-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="72325-138">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="72325-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="72325-139">Die Liste wird für jeden Wert im Feld einmal wiederholt, und der Platzhalter *Feldname* wird jedes Mal durch den Wert dieses Felds im Dataset ersetzt.</span><span class="sxs-lookup"><span data-stu-id="72325-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72325-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72325-140">See Also</span></span>  
 <span data-ttu-id="72325-141">[Textfelder &#40;Berichts-Generator und SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-142">[Formatieren von Text und Platzhaltern &#40;Berichts-Generator und SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-143">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-144">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-145">[Hinzufügen von HTML in einem Bericht (Berichts-Generator und SSRS)](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-146">[Listet &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72325-147">[Formatieren von Zahlen und Datumsangaben &#40;Berichts-Generator und SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72325-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="72325-148">Platzhaltereigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="72325-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
