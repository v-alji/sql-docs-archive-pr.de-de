---
title: Verarbeiten eines Mining Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718949"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="b807f-102">Verarbeiten eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="b807f-102">Process a Mining Model</span></span>
  <span data-ttu-id="b807f-103">Auf der Registerkarte Miningmodelle im Data Mining-Designer von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]können Sie ein bestimmtes Miningmodell verarbeiten, das einer Miningstruktur zugeordnet ist. Sie können auch alle Modelle verarbeiten, die der Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b807f-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="b807f-104">Sie können ein Miningmodell mit den folgenden Tools verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="b807f-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="b807f-105">Sie können auch einen XMLA Process-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b807f-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="b807f-106">Weitere Informationen finden Sie unter [Tools und Ansätze für die Verarbeitung &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b807f-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="b807f-107">Verarbeiten eines einzelnen Miningmodells mit SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="b807f-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="b807f-108">Wählen Sie auf der Registerkarte **Miningmodelle** des Data Mining-Designers ein Miningmodell aus einer oder mehreren Spalten der Modelle im Raster aus.</span><span class="sxs-lookup"><span data-stu-id="b807f-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="b807f-109">Klicken Sie im Menü **Miningmodell** auf **Modell verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b807f-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="b807f-110">Falls Sie Änderungen an der Miningstruktur vorgenommen haben, werden Sie aufgefordert, die Struktur erneut bereitzustellen, bevor Sie das Modell verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b807f-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="b807f-111">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b807f-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b807f-112">Klicken Sie im Dialogfeld **Mining \<model> Modell verarbeiten-** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b807f-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="b807f-113">Das Dialogfeld **Verarbeitungsstatus** wird geöffnet und zeigt Informationen zur Verarbeitung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="b807f-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="b807f-114">Nachdem die Modellverarbeitung erfolgreich abgeschlossen ist, klicken Sie im Dialogfeld **Verarbeitungsstatus** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="b807f-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="b807f-115">Klicken Sie im Dialogfeld **Mining Modell verarbeiten \<model> -** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="b807f-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="b807f-116">Es wurden lediglich die Miningstruktur und das ausgewählte Miningmodell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b807f-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="b807f-117">Verarbeiten aller Miningmodelle, die einer Miningstruktur zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="b807f-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="b807f-118">Wählen Sie auf der Registerkarte **Miningmodelle** im Data Mining-Designer aus dem Menü **Miningmodell** die Option **Miningstruktur und alle Modelle verarbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b807f-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="b807f-119">Falls Sie Änderungen an der Miningstruktur vorgenommen haben, werden Sie aufgefordert, die Struktur erneut bereitzustellen, bevor Sie die Modelle verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b807f-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="b807f-120">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b807f-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b807f-121">Klicken Sie im Dialogfeld **Mining \<structure> Struktur verarbeiten-** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b807f-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="b807f-122">Das Dialogfeld **Verarbeitungsstatus** wird geöffnet und zeigt Informationen zur Verarbeitung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="b807f-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="b807f-123">Nachdem die Modellverarbeitung erfolgreich abgeschlossen ist, klicken Sie im Dialogfeld **Verarbeitungsstatus** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="b807f-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="b807f-124">Klicken Sie im Dialogfeld " \*\*Verarbeitung \<model> \*\* " auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="b807f-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="b807f-125">Die Miningstruktur und alle zugeordneten Miningmodelle wurden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b807f-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b807f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b807f-126">See Also</span></span>  
 [<span data-ttu-id="b807f-127">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b807f-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
