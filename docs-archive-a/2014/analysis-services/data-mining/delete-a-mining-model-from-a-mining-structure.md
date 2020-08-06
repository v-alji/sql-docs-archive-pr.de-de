---
title: Löschen eines Mining Modells aus einer Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621268"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="5a4bf-102">Löschen eines Miningmodells aus einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="5a4bf-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="5a4bf-103">Miningmodelle können mit dem Data Mining-Designer, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]oder DMX-Anweisungen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="5a4bf-104">Löschen eines Miningmodells mit SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="5a4bf-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="5a4bf-105">Wählen Sie die Registerkarte **Miningmodelle** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a4bf-106">Klicken Sie mit der rechten Maustaste auf das zu löschende Modell, und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="5a4bf-107">Das Dialogfeld **Objekte löschen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5a4bf-108">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="5a4bf-109">Löschen eines Miningmodells mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a4bf-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5a4bf-110">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, die das Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="5a4bf-111">Erweitern Sie **Miningstrukturen**und anschließend **Miningmodelle**.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="5a4bf-112">Klicken Sie mit der rechten Maustaste auf das zu löschende Modell, und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="5a4bf-113">Durch Löschen des Modells werden nicht die Trainingsdaten, sondern nur die Metadaten und alle Muster gelöscht, die beim Trainieren des Modells erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5a4bf-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="5a4bf-114">Löschen eines Miningmodells mit DMX</span><span class="sxs-lookup"><span data-stu-id="5a4bf-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="5a4bf-115">DROP MINING MODEL &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="5a4bf-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="5a4bf-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a4bf-116">See Also</span></span>  
 [<span data-ttu-id="5a4bf-117">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5a4bf-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
