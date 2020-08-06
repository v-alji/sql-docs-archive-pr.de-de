---
title: Hinzufügen eines externen Bilds (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696413"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="f1e64-102">Hinzufügen eines externen Bilds (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f1e64-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f1e64-103">Externe Bilder können auf einem Berichtsserver im einheitlichen Modus bzw. im integrierten SharePoint-Modus oder auf einer beliebigen anderen Website gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="f1e64-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="f1e64-104">Wenn Sie externe Bilder im Bericht verwenden, müssen Sie prüfen, ob das Bild vorhanden ist und ob der Leser des Berichts Zugriffsberechtigungen für das Bild hat.</span><span class="sxs-lookup"><span data-stu-id="f1e64-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="f1e64-105">Weitere Informationen finden Sie unter [Bilder &#40;Berichts-Generator und SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f1e64-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="f1e64-106">So fügen Sie ein externes Bild hinzu</span><span class="sxs-lookup"><span data-stu-id="f1e64-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="f1e64-107">Klicken Sie in der Berichtsentwurfsansicht auf der Registerkarte **Einfügen** auf **Bild**.</span><span class="sxs-lookup"><span data-stu-id="f1e64-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="f1e64-108">Klicken Sie auf die Entwurfsoberfläche, und ziehen Sie ein Feld auf die gewünschte Größe des Bilds.</span><span class="sxs-lookup"><span data-stu-id="f1e64-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="f1e64-109">Geben Sie im Dialogfeld **Bildeigenschaften** auf der Registerkarte **Allgemein** einen Namen im Textfeld **Name** ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="f1e64-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="f1e64-110">(Optional) Geben Sie im Textfeld **QuickInfo** Text ein, der angezeigt wird, wenn der Benutzer in einem in HTML gerenderten Bericht auf das Bild zeigt.</span><span class="sxs-lookup"><span data-stu-id="f1e64-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="f1e64-111">Wählen Sie unter **Bildquelle auswählen**die Option **Extern**aus.</span><span class="sxs-lookup"><span data-stu-id="f1e64-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="f1e64-112">Wenn ein Bild auf einem Berichtsserver im einheitlichen Modus gespeichert ist, geben Sie im Feld **Dieses Bild verwenden** einen relativen Pfad zu dem Bild ein, z.B. „../images/image1.jpg“.</span><span class="sxs-lookup"><span data-stu-id="f1e64-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="f1e64-113">Geben Sie für ein Bild auf einem Berichts Server im integrierten SharePoint-Modus oder auf einer beliebigen anderen Website im Feld **dieses Bild verwenden** eine vollständige URL für das Bild ein, z \<SharePointservername> / \<site> . b. http:///Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="f1e64-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="f1e64-114">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f1e64-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="f1e64-115">(Optional) Klicken Sie auf **Größe**, **Sichtbarkeit**, **Aktion**oder **Rahmen** , um weitere Eigenschaften für das Bildberichtselement festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f1e64-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1e64-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1e64-116">See Also</span></span>  
 <span data-ttu-id="f1e64-117">[Einbetten eines Bilds in einen Bericht &#40;Berichts-Generator und SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1e64-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f1e64-118">[Hinzufügen eines Hintergrundbilds (Berichts-Generator und SSRS)](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1e64-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f1e64-119">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f1e64-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
