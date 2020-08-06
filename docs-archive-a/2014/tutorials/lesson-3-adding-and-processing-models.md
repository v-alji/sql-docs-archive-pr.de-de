---
title: 'Lektion 3: Hinzufügen und Verarbeiten von Modellen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608949"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="17e34-102">Lektion 3: Hinzufügen und Verarbeiten von Modellen</span><span class="sxs-lookup"><span data-stu-id="17e34-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="17e34-103">Die ursprüngliche Miningstruktur, die Sie in der vorhergehenden Lektion erstellt haben, umfasst ein einzelnes Miningmodell, das auf dem [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Algorithmus basiert.</span><span class="sxs-lookup"><span data-stu-id="17e34-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="17e34-104">Anhand dieses Modells können Sie Kunden für die Targeted Mailing-Kampagne identifizieren.</span><span class="sxs-lookup"><span data-stu-id="17e34-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="17e34-105">Um fundierte Analyseergebnisse zu erhalten, ist es jedoch üblich, verwandte Modelle anhand verschiedener Algorithmen zu erstellen und deren Ergebnisse zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="17e34-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="17e34-106">Auf diese Weise erhalten Sie auch andere Einblicke.</span><span class="sxs-lookup"><span data-stu-id="17e34-106">That way you can get different insights as well.</span></span> <span data-ttu-id="17e34-107">Aus diesem Grund erstellen Sie zwei zusätzliche Modelle, die Sie anschließend verarbeiten und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="17e34-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="17e34-108">In dieser Lektion erstellen Sie eine Reihe von Miningmodellen, die aus einer Liste potenzieller Kunden die wahrscheinlichsten Kunden vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="17e34-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="17e34-109">Zum Ausführen der Aufgaben in dieser Lektion verwenden Sie den [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) sowie den [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="17e34-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="17e34-110">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="17e34-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="17e34-111">Hinzufügen neuer Modelle zur Ziel-Mailing-Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="17e34-112">Verarbeiten von Modellen in der vorgesehenen Mailing-Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="17e34-113">Erste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="17e34-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="17e34-114">Hinzufügen neuer Modelle zur Ziel-Mailing-Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="17e34-115">Vorherige Lektion</span><span class="sxs-lookup"><span data-stu-id="17e34-115">Previous Lesson</span></span>  
 [<span data-ttu-id="17e34-116">Lektion 2: aufbauen einer Ziel-Mailing Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="17e34-117">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="17e34-117">Next Lesson</span></span>  
 [<span data-ttu-id="17e34-118">Lektion 4: Untersuchen der Ziel-Mailing-Modelle &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="17e34-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17e34-119">See Also</span></span>  
 [<span data-ttu-id="17e34-120">Hinzufügen von Miningmodellen zu einer Struktur &#40;Analysis Services - Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="17e34-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
