---
title: Hinzufügen eines Hintergrundbilds (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723489"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="6ab59-102">Hinzufügen eines Hintergrundbilds (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ab59-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6ab59-103">Sie können einem Berichtselement, z. B. einem Rechteck, Textfeld, einer Liste, Matrix, Tabelle und einigen Teilen eines Diagramms, oder einem Berichtsabschnitt, z. B. dem Seitenkopf, Seitenfuß oder Berichtshauptteil, ein Hintergrundbild hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6ab59-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="6ab59-104">Sie können ein Hintergrundbild für jedes ausgewählte Element in der Berichtsentwurfsoberfläche definieren, für das **BackgroundImage** im Bereich Eigenschaften angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6ab59-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="6ab59-105">Bei dem Hintergrundbild kann es sich wie bei anderen Bildern um eine URL zu einem Bild auf dem Berichtsserver handeln, ein Bild aus einem Datasetfeld oder ein in die Berichtsdefinition eingebettetes Bild.</span><span class="sxs-lookup"><span data-stu-id="6ab59-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="6ab59-106">Wenn Sie ein in den Bericht eingebettetes Bild verwenden möchten, müssen Sie es der Berichtsdefinition hinzufügen, bevor Sie es der Entwurfsoberfläche hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="6ab59-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="6ab59-107">So betten Sie ein Bild in die Berichtsdefinition ein</span><span class="sxs-lookup"><span data-stu-id="6ab59-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="6ab59-108">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf den Knoten **Bilder** , und klicken Sie dann auf **Bild hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6ab59-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ab59-109">Zum Anzeigen des Berichtsdatenbereichs klicken Sie auf der Registerkarte **Ansicht** auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="6ab59-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="6ab59-110">Navigieren Sie zu dem Bild, das Sie in die Berichtsdefinition einbetten möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ab59-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="6ab59-111">So fügen Sie ein Hintergrundbild hinzu</span><span class="sxs-lookup"><span data-stu-id="6ab59-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="6ab59-112">Wählen Sie in der Berichtsentwurfsansicht das Berichtselement aus, dem Sie ein Hintergrundbild hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6ab59-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="6ab59-113">Klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**, falls der Bereich "Eigenschaften" nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6ab59-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="6ab59-114">Erweitern Sie im Bereich "Eigenschaften" die **BackgroundImage**-Eigenschaft, und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6ab59-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="6ab59-115">Eingebettetes Bild:</span><span class="sxs-lookup"><span data-stu-id="6ab59-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="6ab59-116">Legen Sie **Source** auf **Embedded**fest.</span><span class="sxs-lookup"><span data-stu-id="6ab59-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="6ab59-117">Legen Sie für **Value** den Namen eines Bilds fest, das in den Bericht eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="6ab59-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="6ab59-118">Externes Bild:</span><span class="sxs-lookup"><span data-stu-id="6ab59-118">For an external image:</span></span>  
  
         <span data-ttu-id="6ab59-119">Legen Sie **Source** auf **External**fest.</span><span class="sxs-lookup"><span data-stu-id="6ab59-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="6ab59-120">Legen Sie für **Value** einen gültigen Pfad zu einem Bild fest.</span><span class="sxs-lookup"><span data-stu-id="6ab59-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="6ab59-121">Dieses kann sich auf einem Berichtsserver im einheitlichen Modus oder im integrierten SharePoint-Modus bzw. auf einer beliebigen anderen Website befinden.</span><span class="sxs-lookup"><span data-stu-id="6ab59-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="6ab59-122">Weitere Informationen finden Sie unter [Hinzufügen eines externen Bilds (Berichts-Generator und SSRS)](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6ab59-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="6ab59-123">Bild, das in einem Feld in der Datenbank enthalten ist, mit der das Berichtselement verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="6ab59-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="6ab59-124">Legen Sie **Source** auf **Database**fest.</span><span class="sxs-lookup"><span data-stu-id="6ab59-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="6ab59-125">Legen Sie für **Value** den Namen eines Felds im Berichtsdataset fest.</span><span class="sxs-lookup"><span data-stu-id="6ab59-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="6ab59-126">Weitere Informationen finden Sie unter [Hinzufügen eines datengebundenen Bilds (Berichts-Generator und SSRS)](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6ab59-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="6ab59-127">Wählen Sie für **MIMEType** oder als Dateiformat den entsprechenden MIME-Typ für das Bild aus, beispielsweise BMP.</span><span class="sxs-lookup"><span data-stu-id="6ab59-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6ab59-128">Die MIMEType-Eigenschaft trifft nur dann zu, wenn die **Source** -Eigenschaft auf **Database**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6ab59-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="6ab59-129">Wenn die **Source** -Eigenschaft auf **External** oder **Embedded**festgelegt ist, wird der Wert von **MIMEType** ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6ab59-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="6ab59-130">Wählen Sie für **BackgroundRepeat**einen Ausdruck, **Default**, **Repeat**, **RepeatX**, **RepeatY**oder **Clip**aus.</span><span class="sxs-lookup"><span data-stu-id="6ab59-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="6ab59-131">Für Hintergrundbilder in einem Diagramm kann **BackgroundRepeat** auf **Default**, **Repeat**, **Fit**und **Clip**festgelegt werden, jedoch nicht auf **RepeatX** oder **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="6ab59-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab59-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ab59-132">See Also</span></span>  
 <span data-ttu-id="6ab59-133">[Bilder &#40;Berichts-Generator und SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6ab59-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6ab59-134">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ab59-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
