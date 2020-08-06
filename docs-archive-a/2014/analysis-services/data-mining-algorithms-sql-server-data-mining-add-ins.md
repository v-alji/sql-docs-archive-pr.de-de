---
title: Data Mining-Algorithmen (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621279"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="ade0a-102">Data Mining-Algorithmen (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="ade0a-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="ade0a-103">Die Data Mining-Add-Ins für Office unterstützen das Erstellen von Analysemodellen mithilfe der folgenden Data Mining-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="ade0a-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="ade0a-104">Alle Algorithmen basieren auf bekannten Computerlernmethoden und wurden von Microsoft Research implementiert.</span><span class="sxs-lookup"><span data-stu-id="ade0a-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="ade0a-105">Algorithmen</span><span class="sxs-lookup"><span data-stu-id="ade0a-105">Algorithms</span></span>  
  
|<span data-ttu-id="ade0a-106">Computerlernmethode</span><span class="sxs-lookup"><span data-stu-id="ade0a-106">Machine learning method</span></span>|<span data-ttu-id="ade0a-107">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="ade0a-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="ade0a-108">Microsoft Association Rules-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="ade0a-109">Ermitteln, welche Produkte zusammen gekauft werden oder welche Ereignisse zusammen auftreten und Erstellen von Empfehlungen auf Grundlage des Modells.</span><span class="sxs-lookup"><span data-stu-id="ade0a-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="ade0a-110">Microsoft Clustering-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="ade0a-111">Definieren von Marktsegmenten, automatisches Gruppieren verbundener Kunden oder Suchen von Beziehungen in Daten zur weiteren Verwendung im Data Mining.</span><span class="sxs-lookup"><span data-stu-id="ade0a-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="ade0a-112">Microsoft Decision Trees-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="ade0a-113">Identifizieren zuvor unbekannter Beziehungen zwischen verschiedenen Datenelementen, um informiertere Entscheidungen zu treffen, oder Suchen von Faktoren, die bestimmte Ergebnisse bedingen.</span><span class="sxs-lookup"><span data-stu-id="ade0a-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="ade0a-114">Microsoft Linear Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="ade0a-115">Ermitteln einer mathematischen Formel zur Beschreibung der Faktoren, die zu einem numerischen Ergebnis beitragen.</span><span class="sxs-lookup"><span data-stu-id="ade0a-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="ade0a-116">Microsoft Logistic Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="ade0a-117">Identifizieren der Faktoren, die binäre Ergebnisse beeinflussen, und Ermitteln, wie Ergebnisse durch diese Faktoren beeinflusst werden können.</span><span class="sxs-lookup"><span data-stu-id="ade0a-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="ade0a-118">Microsoft Naive Bayes-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="ade0a-119">Analysieren dateninterner Beziehungen und Suchen der Beziehungen, die am stärksten mit einem Ergebnis korrelieren.</span><span class="sxs-lookup"><span data-stu-id="ade0a-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="ade0a-120">Microsoft Neural Network-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="ade0a-121">Suchen verborgener Beziehungen zwischen mehreren Eingaben und sogar mehreren Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="ade0a-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="ade0a-122">Zum Durchsuchen von Daten sowie für Vorhersagen geeignet.</span><span class="sxs-lookup"><span data-stu-id="ade0a-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="ade0a-123">Microsoft Time Series-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="ade0a-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="ade0a-124">Vorhersagen zukünftiger Werte anhand von Vergangenheitsdaten.</span><span class="sxs-lookup"><span data-stu-id="ade0a-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="ade0a-125">Erweiterte Optionen</span><span class="sxs-lookup"><span data-stu-id="ade0a-125">Advanced Options</span></span>  
 <span data-ttu-id="ade0a-126">Wenn Sie den Data Mining-Client für Excel verwenden, können Sie eigene Data Mining-Strukturen und -Modelle erstellen oder die Parameter der Algorithmen optimieren.</span><span class="sxs-lookup"><span data-stu-id="ade0a-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="ade0a-127">Algorithmusparameter &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="ade0a-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="ade0a-128">Modelle können mithilfe dieser erweiterten Optionen auf zwei Weisen angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="ade0a-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="ade0a-129">Verwenden Sie den Assistenten für **Data Mining-Abfragen** , um das Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ade0a-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="ade0a-130">Klicken Sie im **Data Mining-Client**auf **Parameter**, nachdem Sie den Assistenten gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="ade0a-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade0a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ade0a-131">See Also</span></span>  
 <span data-ttu-id="ade0a-132">[Abfrage &#40;SQL Server Data Mining-Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="ade0a-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="ade0a-133">Erweiterte Modellierung &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ade0a-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
