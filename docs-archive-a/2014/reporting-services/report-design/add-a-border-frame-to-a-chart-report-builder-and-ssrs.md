---
title: Hinzufügen eines Rahmens zu einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723486"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="08540-102">Hinzufügen eines Rahmens zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="08540-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="08540-103">Sie können die visuelle Wirkung eines Diagramms verbessern, indem Sie einen Rahmen um das Diagramm ziehen.</span><span class="sxs-lookup"><span data-stu-id="08540-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="08540-104">Sie können einen Rahmen im Dialogfeld **Diagrammeigenschaften** oder im Bereich Eigenschaften auswählen.</span><span class="sxs-lookup"><span data-stu-id="08540-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="08540-105">Die Diagrammrahmen können nicht für einen beliebigen anderen Datenbereich übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="08540-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="08540-106">So fügen Sie einem Diagramm einen Rahmen hinzu</span><span class="sxs-lookup"><span data-stu-id="08540-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="08540-107">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Diagramm, und wählen Sie **Diagrammeigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="08540-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="08540-108">Wenn Sie die **Diagrammeigenschaften**nicht sehen, zeigen Sie im Kontextmenü auf **Diagramm** , und wählen Sie **Diagrammeigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="08540-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="08540-109">Wählen Sie **Rahmen**aus, und klicken Sie auf den Typ des Rahmens, der auf das Diagramm angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08540-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="08540-110">(Optional) Wählen Sie einen Wert aus, oder geben Sie einen Ausdruck ein, der das Format des Rahmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="08540-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="08540-111">(Optional) Geben Sie die Farbe der Linie an, die um das Diagramm als Rahmen gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08540-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="08540-112">Die Liste **Linienfarbe** enthält allgemeine Farben.</span><span class="sxs-lookup"><span data-stu-id="08540-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="08540-113">Wenn Sie aus einer Liste mit weiteren Farben eine Auswahl treffen möchten, klicken Sie in der Liste auf **Weitere Farben** oder auf die Ausdrucksschaltfläche (**fx**) neben der Liste, um den **Ausdrucks-Editor** aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="08540-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="08540-114">(Optional) Geben Sie die Rahmenbreite an.</span><span class="sxs-lookup"><span data-stu-id="08540-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="08540-115">Gültige Werte sind 0,25 pt bis 20 pt.</span><span class="sxs-lookup"><span data-stu-id="08540-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="08540-116">Die Größe des Rahmens sollte zwischen 1 und 3 pt liegen, um einen optimalen visuellen Effekt zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="08540-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="08540-117">(Optional) Falls Ihr Bericht eine andere Hintergrundfarbe als Weiß enthält, sollten Sie eine Seitenfarbe mit derselben Farbe definieren.</span><span class="sxs-lookup"><span data-stu-id="08540-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="08540-118">Die Seitenfarbe ist die Hintergrundfarbe außerhalb der Rahmenlinie.</span><span class="sxs-lookup"><span data-stu-id="08540-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="08540-119">(Optional) Wenn Sie einen Rahmentyp auswählen, geben Sie ein Format und eine Farbe für den Rahmen an.</span><span class="sxs-lookup"><span data-stu-id="08540-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="08540-120">Die Liste **Framefüllfarbe** enthält allgemein verwendete Farben.</span><span class="sxs-lookup"><span data-stu-id="08540-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08540-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08540-121">See Also</span></span>  
 <span data-ttu-id="08540-122">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="08540-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="08540-123">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="08540-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="08540-124">Hinzufügen einer Abschrägung, Prägung und Struktur zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="08540-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
