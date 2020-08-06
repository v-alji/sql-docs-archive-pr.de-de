---
title: Transformations-Editor für Zusammenführungsjoin Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619204"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="19d4d-102">Transformations-Editor für Zusammenführungsjoin</span><span class="sxs-lookup"><span data-stu-id="19d4d-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="19d4d-103">Im Dialogfeld **Transformations-Editor für Zusammenführungsjoin** geben Sie den Jointyp, die Joinspalten und die Ausgabespalten für zwei Eingaben an, die durch einen Join zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="19d4d-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="19d4d-104">Die Transformation für Zusammenführungsjoin erfordert als Eingabe sortierte Daten.</span><span class="sxs-lookup"><span data-stu-id="19d4d-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="19d4d-105">Weitere Informationen zu dieser wichtigen Anforderung finden Sie unter [Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="19d4d-106">Weitere Informationen zur Transformation für Zusammenführungsjoins finden Sie unter [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="19d4d-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="19d4d-107">Options</span></span>  
 <span data-ttu-id="19d4d-108">**Join-Typ**</span><span class="sxs-lookup"><span data-stu-id="19d4d-108">**Join type**</span></span>  
 <span data-ttu-id="19d4d-109">Geben Sie an, ob Sie einen inneren Join, einen linken äußeren Join oder einen vollständigen Join verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="19d4d-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="19d4d-110">**Eingaben vertauschen**</span><span class="sxs-lookup"><span data-stu-id="19d4d-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="19d4d-111">Schalten Sie die Reihenfolge der Eingaben mithilfe der Schaltfläche **Eingaben vertauschen** um.</span><span class="sxs-lookup"><span data-stu-id="19d4d-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="19d4d-112">Diese Option kann sich bei linkem äußeren Join als nützlich erweisen.</span><span class="sxs-lookup"><span data-stu-id="19d4d-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="19d4d-113">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="19d4d-113">**Input**</span></span>  
 <span data-ttu-id="19d4d-114">Wählen Sie alle Spalten, die zur zusammengeführten Ausgabe gehören sollen, in der Liste der verfügbaren Eingaben aus.</span><span class="sxs-lookup"><span data-stu-id="19d4d-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="19d4d-115">Eingaben werden in zwei separaten Tabellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19d4d-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="19d4d-116">Wählen Sie die Spalten aus, die in die Eingabe eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="19d4d-116">Select columns to include in the output.</span></span> <span data-ttu-id="19d4d-117">Verschieben Sie die Spalten, um einen Join zwischen den Tabellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19d4d-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="19d4d-118">Um einen Join zu löschen, wählen Sie diesen aus und drücken dann ENTF.</span><span class="sxs-lookup"><span data-stu-id="19d4d-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="19d4d-119">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="19d4d-119">**Input Column**</span></span>  
 <span data-ttu-id="19d4d-120">Wählen Sie eine Spalte, die in die zusammengeführte Ausgabe eingeschlossen werden soll, in der Liste der für die ausgewählte Eingabe verfügbaren Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="19d4d-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="19d4d-121">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="19d4d-121">**Output Alias**</span></span>  
 <span data-ttu-id="19d4d-122">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="19d4d-122">Type an alias for each output column.</span></span> <span data-ttu-id="19d4d-123">Standardmäßig wird der Name der Eingabespalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="19d4d-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d4d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19d4d-124">See Also</span></span>  
 <span data-ttu-id="19d4d-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="19d4d-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="19d4d-126">[Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="19d4d-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="19d4d-127">[Erweitern eines Datasets mithilfe der Transformation für Zusammenführungsjoin](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="19d4d-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="19d4d-128">[Transformation für Zusammenführen](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="19d4d-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="19d4d-129">Transformation für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="19d4d-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
