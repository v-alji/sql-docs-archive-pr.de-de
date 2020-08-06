---
title: Hinzufügen eines Seitenumbruchs (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608297"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="9b182-102">Hinzufügen eines Seitenumbruchs (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b182-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9b182-103">Sie können Rechtecken, Datenbereichen oder Gruppen innerhalb von Datenbereichen einen Seitenumbruch hinzufügen, um die Datenmenge auf jeder Seite zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9b182-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="9b182-104">Durch Hinzufügen von Seitenumbrüchen kann die Leistung von veröffentlichten Berichten verbessert werden, da beim Anzeigen des Berichts nur die Elemente auf jeder Seite verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9b182-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="9b182-105">Wenn der ganze Bericht aus einer einzelnen Seite besteht, müssen alle Elemente verarbeitet werden, bevor Sie den Bericht anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9b182-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="9b182-106">So fügen Sie einen Seitenumbruch zu einem Datenbereich hinzu</span><span class="sxs-lookup"><span data-stu-id="9b182-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="9b182-107">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Handle in der Ecke des Datenbereichs, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9b182-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="9b182-108">Wählen Sie auf der Registerkarte **Allgemein** unter **Seitenumbruchoptionen**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b182-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="9b182-109">**Seitenumbruch hinzufügen vor**.</span><span class="sxs-lookup"><span data-stu-id="9b182-109">**Add a page break before**.</span></span> <span data-ttu-id="9b182-110">Aktivieren Sie diese Option, wenn Sie vor der Tabelle einen Seitenumbruch hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9b182-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="9b182-111">**Seitenumbruch hinzufügen nach**.</span><span class="sxs-lookup"><span data-stu-id="9b182-111">**Add a page break after**.</span></span> <span data-ttu-id="9b182-112">Aktivieren Sie diese Option, wenn Sie nach der Tabelle einen Seitenumbruch hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9b182-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="9b182-113">**Tabelle möglichst für eine einzelne Seite anpassen**.</span><span class="sxs-lookup"><span data-stu-id="9b182-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="9b182-114">Aktivieren Sie diese Option, wenn die Daten auf einer Seite bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="9b182-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="9b182-115">So fügen Sie einen Seitenumbruch zu einem Rechteck hinzu</span><span class="sxs-lookup"><span data-stu-id="9b182-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="9b182-116">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Rechteck, dem Sie einen Seitenumbruch hinzufügen möchten, und klicken Sie anschließend auf **Rechteckeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9b182-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="9b182-117">Wählen Sie auf der Registerkarte **Allgemein** unter **Seitenumbruchoptionen**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="9b182-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="9b182-118">**Seitenumbruch hinzufügen vor**.</span><span class="sxs-lookup"><span data-stu-id="9b182-118">**Add a page break before**.</span></span> <span data-ttu-id="9b182-119">Aktivieren Sie diese Option, wenn Sie vor dem Rechteck einen Seitenumbruch hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9b182-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="9b182-120">**Seitenumbruch hinzufügen nach**.</span><span class="sxs-lookup"><span data-stu-id="9b182-120">**Add a page break after**.</span></span> <span data-ttu-id="9b182-121">Aktivieren Sie diese Option, wenn Sie nach dem Rechteck einen Seitenumbruch hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9b182-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="9b182-122">**Rahmen an Seitenumbruch auslassen**.</span><span class="sxs-lookup"><span data-stu-id="9b182-122">**Omit border on page break**.</span></span> <span data-ttu-id="9b182-123">Aktivieren Sie diese Option, wenn für den Seitenumbruch kein Rahmen hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b182-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="9b182-124">**Inhalte nach Möglichkeit auf einer Seite zusammenhalten**.</span><span class="sxs-lookup"><span data-stu-id="9b182-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="9b182-125">Aktivieren Sie diese Option, wenn der Inhalt innerhalb des Rechtecks auf einer Seite bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="9b182-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="9b182-126">So fügen Sie einer Gruppe in einer Tabelle, Matrix oder Liste einen Seitenumbruch hinzu</span><span class="sxs-lookup"><span data-stu-id="9b182-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="9b182-127">Klicken Sie im Bereich „Gruppierung“ mit der rechten Maustaste auf eine Zeilengruppe, und klicken Sie anschließend auf **Gruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9b182-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b182-128">Seitenumbrüche werden für Spaltengruppen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9b182-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="9b182-129">Wählen Sie auf der Registerkarte **Seitenumbrüche** die Option **Zwischen den einzelnen Instanzen einer Gruppe** aus, um einen Seitenumbruch zwischen den einzelnen Instanzen einer Gruppe in der Tabelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b182-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="9b182-130">Klicken Sie wahlweise auf **Auch am Anfang einer Gruppe** oder **Auch am Ende einer Gruppe** , um festzulegen, dass ein Seitenumbruch hinzugefügt wird, wenn eine Gruppe in der Tabelle beginnt bzw. endet.</span><span class="sxs-lookup"><span data-stu-id="9b182-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b182-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b182-131">See Also</span></span>  
 <span data-ttu-id="9b182-132">[Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b182-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9b182-133">[Renderingverhalten (Berichts-Generator und SSRS)](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b182-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9b182-134">Seitenkopf- und Seitenfußzeilen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b182-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
