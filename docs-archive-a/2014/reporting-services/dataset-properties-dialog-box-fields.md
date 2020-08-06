---
title: Dataseteigenschaften (Dialog Feld), Felder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609737"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="704ea-102">Dataseteigenschaften (Dialogfeld), Felder</span><span class="sxs-lookup"><span data-stu-id="704ea-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="704ea-103">Wählen Sie im Dialogfeld **Dataseteigenschaften** die Option **Felder** aus, um die Feldauflistung für das Berichtsdataset zu ändern.</span><span class="sxs-lookup"><span data-stu-id="704ea-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="704ea-104">Die Felderliste wird automatisch aufgefüllt, Sie können jedoch mithilfe der Option **Felder** Abfragefelder und berechnete Felder hinzufügen, bearbeiten und löschen.</span><span class="sxs-lookup"><span data-stu-id="704ea-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="704ea-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="704ea-105">Options</span></span>  
 <span data-ttu-id="704ea-106">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="704ea-106">**Add**</span></span>  
 <span data-ttu-id="704ea-107">Fügt dem Dataset ein neues Abfragefeld oder berechnetes Feld hinzu.</span><span class="sxs-lookup"><span data-stu-id="704ea-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="704ea-108">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="704ea-108">**Delete**</span></span>  
 <span data-ttu-id="704ea-109">Löscht das ausgewählte Feld aus dem Dataset.</span><span class="sxs-lookup"><span data-stu-id="704ea-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="704ea-110">**Feldname**</span><span class="sxs-lookup"><span data-stu-id="704ea-110">**Field Name**</span></span>  
 <span data-ttu-id="704ea-111">Geben Sie einen Namen für das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="704ea-111">Type a name for the field.</span></span> <span data-ttu-id="704ea-112">Der Name des Felds muss innerhalb des Datasets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="704ea-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="704ea-113">Für jedes vorhandene Feld in der Datasetabfrage ist der Name bereits eingetragen.</span><span class="sxs-lookup"><span data-stu-id="704ea-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="704ea-114">**Feldquelle**</span><span class="sxs-lookup"><span data-stu-id="704ea-114">**Field Source**</span></span>  
 <span data-ttu-id="704ea-115">Geben Sie einen Wert für das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="704ea-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="704ea-116">Bei einem berechneten Feld muss die Feldquelle dem Namen eines vorhandenen Felds, das von der Datasetabfrage abgerufen wird, oder einem Ausdruck entsprechen, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="704ea-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="704ea-117">Beispiel: Um ein Feld zu erstellen, das 10 mal den Wert im Abfragefeld Sales darstellt, verwenden Sie folgenden Ausdruck `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="704ea-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="704ea-118">Bei einem Abfragefeld muss die Feldquelle dem Namen eines vorhandenen Felds entsprechen, das von der Datasetabfrage abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="704ea-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="704ea-119">**Ausdruck (fx)**</span><span class="sxs-lookup"><span data-stu-id="704ea-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="704ea-120">Fügen Sie einen Ausdruck für das berechnete Feld hinzu, oder ändern Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="704ea-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="704ea-121">Diese Schaltfläche wird nur angezeigt, wenn Sie auf **Hinzufügen** klicken und **Berechnetes Feld**auswählen.</span><span class="sxs-lookup"><span data-stu-id="704ea-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704ea-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="704ea-122">See Also</span></span>  
 <span data-ttu-id="704ea-123">[Datasetfeld-Sammlung &#40;Berichts-Generator und SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="704ea-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="704ea-124">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="704ea-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="704ea-125">Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="704ea-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
