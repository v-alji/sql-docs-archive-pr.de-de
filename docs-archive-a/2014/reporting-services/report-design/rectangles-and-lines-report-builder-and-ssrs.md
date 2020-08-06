---
title: Rechtecke und Linien (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621350"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="8e896-102">Rechtecke und Linien (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8e896-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8e896-103">Mit Rechtecken und Linien können visuelle Effekte in einem Bericht erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="8e896-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="8e896-104">Sie können Anzeigeeigenschaften für diese Berichtselemente im Abschnitt "Rahmen" der Registerkarte "Home" festlegen, und im Bereich "Eigenschaften" können weitere Eigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8e896-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="8e896-105">Sie können einem Rechteck Funktionen wie eine Hintergrundfarbe oder ein Bild, eine QuickInfo oder ein Lesezeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e896-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="8e896-106">Rechtecke und Linien als Berichtsteile</span><span class="sxs-lookup"><span data-stu-id="8e896-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="8e896-107">Sie können Rechtecke mit den darin enthaltenen Elementen getrennt von den Berichten als Berichtsteile veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8e896-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="8e896-108">Die Berichtselemente innerhalb des Rechtecks können nicht als Berichtsteile veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="8e896-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="8e896-109">Wenn Benutzer das Rechteck einem Bericht hinzufügen, erhalten sie das Rechteck und die darin enthaltenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="8e896-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a> <span data-ttu-id="8e896-110">Verwenden eines Rechtecks als Container</span><span class="sxs-lookup"><span data-stu-id="8e896-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="8e896-111">Ein Rechteck kann als Container für andere Elemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e896-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="8e896-112">Wenn Sie das Rechteck verschieben, werden gleichzeitig die darin enthaltenen Elemente verschoben.</span><span class="sxs-lookup"><span data-stu-id="8e896-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="8e896-113">Ein Element innerhalb des Rechtecks zeigt den Namen des Rechtecks in seiner **Parent** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="8e896-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="8e896-114">Weitere Informationen zum Verwenden eines Rechtecks als Container finden Sie unter [Hinzufügen eines Rechtecks oder Containers (Berichts-Generator und SSRS)](add-a-rectangle-or-container-report-builder-and-ssrs.md) und [Anzeigen derselben Daten in einer Matrix und einem Diagramm (Berichts-Generator)](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8e896-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e896-115">Ein Rechteck ist lediglich ein Container für Elemente, die Sie im Rechteck erstellen oder in das Rechteck ziehen.</span><span class="sxs-lookup"><span data-stu-id="8e896-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="8e896-116">Wenn Sie ein Rechteck um ein Element zeichnen, das bereits auf der Entwurfsoberfläche vorhanden ist, fungiert das Rechteck nicht als Container.</span><span class="sxs-lookup"><span data-stu-id="8e896-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="8e896-117">Das Rechteck wird nicht in der Parent-Eigenschaft des Elements aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="8e896-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="8e896-118">Wenn Rechtecke als Container für Berichtselemente verwendet werden, sollten Sie berücksichtigen, wie die Elemente als Ganzes beim Rendern des Berichts beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="8e896-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="8e896-119">Berichtselemente, die wiederholte Zeilen von Daten enthalten (z. B. Tabellen), werden erweitert, um die Daten aufzunehmen, die von einer Abfrage zurückgegeben werden, was die Positionierung anderer Elemente im Rechteck beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="8e896-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="8e896-120">Elemente werden von einer Tabelle nach unten verschoben, wenn sich diese Elemente unterhalb des Datenbereichs befinden.</span><span class="sxs-lookup"><span data-stu-id="8e896-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="8e896-121">Um ein Element an einem bestimmten Platz zu verankern, können Sie das Berichtselement innerhalb eines Rechtecks platzieren, dessen oberer Rand oberhalb des unteren Randes der Tabelle liegt.</span><span class="sxs-lookup"><span data-stu-id="8e896-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="8e896-122">Weitere Informationen finden Sie unter [Renderingverhalten &#40;Berichts-Generator und SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8e896-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a><span data-ttu-id="8e896-123">Hinzufügen eines Berichts Rahmens</span><span class="sxs-lookup"><span data-stu-id="8e896-123">Adding a Report Border</span></span>  
 <span data-ttu-id="8e896-124">Sie können einem Bericht ohne Hinzufügen von Linien oder Rechtecken einen Rahmen hinzufügen, indem Sie Kopfzeilen, Fußzeilen und dem Berichtshauptteil selbst Rahmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e896-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="8e896-125">Weitere Informationen finden Sie unter [Hinzufügen eines Rahmens zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8e896-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="8e896-126">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="8e896-126">How-To Topics</span></span>  
 [<span data-ttu-id="8e896-127">Hinzufügen eines Rahmens zu einem Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e896-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="8e896-128">Hinzufügen eines Rechtecks oder Containers &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e896-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="8e896-129">Hinzufügen und Ändern einer Linie &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e896-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e896-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e896-130">See Also</span></span>  
 [<span data-ttu-id="8e896-131">Hinzufügen eines Rechtecks oder Containers &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e896-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
