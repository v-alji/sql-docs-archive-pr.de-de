---
title: Transformation zum Sortieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619232"
---
# <a name="sort-transformation"></a><span data-ttu-id="67423-102">Transformation zum Sortieren</span><span class="sxs-lookup"><span data-stu-id="67423-102">Sort Transformation</span></span>
  <span data-ttu-id="67423-103">Die Transformation zum Sortieren sortiert Eingabedaten in auf- oder absteigender Reihenfolge und kopiert die sortierten Daten in die Transformationsausgabe.</span><span class="sxs-lookup"><span data-stu-id="67423-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="67423-104">Auf eine Eingabe können mehrere Sortierungen angewendet werden. Jede Sortierung wird durch eine Ziffer identifiziert, die die Sortierreihenfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="67423-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="67423-105">Die Spalte mit der niedrigsten Nummer wird zuerst sortiert, anschließend die Sortierungsspalte mit der zweitniedrigsten Nummer usw.</span><span class="sxs-lookup"><span data-stu-id="67423-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="67423-106">Wenn z.B. die **CountryRegion** -Spalte die Sortierreihenfolge 1 und die **City** -Spalte die Sortierreihenfolge 2 aufweist, wird die Ausgabe nach Land/Region und anschließend nach dem Ort sortiert.</span><span class="sxs-lookup"><span data-stu-id="67423-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="67423-107">Eine positive Zahl bedeutet eine aufsteigende Sortierung, eine negative Zahl eine absteigende Sortierung.</span><span class="sxs-lookup"><span data-stu-id="67423-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="67423-108">Nicht sortierte Spalten haben die Sortierreihenfolge 0.</span><span class="sxs-lookup"><span data-stu-id="67423-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="67423-109">Spalten, die nicht für die Sortierung ausgewählt sind, werden automatisch zusammen mit den sortierten Spalten in die Transformationsausgabe kopiert.</span><span class="sxs-lookup"><span data-stu-id="67423-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="67423-110">Die Transformation zum Sortieren schließt Vergleichsoptionen ein, um zu definieren, wie die Transformation die Zeichenfolgendaten in einer Spalte behandelt.</span><span class="sxs-lookup"><span data-stu-id="67423-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="67423-111">Weitere Informationen finden Sie unter [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="67423-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67423-112">Mit der Transformation zum Sortieren können GUIDs nicht in der Reihenfolge sortiert werden, in der sie mit der ORDER BY-Klausel in Transact-SQL sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="67423-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="67423-113">Mit der Transformation zum Sortieren werden GUIDs, die mit 0-9 beginnen, vor GUIDs sortiert, die mit A-F beginnen. Mit der ORDER BY-Klausel erfolgt die Sortierung entsprechend der Implementierung in [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]anders.</span><span class="sxs-lookup"><span data-stu-id="67423-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="67423-114">Weitere Informationen finden Sie unter [ORDER BY-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="67423-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="67423-115">Mit der Transformation zum Sortieren können beim Sortieren auch doppelte Zeilen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="67423-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="67423-116">Doppelte Zeilen sind Zeilen mit denselben Sortierschlüsselwerten.</span><span class="sxs-lookup"><span data-stu-id="67423-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="67423-117">Der Sortierschlüsselwert wird basierend auf den verwendeten Optionen für Zeichenfolgenvergleiche generiert. Dies bedeutet, dass verschiedene Literalzeichenfolgen die gleichen Sortierschlüsselwerte aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="67423-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="67423-118">Die Transformation identifiziert Zeilen in den Eingabespalten mit unterschiedlichen Werten, aber mit dem gleichen Sortierschlüssel wie Duplikate.</span><span class="sxs-lookup"><span data-stu-id="67423-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="67423-119">Die Transformation zum Sortieren schließt die benutzerdefinierte Eigenschaft `MaximumThreads` ein, die beim Laden des Pakets durch einen Eigenschaftsausdruck aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="67423-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="67423-120">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="67423-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="67423-121">Diese Transformation weist je eine Eingabe und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="67423-121">This transformation has one input and one output.</span></span> <span data-ttu-id="67423-122">Fehlerausgaben werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67423-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="67423-123">Konfiguration der Transformation zum Sortieren</span><span class="sxs-lookup"><span data-stu-id="67423-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="67423-124">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="67423-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="67423-125">Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Sortierung** festlegen können, finden Sie unter [Sort Transformation Editor](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="67423-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="67423-126">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="67423-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="67423-127">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="67423-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="67423-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="67423-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="67423-129">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="67423-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="67423-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="67423-130">Related Tasks</span></span>  
 <span data-ttu-id="67423-131">Weitere Informationen zum Festlegen von Eigenschaften der Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="67423-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="67423-132">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="67423-132">Related Content</span></span>  
 <span data-ttu-id="67423-133">Beispiel, [SortDeDuplicateDelimitedString Custom SSIS-Komponente](https://go.microsoft.com/fwlink/?LinkId=220821), auf codeplex.com</span><span class="sxs-lookup"><span data-stu-id="67423-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67423-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67423-134">See Also</span></span>  
 <span data-ttu-id="67423-135">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="67423-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="67423-136">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="67423-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
