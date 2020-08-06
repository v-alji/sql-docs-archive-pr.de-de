---
title: Hinzufügen neuer Modelle zur Ziel-Mailing-Struktur (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720542"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="5f4a3-102">Hinzufügen neuer Modelle zur Targeted Mailing-Struktur (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="5f4a3-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="5f4a3-103">In dieser Aufgabe definieren Sie zwei zusätzliche Modelle, indem Sie die Registerkarte **Mining Modelle** des Data Mining-Designers verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="5f4a3-104">Zum Erstellen der Modelle verwenden Sie die Algorithmen Microsoft Clustering und Microsoft Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="5f4a3-105">Diese beiden Algorithmen werden aufgrund ihrer Fähigkeit ausgewählt, einen diskreten Wert (z. B. Fahrradkauf) vorhersagen zu können.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="5f4a3-106">Weitere Informationen zu diesen Algorithmen finden Sie unter [Microsoft Clustering-Algorithmus](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) und [Microsoft Naive Bayes-Algorithmus](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md) .</span><span class="sxs-lookup"><span data-stu-id="5f4a3-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="5f4a3-107">So legen Sie ein Clustering-Miningmodell an</span><span class="sxs-lookup"><span data-stu-id="5f4a3-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="5f4a3-108">Wechseln Sie in zur Registerkarte **Mining Modelle** im Data Mining-Designer [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f4a3-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="5f4a3-109">Beachten Sie, dass im Designer zwei Spalten angezeigt werden: eine für die Mining Struktur und eine für das `TM_Decision_Tree` Mining Modell, die Sie in der vorherigen Lektion erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="5f4a3-110">Klicken Sie mit der rechten Maustaste auf die Spalte **Struktur** , und wählen Sie **Neues Mining Modell**.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="5f4a3-111">Geben Sie im Dialogfeld **Neues Mining Modell** unter **Modellname den Namen**ein `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="5f4a3-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="5f4a3-112">Wählen Sie unter **Algorithmusname den Namen** **Microsoft Clustering**aus.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="5f4a3-113">Das neue Modell wird jetzt auf der Registerkarte **Mining Modelle** im Data Mining-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="5f4a3-114">Dieses Modell, das mit dem [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering-Algorithmus erstellt wurde, gruppiert Kunden mit ähnlichen Merkmalen in Clustern und prognostiziert den Fahrradkauf für jeden Cluster.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="5f4a3-115">Obwohl Sie die Spalten Verwendung und die Eigenschaften für das neue Modell ändern können, `TM_Clustering` sind für dieses Tutorial keine Änderungen am Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="5f4a3-116">So erstellen Sie ein Naive Bayes-Miningmodell</span><span class="sxs-lookup"><span data-stu-id="5f4a3-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="5f4a3-117">Klicken Sie im Data Mining-Designer auf der Registerkarte **Mining Modelle** mit der rechten Maustaste auf die Spalte **Struktur** , und wählen Sie **Neues Mining Modell**aus.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="5f4a3-118">Geben Sie im Dialogfeld **Neues Mining Modell** unter **Modellname den Namen**ein `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="5f4a3-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="5f4a3-119">Wählen Sie unter **Algorithmusname**die Option **Microsoft Naive Bayes**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="5f4a3-120">Es wird eine Meldung angezeigt, die besagt, dass der [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes-Algorithmus die Spalten **Alter** und **jährlicher Einkommen** , die kontinuierlich sind, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="5f4a3-121">Klicken Sie auf **Ja** , um die Meldung zu bestätigen und fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="5f4a3-122">Auf der Registerkarte **Mining Modelle** des Data Mining-Designers wird ein neues Modell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="5f4a3-123">Obwohl Sie die Spalten Verwendung und-Eigenschaften für alle Modelle auf dieser Registerkarte ändern können, `TM_NaiveBayes` sind für dieses Tutorial keine Änderungen am Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f4a3-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5f4a3-124">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="5f4a3-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5f4a3-125">Verarbeiten von Modellen in der vorgesehenen Mailing-Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="5f4a3-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f4a3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f4a3-126">See Also</span></span>  
 <span data-ttu-id="5f4a3-127">[Hinzufügen von Mining Modellen zu einer Struktur &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5f4a3-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="5f4a3-128">[Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5f4a3-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="5f4a3-129">Verschieben von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="5f4a3-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
