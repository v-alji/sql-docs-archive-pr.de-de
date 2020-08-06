---
title: Erstellen und Verwalten von Measures (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616209"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="4fc80-102">Erstellen und Verwalten von Measures (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="4fc80-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="4fc80-103">Ein Measure ist eine Formel, die zur Verwendung in einem Bericht oder einer PivotTable (oder einem PivotChart) von Excel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4fc80-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="4fc80-104">Measures können auf Standardaggregationsfunktionen basieren, z. B. COUNT oder SUM, oder Sie können mit DAX eigene Formeln definieren.</span><span class="sxs-lookup"><span data-stu-id="4fc80-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="4fc80-105">In den Tasks in diesem Thema wird beschrieben, wie Measures mithilfe des measurerasters einer Tabelle erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4fc80-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="4fc80-106">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="4fc80-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="4fc80-107">So erstellen Sie ein Measure mithilfe einer Standardaggregationsformel</span><span class="sxs-lookup"><span data-stu-id="4fc80-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="4fc80-108">So erstellen Sie ein Measure mithilfe einer benutzerdefinierten Formel</span><span class="sxs-lookup"><span data-stu-id="4fc80-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="4fc80-109">So bearbeiten Sie Measure-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4fc80-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="4fc80-110">So benennen Sie ein Measure um</span><span class="sxs-lookup"><span data-stu-id="4fc80-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="4fc80-111">So löschen Sie ein Measure</span><span class="sxs-lookup"><span data-stu-id="4fc80-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="4fc80-112">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="4fc80-112">Tasks</span></span>  
 <span data-ttu-id="4fc80-113">Zum Erstellen und Verwalten von Measures verwenden Sie das measureraster einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fc80-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="4fc80-114">Sie können das Measureraster für eine Tabelle nur in der Datensicht des Modell-Designers anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4fc80-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="4fc80-115">In der Diagrammsicht können Sie keine Measures erstellen und kein Measureraster anzeigen. Vorhandene Measures können in der Diagrammsicht jedoch angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4fc80-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="4fc80-116">Um das Measureraster für eine Tabelle anzuzeigen, klicken Sie auf das Menü **Tabelle** und dann auf **Measureraster anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4fc80-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="4fc80-117">So erstellen Sie ein Measure mithilfe einer Standard Aggregations Formel</span><span class="sxs-lookup"><span data-stu-id="4fc80-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="4fc80-118">Klicken Sie auf die Spalte, für die Sie das Measure erstellen möchten, klicken Sie dann auf das Menü **Spalte** , zeigen Sie auf **AutoSumme**, und klicken Sie dann auf einen Aggregationstyp.</span><span class="sxs-lookup"><span data-stu-id="4fc80-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="4fc80-119">Das Measure wird automatisch mit einem Standardnamen erstellt, gefolgt von der Formel in der ersten Zelle im Measureraster direkt unterhalb der Spalte.</span><span class="sxs-lookup"><span data-stu-id="4fc80-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="4fc80-120">So erstellen Sie ein Measure mithilfe einer benutzerdefinierten Formel</span><span class="sxs-lookup"><span data-stu-id="4fc80-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="4fc80-121">Klicken Sie im Measureraster unter der Spalte, für die Sie das Measure erstellen möchten, auf eine Zelle, und geben Sie dann in der Bearbeitungsleiste einen Namen gefolgt von einem Doppelpunkt (:), einem Gleichheitszeichen (=) und der Formel ein.</span><span class="sxs-lookup"><span data-stu-id="4fc80-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="4fc80-122">Drücken Sie die EINGABETASTE, um die Formel zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="4fc80-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a> <span data-ttu-id="4fc80-123">So bearbeiten Sie Measureeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4fc80-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="4fc80-124">Klicken Sie im Measureraster auf ein Measure, und geben Sie dann im Fenster **Eigenschaften** einen anderen Eigenschaftswert ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="4fc80-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a> <span data-ttu-id="4fc80-125">So benennen Sie ein Measure um</span><span class="sxs-lookup"><span data-stu-id="4fc80-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="4fc80-126">Klicken Sie im Measureraster auf ein Measure, und geben Sie dann im Fenster **Eigenschaften** in **Measurename**einen neuen Namen ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4fc80-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="4fc80-127">Sie können ein Measure auch in der Bearbeitungsleiste umbenennen.</span><span class="sxs-lookup"><span data-stu-id="4fc80-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="4fc80-128">Der Measurename ist der Formel gefolgt von einem Doppelpunkt vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="4fc80-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="4fc80-129">So löschen Sie ein Measure</span><span class="sxs-lookup"><span data-stu-id="4fc80-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="4fc80-130">Klicken Sie im Measureraster mit der rechten Maustaste auf ein Measure, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4fc80-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc80-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fc80-131">See Also</span></span>  
 <span data-ttu-id="4fc80-132">[Measures &#40;tabellarischen SSAS-&#41;](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="4fc80-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="4fc80-133">[KPIs &#40;tabellarischen SSAS-&#41;](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="4fc80-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="4fc80-134">Berechnete Spalten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc80-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
