---
title: Exportieren in eine Bilddatei (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617788"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="b71aa-102">Exportieren in eine Bilddatei (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b71aa-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b71aa-103">Die Bildrenderingerweiterung rendert einen Bericht als Bitmap oder Metadatei.</span><span class="sxs-lookup"><span data-stu-id="b71aa-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="b71aa-104">Standardmäßig erstellt die Bildrenderingerweiterung eine TIFF-Datei des Berichts, die auf mehreren Seiten angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b71aa-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="b71aa-105">Nachdem der Client das Bild erhalten hat, kann es in einem Image Viewer angezeigt und gedruckt werden.</span><span class="sxs-lookup"><span data-stu-id="b71aa-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="b71aa-106">Dieses Thema enthält für das Bildrendering spezifische Informationen und beschreibt Ausnahmen zu den Renderingregeln.</span><span class="sxs-lookup"><span data-stu-id="b71aa-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="b71aa-107">Die Bildrenderingerweiterung kann Dateien in allen von [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]unterstützten Formaten generieren: BMP, EMF, EMFPlus, GIF, JPEG, PNG und TIFF.</span><span class="sxs-lookup"><span data-stu-id="b71aa-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="b71aa-108">Für TIFF lautet der Dateiname des primären Datenstromes *ReportName*.tif.</span><span class="sxs-lookup"><span data-stu-id="b71aa-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="b71aa-109">Für alle anderen Formate, die als Einzelseite pro Datei gerendert werden, lautet der Dateiname *ReportName_Page.ext* .</span><span class="sxs-lookup"><span data-stu-id="b71aa-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="b71aa-110">Dabei ist*ext* die Dateierweiterung für das ausgewählte Format.</span><span class="sxs-lookup"><span data-stu-id="b71aa-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="b71aa-111">Geben Sie eine der oben aufgeführten Zeichenfolgen in der **OutputFormatDeviceInfo** -Einstellung an, um eine Datei in einem anderen bildunterstützten Format zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b71aa-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="b71aa-112">Unterstützte Bildformate</span><span class="sxs-lookup"><span data-stu-id="b71aa-112">Supported Image Formats</span></span>  
 <span data-ttu-id="b71aa-113">In der folgenden Tabelle werden die Dateierweiterung und der MIME-Typ für jedes Bildrendererformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b71aa-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="b71aa-114">**Type**</span><span class="sxs-lookup"><span data-stu-id="b71aa-114">**Type**</span></span>|<span data-ttu-id="b71aa-115">**Erweiterung**</span><span class="sxs-lookup"><span data-stu-id="b71aa-115">**Extension**</span></span>|<span data-ttu-id="b71aa-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="b71aa-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="b71aa-117">BMP</span><span class="sxs-lookup"><span data-stu-id="b71aa-117">BMP</span></span>|<span data-ttu-id="b71aa-118">bmp</span><span class="sxs-lookup"><span data-stu-id="b71aa-118">bmp</span></span>|<span data-ttu-id="b71aa-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="b71aa-119">image/bmp</span></span>|  
|<span data-ttu-id="b71aa-120">GIF</span><span class="sxs-lookup"><span data-stu-id="b71aa-120">GIF</span></span>|<span data-ttu-id="b71aa-121">GIF</span><span class="sxs-lookup"><span data-stu-id="b71aa-121">gif</span></span>|<span data-ttu-id="b71aa-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="b71aa-122">image/gif</span></span>|  
|<span data-ttu-id="b71aa-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="b71aa-123">JPEG</span></span>|<span data-ttu-id="b71aa-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="b71aa-124">jpeg</span></span>|<span data-ttu-id="b71aa-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="b71aa-125">image/jpeg</span></span>|  
|<span data-ttu-id="b71aa-126">PNG</span><span class="sxs-lookup"><span data-stu-id="b71aa-126">PNG</span></span>|<span data-ttu-id="b71aa-127">png</span><span class="sxs-lookup"><span data-stu-id="b71aa-127">png</span></span>|<span data-ttu-id="b71aa-128">image/png</span><span class="sxs-lookup"><span data-stu-id="b71aa-128">image/png</span></span>|  
|<span data-ttu-id="b71aa-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="b71aa-129">TIFF</span></span>|<span data-ttu-id="b71aa-130">tif</span><span class="sxs-lookup"><span data-stu-id="b71aa-130">tif</span></span>|<span data-ttu-id="b71aa-131">image/tiff</span><span class="sxs-lookup"><span data-stu-id="b71aa-131">image/tiff</span></span>|  
|<span data-ttu-id="b71aa-132">EMF</span><span class="sxs-lookup"><span data-stu-id="b71aa-132">EMF</span></span>|<span data-ttu-id="b71aa-133">EMF</span><span class="sxs-lookup"><span data-stu-id="b71aa-133">emf</span></span>|<span data-ttu-id="b71aa-134">image/emf</span><span class="sxs-lookup"><span data-stu-id="b71aa-134">image/emf</span></span>|  
|<span data-ttu-id="b71aa-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="b71aa-135">EMFPlus</span></span>|<span data-ttu-id="b71aa-136">EMF</span><span class="sxs-lookup"><span data-stu-id="b71aa-136">emf</span></span>|<span data-ttu-id="b71aa-137">image/emf</span><span class="sxs-lookup"><span data-stu-id="b71aa-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="b71aa-138">Rendern von mehreren Seiten</span><span class="sxs-lookup"><span data-stu-id="b71aa-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="b71aa-139">TIFF ist das einzige Format, das mehrseitige Dokumente in einer einzelnen Datei unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b71aa-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="b71aa-140">Andere Formate, wie JPG oder PNG, geben jeweils nur eine Seite aus und erfordern für jede Seite einen separaten Aufruf der Renderingerweiterung.</span><span class="sxs-lookup"><span data-stu-id="b71aa-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="b71aa-141">Interaktivität</span><span class="sxs-lookup"><span data-stu-id="b71aa-141">Interactivity</span></span>  
 <span data-ttu-id="b71aa-142">Interaktivität wird von keinem der durch diesen Renderer generierten Bildformate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b71aa-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="b71aa-143">Die folgenden interaktiven Elemente werden nicht gerendert:</span><span class="sxs-lookup"><span data-stu-id="b71aa-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="b71aa-144">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="b71aa-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="b71aa-145">Anzeigen oder ausblenden</span><span class="sxs-lookup"><span data-stu-id="b71aa-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="b71aa-146">Dokumentstruktur</span><span class="sxs-lookup"><span data-stu-id="b71aa-146">Document Map</span></span>  
  
-   <span data-ttu-id="b71aa-147">Drillthrough oder Links mit Durchklicken</span><span class="sxs-lookup"><span data-stu-id="b71aa-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="b71aa-148">Endbenutzersortierung</span><span class="sxs-lookup"><span data-stu-id="b71aa-148">End user sort</span></span>  
  
-   <span data-ttu-id="b71aa-149">Feste Berichtsköpfe</span><span class="sxs-lookup"><span data-stu-id="b71aa-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="b71aa-150">Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="b71aa-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="b71aa-151">Geräte Informationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b71aa-151">Device Information Settings</span></span>  
 <span data-ttu-id="b71aa-152">Sie können einige Standardeinstellungen für diesen Renderer ändern, indem Sie die Geräteinformationseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="b71aa-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="b71aa-153">Weitere Informationen finden Sie unter [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b71aa-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="b71aa-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b71aa-154">See Also</span></span>  
 <span data-ttu-id="b71aa-155">[Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b71aa-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b71aa-156">[Renderingverhaltensweisen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b71aa-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b71aa-157">[Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen &#40;Berichts-Generator und SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b71aa-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="b71aa-158">[Rendern von Berichts Elementen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b71aa-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b71aa-159">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b71aa-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
