---
title: Aktivieren von Drillthrough für ein Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608919"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="db015-102">Aktivieren von Drillthrough für ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="db015-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="db015-103">Wenn Sie Drillthrough für ein Miningmodell aktiviert haben, können Sie beim Durchsuchen des Modells detaillierte Informationen über die Fälle abrufen, die für die Erstellung des Modells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="db015-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="db015-104">Zum Anzeigen dieser Informationen benötigen Sie die erforderlichen Berechtigungen. Außerdem muss die Struktur bereits verarbeitet worden sein.</span><span class="sxs-lookup"><span data-stu-id="db015-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="db015-105">**Berechtigungen:** Damit ein Benutzer einen Drillthrough in Modell- oder Strukturdaten ausführen kann, muss er Mitglied einer Rolle sein, die über [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) -Berechtigungen für das Miningmodell oder die Miningstruktur verfügt.</span><span class="sxs-lookup"><span data-stu-id="db015-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="db015-106">Drillthroughberechtigungen werden getrennt für die Struktur und das Modell festgelegt.</span><span class="sxs-lookup"><span data-stu-id="db015-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="db015-107">Mit Drillthrough-Berechtigungen für das Modell können Sie einen Drillthrough des Modells durchführen, auch wenn Sie keine Berechtigungen für die Struktur besitzen.</span><span class="sxs-lookup"><span data-stu-id="db015-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="db015-108">Mit Drillthroughberechtigungen für die Struktur können Sie außerdem mit der Funktion [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) Strukturspalten in Drillthroughabfragen für das Modell einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="db015-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="db015-109">Sie können auch die Trainings-und Testfälle in der Struktur Abfragen, indem Sie die Option Select... Aus \<structure> . Fälle-Syntax.</span><span class="sxs-lookup"><span data-stu-id="db015-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="db015-110">**Zwischenspeichern von Trainingsfällen:** Beim Drillthrough werden Informationen über die Trainingsfälle in der Miningstruktur abgerufen.</span><span class="sxs-lookup"><span data-stu-id="db015-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="db015-111">Diese Informationen werden zwischengespeichert, wenn die Struktur verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="db015-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="db015-112">Wenn Sie alle zwischengespeicherten Daten durch Ändern der <xref:Microsoft.AnalysisServices.MiningStructureCacheMode>-Eigenschaft in `ClearAfterProcessing` löschen, funktioniert der Drillthrough nicht.</span><span class="sxs-lookup"><span data-stu-id="db015-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db015-113">Wenn die Trainingsfälle nicht zwischengespeichert wurden, müssen Sie die <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> -Eigenschaft in **KeepTrainingCases** ändern und das Modell anschließend erneut verarbeiten, bevor Sie die Falldaten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="db015-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="db015-114">Weitere Informationen finden Sie unter [Drillthroughabfragen &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="db015-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="db015-115">So aktivieren Sie Drillthrough für ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="db015-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="db015-116">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Data Mining-Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste auf den Namen des Miningmodells, für das Sie Drillthrough aktivieren möchten, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="db015-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="db015-117">Klicken Sie im Fenster **Eigenschaften** auf **AllowDrillThrough**, und wählen Sie **true**aus.</span><span class="sxs-lookup"><span data-stu-id="db015-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="db015-118">Klicken Sie auf der Registerkarte **Mining Modelle** mit der rechten Maustaste auf das Modell, und wählen Sie **Modell verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="db015-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="db015-119">So aktivieren Sie das Zwischenspeichern für eine Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="db015-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="db015-120">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Data Mining-Designer auf der Registerkarte **Miningstruktur** mit der rechten Maustaste auf den Namen der Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="db015-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="db015-121">Öffnen Sie das Fenster **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="db015-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="db015-122">Suchen Sie im Fenster **Eigenschaften** die **CacheMode** -Eigenschaft, und wählen Sie dann **KeepTrainingCases** in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="db015-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="db015-123">Aktivieren Sie im Menü **Datenbank** die Option **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="db015-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db015-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db015-124">See Also</span></span>  
 [<span data-ttu-id="db015-125">Drillthroughabfragen &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="db015-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
