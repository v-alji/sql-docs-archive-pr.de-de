---
title: Bilder (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697545"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="08d13-102">Bilder (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="08d13-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="08d13-103">Ein Bild ist ein Berichtselement mit einem Verweis auf ein Bild, das in den Bericht eingebettet, in einer Datenbank, auf dem Berichtsserver oder an einer anderen Stelle im Internet gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="08d13-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="08d13-104">Ein Bild kann ein mit Datenzeilen wiederholtes Bild darstellen.</span><span class="sxs-lookup"><span data-stu-id="08d13-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="08d13-105">Sie können ein Bild auch als Hintergrund für bestimmte Berichtselemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="08d13-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="08d13-106">Es empfiehlt sich, Logos auf einem Server zu speichern, da das gleiche Logo in zahlreichen Berichten wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="08d13-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="08d13-107">Vergleichen externer, eingebetteter und datengebundener Bilder</span><span class="sxs-lookup"><span data-stu-id="08d13-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="08d13-108">Wenn Sie ein serverbasiertes oder anderes externes Bild in einem Bericht verwenden, enthält das Bildelement einen Pfad, der auf ein Bild auf dem Berichtsserver oder an einer beliebigen Stelle im Web zeigt.</span><span class="sxs-lookup"><span data-stu-id="08d13-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="08d13-109">Wenn Sie allerdings ein eingebettetes Bild verwenden, werden die Bilddaten innerhalb der Berichtsdefinition gespeichert. Sie sind demnach nicht als separate Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="08d13-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="08d13-110">Serverbasierte Bilder eignen sich gut für Logos und statische Bilder, die für mehrere Berichte oder Webseiten freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="08d13-111">Mit eingebetteten Bildern wird sichergestellt, dass die Bilder immer für den Bericht verfügbar sind. Sie können allerdings nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="08d13-112">Berichtsdefinitionen mit externen Bildern sind kleiner als Definitionen mit eingebetteten Bildern.</span><span class="sxs-lookup"><span data-stu-id="08d13-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="08d13-113">Datengebundene Bilder können auch aus in einer Datenbank gespeicherten Binärdaten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="08d13-114">Datenbankbilder sind beispielsweise Bilder, die neben Produktnamen in einer Produktliste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="08d13-115">In der folgenden Abbildung werden die Bilder von Fahrrädern in einer Datenbank gespeichert und im Bericht abgerufen, um die einzelnen Produkte zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="08d13-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="08d13-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="08d13-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="08d13-117">Bilder als Berichtsteile</span><span class="sxs-lookup"><span data-stu-id="08d13-117">Images as Report Parts</span></span>  
 <span data-ttu-id="08d13-118">Bilder können getrennt von einem Bericht als Berichtsteile gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="08d13-119">Einbetten von Bildern</span><span class="sxs-lookup"><span data-stu-id="08d13-119">Embedding Images</span></span>  
 <span data-ttu-id="08d13-120">Sie können Bilder in einen Bericht einbetten, sodass alle Bilddaten innerhalb der Berichtsdefinition gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="08d13-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="08d13-121">Wenn Sie ein Bild einbetten, wird für das Bild die MIME-Codierung ausgeführt, und es wird als Text in der Berichtsdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="08d13-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="08d13-122">Durch das Verwenden eines eingebetteten Bilds wird sichergestellt, dass das Bild immer für den Bericht verfügbar ist. Gleichzeitig nimmt allerdings die Größe der Berichtsdefinition zu.</span><span class="sxs-lookup"><span data-stu-id="08d13-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="08d13-123">Weitere Informationen zum Einbetten eines Bilds finden Sie unter [Einbetten eines Bilds in einen Bericht &#40;Berichts-Generator und SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="08d13-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="08d13-124">Externe Bilder</span><span class="sxs-lookup"><span data-stu-id="08d13-124">External Images</span></span>  
 <span data-ttu-id="08d13-125">Sie können gespeicherte Bilder in einen Bericht einschließen, indem Sie eine URL zum Bild angeben.</span><span class="sxs-lookup"><span data-stu-id="08d13-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="08d13-126">Wenn Sie in einem Bericht ein externes Bild verwenden, wird die Bildquelle auf `External` festgelegt, und der Wert des Bilds entspricht der URL-Adresse oder dem Pfad zum Bild.</span><span class="sxs-lookup"><span data-stu-id="08d13-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="08d13-127">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="08d13-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="08d13-128">Wenn der Bericht im Berichts-Generator oder im Berichts-Designer ausgeführt wird, verwendet die Vorschau die Anmeldeinformationen des Benutzers zur Anzeige des Bilds.</span><span class="sxs-lookup"><span data-stu-id="08d13-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="08d13-129">Wenn der Bericht auf dem Berichtsserver ausgeführt wird, wird das Bild in dem Bericht möglicherweise nicht angezeigt, wenn die Serveranmeldeinformationen nicht für den Zugriff auf das Bild ausreichen.</span><span class="sxs-lookup"><span data-stu-id="08d13-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="08d13-130">In diesem Fall wenden Sie sich an den Systemadministrator.</span><span class="sxs-lookup"><span data-stu-id="08d13-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="08d13-131">Weitere Informationen zum Hinzufügen eines externen Bilds zu einem Bericht finden Sie unter [Hinzufügen eines externen Bilds &#40;Berichts-Generator und SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="08d13-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="08d13-132">Hintergrundbilder</span><span class="sxs-lookup"><span data-stu-id="08d13-132">Background Images</span></span>  
 <span data-ttu-id="08d13-133">Sie können ein Bild im Hauptteil des Berichts, in einem Rechteck oder Textfeld, einer Liste, Matrix oder Tabelle als Hintergrundbild verwenden.</span><span class="sxs-lookup"><span data-stu-id="08d13-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="08d13-134">Ein Hintergrundbild hat ähnliche Eigenschaften wie ein Bild.</span><span class="sxs-lookup"><span data-stu-id="08d13-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="08d13-135">Sie können auch angeben, wie das Bild zum Ausfüllen des Elementhintergrundes wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="08d13-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08d13-136">Einige Renderingerweiterungen, z.B. die HTML-Renderingerweiterung, rendern das Hintergrundbild für den Hauptteil des Berichts im Hauptteil, in der Kopfzeile und in der Fußzeile.</span><span class="sxs-lookup"><span data-stu-id="08d13-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="08d13-137">Sie können ein separates Hintergrundbild für die Kopfzeile und die Fußzeile definieren. Wenn jedoch kein Bild definiert ist, verwendet der Bericht das Hintergrundbild des Hauptteiles.</span><span class="sxs-lookup"><span data-stu-id="08d13-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="08d13-138">Bei anderen Renderingerweiterungen, z.B. der Bildrenderingerweiterung, wird das Hintergrundbild nicht in der Kopfzeile und Fußzeile gerendert.</span><span class="sxs-lookup"><span data-stu-id="08d13-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="08d13-139">Weitere Informationen zum Hinzufügen eines Hintergrundbilds finden Sie unter [Hinzufügen eines Hintergrundbilds &#40;Berichts-Generator und SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="08d13-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="08d13-140">Datengebundene Bilder</span><span class="sxs-lookup"><span data-stu-id="08d13-140">Data-bound Images</span></span>  
 <span data-ttu-id="08d13-141">Sie können einem Bericht Bilder hinzufügen, die in einer Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="08d13-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="08d13-142">Dabei können Sie dasselbe Bildberichtselement wie für statische Bilder verwenden, jedoch mit einer Reihe von Eigenschaften, die die Speicherung des Bilds in einer Datenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="08d13-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="08d13-143">Anleitungen zum Verwenden von datengebundenen Bildern finden Sie unter [Hinzufügen eines datengebundenen Bilds &#40;Berichts-Generator und SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="08d13-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="08d13-144">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="08d13-144">How-to Topics</span></span>  
 [<span data-ttu-id="08d13-145">Hinzufügen eines externen Bilds &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="08d13-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="08d13-146">Einbetten eines Bilds in einen Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="08d13-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="08d13-147">Hinzufügen eines Hintergrundbilds &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="08d13-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="08d13-148">Hinzufügen eines datengebundenen Bilds &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="08d13-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="08d13-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08d13-149">See Also</span></span>  
 <span data-ttu-id="08d13-150">[Exportieren in eine Bilddatei &#40;Berichts-Generator und SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="08d13-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="08d13-151">Renderingverhalten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="08d13-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
