---
title: Löschen eines Filters aus einem Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609529"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="fea1b-102">Löschen eines Filters aus einem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="fea1b-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="fea1b-103">Wenn Sie auf einem Miningmodell einen Filter erstellen, können Sie Modelle auf einer Teilmenge der Daten in der Datenquellensicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="fea1b-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="fea1b-104">Filter sind auch für das Testen der Genauigkeit des Modells auf einer Teilmenge der ursprünglichen Daten nützlich.</span><span class="sxs-lookup"><span data-stu-id="fea1b-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="fea1b-105">Sie müssen den Filter jedoch löschen, wenn Sie wieder den vollständigen Satz von Fällen anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="fea1b-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="fea1b-106">Dieses Verfahren beschreibt, wie Sie Bedingungen in einem Filter entfernen oder den Filter vollständig löschen.</span><span class="sxs-lookup"><span data-stu-id="fea1b-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="fea1b-107">So löschen Sie eine Bedingung aus einem Filter in einem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="fea1b-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="fea1b-108">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Projektmappen-Explorer auf die Miningstruktur, die das Miningmodell enthält, auf das Sie einen Filter anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fea1b-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="fea1b-109">Klicken Sie auf die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="fea1b-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="fea1b-110">Wählen Sie das Modell aus, und klicken Sie mit der rechten Maustaste, um das Kontextmenü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fea1b-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="fea1b-111">Oder</span><span class="sxs-lookup"><span data-stu-id="fea1b-111">-or-</span></span>  
  
     <span data-ttu-id="fea1b-112">Wählen Sie das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="fea1b-112">Select the model.</span></span> <span data-ttu-id="fea1b-113">Wählen Sie im Menü **Miningmodell** die Option **Modellfilter festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="fea1b-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="fea1b-114">Klicken Sie im Dialogfeld **Modellfilter** mit der rechten Maustaste auf die Zeile im Raster, die die Bedingung enthält, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="fea1b-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="fea1b-115">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="fea1b-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="fea1b-116">So löschen Sie den Filter in einem Miningmodell im Dialogfeld 'Filter-Editor'</span><span class="sxs-lookup"><span data-stu-id="fea1b-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="fea1b-117">Klicken Sie im Dialogfeld **Filter-Editor** mit der rechten Maustaste auf eine beliebige Zeile im Raster, und wählen Sie **Alle löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fea1b-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="fea1b-118">Arbeiten mit Modellfiltern mit dem Eigenschaftenfenster</span><span class="sxs-lookup"><span data-stu-id="fea1b-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="fea1b-119">Wenn Sie den gesamten Filter löschen möchten, müssen Sie die Dialogfelder des Filter-Editors nicht öffnen.</span><span class="sxs-lookup"><span data-stu-id="fea1b-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="fea1b-120">Die Filterbedingungen, die Sie erstellt haben, sind in der `Filter`-Eigenschaft des Miningmodells verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fea1b-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fea1b-121">Sie können die Eigenschaften eines Miningmodells in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]anzeigen, aber nicht in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fea1b-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="fea1b-122">So löschen Sie den Filter in einem Miningmodell im Projektmappen-Explorer</span><span class="sxs-lookup"><span data-stu-id="fea1b-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="fea1b-123">Klicken Sie im Projektmappen-Explorer auf das Miningmodell, das den Filter enthält.</span><span class="sxs-lookup"><span data-stu-id="fea1b-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="fea1b-124">Klicken Sie im **Eigenschaften** Fenster mit der rechten Maustaste auf den Filter Text in der- `Filter` Eigenschaft, und wählen Sie **Alle auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="fea1b-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="fea1b-125">Drücken Sie die Rücktaste oder die Taste ENTF.</span><span class="sxs-lookup"><span data-stu-id="fea1b-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea1b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fea1b-126">See Also</span></span>  
 <span data-ttu-id="fea1b-127">[Drillthrough zu Falldaten aus einem Mining Modell](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="fea1b-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="fea1b-128">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="fea1b-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="fea1b-129">Filter für Miningmodelle &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fea1b-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
