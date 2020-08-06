---
title: Dialog Feld ' Aggregations Entwurf zuweisen ' (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.copyaggregationdesign.f1
ms.assetid: 50c26cb1-c294-4f17-8b9e-435fdbd4806d
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfc4f7a0847373360a79ddda366ad7aa3f02c5de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615218"
---
# <a name="assign-aggregation-design-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d847a-102">Dialogfeld 'Aggregationsentwurf zuweisen' (Analysis Services - Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="d847a-102">Assign Aggregation Design Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d847a-103">Mithilfe des Dialogfelds **Aggregationsentwurf zuweisen** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie Aggregationsentwürfe einer oder mehreren Zielpartitionen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d847a-103">Use the **Assign Aggregation Design** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to assign aggregation designs to one or more destination partitions.</span></span> <span data-ttu-id="d847a-104">Sie können das Dialogfeld **Aggregationsentwurf zuweisen** anzeigen, indem Sie mit der rechten Maustaste im **Objekt-Explorer** auf eine Partition oder einen Aggregationsentwurf klicken und **Aggregationsentwurf zuweisen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="d847a-104">You can display the **Assign Aggregation Design** dialog box by right-clicking a partition or aggregation design in **Object Explorer** and selecting **Assign Aggregation Design**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d847a-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d847a-105">Options</span></span>  
  
|<span data-ttu-id="d847a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d847a-106">Term</span></span>|<span data-ttu-id="d847a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d847a-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d847a-108">**Aggregationsentwürfe**</span><span class="sxs-lookup"><span data-stu-id="d847a-108">**Aggregation designs**</span></span>|<span data-ttu-id="d847a-109">Wählen Sie einen Aggregationsentwurf aus, um ihn einer oder mehreren Zielpartitionen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d847a-109">Select an aggregation design to assign to one or more destination partitions.</span></span>|  
|<span data-ttu-id="d847a-110">**Zielpartitionen**</span><span class="sxs-lookup"><span data-stu-id="d847a-110">**Destination partitions**</span></span>|<span data-ttu-id="d847a-111">Wählen Sie die Partitionen aus, denen Sie den Aggregationsentwurf zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d847a-111">Select the partitions to which to assign the aggregation design.</span></span> <span data-ttu-id="d847a-112">Das folgende Raster wird verwendet, um Zielpartitionen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d847a-112">The following grid is used to specify destination partitions:</span></span><br /><br /> <span data-ttu-id="d847a-113">\<check box>: Aktivieren oder deaktivieren Sie das Kontrollkästchen in der Spaltenüberschrift, um alle aufgelisteten Partitionen als Ziel Partitionen einzuschließen oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="d847a-113">\<check box>: Select or clear the check box in the column header to include or exclude all listed partitions as destination partitions.</span></span> <span data-ttu-id="d847a-114">Aktivieren oder deaktivieren Sie das Kontrollkästchen neben einer Partition, um diese Partition als Zielpartition einzuschließen oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="d847a-114">Select or clear a check box next to a partition to include or exclude that partition as a destination partition.</span></span><br /><br /> <span data-ttu-id="d847a-115">**Partition**: zeigt den Namen der Partition an.</span><span class="sxs-lookup"><span data-stu-id="d847a-115">**Partition**: Displays the name of the partition.</span></span><br /><br /> <span data-ttu-id="d847a-116">**Quelle**: zeigt die Quell Tabelle oder Abfrage für die Partition an.</span><span class="sxs-lookup"><span data-stu-id="d847a-116">**Source**: Displays the source table or query for the partition.</span></span><br /><br /> <span data-ttu-id="d847a-117">**Aggregations Entwurf**: zeigt den Namen des vorhandenen Aggregations Entwurfs für die Partition an.</span><span class="sxs-lookup"><span data-stu-id="d847a-117">**Aggregation Design**: Displays the name of the existing aggregation design for the partition.</span></span>|  
|<span data-ttu-id="d847a-118">**Partitionen mit Aggregationsentwürfen ausblenden**</span><span class="sxs-lookup"><span data-stu-id="d847a-118">**Hide partitions with aggregation designs**</span></span>|<span data-ttu-id="d847a-119">Wählen Sie diese Option aus, um nur die Partitionen anzuzeigen, denen keine Aggregationsentwürfe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="d847a-119">Select to show only the partitions that do not have aggregation designs assigned to them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d847a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d847a-120">See Also</span></span>  
 [<span data-ttu-id="d847a-121">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="d847a-121">Aggregations and Aggregation Designs</span></span>](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
