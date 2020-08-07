---
title: Angeben eines Bilds als Zeiger auf einem Messgerät (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719456"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="b45b6-102">Festlegen eines Bilds als Zeiger auf einem Messgerät (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b45b6-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b45b6-103">Messgeräte enthalten drei integrierte Formate, mit denen Sie die Darstellung des Zeigers anpassen können.</span><span class="sxs-lookup"><span data-stu-id="b45b6-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="b45b6-104">Für ein radiales Messgerät lauten die integrierten Stile: Nadel, Marker und Balken.</span><span class="sxs-lookup"><span data-stu-id="b45b6-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="b45b6-105">Für ein lineares Messgerät lauten die integrierten Stile: Marker, Balken und Thermometer.</span><span class="sxs-lookup"><span data-stu-id="b45b6-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="b45b6-106">Falls ein besonderer Zeiger benötigt wird, können Benutzer ein Bild erstellen und angeben, das dann als voll funktionsfähiger Zeiger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b45b6-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="b45b6-107">Wenn Sie ein Bild für den Zeiger auswählen, muss dieses Bild die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b45b6-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="b45b6-108">Der Ursprung des Zeigers bzw. das Zentrum der Drehung muss am oberen Rand des Bilds liegen.</span><span class="sxs-lookup"><span data-stu-id="b45b6-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="b45b6-109">Das Ende des Zeigers muss nach unten zeigen.</span><span class="sxs-lookup"><span data-stu-id="b45b6-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="b45b6-110">Da der Zeiger eine unregelmäßige Form aufweist, müssen Sie mit einer Transparenzfarbe die überflüssigen Teile des Bilds ausblenden.</span><span class="sxs-lookup"><span data-stu-id="b45b6-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="b45b6-111">Sie können hierfür eine Farbe verwenden, die normalerweise nicht auf dem Messgerät als Transparenzfarbe angezeigt wird, da die angegebenen Farben nicht auf dem Messgerät erscheinen.</span><span class="sxs-lookup"><span data-stu-id="b45b6-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="b45b6-112">So legen Sie ein Bild als Zeiger auf dem Messgerät fest</span><span class="sxs-lookup"><span data-stu-id="b45b6-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="b45b6-113">Klicken Sie in der Entwurfsansicht auf den Zeiger des Messgeräts.</span><span class="sxs-lookup"><span data-stu-id="b45b6-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="b45b6-114">Optionale Wenn auf dem Messgerät kein Zeiger vorhanden ist, klicken Sie mit der rechten Maustaste auf das Messgerät, und wählen Sie **Zeiger hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b45b6-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="b45b6-115">Es wird ein Zeiger zum Messgerät hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b45b6-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="b45b6-116">Klicken Sie im Menüband auf die Registerkarte **Einfügen** , und doppelklicken Sie auf das Bildsymbol.</span><span class="sxs-lookup"><span data-stu-id="b45b6-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="b45b6-117">Das Dialogfeld **Bildeigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b45b6-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="b45b6-118">Fügen Sie dem Bericht ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="b45b6-118">Add an image to your report.</span></span> <span data-ttu-id="b45b6-119">Weitere Informationen finden Sie unter [Einbetten eines Bilds in einen Bericht &#40;Berichts-Generator und SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b45b6-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="b45b6-120">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b45b6-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="b45b6-121">Klicken Sie auf der Entwurfsoberfläche auf den Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b45b6-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="b45b6-122">Die Eigenschaften für den Zeiger werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b45b6-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="b45b6-123">Erweitern Sie den Knoten PointerImage.</span><span class="sxs-lookup"><span data-stu-id="b45b6-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="b45b6-124">Wählen Sie unter **Quelle**die Option **eingebettet** aus der Dropdown Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b45b6-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b45b6-125">Falls das Bild in der Datenbank oder im Web gespeichert ist, wählen Sie die entsprechende Option für diese Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="b45b6-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="b45b6-126">Weitere Informationen finden Sie unter [Bildeigenschaften (Dialog Feld), allgemein &#40;Berichts-Generator und SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b45b6-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="b45b6-127">Wählen Sie unter **Wert**den Namen des Images aus der Dropdown Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b45b6-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="b45b6-128">Wählen Sie in **TransparentColor**einen Farbwert aus, den Sie aus dem Bild entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="b45b6-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="b45b6-129">Dies führt zu einer gleichmäßigen Darstellung des Zeigers auf dem Messgerät.</span><span class="sxs-lookup"><span data-stu-id="b45b6-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45b6-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b45b6-130">See Also</span></span>  
 <span data-ttu-id="b45b6-131">[Formatieren von Zeigern auf einem Messgerät &#40;Berichts-Generator und SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b45b6-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b45b6-132">[Hinzufügen eines Messgerätes zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b45b6-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b45b6-133">[Formatieren von Linien, Farben und Bildern &#40;Berichts-Generator und SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b45b6-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b45b6-134">Messgeräte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b45b6-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
