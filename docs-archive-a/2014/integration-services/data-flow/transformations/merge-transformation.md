---
title: Transformation für Zusammenführen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724014"
---
# <a name="merge-transformation"></a><span data-ttu-id="cbf6d-102">Transformation für Zusammenführen</span><span class="sxs-lookup"><span data-stu-id="cbf6d-102">Merge Transformation</span></span>
  <span data-ttu-id="cbf6d-103">Die Transformation für Zusammenführen fasst zwei sortierte Datasets zu einem Dataset zusammen.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="cbf6d-104">Die Zeilen aus jedem Dataset werden basierend auf Werten in den Schlüsselspalten in die Ausgabe eingefügt.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="cbf6d-105">Durch Einschließen der Transformation für Zusammenführen in einen Datenfluss können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="cbf6d-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="cbf6d-106">Zusammenführen von Daten aus zwei Datenquellen, wie z. B. Tabellen und Dateien.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="cbf6d-107">Erstellen komplexer Datasets durch Schachteln von Transformationen für Zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="cbf6d-108">Erneutes Zusammenführen von Zeilen nach dem Korrigieren von Fehlern in den Daten.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="cbf6d-109">Die Transformation für Zusammenführen ist mit den Transformationen für UNION ALL vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="cbf6d-110">Verwenden Sie die Transformation für UNION ALL in folgenden Situationen anstelle der Transformation für Zusammenführen:</span><span class="sxs-lookup"><span data-stu-id="cbf6d-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="cbf6d-111">Die Transformationseingaben werden nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="cbf6d-112">Die kombinierte Ausgabe muss nicht sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="cbf6d-113">Die Transformation weist mehr als zwei Eingaben auf.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="cbf6d-114">Eingabeanforderungen</span><span class="sxs-lookup"><span data-stu-id="cbf6d-114">Input Requirements</span></span>  
 <span data-ttu-id="cbf6d-115">Die Transformation für Zusammenführen erfordert als Eingabe sortierte Daten.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="cbf6d-116">Weitere Informationen zu dieser wichtigen Anforderung finden Sie unter [Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="cbf6d-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="cbf6d-117">Für die Transformation für Zusammenführung müssen die zusammengeführten Spalten außerdem in ihren Ausgaben übereinstimmende Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="cbf6d-118">Beispielsweise kann eine Spalte mit einem numerischen Datentyp nicht mit einer Spalte mit einem Zeichendatentyp zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="cbf6d-119">Wenn die Daten einen Zeichenfolgen-Datentyp aufweisen, muss die Länge der Spalte in der zweiten Eingabe kleiner oder gleich der Länge der Spalte in der ersten Eingabe sein, mit der diese zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="cbf6d-120">Im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer ordnet die Benutzeroberfläche für die Transformation für Zusammenführung automatisch Spalten mit den gleichen Metadaten zu.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="cbf6d-121">Sie können dann manuell andere Spalten mit kompatiblen Datentypen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="cbf6d-122">Diese Transformation weist zwei Eingaben und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="cbf6d-123">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="cbf6d-124">Konfiguration der Zusammenführungstransformation</span><span class="sxs-lookup"><span data-stu-id="cbf6d-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="cbf6d-125">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="cbf6d-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cbf6d-126">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Zusammenführen** festlegen können, finden Sie unter [Merge Transformation Editor](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cbf6d-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="cbf6d-127">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu anzuzeigen, die Sie programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="cbf6d-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cbf6d-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="cbf6d-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="cbf6d-129">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="cbf6d-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="cbf6d-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="cbf6d-130">Related Tasks</span></span>  
 <span data-ttu-id="cbf6d-131">Nähere Informationen zum Festlegen von Eigenschaften finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="cbf6d-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="cbf6d-132">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="cbf6d-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="cbf6d-133">Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin</span><span class="sxs-lookup"><span data-stu-id="cbf6d-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="cbf6d-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbf6d-134">See Also</span></span>  
 <span data-ttu-id="cbf6d-135">[Transformation für Zusammenführungsjoin](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="cbf6d-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="cbf6d-136">[Transformation für UNION ALL](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="cbf6d-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="cbf6d-137">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="cbf6d-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="cbf6d-138">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="cbf6d-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
