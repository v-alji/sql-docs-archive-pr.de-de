---
title: Algorithmusparameter (Dialog Feld) (Mining Modell Ansicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615221"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="ba76f-102">Algorithmusparameter (Dialogfeld, Miningmodelle-Sicht)</span><span class="sxs-lookup"><span data-stu-id="ba76f-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="ba76f-103">Verwenden Sie das Dialogfeld **Algorithmusparameter** , um für das ausgewählte Modell spezifische Algorithmusparameter anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ba76f-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="ba76f-104">Wenn Sie einen Algorithmusparameter ändern, ändern Sie normalerweise auch die Ergebnisse des Miningmodells.</span><span class="sxs-lookup"><span data-stu-id="ba76f-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="ba76f-105">Die Art, in der die einzelnen Parameter sich auf die Ergebnisse auswirken, ist abhängig vom verwendeten Algorithmus und den Daten.</span><span class="sxs-lookup"><span data-stu-id="ba76f-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="ba76f-106">Weitere Informationen finden Sie unter [Anpassen von Miningmodellen und -strukturen](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ba76f-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba76f-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ba76f-107">Options</span></span>  
 <span data-ttu-id="ba76f-108">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="ba76f-108">**Parameters**</span></span>  
 <span data-ttu-id="ba76f-109">Listet die Parameter auf, die für das ausgewählte Miningmodell verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ba76f-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="ba76f-110">In der folgenden Liste werden die verfügbaren Spalten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba76f-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="ba76f-111">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba76f-111">Column</span></span>|<span data-ttu-id="ba76f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ba76f-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ba76f-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="ba76f-113">**Parameter**</span></span>|<span data-ttu-id="ba76f-114">Listet die Namen der Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="ba76f-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="ba76f-115">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ba76f-115">**Value**</span></span>|<span data-ttu-id="ba76f-116">Geben Sie einen Wert nur dann ein, wenn Sie den Standardwert des Parameters ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ba76f-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="ba76f-117">**Standard**</span><span class="sxs-lookup"><span data-stu-id="ba76f-117">**Default**</span></span>|<span data-ttu-id="ba76f-118">Listet den Standardwert des Parameters auf, den der Algorithmus verwendet, wenn Sie keinen Wert in der **Wert** -Spalte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba76f-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="ba76f-119">**Bereich**</span><span class="sxs-lookup"><span data-stu-id="ba76f-119">**Range**</span></span>|<span data-ttu-id="ba76f-120">Listet den Bereich der möglichen Werte auf, die Sie in die **Wert** -Spalte eingeben können.</span><span class="sxs-lookup"><span data-stu-id="ba76f-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="ba76f-121">Die Bereiche können einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ba76f-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="ba76f-122">Eine diskrete Liste, z. b. 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="ba76f-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="ba76f-123">Ein inklusiver Bereich, z. b. [0, 100]</span><span class="sxs-lookup"><span data-stu-id="ba76f-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="ba76f-124">Ein exklusiver Bereich, z. b. (0,...)</span><span class="sxs-lookup"><span data-stu-id="ba76f-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="ba76f-125">Eine Kombination, z. b. [0,...)</span><span class="sxs-lookup"><span data-stu-id="ba76f-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="ba76f-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba76f-126">**Description**</span></span>  
 <span data-ttu-id="ba76f-127">Beschreibt den in der **Parameter** -Liste ausgewählten Parameter.</span><span class="sxs-lookup"><span data-stu-id="ba76f-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="ba76f-128">**Add**</span><span class="sxs-lookup"><span data-stu-id="ba76f-128">**Add**</span></span>  
 <span data-ttu-id="ba76f-129">Klicken Sie auf diese Option, um der Liste zusätzliche, algorithmusspezifische Parameter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba76f-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="ba76f-130">Nachdem der Parameter hinzugefügt wurde, können Sie den richtigen Namen in die Spalte **Parameter** und einen Wert in die Spalte **Wert** eingeben.</span><span class="sxs-lookup"><span data-stu-id="ba76f-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="ba76f-131">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="ba76f-131">**Remove**</span></span>  
 <span data-ttu-id="ba76f-132">Klicken Sie auf diese Option, um einen benutzerdefinierten Parameter aus der Liste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ba76f-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="ba76f-133">Wenn Sie einen der Algorithmusstandardparameter von Analysis Services aus der Liste löschen, wird der Parameter im Modell weiterhin verwendet, jedoch mit den Standardwerten für den betreffenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="ba76f-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="ba76f-134">Der Parameter wird nicht dauerhaft gelöscht und wird beim nächsten Öffnen des Dialogfelds wieder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba76f-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba76f-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba76f-135">See Also</span></span>  
 <span data-ttu-id="ba76f-136">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ba76f-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ba76f-137">[Mining Modell Ansicht &#40;Data Mining-Modell-Designer&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ba76f-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="ba76f-138">Verschieben von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="ba76f-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
