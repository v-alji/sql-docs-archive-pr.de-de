---
title: Kopieren einer Sicht eines Mining Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694846"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="ed6d1-102">Kopieren einer Sicht eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="ed6d1-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="ed6d1-103">Auf der Registerkarte **Miningmodell-Viewer** des Data Mining-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] wird für jeden Typ von Miningmodell ein separater Viewer verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="ed6d1-104">Einige der Viewer weisen Komponenten auf, aus denen der Inhalt in die Zwischenablage kopiert und von dort in ein Dokument oder eine Bildbearbeitungssoftware eingefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="ed6d1-105">Folgende Komponenten stellen diese Funktionalität zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ed6d1-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="ed6d1-106">Clusterdiagramm im Cluster-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)] und im Sequenzcluster-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6d1-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="ed6d1-107">Entscheidungsstruktur im Struktur-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)] und im Zeitreihe-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6d1-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="ed6d1-108">Statusübergänge im Sequenzcluster-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6d1-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="ed6d1-109">Abhängigkeitsnetzwerk im Zuordnungsregeln-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)] , Viewer für naives Bayes-Verfahren von [!INCLUDE[msCoName](../../includes/msconame-md.md)] und Struktur-Viewer von [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6d1-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="ed6d1-110">Miningmodellinhalt, im Bereich Knotendetails des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewers</span><span class="sxs-lookup"><span data-stu-id="ed6d1-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="ed6d1-111">Sie können die gesamte Darstellung des Miningmodells oder nur den im Viewer sichtbaren Teil kopieren.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ed6d1-112">Wenn Sie mit dem Viewer ein Modell kopieren, wird kein neues Modellobjekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="ed6d1-113">Um ein neues Modell zu erstellen, müssen Sie entweder den Assistenten oder den Data Mining-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="ed6d1-114">Weitere Informationen finden Sie unter [Erstellen einer Kopie eines Miningmodells](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="ed6d1-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="ed6d1-115">So kopieren Sie das gesamte Modell in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ed6d1-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="ed6d1-116">Wählen Sie in der Liste **Miningmodell** auf der Registerkarte **Miningmodell-Viewer** das Miningmodell aus, das angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="ed6d1-117">Wählen Sie die entsprechende Registerkarte aus, beispielsweise die Registerkarte **Abhängigkeitsnetzwerk** , und klicken Sie dann auf der Symbolleiste dieser Registerkarte auf **Gesamtes Diagramm kopieren** .</span><span class="sxs-lookup"><span data-stu-id="ed6d1-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="ed6d1-118">So kopieren Sie den sichtbaren Teil des Modells in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ed6d1-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="ed6d1-119">Wählen Sie in der Liste **Miningmodell** auf der Registerkarte **Miningmodell-Viewer** das Miningmodell aus, das angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="ed6d1-120">Wählen Sie die entsprechende Registerkarte aus, beispielsweise die Registerkarte **Abhängigkeitsnetzwerk** , und vergrößern bzw. verkleinern Sie die Darstellung dann entsprechend, um das Modell in dem von Ihnen gewünschten Umfang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="ed6d1-121">Klicken Sie auf der Symbolleiste der ausgewählten Registerkarte auf **Diagrammsicht kopieren** .</span><span class="sxs-lookup"><span data-stu-id="ed6d1-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="ed6d1-122">So kopieren Sie den Inhalt des Miningmodells in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="ed6d1-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="ed6d1-123">Wählen Sie in der Liste **Miningmodell** auf der Registerkarte **Miningmodell-Viewer** das Miningmodell aus, das angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="ed6d1-124">Wählen Sie in der Dropdownliste **Viewer** die Option **Microsoft Generic Content Tree Viewer**aus.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="ed6d1-125">Klicken Sie im Bereich **Knotenbeschriftung (eindeutige ID)** auf einen Knoten.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="ed6d1-126">Klicken Sie mit der rechten Maustaste auf den Bereich **Knotendetails** , und wählen Sie **Alles auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="ed6d1-127">Klicken Sie mit der rechten Maustaste erneut auf den Bereich **Knotendetails** , und wählen Sie **Kopieren**aus.</span><span class="sxs-lookup"><span data-stu-id="ed6d1-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6d1-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed6d1-128">See Also</span></span>  
 [<span data-ttu-id="ed6d1-129">Tasks und Anweisungen für Miningmodell-Viewer</span><span class="sxs-lookup"><span data-stu-id="ed6d1-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
