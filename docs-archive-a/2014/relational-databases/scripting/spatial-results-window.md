---
title: Fenster "Räumliche Ergebnisse"
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726865"
---
# <a name="spatial-results-window"></a><span data-ttu-id="95b05-102">Fenster "Räumliche Ergebnisse"</span><span class="sxs-lookup"><span data-stu-id="95b05-102">Spatial Results Window</span></span>
  <span data-ttu-id="95b05-103">Im Fenster **Räumliche Ergebnisse** werden visuelle Zuordnungstools zum Anzeigen räumlicher Daten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="95b05-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="95b05-104">Zum Anzeigen von Ergebnissen für räumliche Daten müssen die Abfrageergebnisse eine räumliche Spalte mit Geometrie- oder Geografiedaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="95b05-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95b05-105">Das Fenster **Räumliche Ergebnisse** ist nur verfügbar, wenn die Ergebnisse im Fenster **Ergebnisse** in ein Raster zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="95b05-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="95b05-106">Wenn Sie angeben, dass die Ergebnisse als Text zurückgegeben werden, ist dieses Fenster nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95b05-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="95b05-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="95b05-107">Options</span></span>  
 <span data-ttu-id="95b05-108">**Räumliche Spalte auswählen**</span><span class="sxs-lookup"><span data-stu-id="95b05-108">**Select spatial column**</span></span>  
 <span data-ttu-id="95b05-109">Geben Sie die räumliche Spalte an, die Sie in den Abfrageergebnissen in den räumlichen Spalten anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="95b05-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="95b05-110">Es kann nur jeweils eine Spalte ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="95b05-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="95b05-111">**Bezeichnungsspalte auswählen**</span><span class="sxs-lookup"><span data-stu-id="95b05-111">**Select label column**</span></span>  
 <span data-ttu-id="95b05-112">Geben Sie die nicht räumliche Spalte in den Spalten an, die in den Abfrageergebnissen zurückgegeben wurden, um die räumlichen Daten zu beschriften.</span><span class="sxs-lookup"><span data-stu-id="95b05-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="95b05-113">Es kann nur jeweils eine Spalte ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="95b05-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="95b05-114">Diese Option ist nicht verfügbar, wenn in einer Abfrage nur Instanzen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="95b05-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="95b05-115">**Projektion auswählen**</span><span class="sxs-lookup"><span data-stu-id="95b05-115">**Select projection**</span></span>  
 <span data-ttu-id="95b05-116">Sie können Geografiedaten in einer von vier Projektionen anzeigen: Equirectangular, Mercator, Robinson oder Bonne.</span><span class="sxs-lookup"><span data-stu-id="95b05-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="95b05-117">Diese Option ist für Geometriedaten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95b05-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="95b05-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="95b05-118">**Zoom**</span></span>  
 <span data-ttu-id="95b05-119">Stellen Sie die Zuordnungsanzeige auf einer exponentiellen Skala ein.</span><span class="sxs-lookup"><span data-stu-id="95b05-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="95b05-120">**Gitternetzlinien anzeigen**</span><span class="sxs-lookup"><span data-stu-id="95b05-120">**Show grid lines**</span></span>  
 <span data-ttu-id="95b05-121">Sie können Koordinatengitternetzlinien aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b05-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="95b05-122">Bei polygonen Formen wird die Bezeichnung nur angezeigt, wenn die Form groß genug ist, um den Bezeichnungstext aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="95b05-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="95b05-123">Um Bezeichnungen für kleine Formen anzuzeigen, passen Sie den Zoom an.</span><span class="sxs-lookup"><span data-stu-id="95b05-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95b05-124">Punktinstanzen können nicht bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="95b05-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b05-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95b05-125">See Also</span></span>  
 <span data-ttu-id="95b05-126">[Anzeigen räumlicher Daten im Objekt-Explorer](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="95b05-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="95b05-127">[Räumliche Daten &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95b05-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="95b05-128">[Abfrage-Editor der Datenbank-Engine &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="95b05-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="95b05-129">Abfrage- und Text-Editoren &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="95b05-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
