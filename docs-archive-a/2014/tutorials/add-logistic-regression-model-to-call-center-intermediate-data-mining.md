---
title: Hinzufügen eines logistischen Regressionsmodells zur Callcenterstruktur (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720560"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="1d341-102">Hinzufügen eines logistischen Regressionsmodells zur Callcenterstruktur (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="1d341-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="1d341-103">Zusätzlich zur Analyse der Faktoren, die sich auf den Callcenterbetrieb auswirken können, wurden Sie außerdem aufgefordert, bestimmte Empfehlungen zur Verbesserung der Dienst Qualität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1d341-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="1d341-104">Für diese Aufgabe verwenden Sie dieselbe Miningstruktur wie beim Erstellen des explorativen Modells. Sie fügen jedoch ein Miningmodell hinzu, das zum Erstellen von Vorhersagen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d341-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="1d341-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] basiert ein logistisches Regressionsmodell auf dem neuronalen Netzwerke-Algorithmus und hat daher dieselbe Flexibilität und Leistungsstärke wie ein neuronales Netzwerkmodell.</span><span class="sxs-lookup"><span data-stu-id="1d341-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="1d341-106">Die logistische Regression ist jedoch besonders gut dafür geeignet, binäre Ergebnisse vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="1d341-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="1d341-107">Für dieses Szenario verwenden Sie die gleiche Miningstruktur, die Sie für das neuronale Netzwerkmodell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="1d341-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="1d341-108">Sie passen jedoch das neue Modell an, um Ihre Geschäftsfragen gezielt zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="1d341-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="1d341-109">Sie möchten die Dienstqualität verbessern und bestimmen, wie viele erfahrene Operatoren Sie benötigen. Deshalb richten Sie das Modell für die Vorhersage dieser Werte ein.</span><span class="sxs-lookup"><span data-stu-id="1d341-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="1d341-110">Um sicherzustellen, dass alle Modelle auf Grundlage der Callcenterdaten die größtmögliche Ähnlichkeit aufweisen, verwenden Sie denselben Ausgangswert wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="1d341-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="1d341-111">Durch Festlegen des Ausgangswertparameters gewährleisten Sie, dass das Modell die Daten vom gleichen Ausgangspunkt verarbeitet. Sie minimieren so die von Artefakten in den Daten verursachten Variationen.</span><span class="sxs-lookup"><span data-stu-id="1d341-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="1d341-112">So fügen Sie der Callcenter-Miningstruktur ein neues Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="1d341-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="1d341-113">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf die Mining Struktur **Call Center Binned**, und wählen Sie dann die Option zum **Öffnen des Designers**aus.</span><span class="sxs-lookup"><span data-stu-id="1d341-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="1d341-114">Klicken Sie im Data Mining-Designer auf die Registerkarte **Mining Modelle** .</span><span class="sxs-lookup"><span data-stu-id="1d341-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="1d341-115">Klicken Sie auf Verknüpftes **Mining Modell erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1d341-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="1d341-116">Geben Sie im Dialogfeld **Neues Mining Modell** für **Modellname den Namen**ein `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="1d341-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="1d341-117">Wählen Sie unter **Algorithmusname**die Option **Microsoft Logistic Regression**aus.</span><span class="sxs-lookup"><span data-stu-id="1d341-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="1d341-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d341-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="1d341-119">Das neue Mining Modell wird auf der Registerkarte **Mining Modelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d341-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="1d341-120">So passen Sie das logistische Regressionsmodell an</span><span class="sxs-lookup"><span data-stu-id="1d341-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="1d341-121">Belassen Sie in der Spalte für das neue Mining Modell die `Call Center - LR` Fakten-Callcenter-ID als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="1d341-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="1d341-122">Ändern Sie den Wert für die **vorher zusagenden**Operatoren Service Grade und Level Two.</span><span class="sxs-lookup"><span data-stu-id="1d341-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="1d341-123">Diese Spalten werden sowohl für die Eingabe als auch für Vorhersagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d341-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="1d341-124">In Wesentlichen erstellen Sie zwei separate Modelle auf derselben Datenbasis: eines für die Vorhersage der Operatorenzahl, und eines für die Vorhersage der Dienstqualität.</span><span class="sxs-lookup"><span data-stu-id="1d341-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="1d341-125">Ändern Sie alle anderen Spalten in **Input**.</span><span class="sxs-lookup"><span data-stu-id="1d341-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="1d341-126">So geben Sie den Ausgangswert an und verarbeiten die Modelle</span><span class="sxs-lookup"><span data-stu-id="1d341-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="1d341-127">Klicken Sie auf der Registerkarte **Mining Modell** mit der rechten Maustaste auf die Spalte für das Modell "Callcenter-LR", und wählen Sie **Algorithmusparameter festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="1d341-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="1d341-128">Klicken Sie in der Zeile für den HOLDOUT_SEED-Parameter auf die leere Zelle unter **Wert**, und geben Sie ein `1` .</span><span class="sxs-lookup"><span data-stu-id="1d341-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="1d341-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d341-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d341-130">Welchen Wert Sie als Ausgangswert auswählen, ist gleichgültig, solange für alle verwandten Modelle der gleiche Ausgangswert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d341-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="1d341-131">Wählen Sie im Menü **Mining Modelle** die Option **Mining Struktur und alle Modelle verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1d341-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="1d341-132">Klicken Sie auf **Ja** , um das aktualisierte Data Mining-Projekt auf dem Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1d341-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="1d341-133">Klicken Sie im Dialogfeld **Miningmodell verarbeiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1d341-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="1d341-134">Klicken Sie auf **Schließen** , um das Dialogfeld **Verarbeitungsstatus** zu schließen, und klicken Sie im Dialogfeld **Miningmodell verarbeiten** erneut auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="1d341-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1d341-135">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="1d341-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1d341-136">Erstellen von Vorhersagen für die Callcentermodelle &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="1d341-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d341-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d341-137">See Also</span></span>  
 [<span data-ttu-id="1d341-138">Anforderungen und Überlegungen zur Verarbeitung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="1d341-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
