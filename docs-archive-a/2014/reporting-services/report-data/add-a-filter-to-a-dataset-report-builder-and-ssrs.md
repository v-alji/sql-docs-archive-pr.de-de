---
title: Hinzufügen eines Filters zu einem Dataset (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608343"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="11ebf-102">Hinzufügen eines Filters zu einem Dataset (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="11ebf-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="11ebf-103">Fügen Sie einem Dataset einen Filter hinzu, um die Daten in einem Bericht einzuschränken, nachdem die Daten aus einer externen Datenquelle abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="11ebf-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="11ebf-104">Wenn Sie einem Dataset einen Filter hinzufügen, verwenden alle Berichtsteile oder Datenbereiche nur Daten, die den Filterbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="11ebf-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="11ebf-105">Bei einem freigegebenen Dataset muss ein Filter, der für alle abhängigen Elemente gilt, Teil der freigegebenen Datasetdefinition auf dem Berichtsserver sein.</span><span class="sxs-lookup"><span data-stu-id="11ebf-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="11ebf-106">Ein Bericht oder ein Berichtsteil, der eine Instanz eines freigegebenen Datasets enthält, kann einen zusätzlichen Filter erstellen, der nur für die Instanz gilt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="11ebf-107">Um einen Filter hinzuzufügen, müssen Sie eine oder mehrere Bedingungen angeben, die Filtergleichungen sind.</span><span class="sxs-lookup"><span data-stu-id="11ebf-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="11ebf-108">Eine Filtergleichung besteht aus einem Ausdruck, der die zu filternden Daten definiert, einem Operator und dem Vergleichswert.</span><span class="sxs-lookup"><span data-stu-id="11ebf-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="11ebf-109">Der Datentyp der gefilterten Daten und des Werts muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="11ebf-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="11ebf-110">Das Filtern von aggregierten Werden für ein Dataset wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="11ebf-111">So fügen Sie einem freigegebenen Dataset einen Filter hinzu</span><span class="sxs-lookup"><span data-stu-id="11ebf-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="11ebf-112">Öffnen Sie im freigegebenen Datasetmodus ein freigegebenes Dataset.</span><span class="sxs-lookup"><span data-stu-id="11ebf-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="11ebf-113">Klicken Sie auf der Registerkarte **Home** in der Gruppe **Freigegebene Datasets** auf Datasets.</span><span class="sxs-lookup"><span data-stu-id="11ebf-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="11ebf-114">Das Dialogfeld **Dataseteigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="11ebf-115">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="11ebf-115">Click **Filters**.</span></span> <span data-ttu-id="11ebf-116">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="11ebf-117">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="11ebf-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="11ebf-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="11ebf-118">Click **Add**.</span></span> <span data-ttu-id="11ebf-119">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="11ebf-120">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="11ebf-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="11ebf-121">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="11ebf-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="11ebf-122">Wählen Sie im Listenfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="11ebf-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="11ebf-123">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11ebf-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="11ebf-124">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11ebf-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="11ebf-125">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="11ebf-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="11ebf-126">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="11ebf-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="11ebf-127">So fügen Sie einem eingebetteten Dataset oder einer freigegebenen Datasetinstanz einen Filter hinzu</span><span class="sxs-lookup"><span data-stu-id="11ebf-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="11ebf-128">Öffnen Sie einen Bericht in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="11ebf-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="11ebf-129">Klicken Sie im Fenster **Berichtsdaten** mit der rechten Maustaste auf ein Dataset, und klicken Sie dann auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="11ebf-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="11ebf-130">Das Dialogfeld **Dataseteigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="11ebf-131">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="11ebf-131">Click **Filters**.</span></span> <span data-ttu-id="11ebf-132">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="11ebf-133">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="11ebf-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="11ebf-134">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="11ebf-134">Click **Add**.</span></span> <span data-ttu-id="11ebf-135">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ebf-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="11ebf-136">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="11ebf-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="11ebf-137">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="11ebf-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="11ebf-138">Wählen Sie im Dropdownfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="11ebf-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="11ebf-139">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11ebf-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="11ebf-140">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11ebf-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="11ebf-141">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="11ebf-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="11ebf-142">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="11ebf-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11ebf-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11ebf-143">See Also</span></span>  
 <span data-ttu-id="11ebf-144">[Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="11ebf-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="11ebf-145">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="11ebf-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="11ebf-146">Hinzufügen eines Filters (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="11ebf-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
