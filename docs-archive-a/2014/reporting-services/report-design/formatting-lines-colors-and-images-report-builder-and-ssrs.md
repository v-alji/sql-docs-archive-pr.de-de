---
title: Formatieren von Linien, Farben und Bildern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695378"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="0a676-102">Formatieren von Linien, Farben und Bildern (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a676-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="0a676-103">können Sie Linien, Farben, Datenbereiche, Bilder und andere Berichtselemente formatieren.</span><span class="sxs-lookup"><span data-stu-id="0a676-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="0a676-104">Rahmen, Linien und Gitternetzlinien</span><span class="sxs-lookup"><span data-stu-id="0a676-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="0a676-105">Mithilfe von Rahmen, Linien und Gitternetzlinien können Elemente auf einer Seite verbunden und angeordnet werden, damit Leser den Inhalt des Berichts besser erfassen können.</span><span class="sxs-lookup"><span data-stu-id="0a676-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="0a676-106">Mithilfe der vordefinierten Rahmenstile können Sie einem Textfeld, einer Gruppe von Textfeldern oder einem Bild schnell einen Rahmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a676-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="0a676-107">Außerdem können Sie für die Rahmen, Linien und Gitternetzlinien den Stil, die Breite und die Farbe ändern.</span><span class="sxs-lookup"><span data-stu-id="0a676-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="0a676-108">Rahmen werden um ein gesamtes ausgewähltes Element oder entlang der Umrandung eines Elements hinzugefügt, zum Beispiel an der Unterseite eines Textfelds.</span><span class="sxs-lookup"><span data-stu-id="0a676-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="0a676-109">Verwenden Sie die Registerkarte **Rahmen** im Dialogfeld **Eigenschaften** des Berichtselements, um Rahmen und Gitternetzlinien in einem Textfeld, Berichtslayout oder als Bildeinfassung zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="0a676-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="0a676-110">Wenn Sie z.B. einen Rahmen für ein Bild hinzufügen möchten, klicken Sie mit der rechten Maustaste auf das Bild, und klicken Sie anschließend im Dialogfeld **Bildeigenschaften** auf **Rahmen**.</span><span class="sxs-lookup"><span data-stu-id="0a676-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="0a676-111">Neben den Standardrahmen können auch zusätzliche Rahmen für Diagramme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a676-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="0a676-112">Weitere Informationen finden Sie unter [Hinzufügen eines Rahmens zu einem Diagramm (Berichts-Generator und SSRS)](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a676-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0a676-113">Sie können auch dem Bericht selbst einen Rahmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a676-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="0a676-114">Weitere Informationen finden Sie unter [Hinzufügen eines Rahmens zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a676-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="0a676-115">Anwenden von Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="0a676-115">Applying Background Colors</span></span>  
 <span data-ttu-id="0a676-116">Sie können dem Hintergrund eines gesamten Berichts, eines Textfelds im Bericht oder einer Zelle oder Gruppe von Zellen in einem Datenbereich eine Volltonfarbe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a676-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="0a676-117">Die Hintergrundfarbe ist standardmäßig Weiß. Sie können jedoch auf der Registerkarte **Ausfüllen** im Dialogfeld **Eigenschaften** des Berichtselements eine andere Farbe auswählen.</span><span class="sxs-lookup"><span data-stu-id="0a676-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="0a676-118">Wenn Sie z.B. die Hintergrundfarbe eines Textfelds ändern möchten, klicken Sie mit der rechten Maustaste auf das Textfeld, und wählen Sie **Textfeldeigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="0a676-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="0a676-119">Klicken Sie auf **Ausfüllen** , und wählen Sie die dann die gewünschte Farbe aus.</span><span class="sxs-lookup"><span data-stu-id="0a676-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="0a676-120">In diesem Dialogfeld können Sie für das ausgewählte Element eine Hintergrundfarbe festlegen, oder Sie können ein Bild hinzufügen, das im Hintergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a676-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="0a676-121">Wenn Sie das Diagramm verwenden, können Sie für Hintergrundfarben auch Farbverläufe und Musterarten angeben.</span><span class="sxs-lookup"><span data-stu-id="0a676-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="0a676-122">Weitere Informationen finden Sie unter [Formatieren eines Diagramms (Berichts-Generator und SSRS)](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a676-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="0a676-123">Verwenden von Bildern als Formatierung</span><span class="sxs-lookup"><span data-stu-id="0a676-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="0a676-124">Sie können Felder, die Bilder enthalten, einem Datenbereich hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a676-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="0a676-125">Wenn Sie ein Bildfeld verwenden, werden die Bilder im Bericht beim Ausführen des Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0a676-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="0a676-126">Sie können dem Hintergrund des Berichts oder einem Rechteck, einem Textfeld, einer Tabelle, einer Matrix, einigen Teilen eines Diagramms oder den Text- und Seitenabschnitten eines Berichts auch Bilder hinzufügen, z. B. Logos.</span><span class="sxs-lookup"><span data-stu-id="0a676-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="0a676-127">Weitere Informationen finden Sie unter [Bilder &#40;Berichts-Generator und SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a676-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a676-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a676-128">See Also</span></span>  
 <span data-ttu-id="0a676-129">[Formatieren von Text und Platzhaltern &#40;Berichts-Generator und SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a676-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0a676-130">[Formatieren von Zahlen und Datumsangaben &#40;Berichts-Generator und SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a676-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0a676-131">[Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS)](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a676-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0a676-132">Ausfüllen (Dialogfeld) (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a676-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
