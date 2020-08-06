---
title: Dataseteigenschaften (Dialog Feld), Parameter (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10023"
ms.assetid: 3a0672ad-c969-455b-b952-585164ce1dda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ef038e7cbf113556b11af9a0e6c59aa190b2400b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622442"
---
# <a name="dataset-properties-dialog-box-parameters-report-builder"></a><span data-ttu-id="c936b-102">Dataseteigenschaften (Dialogfeld), Parameter (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="c936b-102">Dataset Properties Dialog Box, Parameters (Report Builder)</span></span>
  <span data-ttu-id="c936b-103">Wählen Sie im Dialogfeld **Dataseteigenschaften** die Option **Parameter** aus, um Abfrage Parameter hinzuzufügen, zu ändern und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c936b-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters.</span></span>  
  
 <span data-ttu-id="c936b-104">Bei eingebetteten Datasets gelten die Optionen für das Dataset in der Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="c936b-104">For an embedded dataset, options apply to the dataset in the report definition.</span></span>  
  
 <span data-ttu-id="c936b-105">Bei freigegebenen Datasets gelten die Optionen für die Definition des freigegebenen Datasets auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="c936b-105">For a shared dataset, options apply to the shared dataset definition on the report server.</span></span>  
  
 <span data-ttu-id="c936b-106">Weitere Informationen finden Sie unter [Eingebettete und freigegebene Datasets (Berichts-Generator und SSRS)](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c936b-106">For more information, see [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c936b-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c936b-107">Options</span></span>  
 <span data-ttu-id="c936b-108">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="c936b-108">**Add**</span></span>  
 <span data-ttu-id="c936b-109">Fügt der Liste einen neuen Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="c936b-109">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="c936b-110">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="c936b-110">**Delete**</span></span>  
 <span data-ttu-id="c936b-111">Entfernt den ausgewählten Parameter aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="c936b-111">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="c936b-112">**Pfeil nach oben**</span><span class="sxs-lookup"><span data-stu-id="c936b-112">**Up arrow**</span></span>  
 <span data-ttu-id="c936b-113">Verschiebt den ausgewählten Parameter in der Liste nach oben.</span><span class="sxs-lookup"><span data-stu-id="c936b-113">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="c936b-114">**Pfeil nach unten**</span><span class="sxs-lookup"><span data-stu-id="c936b-114">**Down arrow**</span></span>  
 <span data-ttu-id="c936b-115">Verschiebt den ausgewählten Parameter in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="c936b-115">Move the selected parameter down in the list.</span></span>  
  
 <span data-ttu-id="c936b-116">**Parametername**</span><span class="sxs-lookup"><span data-stu-id="c936b-116">**Parameter name**</span></span>  
 <span data-ttu-id="c936b-117">Geben Sie auf der Registerkarte **Abfrage** des Dialogfelds **Dataseteigenschaften** den Namen eines Abfrageparameters ein, den Sie zum Dataset hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="c936b-117">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="c936b-118">**Parameterwert**</span><span class="sxs-lookup"><span data-stu-id="c936b-118">**Parameter value**</span></span>  
 <span data-ttu-id="c936b-119">Nur für eingebettete Datasets.</span><span class="sxs-lookup"><span data-stu-id="c936b-119">For embedded datasets only.</span></span>  
  
 <span data-ttu-id="c936b-120">Geben Sie einen Wert für den Abfrageparameter ein.</span><span class="sxs-lookup"><span data-stu-id="c936b-120">Enter a value for the query parameter.</span></span> <span data-ttu-id="c936b-121">Dies kann ein statischer Wert sein oder ein Ausdruck, der sich auf ein Objekt innerhalb des Berichts bezieht. Der Ausdruck darf sich jedoch nicht auf Berichtselemente oder Felder beziehen.</span><span class="sxs-lookup"><span data-stu-id="c936b-121">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="c936b-122">Standardmäßig enthält **Wert** einen Ausdruck, der auf einen Berichtsparameter verweist.</span><span class="sxs-lookup"><span data-stu-id="c936b-122">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="c936b-123">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="c936b-123">**Default value**</span></span>  
 <span data-ttu-id="c936b-124">Nur für freigegebene Datasets.</span><span class="sxs-lookup"><span data-stu-id="c936b-124">For shared datasets only.</span></span>  
  
 <span data-ttu-id="c936b-125">Aktivieren Sie das Kontrollkästchen, um einen Standardwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c936b-125">Select the check box to specify a default value.</span></span>  
  
 <span data-ttu-id="c936b-126">Geben Sie einen Standardwert ein.</span><span class="sxs-lookup"><span data-stu-id="c936b-126">Enter a default value.</span></span> <span data-ttu-id="c936b-127">Dies kann ein statischer Wert oder ein Ausdruck sein, der auf ein Objekt innerhalb des Berichts verweist.</span><span class="sxs-lookup"><span data-stu-id="c936b-127">This can be a static value or an expression that refers to an object within the report.</span></span> <span data-ttu-id="c936b-128">Der Ausdruck kann nicht auf Berichtselemente, Berichtsparameter oder Felder verweisen.</span><span class="sxs-lookup"><span data-stu-id="c936b-128">The expression cannot refer to report items, report parameters, or fields.</span></span>  
  
 <span data-ttu-id="c936b-129">Um ein Leerzeichen anzugeben, lassen Sie das Textfeld leer.</span><span class="sxs-lookup"><span data-stu-id="c936b-129">To specify a blank, leave the text box empty.</span></span>  
  
 <span data-ttu-id="c936b-130">Um NULL anzugeben, aktivieren Sie die Option NULL zulassen.</span><span class="sxs-lookup"><span data-stu-id="c936b-130">To specify a null, select the Nullable option.</span></span>  
  
 <span data-ttu-id="c936b-131">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="c936b-131">**Read Only**</span></span>  
 <span data-ttu-id="c936b-132">Nur für freigegebene Datasets.</span><span class="sxs-lookup"><span data-stu-id="c936b-132">For shared datasets only.</span></span>  
  
 <span data-ttu-id="c936b-133">Aktivieren Sie diese Option, um diesen Parameter in der freigegebenen Datasetdefinition als schreibgeschützt zu markieren.</span><span class="sxs-lookup"><span data-stu-id="c936b-133">Select this option to mark this parameter read only in the shared dataset definition.</span></span> <span data-ttu-id="c936b-134">Wenn das freigegebene Dataset einem Bericht hinzugefügt wird, wird der Parameter nicht in den Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c936b-134">When the shared dataset is added to a report, the parameter does not appear in the properties.</span></span> <span data-ttu-id="c936b-135">Wenn das freigegebene Dataset auf dem Berichtsserver zwischengespeichert wird, kann der Wert nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c936b-135">When the shared dataset is cached on the report server, the value cannot be changed.</span></span>  
  
 <span data-ttu-id="c936b-136">**NULL zulassen**</span><span class="sxs-lookup"><span data-stu-id="c936b-136">**Nullable**</span></span>  
 <span data-ttu-id="c936b-137">Nur für freigegebene Datasets.</span><span class="sxs-lookup"><span data-stu-id="c936b-137">For shared datasets only.</span></span>  
  
 <span data-ttu-id="c936b-138">Aktivieren Sie diese Option, um NULL-Werte zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="c936b-138">Select this option to allow a null value.</span></span>  
  
 <span data-ttu-id="c936b-139">**In Abfrage auslassen**</span><span class="sxs-lookup"><span data-stu-id="c936b-139">**Omit From Query**</span></span>  
 <span data-ttu-id="c936b-140">Nur für freigegebene Datasets.</span><span class="sxs-lookup"><span data-stu-id="c936b-140">For shared datasets only.</span></span>  
  
 <span data-ttu-id="c936b-141">Aktivieren Sie diese Option, wenn ein Verweis auf einen Berichtsparameter sich in einem Ausdruck im freigegebenen Datasetfilter befindet und nicht in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="c936b-141">Select this option when a reference to a report parameter is in an expression in the shared dataset filter and not in the query.</span></span> <span data-ttu-id="c936b-142">Wenn Sie diese Option aktivieren, müssen Sie keinen Standardwert für diesen Parameter angeben, wenn die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c936b-142">When you select this option, you do not need to specify a default value for this parameter when the query runs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c936b-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c936b-143">See Also</span></span>  
 <span data-ttu-id="c936b-144">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-144">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="c936b-145">[Dataseteigenschaften (Dialog Feld), Abfrage &#40;Berichts-Generator&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-145">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="c936b-146">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-146">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c936b-147">[Tutorial: Hinzufügen eines Parameters zu einem Bericht &#40;Berichts-Generator&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-147">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="c936b-148">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-148">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="c936b-149">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-149">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c936b-150">[Abfrage-Designer &#40;Berichts-Generator&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-150">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="c936b-151">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c936b-151">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c936b-152">Erstellen eines freigegebenen Datasets oder eingebetteten Datasets &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c936b-152">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
  
