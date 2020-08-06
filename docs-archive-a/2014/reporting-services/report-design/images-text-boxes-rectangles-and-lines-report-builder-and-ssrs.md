---
title: Bilder, Textfelder, Rechtecke und Linien (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697541"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="47073-102">Bilder, Textfelder, Rechtecke und Linien (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="47073-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47073-103">Neben Datenbereichen wie Tabellen, Matrizen und Diagrammen werden in Berichten andere Berichtselemente wie Bilder, Textfelder und Rechtecke verwendet, um visuelle Effekte hinzuzufügen, wichtige Informationen hervorzuheben oder verwandte Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="47073-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="47073-104">Sie können die Formatierung eines Berichtselements ändern.</span><span class="sxs-lookup"><span data-stu-id="47073-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="47073-105">Sie können z. B. einen Rahmen oder eine Auffüllung hinzufügen, die ursprüngliche Sichtbarkeit oder Richtung ändern oder die genaue Größe oder Position des Elements angeben.</span><span class="sxs-lookup"><span data-stu-id="47073-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="47073-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="47073-106">In This Section</span></span>  
 [<span data-ttu-id="47073-107">Textfelder &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47073-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="47073-108">Textfelder können beliebig in einem Bericht platziert werden und können Bezeichnungen, Felder oder berechnete Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="47073-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="47073-109">Der beim Anzeigen eines Berichts in einem Textfeld anzuzeigende Wert wird mithilfe von Ausdrücken definiert.</span><span class="sxs-lookup"><span data-stu-id="47073-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="47073-110">Jede Zelle in einer Tabelle oder Matrix ist ebenfalls ein Textfeld, das auf dieselbe Weise formatiert werden kann wie eigenständige Textfelder.</span><span class="sxs-lookup"><span data-stu-id="47073-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="47073-111">Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47073-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="47073-112">**Linien** werden horizontal, vertikal oder diagonal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47073-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="47073-113">Eine Linie wird durch einen Anfangs- und einen Endpunkt definiert, und ihr können verschiedene Formateigenschaften (z. B. Breite und Farbe) zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="47073-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="47073-114">Einer Linie sind keine Daten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="47073-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="47073-115">**Rechtecke** können als grafisches Element oder als Container für andere Berichtselemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47073-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="47073-116">Als grafisches Element verfügt ein Rechteck über die gleichen Eigenschaften wie eine Zeile.</span><span class="sxs-lookup"><span data-stu-id="47073-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="47073-117">Ein Rechteck fungiert als übergeordneter Container für alle enthaltenen Berichtselemente.</span><span class="sxs-lookup"><span data-stu-id="47073-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="47073-118">Durch Platzieren von Berichtselementen in einen übergeordneten Container können Sie besser kontrollieren, wie die Elemente auf jeder Berichtsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="47073-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="47073-119">Bilder &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47073-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="47073-120">Bilder zeigen binäre Bilddaten in einem Bericht an.</span><span class="sxs-lookup"><span data-stu-id="47073-120">Images display binary image data in a report.</span></span> <span data-ttu-id="47073-121">Sie stellen die Quelle für das Bild bereit.</span><span class="sxs-lookup"><span data-stu-id="47073-121">You provide the source for the image.</span></span> <span data-ttu-id="47073-122">Bei der Quelle kann es sich um einen URL-Verweis auf ein auf einem Webserver gespeichertes Bild, einen Verweis auf eingebettete Bilddaten oder einen Verweis auf binäre Bilddaten in einer Datenbank handeln.</span><span class="sxs-lookup"><span data-stu-id="47073-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="47073-123">Berichts-Generator und Berichts-Designer unterstützen BMP-, JPEG-, GIF- und PNG-Dateien.</span><span class="sxs-lookup"><span data-stu-id="47073-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47073-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47073-124">See Also</span></span>  
 [<span data-ttu-id="47073-125">Formatieren von Berichtselementen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47073-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
