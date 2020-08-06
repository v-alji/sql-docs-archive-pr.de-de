---
title: Drilldownaktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621356"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="f0dc9-102">Drilldownaktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f0dc9-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f0dc9-103">Durch die Bereitstellung von Plus- oder Minussymbolen für ein Textfeld können Sie Benutzern das interaktive Aus- und Einblenden von Elementen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="f0dc9-104">Dies wird als *Drilldownaktion* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="f0dc9-105">Für eine Tabelle oder Matrix können Sie statische Zeilen und Spalten oder Zeilen und Spalten ein- und ausblenden, die Gruppen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="f0dc9-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="f0dc9-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="f0dc9-107">In dieser Abbildung klickt der Benutzer im Bericht auf die Pluszeichen (+), um Detaildaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="f0dc9-108">Sie können für eine Tabelle mit Zeilengruppen z. B. anfänglich alle Zeilen mit Ausnahme der äußeren Gruppenzusammenfassungszeile ausblenden.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="f0dc9-109">Fügen Sie für jede innere Gruppe (einschließlich der Detailgruppe) der Gruppierungszelle der enthaltenden Gruppe ein Symbol zum Erweitern/Reduzieren hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="f0dc9-110">Beim Rendern des Berichts kann der Benutzer auf das Textfeld klicken, um die Detaildaten zu erweitern und zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="f0dc9-111">Weitere Informationen finden Sie unter [Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f0dc9-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f0dc9-112">Zu diesem Zweck legen Sie die Sichtbarkeitseigenschaften eines Elements fest, das von Benutzern erweitert oder reduziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0dc9-113">Wenn Sie einen Bericht mit einer Drilldownaktion erstellen, müssen die Sichtbarkeitsinformationen nicht nur für ein einzelnes Textfeld in der Zeile oder Spalte, sondern für die auszublendende Gruppe, Zeile oder Spalte und festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="f0dc9-114">Darüber hinaus muss sich das für die Umschaltfläche verwendete Textfeld in einem enthaltenden Bereich befinden, der das aus- bzw. einzublendende Element steuert.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="f0dc9-115">Wenn Sie z. B. eine Zeile ausblenden möchten, die einer geschachtelten Gruppe zugeordnet ist, muss sich das Textfeld in einer Zeile befinden, die der übergeordneten Gruppe oder einem Element an höherer Stelle in der Kapselungshierarchie zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="f0dc9-116">Weitere Informationen zum Festlegen von Sichtbarkeitsinformationen für die Gruppe, Spalte oder Zeile finden Sie unter [Hinzufügen einer Erweiterungs- oder Reduzieraktion zu einem Element (Berichts-Generator und SSRS)](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f0dc9-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="f0dc9-117">Weitere Informationen zum Ausblenden von Berichtselementen finden Sie unter [Ausblenden eines Elements (Berichts-Generator und SSRS)](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f0dc9-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="f0dc9-118">Vergleichen von Drilldown- und Drillthroughberichten</span><span class="sxs-lookup"><span data-stu-id="f0dc9-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="f0dc9-119">In einem Drilldownbericht klickt ein Benutzer auf eine Plus- oder Minusschaltfläche, um einen Abschnitt eines Berichts zu erweitern oder zu reduzieren und so Detaildaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="f0dc9-120">In einem Drillthroughbericht klickt der Benutzer auf einen Link für einen Zusammenfassungswert, wodurch ein separater, zugehöriger Bericht zum Anzeigen von Detaildaten geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="f0dc9-121">Die Detaildaten werden nur abgerufen, wenn der Detailbericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="f0dc9-122">Drillthroughberichte erfordern normalerweise weniger Ressourcen als Drilldownberichte.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="f0dc9-123">Weitere Informationen finden Sie unter [Drillthrough, Drilldown, Unterberichte und geschachtelte Datenbereiche &#40;Berichts-Generator und SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="f0dc9-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="f0dc9-124">Unterstützung ausgeblendeter Berichtselemente durch Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="f0dc9-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="f0dc9-125">Die Umschaltfläche zum Ein- und Ausblenden von Berichtselementen wird nur von Renderingerweiterungen mit Unterstützung für Benutzerinteraktivität unterstützt, z. B. die beim Ausführen eines Berichts im Berichts-Generator und Berichts-Manager verwendete HTML-Renderingerweiterung.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="f0dc9-126">Bei anderen Renderingerweiterungen werden ausgeblendete Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="f0dc9-127">In der folgenden Liste wird die Unterstützung von Berichtselementen mit bedingter Sichtbarkeit beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f0dc9-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="f0dc9-128">Wenn Elemente in HTML ausgeblendet sind, sind sie in der HTML-Quelle nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="f0dc9-129">Die XML-Renderingerweiterung zeigt alle Berichtselemente an, unabhängig davon, ob sie ausgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="f0dc9-130">Die Excel-Renderingerweiterung zeigt ausgeblendete Zeilen und Spalten für eine Tabelle, Matrix oder Liste an und erweitert diese.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="f0dc9-131">Alle Zeilen und Spalten sind sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f0dc9-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="f0dc9-132">Weitere Informationen finden Sie unter [Renderingverhalten &#40;Berichts-Generator und SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f0dc9-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0dc9-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0dc9-133">See Also</span></span>  
 <span data-ttu-id="f0dc9-134">[Drillthrough, Drilldown, Unterberichte und geschachtelte Datenbereiche &#40;Berichts-Generator und SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="f0dc9-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="f0dc9-135">[Interaktive Sortierung, Dokumentstrukturen und Links &#40;Berichts-Generator und SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f0dc9-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f0dc9-136">Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f0dc9-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
