---
title: Verarbeiten von Modellen in der Ziel-Mailing Struktur (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699056"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="ed6d0-102">Verarbeiten von Modellen in der Targeted Mailing-Struktur (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="ed6d0-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ed6d0-103">Bevor Sie die erstellten Miningmodelle durchsuchen und verwenden können, müssen Sie das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Projekt bereitstellen und die Miningstruktur und die Miningmodelle verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="ed6d0-104">Bei der Bereitstellung wird das Projekt an einen *Server gesendet,* und es werden alle Objekte in diesem Projekt auf dem Server erstellt.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="ed6d0-105">Bei der *Verarbeitung* werden- [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Objekte mit Daten aus relationalen Datenquellen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="ed6d0-106">Modelle können erst dann verwendet werden, wenn sie bereitgestellt und verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="ed6d0-107">Wenn Sie Änderungen am Modell vornehmen, z. B. neue Daten hinzufügen, müssen Sie die Modelle darüber hinaus erneut bereitstellen und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="ed6d0-108">Sicherstellen von Konsistenz mit HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="ed6d0-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="ed6d0-109">Wenn Sie ein Projekt bereitstellen und die Struktur sowie die Modelle verarbeiten, werden die einzelnen Zeilen in der Datenstruktur auf Grundlage eines numerischen Ausgangswerts entweder dem Trainings- oder Testsatz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="ed6d0-110">Der numerische Ausgangswert wird in der Regel auf der Basis von Attributen der Datenstruktur berechnet.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="ed6d0-111">Bei einer Änderung der Modellaspekte würde sich der Ausgangswert jedoch ändern und zu leicht abweichenden Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="ed6d0-112">Um sicherzustellen, dass Ihre Ergebnisse den hier beschriebenen entsprechen, weisen wir daher willkürlich *einen festgehaltenen* Ausgangswert von zurück `12` .</span><span class="sxs-lookup"><span data-stu-id="ed6d0-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="ed6d0-113">Mit dem Ausgangswert zurückgehaltener Daten wird der Stichprobenalgorithmus initialisiert, und es wird sichergestellt, dass die Daten für alle Miningstrukturen und deren Modelle weitestgehend auf die gleiche Weise partitioniert werden.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="ed6d0-114">Dieser Wert hat keinen Einfluss auf die Anzahl der Fälle im Trainingssatz, sondern stellt lediglich sicher, dass bei jeder Modellerstellung dieselbe Partitionierungsmethode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="ed6d0-115">Weitere Informationen zum Ausgangswert für zurück gehaltene Daten finden Sie unter [Trainings-und Test Datasets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ed6d0-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="ed6d0-116">So legen Sie den Ausgangswert zurückgehaltener Daten fest</span><span class="sxs-lookup"><span data-stu-id="ed6d0-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="ed6d0-117">Klicken Sie im Data Mining-Designer von auf die Registerkarte **Mining Struktur** oder auf die Registerkarte **Mining Modelle** [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed6d0-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="ed6d0-118">Die **Ziel-Mailing-Mining Struktur** wird im **Eigenschaften** Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="ed6d0-119">Stellen Sie sicher, dass der Bereich **Eigenschaften** durch Drücken von **F4**geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="ed6d0-120">Stellen Sie sicher, dass **CacheMode** auf **KeepTrainingCases**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="ed6d0-121">Geben Sie `12` für **HoldoutSeed**ein.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="ed6d0-122">Bereitstellen und Verarbeiten der Modelle</span><span class="sxs-lookup"><span data-stu-id="ed6d0-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="ed6d0-123">Im Data Mining-Designer können Sie entscheiden, welche Objekte verarbeitet werden sollen, abhängig vom Umfang der Änderungen, die Sie am Modell oder den zugrunde liegenden Daten vorgenommen haben:</span><span class="sxs-lookup"><span data-stu-id="ed6d0-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="ed6d0-124">Bei dieser Aufgabe verarbeiten Sie die Struktur und alle Modelle gleichzeitig, weil die Daten und Modelle neu sind.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="ed6d0-125">So stellen Sie das Projekt bereit und verarbeiten alle Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="ed6d0-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="ed6d0-126">Wählen Sie im Menü **Mining Modell** die Option **Mining Struktur und alle Modelle verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="ed6d0-127">Falls Sie Änderungen an der Miningstruktur vorgenommen haben, werden Sie aufgefordert, das Projekt zu erstellen und bereitzustellen, bevor Sie die Modelle verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="ed6d0-128">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="ed6d0-129">Klicken Sie im Dialogfeld **Verarbeitungs Mining Struktur-Ziel** senden auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ed6d0-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="ed6d0-130">Das Dialogfeld **Verarbeitungsstatus** wird geöffnet und zeigt detaillierte Informationen zur Verarbeitung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="ed6d0-131">Die Modell Verarbeitung kann je nach Computer einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ed6d0-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="ed6d0-132">Klicken Sie nach Abschluss der Modellverarbeitung im Dialogfeld **Verarbeitungsstatus** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="ed6d0-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="ed6d0-133">Klicken Sie im Dialogfeld **Mining Struktur verarbeiten \<structure> -** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="ed6d0-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="ed6d0-134">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ed6d0-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="ed6d0-135">Hinzufügen neuer Modelle zur Ziel-Mailing-Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6d0-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ed6d0-136">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="ed6d0-136">Next Lesson</span></span>  
 [<span data-ttu-id="ed6d0-137">Lektion 4: Untersuchen der Ziel-Mailing-Modelle &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6d0-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed6d0-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed6d0-138">See Also</span></span>  
 [<span data-ttu-id="ed6d0-139">Anforderungen und Überlegungen zur Verarbeitung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6d0-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
