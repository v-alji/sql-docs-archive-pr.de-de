---
title: Erstellen einer Kopie eines Mining Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608104"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="4f35c-102">Erstellen einer Kopie eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="4f35c-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="4f35c-103">Die Erstellung einer Kopie eines Miningmodells ist hilfreich, wenn Sie schnell mehrere Miningmodelle erstellen möchten, die auf den gleichen Daten basieren.</span><span class="sxs-lookup"><span data-stu-id="4f35c-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="4f35c-104">Nach dem Kopieren des Modells können Sie die neue Kopie bearbeiten, indem Sie Parameter ändern oder einen Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f35c-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="4f35c-105">Wenn Sie zum Beispiel eine Customers-Tabelle besitzen, die mit einer Tabelle verknüpft ist, in der Einkäufe aufgeführt sind, können Sie Kopien erstellen, um separate Miningmodelle für jede Kundendemografie zu generieren und nach Attributen wie Alter oder Region zu filtern.</span><span class="sxs-lookup"><span data-stu-id="4f35c-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="4f35c-106">Informationen zum Kopieren des Inhalts des Modells (z.B. die grafische Darstellung oder die Modellmuster) in die Zwischenablage zur Verwendung in anderen Programmen finden Sie unter [Kopieren einer Sicht eines Miningmodells](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="4f35c-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="4f35c-107">So erstellen Sie ein verknüpftes Miningmodell</span><span class="sxs-lookup"><span data-stu-id="4f35c-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="4f35c-108">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]in Projektmappen-Explorer auf die Miningstruktur, die das Miningmodell enthält.</span><span class="sxs-lookup"><span data-stu-id="4f35c-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="4f35c-109">Klicken Sie auf die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="4f35c-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="4f35c-110">Wählen Sie das Modell aus, und klicken Sie mit der rechten Maustaste, um das Kontextmenü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4f35c-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="4f35c-111">Oder</span><span class="sxs-lookup"><span data-stu-id="4f35c-111">-or-</span></span>  
  
     <span data-ttu-id="4f35c-112">Wählen Sie das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="4f35c-112">Select the model.</span></span> <span data-ttu-id="4f35c-113">Klicken Sie im Menü **Miningmodell** auf **Neues Miningmodell**.</span><span class="sxs-lookup"><span data-stu-id="4f35c-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="4f35c-114">Geben Sie einen Namen für das neue Miningmodell ein, und wählen Sie einen Algorithmus aus.</span><span class="sxs-lookup"><span data-stu-id="4f35c-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="4f35c-115">So bearbeiten Sie den Filter im kopierten Miningmodell</span><span class="sxs-lookup"><span data-stu-id="4f35c-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="4f35c-116">Wählen Sie das Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="4f35c-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="4f35c-117">Klicken Sie im Fenster **Eigenschaften** auf das Textfeld für die **Filter** -Eigenschaft, und klicken Sie auf die Schaltfläche Erstellen **(...)** .</span><span class="sxs-lookup"><span data-stu-id="4f35c-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="4f35c-118">Ändern Sie die Filterbedingungen.</span><span class="sxs-lookup"><span data-stu-id="4f35c-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="4f35c-119">Weitere Informationen zur Verwendung der Dialogfelder des Filter-Editors finden Sie unter [Anwenden eines Filters auf ein Miningmodell](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="4f35c-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="4f35c-120">Klicken Sie im Fenster **Eigenschaften** in das `AlgorithmParameters` Textfeld, klicken Sie auf die **Parameter "mintalgorithm**", und ändern Sie bei Bedarf Algorithmusparameter.</span><span class="sxs-lookup"><span data-stu-id="4f35c-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f35c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f35c-121">See Also</span></span>  
 <span data-ttu-id="4f35c-122">[Filter für Mining Modelle &#40;Analysis Services Data Mining-&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4f35c-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4f35c-123">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="4f35c-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="4f35c-124">Löschen eines Filters aus einem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="4f35c-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
