---
title: Angeben eines Test Datasets für die Struktur (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608156"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="3a115-102">Angeben eines Testdatasets für die Struktur (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="3a115-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="3a115-103">Auf den letzten Seiten des Data Mining-Assistenten teilen Sie Ihre Daten in einen Testsatz und einen Trainingssatz auf.</span><span class="sxs-lookup"><span data-stu-id="3a115-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="3a115-104">Anschließend benennen Sie die Struktur und aktivieren Drillthrough für das Modell.</span><span class="sxs-lookup"><span data-stu-id="3a115-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="3a115-105">Angeben eines Testsatzes</span><span class="sxs-lookup"><span data-stu-id="3a115-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="3a115-106">Indem die Daten beim Erstellen einer Miningstruktur in einen Trainings- und einen Testsatz aufgeteilt werden, wird die Beurteilung der Genauigkeit von Miningmodellen, die Sie zu einem späteren Zeitpunkt erstellen, erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="3a115-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="3a115-107">Weitere Informationen zu Test Sätzen finden Sie unter [Trainings-und Test Datasets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="3a115-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="3a115-108">So geben Sie den Testsatz an</span><span class="sxs-lookup"><span data-stu-id="3a115-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="3a115-109">Überprüfen Sie auf der Seite **Testsatz erstellen** für den **Prozentsatz der zu testenden Daten**den Standardwert `30` .</span><span class="sxs-lookup"><span data-stu-id="3a115-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="3a115-110">Geben Sie für **Maximale Anzahl von Fällen in Test**Dataset ein `1000` .</span><span class="sxs-lookup"><span data-stu-id="3a115-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="3a115-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3a115-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="3a115-112">Angeben von Drillthrough</span><span class="sxs-lookup"><span data-stu-id="3a115-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="3a115-113">Drillthrough kann für Modelle und für Strukturen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3a115-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="3a115-114">Durch das Kontrollkästchen in diesem Dialogfeld wird der Drillthrough für das benannte Modell aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a115-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="3a115-115">Nach der Verarbeitung des Modells können Sie detaillierte Informationen aus den Trainingsdaten abrufen, die zur Modellerstellung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="3a115-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="3a115-116">Wenn auch in der zugrunde liegenden Miningstruktur die Verwendung von Drillthrough konfiguriert wurde, können Sie detaillierte Informationen sowohl aus den Modellfällen als auch aus der Miningstruktur abrufen, einschließlich Spalten, die nicht im Miningmodell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3a115-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="3a115-117">Weitere Informationen finden Sie unter [Drillthroughabfragen &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3a115-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="3a115-118">So benennen Sie das Modell und die Struktur und geben Drillthrough an</span><span class="sxs-lookup"><span data-stu-id="3a115-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="3a115-119">Geben Sie auf der Seite **Assistenten abschließen** unter **Mining Struktur Name den Namen**ein `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="3a115-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="3a115-120">Geben Sie in **Mining Modellname den Namen**ein `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="3a115-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="3a115-121">Aktivieren Sie das Kontrollkästchen **Drillthrough zulassen** .</span><span class="sxs-lookup"><span data-stu-id="3a115-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="3a115-122">Überprüfen Sie den **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="3a115-122">Review the **Preview** pane.</span></span> <span data-ttu-id="3a115-123">Beachten Sie, dass nur die Spalten angezeigt werden, die als **Schlüssel**, **Eingabe** oder **vorhersagbar** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="3a115-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="3a115-124">Die anderen ausgewählten Spalten, z. B. AddressLine1, werden nicht zum Erstellen des Modells verwendet. Sie sind jedoch in der zugrunde liegenden Struktur verfügbar und können nach Verarbeitung und Bereitstellung des Modells abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="3a115-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="3a115-125">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3a115-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="3a115-126">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="3a115-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="3a115-127">Angeben des Datentyps und des Inhaltstyps &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="3a115-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="3a115-128">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="3a115-128">Next Lesson</span></span>  
 [<span data-ttu-id="3a115-129">Lektion 3: Hinzufügen und Verarbeiten von Modellen</span><span class="sxs-lookup"><span data-stu-id="3a115-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a115-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a115-130">See Also</span></span>  
 <span data-ttu-id="3a115-131">[Aktivieren von Drillthrough für ein Mining Modell](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="3a115-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="3a115-132">[Drillthrough-Abfragen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3a115-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="3a115-133">Geben Sie den Data Mining-Assistenten für Trainingsdaten &#40;an&#41;</span><span class="sxs-lookup"><span data-stu-id="3a115-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
