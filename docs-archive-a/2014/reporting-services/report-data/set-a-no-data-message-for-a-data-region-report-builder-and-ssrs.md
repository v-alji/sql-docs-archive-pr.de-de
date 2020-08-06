---
title: Festlegen einer Meldung über fehlende Daten für einen Datenbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697549"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="6f754-102">Festlegen einer Meldung über fehlende Daten für einen Datenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6f754-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6f754-103">Legen Sie die NoRowsMessage-Eigenschaft für eine Tabelle, eine Matrix oder einen Listendatenbereich, die NoDataMessage-Eigenschaft für einen Diagrammdatenbereich und die NoDataText-Eigenschaft für die Farbskala einer Karte fest, wenn Sie Text angeben möchten, der im gerenderten Bericht anstelle von Datenbereichen ohne Daten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6f754-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="6f754-104">Zur Laufzeit führt der Berichtsprozessor die Abfrage für die einzelnen Datasets in einem Bericht aus. Bei einer Datasetabfrage kann es vorkommen, dass kein Resultset zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6f754-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="6f754-105">Für Datenbereiche, die an leere Datasets gebunden sind, können Sie Text angeben, der anstelle der leeren Datenbereiche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6f754-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="6f754-106">Sie können die NoRowsMessage-Eigenschaft auch für Unterberichte festlegen, für deren Datasets zur Laufzeit keine Daten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6f754-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="6f754-107">So legen Sie die NoRowsMessage-Eigenschaft für eine Tabelle, Matrix oder Liste fest</span><span class="sxs-lookup"><span data-stu-id="6f754-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="6f754-108">Klicken Sie in der Entwurfsansicht auf die Tabelle, die Matrix, den Listendatenbereich oder auf den Unterbericht auf der Entwurfsoberfläche, um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6f754-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="6f754-109">Die Eigenschaften für das ausgewählte Element werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f754-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="6f754-110">Geben Sie im Eigenschaften Bereich den Text ein, der als Meldung im Eigenschaften Feld angezeigt werden soll `NoRowsMessage` .</span><span class="sxs-lookup"><span data-stu-id="6f754-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="6f754-111">Sie können auch in der Dropdownliste auf **Ausdruck** klicken, um das Dialogfeld **Ausdruck** zu öffnen und einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f754-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="6f754-112">So legen Sie die NoDataMessage-Eigenschaft für ein Diagramm fest</span><span class="sxs-lookup"><span data-stu-id="6f754-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="6f754-113">Klicken Sie in der Entwurfsansicht auf das Diagramm auf der Entwurfsoberfläche, um dieses auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6f754-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="6f754-114">Die Eigenschaften für das ausgewählte Element werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f754-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="6f754-115">Erweitern Sie im Bereich Eigenschaften den Knoten für `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="6f754-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="6f754-116">Geben Sie in **Beschriftung**den Text ein, der als Meldung im Eigenschaften Feld angezeigt werden soll `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="6f754-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="6f754-117">Sie können auch in der Dropdownliste auf **Ausdruck** klicken, um das Dialogfeld **Ausdruck** zu öffnen und einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f754-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="6f754-118">So legen Sie die NoRowsMessage für einen Unterbericht fest</span><span class="sxs-lookup"><span data-stu-id="6f754-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="6f754-119">Klicken Sie in der Entwurfsansicht auf den Unterbericht auf der Entwurfsoberfläche, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6f754-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="6f754-120">Die Eigenschaften für das ausgewählte Element werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f754-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="6f754-121">Geben Sie im Eigenschaften Bereich den Text ein, der als Meldung im Eigenschaften Feld angezeigt werden soll `NoRowsMessage` .</span><span class="sxs-lookup"><span data-stu-id="6f754-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="6f754-122">Sie können auch in der Dropdownliste auf **Ausdruck** klicken, um das Dialogfeld **Ausdruck** zu öffnen und einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f754-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="6f754-123">So legen Sie die NoDataText-Eigenschaft für eine Farbskala für eine Karte fest</span><span class="sxs-lookup"><span data-stu-id="6f754-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="6f754-124">Klicken Sie in der Entwurfsansicht auf die Farbskala auf der Karte, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6f754-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="6f754-125">Die Eigenschaften für das ausgewählte Element werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f754-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="6f754-126">Geben Sie im Eigenschaften Bereich in `NoDataText` den Text ein, der als Bezeichnung für Farben ohne Datenwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f754-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="6f754-127">Sie können auch in der Dropdownliste auf **Ausdruck** klicken, um das Dialogfeld **Ausdruck** zu öffnen und einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f754-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f754-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f754-128">See Also</span></span>  
 <span data-ttu-id="6f754-129">[Unterberichte &#40;Berichts-Generator und SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f754-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6f754-130">[Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f754-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6f754-131">[Diagramme &#40;Berichts-Generator und SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f754-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6f754-132">[Karten &#40;Berichts-Generator und SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f754-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6f754-133">Unterberichte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6f754-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
