---
title: Transformations-Editor für Aggregieren (Registerkarte Erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615530"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="38cb3-102">Transformations-Editor für Aggregieren (Registerkarte Erweitert)</span><span class="sxs-lookup"><span data-stu-id="38cb3-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="38cb3-103">Mithilfe der Registerkarte **Erweitert** des Dialogfelds **Transformations-Editor für Aggregieren** können Sie Komponenteneigenschaften festlegen, Aggregationen angeben und die Eigenschaften von Eingabe- und Ausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="38cb3-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38cb3-104">Die Optionen für die Anzahl an Schlüsseln, die Schlüsselskala, die Anzahl unterschiedlicher Schlüssel sowie für unterschiedliche Schlüsselskalen gelten auf der Komponentenebene, wenn sie auf der Registerkarte **Erweitert** angegeben wurden; sie gelten auf der Ausgabeebene, wenn sie in der erweiterten Ansicht der Registerkarte **Aggregationen** angegeben wurden und auf der Spaltenebene, wenn sie in der Spaltenliste im unteren Bereich der Registerkarte **Aggregationen** angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="38cb3-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="38cb3-105">In der Transformation für das Aggregieren beziehen sich **Schlüssel** und **Schlüsselskala** auf die Anzahl der Gruppen, die als Ergebnis eines **GROUP BY** -Vorgangs erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="38cb3-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="38cb3-106">**COUNT DISTINCT-Schlüssel** und **COUNT DISTINCT-Skala** beziehen sich auf die Anzahl der unterschiedlichen Werte, die als Ergebnis eines **DISTINCT COUNT** -Vorgangs erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="38cb3-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="38cb3-107">Weitere Informationen zur Transformation für das Aggregieren finden Sie unter [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="38cb3-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="38cb3-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="38cb3-108">Options</span></span>  
 <span data-ttu-id="38cb3-109">**Schlüsselskala**</span><span class="sxs-lookup"><span data-stu-id="38cb3-109">**Keys scale**</span></span>  
 <span data-ttu-id="38cb3-110">Gibt optional die ungefähre Anzahl an Schlüsseln an, die von der Aggregation erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="38cb3-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="38cb3-111">Für die Transformation wird diese Information verwendet, um die anfängliche Cachegröße zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="38cb3-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="38cb3-112">Der Standardwert für diese Option ist **Keine Angabe**.</span><span class="sxs-lookup"><span data-stu-id="38cb3-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="38cb3-113">Wenn sowohl **Schlüsselskala** als auch **Anzahl von Schlüsseln** angegeben wurden, hat **Anzahl von Schlüsseln** Vorrang.</span><span class="sxs-lookup"><span data-stu-id="38cb3-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="38cb3-114">Wert</span><span class="sxs-lookup"><span data-stu-id="38cb3-114">Value</span></span>|<span data-ttu-id="38cb3-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38cb3-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38cb3-116">Nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-116">Unspecified</span></span>|<span data-ttu-id="38cb3-117">Die Eigenschaft **Schlüsselskala** wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="38cb3-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="38cb3-118">Niedrig</span><span class="sxs-lookup"><span data-stu-id="38cb3-118">Low</span></span>|<span data-ttu-id="38cb3-119">Die Aggregation kann ungefähr 500.000 Schlüssel schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="38cb3-120">Medium</span><span class="sxs-lookup"><span data-stu-id="38cb3-120">Medium</span></span>|<span data-ttu-id="38cb3-121">Die Aggregation kann ungefähr 5.000.000 Schlüssel schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="38cb3-122">Hoch</span><span class="sxs-lookup"><span data-stu-id="38cb3-122">High</span></span>|<span data-ttu-id="38cb3-123">Die Aggregation kann mehr als 25.000.000 Schlüssel schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="38cb3-124">**Anzahl von Schlüsseln**</span><span class="sxs-lookup"><span data-stu-id="38cb3-124">**Number of keys**</span></span>  
 <span data-ttu-id="38cb3-125">Gibt optional die genaue Anzahl an Schlüsseln an, die von der Aggregation erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="38cb3-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="38cb3-126">Für die Transformation wird diese Information verwendet, um die anfängliche Cachegröße zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="38cb3-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="38cb3-127">Wenn sowohl **Schlüsselskala** als auch **Anzahl von Schlüsseln** angegeben wurden, hat **Anzahl von Schlüsseln** Vorrang.</span><span class="sxs-lookup"><span data-stu-id="38cb3-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="38cb3-128">**Eindeutige Skala zählen**</span><span class="sxs-lookup"><span data-stu-id="38cb3-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="38cb3-129">Gibt optional die ungefähre Anzahl unterschiedlicher Werte an, die durch die Aggregation geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="38cb3-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="38cb3-130">Der Standardwert für diese Option ist **Keine Angabe**.</span><span class="sxs-lookup"><span data-stu-id="38cb3-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="38cb3-131">Wenn sowohl **COUNT DISTINCT-Skala** als auch **COUNT DISTINCT-Schlüssel** angegeben wurden, hat **COUNT DISTINCT-Schlüssel** Vorrang.</span><span class="sxs-lookup"><span data-stu-id="38cb3-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="38cb3-132">Wert</span><span class="sxs-lookup"><span data-stu-id="38cb3-132">Value</span></span>|<span data-ttu-id="38cb3-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38cb3-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38cb3-134">Nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-134">Unspecified</span></span>|<span data-ttu-id="38cb3-135">Die CountDistinctScale-Eigenschaft wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="38cb3-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="38cb3-136">Niedrig</span><span class="sxs-lookup"><span data-stu-id="38cb3-136">Low</span></span>|<span data-ttu-id="38cb3-137">Die Aggregation kann ungefähr 500.000 unterschiedliche Werte schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="38cb3-138">Medium</span><span class="sxs-lookup"><span data-stu-id="38cb3-138">Medium</span></span>|<span data-ttu-id="38cb3-139">Die Aggregation kann ungefähr 5.000.000 unterschiedliche Werte schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="38cb3-140">Hoch</span><span class="sxs-lookup"><span data-stu-id="38cb3-140">High</span></span>|<span data-ttu-id="38cb3-141">Die Aggregation kann mehr als 25.000.000 unterschiedliche Werte schreiben.</span><span class="sxs-lookup"><span data-stu-id="38cb3-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="38cb3-142">**Eindeutige Schlüssel zählen**</span><span class="sxs-lookup"><span data-stu-id="38cb3-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="38cb3-143">Gibt optional die genaue Anzahl unterschiedlicher Werte an, die durch die Aggregation geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="38cb3-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="38cb3-144">Wenn sowohl **COUNT DISTINCT-Skala** als auch **COUNT DISTINCT-Schlüssel** angegeben wurden, hat **COUNT DISTINCT-Schlüssel** Vorrang.</span><span class="sxs-lookup"><span data-stu-id="38cb3-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="38cb3-145">**Faktor für automatische Erweiterung**</span><span class="sxs-lookup"><span data-stu-id="38cb3-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="38cb3-146">Verwenden Sie einen Wert zwischen 1 und 100, um den Prozentsatz anzugeben, um den der Arbeitsspeicher während der Aggregation erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="38cb3-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="38cb3-147">Der Standardwert für diese Option ist **25 %**.</span><span class="sxs-lookup"><span data-stu-id="38cb3-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cb3-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38cb3-148">See Also</span></span>  
 <span data-ttu-id="38cb3-149">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="38cb3-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="38cb3-150">[Transformations-Editor aggregieren &#40;Registerkarte Aggregationen&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="38cb3-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="38cb3-151">Aggregieren von Werten in einem Dataset mithilfe der Transformation für das Aggregieren</span><span class="sxs-lookup"><span data-stu-id="38cb3-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
