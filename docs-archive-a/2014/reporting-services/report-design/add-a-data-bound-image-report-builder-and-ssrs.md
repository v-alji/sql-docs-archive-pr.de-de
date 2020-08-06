---
title: Hinzufügen eines datengebundenen Bilds (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608304"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="dccbc-102">Hinzufügen eines datengebundenen Bilds (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dccbc-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dccbc-103">Ein Bericht kann einen Verweis auf ein Bild enthalten, das in einer Datenbank gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="dccbc-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="dccbc-104">Ein solches Bild wird als *datengebundenes Bild*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dccbc-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="dccbc-105">Bilder, die neben Produktnamen in einer Produktliste angezeigt werden, sind Beispiele für datengebundene Bilder.</span><span class="sxs-lookup"><span data-stu-id="dccbc-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="dccbc-106">Für das Hinzufügen eines datengebundenes Bilds zu einem Seitenkopf oder -fuß sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dccbc-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="dccbc-107">Weitere Informationen finden Sie unter [Seitenkopf- und Seitenfußzeilen (Berichts-Generator und SSRS)](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dccbc-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="dccbc-108">So fügen Sie ein datengebundenes Bild hinzu</span><span class="sxs-lookup"><span data-stu-id="dccbc-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="dccbc-109">Erstellen Sie in der Berichtsentwurfsansicht eine Tabelle mit einer Datenquellenverbindung und einem Dataset mit einem Feld, das binäre Bilddaten enthält.</span><span class="sxs-lookup"><span data-stu-id="dccbc-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="dccbc-110">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dccbc-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="dccbc-111">Fügen Sie eine Spalte in die Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="dccbc-111">Insert a column in your table.</span></span> <span data-ttu-id="dccbc-112">Weitere Informationen finden Sie unter [Einfügen oder Löschen einer Spalte (Berichts-Generator und SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dccbc-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="dccbc-113">Klicken Sie im Menü **Einfügen** auf **Bild**und dann in die Datenzeile der neuen Spalte.</span><span class="sxs-lookup"><span data-stu-id="dccbc-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="dccbc-114">Geben Sie im Dialogfeld **Bildeigenschaften** auf der Seite **Allgemein** einen Namen im Textfeld Name ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="dccbc-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="dccbc-115">(Optional) Geben Sie im Textfeld **QuickInfo** Text ein, der angezeigt wird, wenn der Benutzer in dem in HTML gerenderten Bericht auf das Bild zeigt.</span><span class="sxs-lookup"><span data-stu-id="dccbc-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="dccbc-116">Wählen Sie unter **Bildquelle auswählen**die Option **Datenbank**aus.</span><span class="sxs-lookup"><span data-stu-id="dccbc-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="dccbc-117">Wählen Sie unter **Dieses Feld verwenden**das Feld aus, das Bilder im Bericht enthält.</span><span class="sxs-lookup"><span data-stu-id="dccbc-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="dccbc-118">Wählen Sie unter **Diesen MIME-Typ verwenden** den MIME-Typ oder das Dateiformat des Bilds aus, beispielsweise BMP.</span><span class="sxs-lookup"><span data-stu-id="dccbc-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="dccbc-119">Ein Bildplatzhalter wird auf der Berichtsentwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dccbc-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccbc-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dccbc-120">See Also</span></span>  
 <span data-ttu-id="dccbc-121">[Bilder &#40;Berichts-Generator und SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dccbc-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dccbc-122">[Einbetten eines Bilds in einen Bericht &#40;Berichts-Generator und SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dccbc-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dccbc-123">[Hinzufügen eines externen Bilds &#40;Berichts-Generator und SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dccbc-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dccbc-124">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dccbc-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
