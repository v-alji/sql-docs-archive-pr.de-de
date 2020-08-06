---
title: Spalten Verteilungen (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630427"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="d036e-102">Spaltenverteilungen [Data Mining]</span><span class="sxs-lookup"><span data-stu-id="d036e-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="d036e-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] können Sie Spalten Verteilungen in einer Mining Struktur definieren, um zu beeinflussen, wie Algorithmen die Daten in diesen Spalten verarbeiten, wenn Sie Mining Modelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="d036e-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="d036e-104">Für einige Algorithmen ist es hilfreich, vor dem Verarbeiten des Modells für jede kontinuierliche Spalte die Verteilung zu definieren, wenn für die Spalten bekannt ist, dass sie normal verteilte Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="d036e-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="d036e-105">Wenn Sie die Verteilungen nicht definieren, liefern die sich ergebenden Miningmodelle möglicherweise ungenauere Vorhersagen, da die Algorithmen weniger Informationen zum Interpretieren der Daten haben.</span><span class="sxs-lookup"><span data-stu-id="d036e-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="d036e-106">Die in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verfügbaren Algorithmen unterstützen folgende Verteilungstypen:</span><span class="sxs-lookup"><span data-stu-id="d036e-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="d036e-107">`Normal`Die Werte für die kontinuierliche Spalte bilden ein Histogramm mit normaler Verteilung.</span><span class="sxs-lookup"><span data-stu-id="d036e-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="d036e-108">![Histogramm mit Normalverteilung](../media/normal-distribution.gif "Histogramm mit Normalverteilung")</span><span class="sxs-lookup"><span data-stu-id="d036e-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="d036e-109">`Log Normal`Die Werte für die kontinuierliche Spalte bilden ein Histogramm, in dem die Kurve am oberen Ende gestreckt wird und zum unteren Ende verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="d036e-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="d036e-110">![Histogramm mit Protokollnormalverteilung](../media/log-normal-distribution.gif "Histogramm mit Protokollnormalverteilung")</span><span class="sxs-lookup"><span data-stu-id="d036e-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="d036e-111">`Uniform`Die Werte für die kontinuierliche Spalte bilden eine flache Kurve, in der alle Werte gleich wahrscheinlich sind.</span><span class="sxs-lookup"><span data-stu-id="d036e-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="d036e-112">![Histogramm mit Gleichverteilung](../media/uniform-distribution.gif "Histogramm mit Gleichverteilung")</span><span class="sxs-lookup"><span data-stu-id="d036e-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="d036e-113">Weitere Informationen zu den von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitgestellten Algorithmen finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d036e-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d036e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d036e-114">See Also</span></span>
 <span data-ttu-id="d036e-115">[Inhaltstypen &#40;Data Mining-&#41;](content-types-data-mining.md) [Mining Strukturen &#40;Analysis Services-Data Mining-&#41;](mining-structures-analysis-services-data-mining.md) [Diskretisierungsmethoden &#40;Data Mining-&#41;](discretization-methods-data-mining.md) [Verteilungen &#40;DMX-&#41;](/sql/dmx/distributions-dmx) [Mining Struktur Spalten](mining-structure-columns.md)</span><span class="sxs-lookup"><span data-stu-id="d036e-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


