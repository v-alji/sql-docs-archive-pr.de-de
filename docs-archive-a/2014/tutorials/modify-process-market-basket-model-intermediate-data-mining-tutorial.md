---
title: Ändern und Verarbeiten des Market Basket-Modells (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608165"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="ee7d4-102">Ändern und Verarbeiten des Market Basket-Modells (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="ee7d4-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ee7d4-103">Bevor Sie das von Ihnen erstellte Association-Miningmodell verarbeiten, müssen Sie die Standardwerte von zwei der Parameter ändern: *Support* und *Probability*.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="ee7d4-104">*Support* definiert den Prozentsatz von Fällen, in denen eine Regel vorhanden sein muss, um als gültig betrachtet zu werden.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="ee7d4-105">Geben Sie an, dass bei mindestens 1 Prozent der Fälle eine Regel vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="ee7d4-106">*Probability* definiert, wie wahrscheinlich eine Zuordnung sein muss, um als gültig betrachtet zu werden.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="ee7d4-107">Berücksichtigen Sie alle Zuordnungen mit einer Wahrscheinlichkeit von mindestens 10 Prozent.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="ee7d4-108">Weitere Informationen zu den Auswirkungen der Erhöhung oder Verringerung der Unterstützung und der Wahrscheinlichkeit finden Sie unter [Technische Referenz für den Microsoft Association-Algorithmus](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ee7d4-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="ee7d4-109">Nachdem Sie Struktur und Parameter für das **Association** -Miningmodell definiert haben, können Sie das Modell verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="ee7d4-110">So passen Sie die Parameter für das Modell Association an</span><span class="sxs-lookup"><span data-stu-id="ee7d4-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="ee7d4-111">Öffnen Sie im Data Mining-Designer die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="ee7d4-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="ee7d4-112">Klicken Sie im Designer mit der rechten Maustaste auf die Spalte **Association** , und wählen Sie **Algorithmusparameter festlegen** , um das Dialogfeld Algorithmusparameter zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="ee7d4-113">Legen Sie in der Spalte **Wert** des Dialogfelds **Algorithmusparameter** folgende Parameter fest:</span><span class="sxs-lookup"><span data-stu-id="ee7d4-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="ee7d4-114">MINIMUM_PROBABILITY = 0.1</span><span class="sxs-lookup"><span data-stu-id="ee7d4-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="ee7d4-115">MINIMUM_SUPPORT = 0.01</span><span class="sxs-lookup"><span data-stu-id="ee7d4-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="ee7d4-116">So wird das Miningmodell verarbeitet</span><span class="sxs-lookup"><span data-stu-id="ee7d4-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="ee7d4-117">Wählen Sie im Menü **Mining Modell** von die Option [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] **Mining Struktur und alle Modelle verarbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="ee7d4-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="ee7d4-118">Klicken Sie in der Meldung mit der Frage, ob Sie das Projekt erstellen und bereitstellen möchten, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="ee7d4-119">Das Dialogfeld **Miningstruktur verarbeiten - Association** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ee7d4-120">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="ee7d4-121">Das Dialogfeld **Verarbeitungsstatus** wird geöffnet und zeigt Informationen zur Verarbeitung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="ee7d4-122">Das Verarbeiten der neuen Struktur und des Modells kann eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="ee7d4-123">Nachdem die Verarbeitung abgeschlossen ist, klicken Sie auf **Schließen** , um das Dialogfeld **Verarbeitungsstatus** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="ee7d4-124">Klicken Sie auf **Schließen** , um das Dialogfeld **Miningstruktur verarbeiten - Association** wieder zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ee7d4-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ee7d4-125">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ee7d4-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ee7d4-126">Erkunden des Market Basket-Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="ee7d4-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee7d4-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee7d4-127">See Also</span></span>  
 [<span data-ttu-id="ee7d4-128">Anforderungen und Überlegungen zur Verarbeitung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ee7d4-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
