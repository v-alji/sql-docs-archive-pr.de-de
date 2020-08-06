---
title: Data Quality-Abgleich im MDS-Add-In für Excel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621036"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="3b39c-102">Data Quality-Abgleich im MDS-Add-In für Excel</span><span class="sxs-lookup"><span data-stu-id="3b39c-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="3b39c-103">Es ist möglich, dass Sie dem MDS-Repository im Laufe der Zeit weitere Daten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3b39c-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="3b39c-104">Vor dem Hinzufügen von Daten kann es hilfreich sein, die neuen Daten mit den bereits in MDS verwalteten Daten zu vergleichen, um sicherzustellen, dass Sie keine doppelten oder ungenauen Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3b39c-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="3b39c-105">Unter MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] wird das Data Quality Services-Feature (DQS) von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet, um ähnliche Daten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3b39c-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="3b39c-106">Wenn Sie im Add-In die Abgleichfunktion verwenden, werden ähnliche Datensätze gruppiert, und es wird ein Wert angezeigt, der die Genauigkeit des Ergebnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="3b39c-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="3b39c-107">Weitere Informationen zur Abgleichfunktion von DQS finden Sie unter [Data Matching](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="3b39c-108">Workflow für Data Quality-Abgleich</span><span class="sxs-lookup"><span data-stu-id="3b39c-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="3b39c-109">Verwenden Sie beim Nutzen von DQS in Verbindung mit MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]den folgenden Workflow:</span><span class="sxs-lookup"><span data-stu-id="3b39c-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="3b39c-110">Rufen Sie eine Liste mit von MDS verwalteten Daten ab, und kombinieren Sie diese mit einer Liste, die nicht unter MDS verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="3b39c-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="3b39c-111">Weitere Informationen finden Sie unter [Kombinieren von Daten &#40;MDS-Add-In für Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="3b39c-112">Vergleichen Sie die Daten mithilfe der DQS-Erkenntnisse in der kombinierten Liste.</span><span class="sxs-lookup"><span data-stu-id="3b39c-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="3b39c-113">Weitere Informationen finden Sie unter [Abgleichen ähnlicher Daten &#40;MDS-Add-In für Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="3b39c-114">Zeigen Sie die Detailspalten an, um weitere Details zu den mit DQS ermittelten Ähnlichkeiten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3b39c-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="3b39c-115">Gehen Sie die Ergebnisse durch, und bestimmen Sie, welche Daten dem MDS-Repository hinzugefügt werden sollen und welche Daten doppelt vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3b39c-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="3b39c-116">Veröffentlichen Sie die neuen und/oder aktualisierten Daten im MDS-Repository.</span><span class="sxs-lookup"><span data-stu-id="3b39c-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="3b39c-117">Knowledge Bases</span><span class="sxs-lookup"><span data-stu-id="3b39c-117">Knowledge Bases</span></span>  
 <span data-ttu-id="3b39c-118">Die im Add-In angegebenen Abgleichergebnisse basieren auf einer DQS-Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="3b39c-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="3b39c-119">Die Standardwissensdatenbank (DQS-Daten) wird bei der Installation von DQS erstellt.</span><span class="sxs-lookup"><span data-stu-id="3b39c-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="3b39c-120">Wenn Sie die Standardwissensdatenbank verwenden (ohne eine Abgleichsrichtlinie zur Standardwissensdatenbank im Data Quality Client hinzuzufügen), müssen Sie Spalten im Arbeitsblatt Domänen in der Wissensdatenbank zuordnen und dann den ausgewählten Domänen einen Gewichtungswert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3b39c-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="3b39c-121">Sie können mit dem Data Quality Client eine neue Wissensdatenbank mit einer Abgleichsrichtlinie erstellen oder der Standardwissensdatenbank eine Abgleichsrichtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3b39c-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="3b39c-122">In diesem Fall werden die Gewichtungswerte von der Abgleichrichtlinie bestimmt, die Sie bereits erstellt haben, und Sie müssen lediglich die Spalten den Domänen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3b39c-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="3b39c-123">Weitere Informationen finden Sie unter [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="3b39c-124">Weitere Informationen zu Wissensdatenbanken finden Sie unter [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3b39c-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3b39c-125">Related Tasks</span></span>  
  
|<span data-ttu-id="3b39c-126">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3b39c-126">Task Description</span></span>|<span data-ttu-id="3b39c-127">Thema</span><span class="sxs-lookup"><span data-stu-id="3b39c-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="3b39c-128">Kombinieren Sie als Vorbereitung eines Vergleichs externe Daten mit von MDS verwalteten Daten.</span><span class="sxs-lookup"><span data-stu-id="3b39c-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="3b39c-129">Kombinieren von Daten &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3b39c-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="3b39c-130">Verwenden Sie DQS-Erkenntnisse zum Ermitteln von ähnlichen Elementen in Ihren Daten.</span><span class="sxs-lookup"><span data-stu-id="3b39c-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="3b39c-131">Abgleichen ähnlicher Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="3b39c-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="3b39c-132">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="3b39c-132">Related Content</span></span>  
  
-   [<span data-ttu-id="3b39c-133">Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3b39c-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="3b39c-134">Datenabgleich</span><span class="sxs-lookup"><span data-stu-id="3b39c-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
