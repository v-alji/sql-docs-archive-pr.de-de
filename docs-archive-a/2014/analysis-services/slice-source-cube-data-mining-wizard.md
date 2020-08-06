---
title: Quellcube in Slice (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721802"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="2e0aa-102">Quellcube in Slices aufteilen (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="2e0aa-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="2e0aa-103">Im Dialogfeld **Quellcube in Slices aufteilen** können Sie die zum Trainieren des Modells verwendeten Daten einschränken.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="2e0aa-104">In der Regel enthält ein Cube Daten, die sich auf viele unterschiedliche Dimensionen und Attribute beziehen, z. B. auf alle Geschäfte, alle Regionen und alle Produkte.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="2e0aa-105">Da es nicht empfehlenswert ist, ein Modell für eine unbegrenzte Anzahl von Attributkombinationen zu trainieren, verwenden Sie dieses Dialogfeld, um einen bestimmten Trainingssatz für ein Modell auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="2e0aa-106">Beispielsweise könnten Sie den AdventureWorks-Cube in Slices aufteilen, um nur einen Teil der Daten zu erhalten. Die Aufteilung kann nach einer bestimmten Produktlinie oder Region bzw. nach einem bestimmten Jahr erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="2e0aa-107">Wenn Sie mit Slices und Cubes nicht vertraut sind, empfehlen wir, die folgenden Artikel zu lesen:</span><span class="sxs-lookup"><span data-stu-id="2e0aa-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="2e0aa-108">Legen Sie die Eigenschaft Partitions Slice &#40;Analysis Services fest&#41;</span><span class="sxs-lookup"><span data-stu-id="2e0aa-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="2e0aa-109">Erstellen und Verwalten einer lokalen Partition &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2e0aa-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="2e0aa-110">Beachten Sie, dass dynamische MDX-Funktionen (z.B. [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) oder [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) in der Slice-Eigenschaft für Partitionen nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="2e0aa-111">Sie müssen das Slice mit expliziten Tupel- oder Elementverweisen definieren.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="2e0aa-112">Anstatt beispielsweise [: &#40;Range&#41; &#40;MDX-&#41;](/sql/mdx/range-mdx) zum Definieren eines Bereichs zu verwenden, müssen Sie jedes Element anhand der bestimmten Jahre auflisten.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="2e0aa-113">Wenn Sie ein komplexes Slice definieren müssen, empfiehlt sich das Definieren der Tupel im Slice mithilfe eines XMLA-Alter-Skripts.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="2e0aa-114">Anschließend können Sie das Befehlszeilentool „Ascmd“ oder die SSIS- [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) verwenden, um unmittelbar vor dem Verarbeiten der Partition das Skript auszuführen und den bestimmten Satz an Elementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="2e0aa-115">**Weitere Informationen:** [Data Mining-Assistent &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Erstellen einer relationalen Miningstruktur](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="2e0aa-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="2e0aa-116">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2e0aa-116">Options</span></span>  
 <span data-ttu-id="2e0aa-117">**Dimension**</span><span class="sxs-lookup"><span data-stu-id="2e0aa-117">**Dimension**</span></span>  
 <span data-ttu-id="2e0aa-118">Wählen Sie die Dimension aus, die Sie in Slices aufteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="2e0aa-119">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="2e0aa-119">**Hierarchy**</span></span>  
 <span data-ttu-id="2e0aa-120">Wählen Sie die Hierarchie aus, die Sie in Slices aufteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="2e0aa-121">Sie können eine beliebige Hierarchieebene auswählen. Allerdings befinden sich die im Modell verwendeten Attribute immer nur auf der ausgewählten Ebene.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="2e0aa-122">Wenn Sie beispielsweise die Geography-Hierarchie verwenden und "Country" als Ebene auswählen, können Sie kein Modell erstellen, für das "City" als Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="2e0aa-123">Wenn Sie andererseits "City" als Ebene der Hierarchie auswählen, nach der die Sliceaufteilung erfolgen soll, können Sie kein Miningmodell erstellen, das auf "Country" basiert.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="2e0aa-124">**Operator**</span><span class="sxs-lookup"><span data-stu-id="2e0aa-124">**Operator**</span></span>  
 <span data-ttu-id="2e0aa-125">Wählen Sie den Operator aus, der beim Erstellen eines Sliceausdrucks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="2e0aa-126">Wenn Sie z. b. geography als Hierarchie ausgewählt haben, können Sie den Operator = auswählen und dann "Europe" als Filter eingeben, um nur die Cube-Daten für Europa zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="2e0aa-127">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="2e0aa-127">**Filter Expression**</span></span>  
 <span data-ttu-id="2e0aa-128">Geben Sie einen Ausdruck ein, der beim Filtern des Cubes nach der ausgewählten Dimension als Kriterium verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="2e0aa-129">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="2e0aa-129">**Parameters**</span></span>  
 <span data-ttu-id="2e0aa-130">Diese Option wird nicht für Data Mining-Modelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e0aa-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0aa-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e0aa-131">See Also</span></span>  
 <span data-ttu-id="2e0aa-132">[Der Assistent &#40;Data Mining-Assistenten wird abgeschlossen&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="2e0aa-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="2e0aa-133">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="2e0aa-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="2e0aa-134">Verwendungs &#40;Data Mining-Assistenten für Mining Modell Spalten angeben&#41;</span><span class="sxs-lookup"><span data-stu-id="2e0aa-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
