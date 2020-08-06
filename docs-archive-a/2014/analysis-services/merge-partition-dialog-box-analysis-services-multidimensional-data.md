---
title: Mergepartition (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621240"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="30be6-102">Dialogfeld 'Mergepartition' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="30be6-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="30be6-103">Mithilfe des Dialogfelds **Mergepartition** in **SQL Server Management Studio** können Sie Partitionen für eine Measuregruppe in einem Cube zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="30be6-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="30be6-104">Sie können das Dialogfeld **Mergepartition** anzeigen, indem Sie mit der rechten Maustaste auf den Ordner „Partitionen“ oder eine Partition im **Objekt-Explorer** klicken und aus dem Kontextmenü die Option **Partitionen zusammenführen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="30be6-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30be6-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="30be6-105">Options</span></span>  
 <span data-ttu-id="30be6-106">**Server**</span><span class="sxs-lookup"><span data-stu-id="30be6-106">**Server**</span></span>  
 <span data-ttu-id="30be6-107">Wählen Sie den Namen der Analysis Services-Instanz aus, die die Zielpartition enthält.</span><span class="sxs-lookup"><span data-stu-id="30be6-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="30be6-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="30be6-108">**Name**</span></span>  
 <span data-ttu-id="30be6-109">Wählen Sie den Namen einer vorhandenen Partition aus, die als Zielpartition verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30be6-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="30be6-110">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="30be6-110">**Folder**</span></span>  
 <span data-ttu-id="30be6-111">Zeigt den Namen des Ordners an, der die Zielpartition enthält, wenn die unter Name ausgewählte Partition nicht den Standardordner für die Analysis Services-Instanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="30be6-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="30be6-112">**Quellpartitionen**</span><span class="sxs-lookup"><span data-stu-id="30be6-112">**Source Partitions**</span></span>  
 <span data-ttu-id="30be6-113">Zeigt ein Raster mit den Quellpartitionen an, die in der Zielpartition zusammengeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="30be6-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30be6-114">Nur Partitionen in derselben Measuregruppe, die dasselbe Aggregationsdesign verwenden, können zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="30be6-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="30be6-115">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="30be6-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="30be6-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="30be6-116">Column</span></span>|<span data-ttu-id="30be6-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30be6-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="30be6-118">**Merge** (Zusammenführen)</span><span class="sxs-lookup"><span data-stu-id="30be6-118">**Merge**</span></span>|<span data-ttu-id="30be6-119">Wählen Sie diese Option aus, um die Quellpartitionen in der Zielpartition zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="30be6-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="30be6-120">**Partitionsname**</span><span class="sxs-lookup"><span data-stu-id="30be6-120">**Partition Name**</span></span>|<span data-ttu-id="30be6-121">Zeigt den Namen der Quellpartition an.</span><span class="sxs-lookup"><span data-stu-id="30be6-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="30be6-122">**Zuletzt verarbeitet**</span><span class="sxs-lookup"><span data-stu-id="30be6-122">**Last Processed**</span></span>|<span data-ttu-id="30be6-123">Zeigt das Datum und die Uhrzeit der letzten Verarbeitung der Quellpartition an.</span><span class="sxs-lookup"><span data-stu-id="30be6-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30be6-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30be6-124">See Also</span></span>  
 <span data-ttu-id="30be6-125">[Partitionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="30be6-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="30be6-126">Zusammenführen von Partitionen in Analysis Services &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="30be6-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
