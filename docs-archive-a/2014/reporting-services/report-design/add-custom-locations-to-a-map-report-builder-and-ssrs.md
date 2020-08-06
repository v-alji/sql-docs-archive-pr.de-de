---
title: Hinzufügen benutzerdefinierter Orte zu einer Karte (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722565"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="40001-102">Hinzufügen benutzerdefinierter Orte zu einer Karte (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="40001-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="40001-103">Nachdem Sie einem Bericht eine Karte hinzugefügt haben, können Sie eigene Punktpositionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40001-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="40001-104">Die Anzeigeeigenschaften für alle Punkte in einer Ebene werden durch Festlegen von Optionen für die Punkteigenschaften für die Ebene gesteuert.</span><span class="sxs-lookup"><span data-stu-id="40001-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="40001-105">Für einen ausgewählten eingebetteten Punkt können Sie die Anzeigeeigenschaften überschreiben.</span><span class="sxs-lookup"><span data-stu-id="40001-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40001-106">Wenn Sie die Ebenenanzeigeeigenschaften für den eingebetteten Punkt überschreiben, sind die Änderungen, die Sie vornehmen, nicht umkehrbar.</span><span class="sxs-lookup"><span data-stu-id="40001-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="40001-107">Weitere Informationen finden Sie unter [Unterschiedliche Polygon-, Linien- und Punktanzeigen bei der Verwendung von Regeln und analytischen Daten &#40;Berichts-Generator und SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="40001-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="40001-108">So fügen Sie eine Punktebene hinzu</span><span class="sxs-lookup"><span data-stu-id="40001-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="40001-109">Klicken Sie auf der Berichtsentwurfsoberfläche auf die Karte, um sie auszuwählen und den Kartenbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40001-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="40001-110">Klicken Sie auf der Symbolleiste auf **Ebene hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="40001-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="40001-111">Klicken Sie in der Dropdownliste auf **Punktebene hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="40001-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="40001-112">Der Karte wird eine Punktebene ohne Punkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="40001-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="40001-113">Standardmäßig ist die Punktebene für eingebettete Punkte bereit.</span><span class="sxs-lookup"><span data-stu-id="40001-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="40001-114">So fügen Sie einen benutzerdefinierten Punkt hinzu</span><span class="sxs-lookup"><span data-stu-id="40001-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="40001-115">Klicken Sie auf der Berichtsentwurfsoberfläche auf die Karte, um sie auszuwählen und den Kartenbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40001-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="40001-116">Klicken Sie im Kartenbereich mit der rechten Maustaste auf eine Punktebene, die den Typ **Eingebettet**aufweist, und klicken Sie dann auf **Punkt hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="40001-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="40001-117">Der Cursor verändert sich zu einem Fadenkreuz.</span><span class="sxs-lookup"><span data-stu-id="40001-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="40001-118">Um einen Punkt hinzuzufügen, klicken Sie auf einen Ort auf der Karte.</span><span class="sxs-lookup"><span data-stu-id="40001-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="40001-119">Der ausgewählten Ebene wird an der Position, an der Sie klicken, ein eingebetteter Punkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="40001-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="40001-120">So passen Sie die Anzeige für einen eingebetteten Punkt an</span><span class="sxs-lookup"><span data-stu-id="40001-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="40001-121">Klicken Sie mit der rechten Maustaste auf den Punkt, und klicken Sie dann auf **Punkteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="40001-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="40001-122">Das Dialogfeld **Eigenschaften für eingebettete Punkte der Karte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="40001-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="40001-123">Klicken Sie auf **Punktoptionen für diese Ebene überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="40001-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="40001-124">Mehrere Eigenschaftenseiten werden im linken Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40001-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="40001-125">Klicken Sie auf die Seiten, und legen Sie die Anzeigeeigenschaften fest, die Sie auf diesen Punkt anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="40001-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40001-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40001-126">See Also</span></span>  
 <span data-ttu-id="40001-127">[Karten &#40;Berichts-Generator und SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40001-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="40001-128">Unterschiedliche Polygon-, Linien- und Punktanzeigen bei der Verwendung von Regeln und analytischen Daten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="40001-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
