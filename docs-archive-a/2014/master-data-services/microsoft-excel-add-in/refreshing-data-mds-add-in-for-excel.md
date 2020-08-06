---
title: Aktualisieren von Daten (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724793"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="6618f-102">Aktualisieren von Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="6618f-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="6618f-103">Aktualisieren Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]Daten, wenn Sie die aktuellsten Informationen aus dem MDS-Repository ohne Öffnen eines neuen Arbeitsblatts abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="6618f-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="6618f-104">Sie können entweder alle Zellen oder eine Auswahl von Zellen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6618f-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="6618f-105">Dies kann nützlich sein, wenn Sie Spalten mit benutzerdefinierten Formeln oder anderen Daten eingefügt haben, die nicht in MDS verwaltet werden, und Sie diese Daten beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6618f-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="6618f-106">Wann Sie von MDS verwaltete Daten aktualisieren können</span><span class="sxs-lookup"><span data-stu-id="6618f-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6618f-107">Sie können von MDS verwaltete Daten in einem aktiven Arbeitsblatt aktualisieren, wenn das aktive Arbeitsblatt bereits von MDS verwaltete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="6618f-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="6618f-108">Wenn Sie Attributwerte geändert haben oder dem Arbeitsblatt Elemente hinzugefügt haben, müssen Sie die Änderungen veröffentlichen, bevor Sie eine Aktualisierung vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="6618f-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="6618f-109">Aktualisieren einer Auswahl</span><span class="sxs-lookup"><span data-stu-id="6618f-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="6618f-110">Sie können zwischen dem Aktualisieren aller Zellen und dem Aktualisieren ausgewählter Zellen wählen.</span><span class="sxs-lookup"><span data-stu-id="6618f-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="6618f-111">Die ausgewählten Zellen müssen zusammenhängend sein.</span><span class="sxs-lookup"><span data-stu-id="6618f-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="6618f-112">Wenn ein Satz zusammenhängender Zellen ausgewählt wird, werden alle von MDS verwalteten Zellen in diesem Satz so aktualisiert, um die derzeit auf dem Server gespeicherten Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6618f-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="6618f-113">Unveränderte Zeilen und Spalten, die nicht von MDS verwaltet werden, sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="6618f-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="6618f-114">Was geschieht, wenn Sie von MDS verwaltete Daten aktualisieren</span><span class="sxs-lookup"><span data-stu-id="6618f-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6618f-115">Wenn Sie Daten im [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]aktualisieren, richtet sich die weitere Verwendung der von MDS verwalteten Daten im Blatt danach, was sich im MDS-Repository seit dem letzten Laden der Daten geändert hat.</span><span class="sxs-lookup"><span data-stu-id="6618f-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="6618f-116">Wenn dem Repository neue Elemente hinzugefügt wurden, werden sie am Ende des Arbeitsblatts hinzugefügt und grün hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="6618f-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="6618f-117">Wenn Elemente aus dem Repository gelöscht wurden, werden sie aus dem Arbeitsblatt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6618f-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="6618f-118">Wenn sich ein Attributwert im MDS-Repository geändert hat, wird der Wert im Arbeitsblatt mit dem Wert aus dem MDS-Repository aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6618f-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="6618f-119">Die Zellenfarbe ändert sich nicht.</span><span class="sxs-lookup"><span data-stu-id="6618f-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="6618f-120">Wenn nicht verwaltete Daten im aktiven Arbeitsblatt in Zeilen unter den von MDS verwalteten Daten vorhanden sind, werden die nicht verwalteten Daten möglicherweise überschrieben.</span><span class="sxs-lookup"><span data-stu-id="6618f-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="6618f-121">Dies ist der Fall, wenn Sie das Blatt und neue Zeilen mit von MDS verwalteten Daten, die mit den nicht verwalteten Daten überlappen, aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6618f-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="6618f-122">Wenn Sie eine Aktualisierung vornehmen, werden die Kommentare zu den von MDS verwalteten Zellen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6618f-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="6618f-123">Vorgehensweise: Aktualisieren der von MDS verwalteten Daten</span><span class="sxs-lookup"><span data-stu-id="6618f-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6618f-124">In der Gruppe **Verbinden und laden** auf dem Menüband hat die Schaltfläche **Aktualisieren** zwei Optionen: **Alle aktualisieren** und **Auswahl aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="6618f-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="6618f-125">Die Standardaktion der Menübandschaltfläche lautet **Alle aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="6618f-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="6618f-126">Um das ganze Blatt mit Werten vom Server zu aktualisieren, klicken Sie auf die Schaltfläche **Aktualisieren** , oder wählen Sie die Option **Alle aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6618f-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="6618f-127">Sie müssen zusammenhängende Zellen auswählen und die Option **Auswahl aktualisieren** auswählen, um nur einige der Zellen in einem Blatt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6618f-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6618f-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6618f-128">Related Tasks</span></span>  
  
|<span data-ttu-id="6618f-129">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6618f-129">Task Description</span></span>|<span data-ttu-id="6618f-130">Thema</span><span class="sxs-lookup"><span data-stu-id="6618f-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6618f-131">Herstellen einer Verbindung mit einer [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank</span><span class="sxs-lookup"><span data-stu-id="6618f-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="6618f-132">Herstellen einer Verbindung mit einem MDS-Repository &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6618f-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="6618f-133">Laden Sie MDS-Daten in Excel.</span><span class="sxs-lookup"><span data-stu-id="6618f-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="6618f-134">Laden von Daten aus MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="6618f-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="6618f-135">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6618f-135">Related Content</span></span>  
  
-   [<span data-ttu-id="6618f-136">Verbindungen &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6618f-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="6618f-137">Daten &#40;MDS-Add-in für Excel werden geladen&#41;</span><span class="sxs-lookup"><span data-stu-id="6618f-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="6618f-138">Master Data Services-Add-In für Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="6618f-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
