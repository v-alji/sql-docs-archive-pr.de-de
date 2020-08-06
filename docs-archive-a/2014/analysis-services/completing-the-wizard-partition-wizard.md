---
title: Assistenten abschließen (Partitions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610248"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="f453f-102">Assistenten abschließen (Partitions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="f453f-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="f453f-103">Mithilfe der Seite **Assistenten abschließen** können Sie der Partition einen Namen zuweisen, den Aggregationsentwurf für die Partition definieren und optional die Partition nach dem Abschließen des Partitions-Assistenten bereitstellen und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f453f-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f453f-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f453f-104">Options</span></span>  
 <span data-ttu-id="f453f-105">**Name**</span><span class="sxs-lookup"><span data-stu-id="f453f-105">**Name**</span></span>  
 <span data-ttu-id="f453f-106">Geben Sie den Namen für die neue Partition ein.</span><span class="sxs-lookup"><span data-stu-id="f453f-106">Type the name for the new partition.</span></span> <span data-ttu-id="f453f-107">Wenn Sie mit mehreren Tabellen arbeiten, geben Sie den Präfix ein, der mit dem Tabellennamen kombiniert wird, um den Partitionsnamen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="f453f-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="f453f-108">**Aggregationsoptionen**</span><span class="sxs-lookup"><span data-stu-id="f453f-108">**Aggregation options**</span></span>  
 <span data-ttu-id="f453f-109">Gibt die Aggregationsoption für die Partition an.</span><span class="sxs-lookup"><span data-stu-id="f453f-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="f453f-110">In der folgenden Tabelle sind die verfügbaren Aggregationsoptionen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f453f-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="f453f-111">Option</span><span class="sxs-lookup"><span data-stu-id="f453f-111">Option</span></span>|<span data-ttu-id="f453f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f453f-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f453f-113">**Aggregationen für die Partition jetzt entwerfen**</span><span class="sxs-lookup"><span data-stu-id="f453f-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="f453f-114">Entwirft Aggregationen für die neue Partition, nachdem der Partitions-Assistent die neue Partition erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="f453f-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="f453f-115">Bei Auswahl dieser Option wird der Aggregationsentwurfs-Assistent gestartet, nachdem Sie im Partitions-Assistenten auf **Fertig stellen** geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="f453f-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="f453f-116">Weitere Informationen zum Aggregationsentwurfs-Assistenten finden Sie unter [Aggregationsentwurfs-Assistent (F1-Hilfe)](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="f453f-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="f453f-117">**Aggregationen später entwerfen**</span><span class="sxs-lookup"><span data-stu-id="f453f-117">**Design the aggregations later**</span></span>|<span data-ttu-id="f453f-118">Erstellt die Partition, ohne gleichzeitig Aggregationen zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="f453f-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="f453f-119">**Aggregationsentwurf aus einer vorhandenen Partition kopieren**</span><span class="sxs-lookup"><span data-stu-id="f453f-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="f453f-120">Kopiert den Aggregationsentwurf aus einer vorhandenen Partition der Measuregruppe in die neue Partition.</span><span class="sxs-lookup"><span data-stu-id="f453f-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="f453f-121">Wenn Sie auf diese Option klicken, ist auch die Option **Kopieren von** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f453f-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="f453f-122">Wählen Sie mithilfe der Option **Kopieren von** die Partition aus, aus der der Aggregationsentwurf kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f453f-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="f453f-123">Beachten Sie, dass Partitionen, die in Zukunft zusammengeführt werden können, dieselbe Tabellenstruktur und denselben Aggregations Entwurf aufweisen müssen.</span><span class="sxs-lookup"><span data-stu-id="f453f-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="f453f-124">Wenn Sie die neue Partition mit einer vorhandenen Partition in der Measuregruppe zusammenführen möchten, sollten Sie den Aggregationsentwurf der vorhandenen Partition in die neue Partition kopieren.</span><span class="sxs-lookup"><span data-stu-id="f453f-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="f453f-125">**Jetzt bereitstellen und verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="f453f-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="f453f-126">Wählen Sie diese Option aus, um die Partition auf der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz, die auf der Seite **Speicherorte zum Verarbeiten und Speichern** angegebenen ist, bereitzustellen und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f453f-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="f453f-127">Wenn Sie auf dieser Seite auf **Fertig stellen** klicken, führt der Assistent die Bereitstellung und Verarbeitung der Partition aus.</span><span class="sxs-lookup"><span data-stu-id="f453f-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f453f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f453f-128">See Also</span></span>  
 [<span data-ttu-id="f453f-129">Partitionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f453f-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
