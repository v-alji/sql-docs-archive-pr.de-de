---
title: Anzeigen oder Ändern von Algorithmusparametern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616819"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="0dc59-102">Anzeigen oder Ändern von Algorithmusparametern</span><span class="sxs-lookup"><span data-stu-id="0dc59-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="0dc59-103">Sie können die Parameter ändern, die mit den Algorithmen zum Erstellen von Data Mining-Modellen bereitgestellt wurden, um die Ergebnisse des Modells anzupassen.</span><span class="sxs-lookup"><span data-stu-id="0dc59-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="0dc59-104">Die in bereitgestellten Algorithmusparameter [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ändern viel mehr als nur die Eigenschaften des Modells: Sie können verwendet werden, um die Art und Weise, in der Daten verarbeitet, gruppiert und angezeigt werden, grundlegend zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0dc59-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="0dc59-105">Sie können mithilfe von Algorithmusparametern beispielsweise Folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="0dc59-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="0dc59-106">Ändern der Analysemethode, z. B. die Clustermethode.</span><span class="sxs-lookup"><span data-stu-id="0dc59-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="0dc59-107">Steuern des Funktionsauswahlverhaltens.</span><span class="sxs-lookup"><span data-stu-id="0dc59-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="0dc59-108">Angeben der Größe von Itemsets oder der Wahrscheinlichkeit von Regeln.</span><span class="sxs-lookup"><span data-stu-id="0dc59-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="0dc59-109">Steuern der Elementverzweigung und der Tiefe von Entscheidungsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="0dc59-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="0dc59-110">Angeben eines Ausgangswert oder der Größe des internen zur Modellerstellung verwendeten Zurückhaltungsdatasets.</span><span class="sxs-lookup"><span data-stu-id="0dc59-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="0dc59-111">Die für jeden Algorithmus bereitgestellten Parameter variieren stark. Eine Liste der Parameter, die Sie für jeden Algorithmus festlegen können, finden Sie in den technische Referenzthemen in folgendem Abschnitt: [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0dc59-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="0dc59-112">Ändern eines Algorithmusparameters</span><span class="sxs-lookup"><span data-stu-id="0dc59-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="0dc59-113">Klicken Sie in der Registerkarte **Miningmodelle** des Data Mining-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]mit der rechten Maustaste auf den Algorithmustyp des Miningmodells, dessen Algorithmus Sie optimieren wollen, und klicken Sie anschließend auf **Algorithmusparameter festlegen**.</span><span class="sxs-lookup"><span data-stu-id="0dc59-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="0dc59-114">Das Dialogfeld **Algorithmusparameter** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0dc59-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="0dc59-115">Legen Sie in der **Wert** -Spalte einen neuen Wert für den Algorithmus fest, den Sie ändern wollen.</span><span class="sxs-lookup"><span data-stu-id="0dc59-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="0dc59-116">Wenn Sie in die **Wert** -Spalte keinen Wert eingeben, verwendet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] den Standardparameterwert.</span><span class="sxs-lookup"><span data-stu-id="0dc59-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="0dc59-117">Die **Bereich** -Spalte beschreibt die möglichen Eingabewerte.</span><span class="sxs-lookup"><span data-stu-id="0dc59-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="0dc59-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0dc59-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="0dc59-119">Der Algorithmusparameter wird auf den neuen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0dc59-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="0dc59-120">Die Parameteränderung wird erst dann im Miningmodell widergespiegelt, wenn Sie das Modell erneut verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="0dc59-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="0dc59-121">Anzeigen der in einem vorhandenen Modell verwendeten Parameter</span><span class="sxs-lookup"><span data-stu-id="0dc59-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="0dc59-122">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ein DMX-Abfragefenster in.</span><span class="sxs-lookup"><span data-stu-id="0dc59-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="0dc59-123">Geben Sie eine ähnliche Abfrage wie die Folgende ein:</span><span class="sxs-lookup"><span data-stu-id="0dc59-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0dc59-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dc59-124">See Also</span></span>  
 [<span data-ttu-id="0dc59-125">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0dc59-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
