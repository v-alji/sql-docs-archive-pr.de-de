---
title: Einbetten eines Bilds in einen Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695405"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="0d83b-102">Einbetten eines Bilds in einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d83b-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0d83b-103">Ein Bericht kann ein eingebettetes Bild enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d83b-103">A report can include an embedded image.</span></span> <span data-ttu-id="0d83b-104">Durch das Einbetten eines Bilds wird sichergestellt, dass das Bild immer für den Bericht verfügbar ist. Gleichzeitig nimmt allerdings die Größe der Berichtsdefinition zu; das ist die Datei, die den Bericht definiert.</span><span class="sxs-lookup"><span data-stu-id="0d83b-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="0d83b-105">Die in einen Bericht eingebetteten Bilder werden im Berichtsdatenbereich aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d83b-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="0d83b-106">Sie können ein Bild in die Berichtsdefinition einbetten, bevor Sie es der Entwurfsoberfläche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0d83b-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="0d83b-107">Weitere Informationen finden Sie unter [Hinzufügen eines Hintergrundbilds (Berichts-Generator und SSRS)](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d83b-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="0d83b-108">So betten Sie ein Bild in einen Bericht ein</span><span class="sxs-lookup"><span data-stu-id="0d83b-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="0d83b-109">Klicken Sie in der Berichtsentwurfsansicht auf der Registerkarte **Einfügen** auf **Bild**.</span><span class="sxs-lookup"><span data-stu-id="0d83b-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="0d83b-110">Klicken Sie auf die Entwurfsoberfläche, und ziehen Sie ein Feld auf die gewünschte Größe des Bilds.</span><span class="sxs-lookup"><span data-stu-id="0d83b-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="0d83b-111">Geben Sie im Dialogfeld **Bildeigenschaften** auf der Seite **Allgemein** einen Namen im Textfeld **Name** ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="0d83b-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="0d83b-112">Geben Sie (optional) im Textfeld **QuickInfo** Text ein, der angezeigt wird, wenn der Benutzer im gerenderten Bericht auf das Bild zeigt.</span><span class="sxs-lookup"><span data-stu-id="0d83b-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="0d83b-113">Wählen Sie unter **Bildquelle auswählen**die Option **Eingebettet**aus.</span><span class="sxs-lookup"><span data-stu-id="0d83b-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="0d83b-114">Klicken Sie neben dem Textfeld **Dieses Bild verwenden** auf die Schaltfläche **Importieren** .</span><span class="sxs-lookup"><span data-stu-id="0d83b-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="0d83b-115">Wählen Sie unter **Dateityp**den Bilddateityp aus, navigieren Sie zu der Datei, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="0d83b-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="0d83b-116">Klicken Sie im Dialogfeld **Bildeigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d83b-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="0d83b-117">Das Bild wird in dem auf der Entwurfsoberfläche gezeichneten Feld und die Datei unterhalb des Bildordners im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d83b-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d83b-118">Der MIME-Typ (z. B. BMP) wird beim Importieren des Bilds automatisch abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0d83b-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="0d83b-119">Um den MIME-Typ zu ändern, befolgen Sie die nächste Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="0d83b-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="0d83b-120">(Optional) So ändern Sie den MIME-Typ eines importierten Bilds</span><span class="sxs-lookup"><span data-stu-id="0d83b-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="0d83b-121">Öffnen Sie den Bericht in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="0d83b-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="0d83b-122">Wählen Sie das Bild in der Entwurfsoberfläche aus.</span><span class="sxs-lookup"><span data-stu-id="0d83b-122">Select the image on the design surface.</span></span> <span data-ttu-id="0d83b-123">Der Bereich **Eigenschaften** zeigt die Bildeigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="0d83b-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d83b-124">Zum Anzeigen des Bereichs „Eigenschaften“ klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0d83b-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0d83b-125">Klicken Sie auf das Textfeld neben der **MIMEType** -Eigenschaft, und wählen Sie in der Dropdownliste einen neuen MIME-Typ aus.</span><span class="sxs-lookup"><span data-stu-id="0d83b-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d83b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d83b-126">See Also</span></span>  
 <span data-ttu-id="0d83b-127">[Bilder &#40;Berichts-Generator und SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d83b-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d83b-128">[Hinzufügen eines datengebundenen Bilds (Berichts-Generator und SSRS)](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d83b-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0d83b-129">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d83b-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
