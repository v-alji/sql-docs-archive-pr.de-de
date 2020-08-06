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
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a>Exportieren in eine Bilddatei (Berichts-Generator und SSRS)
  Die Bildrenderingerweiterung rendert einen Bericht als Bitmap oder Metadatei. Standardmäßig erstellt die Bildrenderingerweiterung eine TIFF-Datei des Berichts, die auf mehreren Seiten angezeigt werden kann. Nachdem der Client das Bild erhalten hat, kann es in einem Image Viewer angezeigt und gedruckt werden. Dieses Thema enthält für das Bildrendering spezifische Informationen und beschreibt Ausnahmen zu den Renderingregeln.  
  
 Die Bildrenderingerweiterung kann Dateien in allen von [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]unterstützten Formaten generieren: BMP, EMF, EMFPlus, GIF, JPEG, PNG und TIFF. Für TIFF lautet der Dateiname des primären Datenstromes *ReportName*.tif. Für alle anderen Formate, die als Einzelseite pro Datei gerendert werden, lautet der Dateiname *ReportName_Page.ext* . Dabei ist*ext* die Dateierweiterung für das ausgewählte Format. Geben Sie eine der oben aufgeführten Zeichenfolgen in der **OutputFormatDeviceInfo** -Einstellung an, um eine Datei in einem anderen bildunterstützten Format zu erstellen.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> Unterstützte Bildformate  
 In der folgenden Tabelle werden die Dateierweiterung und der MIME-Typ für jedes Bildrendererformat angezeigt.  
  
|**Type**|**Erweiterung**|**MIMEType**|  
|--------------|-------------------|------------------|  
|BMP|bmp|image/bmp|  
|GIF|GIF|image/gif|  
|JPEG|jpeg|image/jpeg|  
|PNG|png|image/png|  
|TIFF|tif|image/tiff|  
|EMF|EMF|image/emf|  
|EMFPlus|EMF|image/emf|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> Rendern von mehreren Seiten  
 TIFF ist das einzige Format, das mehrseitige Dokumente in einer einzelnen Datei unterstützt. Andere Formate, wie JPG oder PNG, geben jeweils nur eine Seite aus und erfordern für jede Seite einen separaten Aufruf der Renderingerweiterung.  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a>Interaktivität  
 Interaktivität wird von keinem der durch diesen Renderer generierten Bildformate unterstützt. Die folgenden interaktiven Elemente werden nicht gerendert:  
  
-   Hyperlinks  
  
-   Anzeigen oder ausblenden  
  
-   Dokumentstruktur  
  
-   Drillthrough oder Links mit Durchklicken  
  
-   Endbenutzersortierung  
  
-   Feste Berichtsköpfe  
  
-   Lesezeichen  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a>Geräte Informationseinstellungen  
 Sie können einige Standardeinstellungen für diesen Renderer ändern, indem Sie die Geräteinformationseinstellungen ändern. Weitere Informationen finden Sie unter [Image Device Information Settings](../image-device-information-settings.md).  
  
  
## <a name="see-also"></a>Weitere Informationen  
 [Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md)   
 [Renderingverhaltensweisen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md)   
 [Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen &#40;Berichts-Generator und SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md)   
 [Rendern von Berichts Elementen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md)   
 [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
