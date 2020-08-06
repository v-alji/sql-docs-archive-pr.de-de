---
title: Mining Modell Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620654"
---
# <a name="mining-model-properties"></a><span data-ttu-id="e35c5-102">Miningmodelleigenschaften</span><span class="sxs-lookup"><span data-stu-id="e35c5-102">Mining Model Properties</span></span>
  <span data-ttu-id="e35c5-103">Miningmodelle verfügen über die folgenden Arten von Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e35c5-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="e35c5-104">Von der Miningstruktur geerbte Eigenschaften, die den Daten- und Inhaltstyp der von dem Modell verwendeten Daten definieren</span><span class="sxs-lookup"><span data-stu-id="e35c5-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="e35c5-105">Eigenschaften, die sich auf den Algorithmus beziehen, der zum Erstellen des Miningmodells verwendet wurde, einschließlich sämtlicher Kundenparameter</span><span class="sxs-lookup"><span data-stu-id="e35c5-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="e35c5-106">Eigenschaften, die auf dem Modell einen Filter definieren, die zum Trainieren des Modells verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="e35c5-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="e35c5-107">Die Eigenschaften eines Miningmodells werden anfänglich definiert, wann Sie das Modell erstellen. Sie können später die meisten Eigenschaften, einschließlich der Algorithmusparameter, Filter und Spaltenverwendungseigenschaften, jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="e35c5-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="e35c5-108">Mithilfe der Registerkarte **Miningmodelle** des Data Mining-Designers oder mit AMO oder XMLA können Sie Eigenschaften für Miningmodelle anpassen.</span><span class="sxs-lookup"><span data-stu-id="e35c5-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="e35c5-109">Nach dem Ändern einer Eigenschaft müssen Sie das Modell erneut verarbeiten, damit sich die Änderungen im Modell widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="e35c5-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="e35c5-110">Eine erneute Verarbeitung ist auch dann erforderlich, wenn die Änderung nur Metadaten betrifft, wie beispielsweise das Hinzufügen eines Spaltenalias oder einer Spaltenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="e35c5-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="e35c5-111">Eigenschaften von Modellen</span><span class="sxs-lookup"><span data-stu-id="e35c5-111">Properties of Models</span></span>  
 <span data-ttu-id="e35c5-112">In der folgenden Tabelle werden die Eigenschaften, die für Miningmodelle spezifisch sind, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e35c5-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="e35c5-113">Darüber hinaus gibt es Eigenschaften, die Sie im Mining in einzelnen Spalten festlegen können.</span><span class="sxs-lookup"><span data-stu-id="e35c5-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="e35c5-114">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e35c5-114">Property</span></span>|<span data-ttu-id="e35c5-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e35c5-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e35c5-116">**Algorithmus**</span><span class="sxs-lookup"><span data-stu-id="e35c5-116">**Algorithm**</span></span>|<span data-ttu-id="e35c5-117">Legt den Algorithmustyp für das Miningmodell fest.</span><span class="sxs-lookup"><span data-stu-id="e35c5-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="e35c5-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="e35c5-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="e35c5-119">Legt Werte für die zu jedem Algorithmustyp verfügbaren Algorithmusparameter fest.</span><span class="sxs-lookup"><span data-stu-id="e35c5-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="e35c5-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="e35c5-120">**Filter**</span></span>|<span data-ttu-id="e35c5-121">Legt einen Filter fest, der auf die Daten angewendet wird, die zum Trainieren und Testen des Miningmodells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e35c5-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="e35c5-122">Die Filterdefinition wird mit dem Modell gespeichert und kann optional verwendet werden, wenn Sie Vorhersageabfragen erstellen oder die Genauigkeit des Modells testen.</span><span class="sxs-lookup"><span data-stu-id="e35c5-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="e35c5-123">Beim Trainieren des Modells ist der Modellfilter nicht optional.</span><span class="sxs-lookup"><span data-stu-id="e35c5-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="e35c5-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="e35c5-124">**Name**</span></span>|<span data-ttu-id="e35c5-125">Legt den Namen des Miningmodells fest.</span><span class="sxs-lookup"><span data-stu-id="e35c5-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="e35c5-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="e35c5-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="e35c5-127">Gibt an, ob Drillthrough für das Miningmodell aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e35c5-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="e35c5-128">Eigenschaften der Modellspalte</span><span class="sxs-lookup"><span data-stu-id="e35c5-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="e35c5-129">Sie können die folgenden für Data Mining spezifischen Eigenschaften für jede Spalte in einem Miningmodell festlegen.</span><span class="sxs-lookup"><span data-stu-id="e35c5-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="e35c5-130">Diese Eigenschaften können für jedes Miningmodell in einer Miningstruktur auf einen unterschiedlichen Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e35c5-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="e35c5-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e35c5-131">Property</span></span>|<span data-ttu-id="e35c5-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e35c5-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e35c5-133">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e35c5-133">**Description**</span></span>|<span data-ttu-id="e35c5-134">Beschreibt den Zweck der Miningspalte.</span><span class="sxs-lookup"><span data-stu-id="e35c5-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="e35c5-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="e35c5-135">**Name**</span></span>|<span data-ttu-id="e35c5-136">Legt den Namen der Miningmodellspalte fest.</span><span class="sxs-lookup"><span data-stu-id="e35c5-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="e35c5-137">Sie können einen neuen Namen eingeben, um einen Alias für die Miningmodellspalte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e35c5-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="e35c5-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="e35c5-138">**ModelingFlags**</span></span>|<span data-ttu-id="e35c5-139">Legt algorithmusspezifische Flags für die Spalte fest.</span><span class="sxs-lookup"><span data-stu-id="e35c5-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="e35c5-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="e35c5-140">**SourceColumnID**</span></span>|<span data-ttu-id="e35c5-141">Gibt den Namen der Miningstrukturspalte an, auf der die Modellspalte basiert.</span><span class="sxs-lookup"><span data-stu-id="e35c5-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="e35c5-142">Diese Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="e35c5-142">This property is read-only.</span></span>|  
|<span data-ttu-id="e35c5-143">**Verwendung**</span><span class="sxs-lookup"><span data-stu-id="e35c5-143">**Usage**</span></span>|<span data-ttu-id="e35c5-144">Legt fest, wie die Spalte vom Miningmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e35c5-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e35c5-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e35c5-145">See Also</span></span>  
 <span data-ttu-id="e35c5-146">[Mining Modell Spalten](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="e35c5-147">[Mining Strukturen &#40;Analysis Services Data Mining-&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e35c5-148">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="e35c5-149">[Ändern der Eigenschaften eines Mining Modells](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="e35c5-150">[Data Mining-Tools](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="e35c5-151">[Erstellen einer relationalen Mining Struktur](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="e35c5-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="e35c5-152">Erstellen eines Alias für eine Modellspalte</span><span class="sxs-lookup"><span data-stu-id="e35c5-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
