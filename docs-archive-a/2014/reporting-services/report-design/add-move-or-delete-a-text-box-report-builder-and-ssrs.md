---
title: Hinzufügen, Verschieben oder Löschen von Textfeldern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723462"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="5667f-102">Hinzufügen, Verschieben oder Löschen von Textfeldern (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="5667f-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5667f-103">Textfelder sind das am häufigsten verwendete Berichtselement in Berichten.</span><span class="sxs-lookup"><span data-stu-id="5667f-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="5667f-104">Sie können dem Hauptteil des Berichts ein Textfeld hinzufügen, um Informationen wie beispielsweise Titel, Parameterauswahlen, integrierte Felder und Datumsangaben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5667f-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="5667f-105">Jede Zelle in einer Tabelle oder Matrix ist in Wirklichkeit ein Textfeld.</span><span class="sxs-lookup"><span data-stu-id="5667f-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="5667f-106">Die in einem Bericht mit Tabellen und Matrizen angezeigten Berichtsdaten ergeben sich fast alle aus der Auswertung des Inhalts der einzelnen Textfelder im Bericht durch den Berichtsprozessor.</span><span class="sxs-lookup"><span data-stu-id="5667f-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="5667f-107">Sie können Zellen genau so formatieren, wie Sie andere Textfelder außerhalb des Datenbereichs formatieren würden.</span><span class="sxs-lookup"><span data-stu-id="5667f-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="5667f-108">Um einem Listendatenbereich ein Textfeld hinzuzufügen, müssen Sie zuerst das Textfeld hinzufügen und dann in die Liste ziehen.</span><span class="sxs-lookup"><span data-stu-id="5667f-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5667f-109">Wenn Sie auf ein Textfeld klicken, bearbeiten Sie sofort den Text im Textfeld.</span><span class="sxs-lookup"><span data-stu-id="5667f-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="5667f-110">Um das Textfeld selbst auszuwählen, und nicht den Text in dem Textfeld, drücken Sie ESC.</span><span class="sxs-lookup"><span data-stu-id="5667f-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="5667f-111">So fügen Sie ein Textfeld hinzu</span><span class="sxs-lookup"><span data-stu-id="5667f-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="5667f-112">Klicken Sie in der Entwurfsansicht in der Registerkarte **Einfügen** auf **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="5667f-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="5667f-113">Klicken Sie auf der Entwurfsoberfläche auf ein Feld, und ziehen Sie es auf die gewünschte Textfeldgröße.</span><span class="sxs-lookup"><span data-stu-id="5667f-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="5667f-114">Alternativ können Sie auf die Entwurfsoberfläche klicken, um ein Textfeld mit der Standardgröße zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5667f-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="5667f-115">So fügen Sie ein Textfeld in einer Liste hinzu</span><span class="sxs-lookup"><span data-stu-id="5667f-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="5667f-116">Klicken Sie in der Berichtsentwurfsansicht auf der Registerkarte **Einfügen** auf **Liste**.</span><span class="sxs-lookup"><span data-stu-id="5667f-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="5667f-117">Klicken Sie auf der Entwurfsoberfläche auf ein Feld, und ziehen Sie es auf die gewünschte Größe der Liste.</span><span class="sxs-lookup"><span data-stu-id="5667f-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="5667f-118">Alternativ können Sie auf die Entwurfsoberfläche klicken, um eine Liste mit der Standardgröße zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5667f-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="5667f-119">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="5667f-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="5667f-120">Klicken Sie auf die Entwurfsoberfläche, und ziehen Sie dann in der Liste, die Sie in Schritt 1 hinzugefügt haben, ein Feld auf die gewünschte Textfeldgröße.</span><span class="sxs-lookup"><span data-stu-id="5667f-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="5667f-121">Alternativ können Sie auf der Entwurfsoberfläche in die Liste klicken, um ein Textfeld mit der Standardgröße zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5667f-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="5667f-122">Wählen Sie das Textfeld aus, um zu überprüfen, ob es richtig in der Liste eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="5667f-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5667f-123">Wenn Sie im Bearbeitungsmodus in das Textfeld klicken, drücken Sie ESC, um das Textfeld zu wählen.</span><span class="sxs-lookup"><span data-stu-id="5667f-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="5667f-124">Prüfen Sie im Eigenschaftenbereich, ob die **Parent** -Eigenschaft dem Rechteck entspricht, das dem Listendatenbereich automatisch hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="5667f-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5667f-125">Falls der Bereich „Eigenschaften“ nicht angezeigt wird, aktivieren Sie auf der Registerkarte **Ansicht** die Option **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="5667f-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="5667f-126">So verschieben Sie ein Textfeld</span><span class="sxs-lookup"><span data-stu-id="5667f-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="5667f-127">Klicken Sie in der Berichtsentwurfssicht auf eine leere Stelle im Textfeld, um das Textfeld auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5667f-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5667f-128">Wenn Sie im Bearbeitungsmodus in das Textfeld klicken, drücken Sie ESC, um das Textfeld zu wählen.</span><span class="sxs-lookup"><span data-stu-id="5667f-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="5667f-129">Klicken Sie auf den Textfeldziehpunkt, und ziehen Sie das Textfeld an die neue Position.</span><span class="sxs-lookup"><span data-stu-id="5667f-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="5667f-130">Alternativ können Sie die Pfeiltasten verwenden, um das ausgewählte Textfeld horizontal oder vertikal zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="5667f-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="5667f-131">Um das Textfeld in kleineren Schritten auf der Entwurfsoberfläche zu verschieben, verwenden Sie die Pfeiltasten mit gedrückter STRG-TASTE.</span><span class="sxs-lookup"><span data-stu-id="5667f-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="5667f-132">So löschen Sie ein Textfeld</span><span class="sxs-lookup"><span data-stu-id="5667f-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="5667f-133">Klicken Sie in der Berichtsentwurfssicht mit der rechten Maustaste auf eine leere Stelle im Textfeld, um das Textfeld auszuwählen, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5667f-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="5667f-134">Oder klicken Sie auf eine leere Stelle im Textfeld, und drücken Sie dann die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="5667f-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5667f-135">Wenn Sie im Bearbeitungsmodus in das Textfeld klicken, drücken Sie ESC, um das Textfeld zu wählen.</span><span class="sxs-lookup"><span data-stu-id="5667f-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5667f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5667f-136">See Also</span></span>  
 <span data-ttu-id="5667f-137">[Text Felder &#40;Berichts-Generator und SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5667f-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5667f-138">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5667f-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5667f-139">Tastenkombinationen &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="5667f-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
