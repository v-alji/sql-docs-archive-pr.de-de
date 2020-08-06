---
title: Daten vor dem Laden Filtern (MDS-Add-in für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699890"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a><span data-ttu-id="28ee6-102">Filtern von Daten vor dem Laden (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="28ee6-102">Filter Data before Loading (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="28ee6-103">[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] Filtern Sie in Daten, wenn Sie die Größe oder den Bereich der Daten einschränken möchten, die Sie in Excel laden.</span><span class="sxs-lookup"><span data-stu-id="28ee6-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], filter data when you want to limit the size or scope of data that you are loading into Excel.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28ee6-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="28ee6-104">Prerequisites</span></span>  
 <span data-ttu-id="28ee6-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="28ee6-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="28ee6-106">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="28ee6-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-filter-data-before-loading"></a><span data-ttu-id="28ee6-107">So filtern Sie Daten vor dem Laden</span><span class="sxs-lookup"><span data-stu-id="28ee6-107">To filter data before loading</span></span>  
  
1.  <span data-ttu-id="28ee6-108">Öffnen Sie Excel, und stellen Sie auf der Registerkarte **Masterdaten** eine Verbindung mit einem MDS-Repository her.</span><span class="sxs-lookup"><span data-stu-id="28ee6-108">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="28ee6-109">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einem MDS-Repository &#40;MDS-Add-In für Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="28ee6-109">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="28ee6-110">Wählen Sie im Bereich **Master Data Explorer** ein Modell und eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="28ee6-110">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="28ee6-111">Die Liste der Entitäten wird aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="28ee6-111">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="28ee6-112">Wenn der Bereich **Master Data Explorer** nicht sichtbar ist, klicken Sie in der Gruppe **Verbinden und Laden** auf **Explorer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="28ee6-112">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="28ee6-113">Wenn der Bereich **Master Data Explorer** deaktiviert ist, liegt dies daran, dass das vorhandene Blatt bereits von MDS verwaltete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="28ee6-113">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="28ee6-114">Um den Bereich zu aktivieren, öffnen Sie ein neues Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="28ee6-114">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="28ee6-115">Klicken Sie im Bereich **Master Data Explorer** in der Liste der Entitäten auf die Entität, die Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="28ee6-115">In the **Master Data Explorer** pane, in the list of entities, click the entity you want to filter.</span></span>  
  
4.  <span data-ttu-id="28ee6-116">Klicken Sie im Menüband in der Gruppe **Verbinden und Laden** auf **Filtern**.</span><span class="sxs-lookup"><span data-stu-id="28ee6-116">On the ribbon, in the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="28ee6-117">Vervollständigen Sie das Dialogfeld **Filtern** , indem Sie die anzuzeigenden Attribute (Spalten) auswählen, die Reihenfolge der Spalten festlegen und nach Bedarf die Daten so filtern, dass wenigere Zeilen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28ee6-117">Complete the **Filter** dialog box by selecting the attributes (columns) to display, setting the order of the columns, and if needed, filtering the data so fewer rows are returned.</span></span> <span data-ttu-id="28ee6-118">Zeigen Sie den Bereich **Zusammenfassung** an, in dem angegeben ist, wie viele Daten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28ee6-118">View the **Summary** pane for how much data will be returned.</span></span> <span data-ttu-id="28ee6-119">Weitere Informationen finden Sie unter [Filtern &#40;Dialogfeld, MDS-Add-In für Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="28ee6-119">For more information, see [Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="28ee6-120">Klicken Sie auf **Daten laden**.</span><span class="sxs-lookup"><span data-stu-id="28ee6-120">Click **Load Data**.</span></span> <span data-ttu-id="28ee6-121">Das Blatt wird mit von MDS verwalteten Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="28ee6-121">The sheet is populated with MDS-managed data.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="28ee6-122">Nur die erste eine Million von Elementen wird in Excel geladen.</span><span class="sxs-lookup"><span data-stu-id="28ee6-122">Only the first one million members are loaded into Excel.</span></span>  
    > -   <span data-ttu-id="28ee6-123">In Spalten, die eingeschränkte Listen (Domänen basierte Attribute) sind, werden nur die ersten 1000-Werte geladen.</span><span class="sxs-lookup"><span data-stu-id="28ee6-123">In columns that are constrained lists (domain-based attributes), only the first 1000 values are loaded.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="28ee6-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28ee6-124">Next Steps</span></span>  
 [<span data-ttu-id="28ee6-125">Daten aus Excel in MDS &#40;MDS-Add-in für Excel veröffentlichen&#41;</span><span class="sxs-lookup"><span data-stu-id="28ee6-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="28ee6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28ee6-126">See Also</span></span>  
 <span data-ttu-id="28ee6-127">[Daten &#40;MDS-Add-in für Excel werden geladen&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="28ee6-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="28ee6-128">[Dialog Feld "Filter" &#40;MDS-Add-in für Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="28ee6-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="28ee6-129">Neuanordnen von Spalten &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="28ee6-129">Reorder Columns &#40;MDS Add-in for Excel&#41;</span></span>](reorder-columns-mds-add-in-for-excel.md)  
  
  
