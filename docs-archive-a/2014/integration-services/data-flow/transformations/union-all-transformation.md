---
title: Transformation für UNION ALL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621085"
---
# <a name="union-all-transformation"></a><span data-ttu-id="142a9-102">Transformation für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="142a9-102">Union All Transformation</span></span>
  <span data-ttu-id="142a9-103">Die Transformation für UNION ALL kombiniert mehrere Eingaben zu einer einzigen Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="142a9-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="142a9-104">Beispielsweise können die Ausgaben von fünf verschiedenen Flatfilequellen Eingaben für die Transformation für UNION ALL sein und zu einer einzigen Ausgabe kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="142a9-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="142a9-105">Eingaben und Ausgaben</span><span class="sxs-lookup"><span data-stu-id="142a9-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="142a9-106">Die Transformationseingaben werden der Transformationsausgabe nacheinander hinzugefügt. Die Zeilen werden nicht neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="142a9-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="142a9-107">Falls das Paket eine sortierte Ausgabe erfordert, sollten Sie anstelle der Transformation für UNION ALL die Transformation für Zusammenführen verwenden.</span><span class="sxs-lookup"><span data-stu-id="142a9-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="142a9-108">Die erste Eingabe, die Sie mit der Transformation für UNION ALL verbinden, ist die Eingabe, von der die Transformation die Transformationsausgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="142a9-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="142a9-109">Die Spalten in den Eingaben, die Sie anschließend mit der Transformation verbinden, werden den Spalten in der Transformationsausgabe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="142a9-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="142a9-110">Um Eingaben zusammenzuführen, ordnen Sie Eingabespalten Ausgabespalten zu.</span><span class="sxs-lookup"><span data-stu-id="142a9-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="142a9-111">Eine Spalte von mindestens einer Eingabe muss jeder Ausgabespalte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="142a9-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="142a9-112">Für die Zuordnung von zwei Spalten müssen die Metadaten der Spalten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="142a9-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="142a9-113">Beispielsweise müssen die zugeordneten Spalten denselben Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="142a9-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="142a9-114">Wenn die zugeordneten Spalten Zeichenfolgendaten enthalten und die Ausgabespalte kürzer als die Eingabespalte ist, wird die Ausgabespalte automatisch verlängert, damit die Eingabespalten Platz haben.</span><span class="sxs-lookup"><span data-stu-id="142a9-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="142a9-115">Für Eingabespalten, die keinen Ausgabespalten zugeordnet werden, werden in den Ausgabespalten NULL-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="142a9-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="142a9-116">Diese Transformation weist mehrere Eingaben und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="142a9-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="142a9-117">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="142a9-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="142a9-118">Konfiguration der Transformation für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="142a9-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="142a9-119">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="142a9-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="142a9-120">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für UNION ALL** festlegen können, finden Sie unter [Union All Transformation Editor](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="142a9-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="142a9-121">Weitere Informationen zu den Eigenschaften, die Sie programmgesteuert festlegen können, finden Sie unter [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="142a9-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="142a9-122">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zum Festlegen von Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="142a9-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="142a9-123">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="142a9-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="142a9-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="142a9-124">Related Tasks</span></span>  
 [<span data-ttu-id="142a9-125">Zusammenführen von Daten mithilfe der Transformation für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="142a9-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
