---
title: Erstellen eines zugehörigen Sequence Clustering-Modells (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719138"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="a8a16-102">Erstellen eines Clustermodells für verwandte Sequenzen (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="a8a16-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="a8a16-103">Bei der Untersuchung des Sequenzclustermodells haben Sie gelernt, dass Attribute wie "Region" oder "Einkommen" starke Auswirkungen auf die Modelle haben. Aus diesem Grund erstellen Sie nun ein Clustermodell für verwandte Sequenzen und entfernen die Attribute für demografische Kundendaten, um ein besseres Verständnis der Sequenzen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="a8a16-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="a8a16-104">In dieser Aufgabe erstellen Sie eine Kopie des Clustermodells für regionale Sequenzen und entfernen alle Spalten aus dem Modell, die keinen direkten Bezug zu Sequenzen haben.</span><span class="sxs-lookup"><span data-stu-id="a8a16-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="a8a16-105">Das neue Modell enthält die gleichen Spalten wie das zugrunde liegende Miningmodell.</span><span class="sxs-lookup"><span data-stu-id="a8a16-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="a8a16-106">Das Entfernen der Spalten aus der Miningstruktur ist jedoch nicht erforderlich; Sie müssen nur festlegen, dass die Spalten im neuen Miningmodell ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="a8a16-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="a8a16-107">So erstellen Sie eine Kopie des Sequenzclustermodells</span><span class="sxs-lookup"><span data-stu-id="a8a16-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="a8a16-108">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Data Mining-Designer auf die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="a8a16-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="a8a16-109">Klicken Sie mit der rechten Maustaste auf das Modell, das Sie kopieren möchten, und wählen Sie **Neues Miningmodell**aus.</span><span class="sxs-lookup"><span data-stu-id="a8a16-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="a8a16-110">Geben Sie im Dialogfeld **Neues Mining Modell** einen Modellnamen ein, und wählen Sie Microsoft aus `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="a8a16-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="a8a16-111">Geben Sie für dieses Tutorial den Namen ein `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="a8a16-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="a8a16-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a16-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="a8a16-113">So entfernen Sie Spalten aus dem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="a8a16-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="a8a16-114">Klicken Sie auf der Registerkarte **Mining Modell** in der Spalte für das neue Modell Sequence Clustering auf die Zeile für das **Income Group** -Attribut, und wählen Sie **ignorieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a8a16-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="a8a16-115">Wiederholen Sie diesen Schritt für das Attribut **Region**.</span><span class="sxs-lookup"><span data-stu-id="a8a16-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="a8a16-116">Klicken Sie auf das Pluszeichen neben dem Tabellennamen **v Assoc Seq Line Items**, um die Tabelle zu erweitern und die Spalten der geschachtelten Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a8a16-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="a8a16-117">Das neue Modell sollte nur aus folgenden Spalten bestehen:</span><span class="sxs-lookup"><span data-stu-id="a8a16-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="a8a16-118">**Bestellnummern Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a8a16-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="a8a16-119">**Zeilennummern Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a8a16-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="a8a16-120">**Modellvorhersage**</span><span class="sxs-lookup"><span data-stu-id="a8a16-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="a8a16-121">So verarbeiten Sie das neue Sequenzclustermodell</span><span class="sxs-lookup"><span data-stu-id="a8a16-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="a8a16-122">Klicken Sie auf der Registerkarte **Mining Modell** mit der rechten Maustaste auf das neue Modell `Sequence Clustering` , und wählen Sie **Modell verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a8a16-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="a8a16-123">Da das neue vereinfachte Miningmodell auf einer Struktur basiert, die bereits verarbeitet wurde, muss diese nicht erneut verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a8a16-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="a8a16-124">Eine Verarbeitung des neuen Miningmodells ist ausreichend.</span><span class="sxs-lookup"><span data-stu-id="a8a16-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="a8a16-125">Klicken Sie auf **Ja** , um das aktualisierte Data Mining-Projekt auf dem Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a8a16-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="a8a16-126">Klicken Sie im Dialogfeld **Miningmodell verarbeiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a8a16-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="a8a16-127">Klicken Sie auf **Schließen** , um das Dialogfeld **Verarbeitungsstatus** zu schließen, und klicken Sie im Dialogfeld **Miningmodell verarbeiten** erneut auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="a8a16-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a8a16-128">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="a8a16-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a8a16-129">Erstellen von Vorhersagen für ein Sequenz Cluster Modell &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a16-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8a16-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8a16-130">See Also</span></span>  
 [<span data-ttu-id="a8a16-131">Anforderungen und Überlegungen zur Verarbeitung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a16-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
