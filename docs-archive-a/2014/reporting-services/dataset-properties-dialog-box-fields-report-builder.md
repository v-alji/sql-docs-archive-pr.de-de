---
title: Dataseteigenschaften (Dialog Feld), Felder (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609738"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="ae8ce-102">Dataseteigenschaften (Dialogfeld), Felder (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="ae8ce-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="ae8ce-103">Wählen Sie im Dialogfeld **Dataseteigenschaften** die Option **Felder** aus, um die Feldauflistung für das Berichtsdataset zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="ae8ce-104">Die Felderliste wird automatisch aufgefüllt, Sie können jedoch mithilfe der Option **Felder** Abfragefelder und berechnete Felder hinzufügen, bearbeiten und löschen.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="ae8ce-105">Berechnete Felder werden nur bei eingebetteten Datasets unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="ae8ce-106">Weitere Informationen finden Sie unter [Erstellen von Berichten zu eingebetteten und freigegebenen Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ae8ce-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae8ce-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ae8ce-107">Options</span></span>  
 <span data-ttu-id="ae8ce-108">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="ae8ce-108">**Add**</span></span>  
 <span data-ttu-id="ae8ce-109">Fügt dem Dataset ein neues Abfragefeld oder berechnetes Feld hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="ae8ce-110">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="ae8ce-110">**Delete**</span></span>  
 <span data-ttu-id="ae8ce-111">Löscht das ausgewählte Feld aus dem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="ae8ce-112">**Feldname**</span><span class="sxs-lookup"><span data-stu-id="ae8ce-112">**Field Name**</span></span>  
 <span data-ttu-id="ae8ce-113">Geben Sie einen Namen für das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-113">Type a name for the field.</span></span> <span data-ttu-id="ae8ce-114">Der Name des Felds muss innerhalb des Datasets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="ae8ce-115">Für jedes vorhandene Feld im Dataset ist der Name voraufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="ae8ce-116">**Feldquelle**</span><span class="sxs-lookup"><span data-stu-id="ae8ce-116">**Field Source**</span></span>  
 <span data-ttu-id="ae8ce-117">Geben Sie einen Wert für das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="ae8ce-118">Bei einem berechneten Feld muss die Feldquelle dem Namen eines vorhandenen Felds, das von der Datasetabfrage abgerufen wird, oder einem Ausdruck entsprechen, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="ae8ce-119">Beispiel: Um ein Feld zu erstellen, das 10 mal den Wert im Abfragefeld Sales darstellt, verwenden Sie folgenden Ausdruck `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="ae8ce-120">Bei einem Abfragefeld muss die Feldquelle dem Namen eines vorhandenen Felds entsprechen, das von der Datasetabfrage abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="ae8ce-121">**Ausdruck (fx)**</span><span class="sxs-lookup"><span data-stu-id="ae8ce-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="ae8ce-122">Fügen Sie einen Ausdruck für das neue berechnete Feld hinzu, oder ändern Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="ae8ce-123">Diese Schaltfläche wird nur angezeigt, wenn Sie auf **Hinzufügen** klicken und **Berechnetes Feld**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae8ce-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8ce-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae8ce-124">See Also</span></span>  
 <span data-ttu-id="ae8ce-125">[Datasetfeld-Sammlung &#40;Berichts-Generator und SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ae8ce-126">[Erstellen eines freigegebenen Datasets oder eingebetteten Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ae8ce-127">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="ae8ce-128">[Dataseteigenschaften (Dialog Feld), Optionen &#40;Berichts-Generator&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="ae8ce-129">[Dataseteigenschaften (Dialog Feld), Filter &#40;Berichts-Generator&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="ae8ce-130">[Dataseteigenschaften (Dialog Feld), Parameter &#40;Berichts-Generator&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="ae8ce-131">[Dataseteigenschaften (Dialog Feld), Abfrage &#40;Berichts-Generator&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="ae8ce-132">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ce-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ae8ce-133">Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="ae8ce-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
