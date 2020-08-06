---
title: Klassifizierte Spalten (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620678"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="f8244-102">Klassifizierte Spalten [Data Mining]</span><span class="sxs-lookup"><span data-stu-id="f8244-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="f8244-103">Wenn Sie eine klassifizierte Spalte definieren, erstellen Sie eine Beziehung zwischen der aktuellen Spalte und eine andere Spalte in der Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="f8244-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="f8244-104">Die Daten in der Miningstrukturspalte, die Sie als klassifizierte Spalte festlegen, enthält Kategorieinformationen zur Beschreibung der Werte in einer anderen Spalte der Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="f8244-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="f8244-105">Angenommen, Sie verfügen über zwei Spalten mit numerischen Daten: die Spalte [Jährliche Käufe] enthält die gesamten jährlichen Käufe pro Kunde für ein bestimmtes Kalenderjahr, und die andere Spalte [Standardabweichungen] enthält die Standardabweichungen für diese Werte.</span><span class="sxs-lookup"><span data-stu-id="f8244-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="f8244-106">In diesem Fall könnten Sie die Spalte [Jährliche Käufe] als klassifizierte Spalte festlegen, und das Modell wäre in der Lage, diese Beziehung in der Analyse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8244-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8244-107">Von den in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitgestellten Algorithmen werden klassifizierte Spalten nicht unterstützt. Diese Funktion wird für die Erstellung benutzerdefinierter Algorithmen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f8244-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="f8244-108">Definieren einer klassifizierten Spalte</span><span class="sxs-lookup"><span data-stu-id="f8244-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="f8244-109">Der Datentyp für eine klassifizierte Spalte muss entweder `Long` oder `Double` sein.</span><span class="sxs-lookup"><span data-stu-id="f8244-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="f8244-110">In der folgenden Liste werden die Inhaltstypen beschrieben, die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] für klassifizierte Spalten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8244-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="f8244-111">**Besteht**</span><span class="sxs-lookup"><span data-stu-id="f8244-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="f8244-112">Der Wert in der Spalte entspricht der Wahrscheinlichkeit des zugeordneten Wertes und ist eine Zahl zwischen 0 und 1.</span><span class="sxs-lookup"><span data-stu-id="f8244-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="f8244-113">**Varianten**</span><span class="sxs-lookup"><span data-stu-id="f8244-113">**VARIANCE**</span></span>  
 <span data-ttu-id="f8244-114">Der Wert in der Spalte entspricht der Varianz des zugeordneten Wertes.</span><span class="sxs-lookup"><span data-stu-id="f8244-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="f8244-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="f8244-115">**STDEV**</span></span>  
 <span data-ttu-id="f8244-116">Der Wert in der Spalte entspricht der Standardabweichung des zugeordneten Wertes.</span><span class="sxs-lookup"><span data-stu-id="f8244-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="f8244-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="f8244-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="f8244-118">Der Wert in der Spalte entspricht der Varianz der Wahrscheinlichkeit des zugeordneten Wertes.</span><span class="sxs-lookup"><span data-stu-id="f8244-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="f8244-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="f8244-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="f8244-120">Der Wert in der Spalte entspricht der Standardabweichung der Wahrscheinlichkeit des zugeordneten Wertes.</span><span class="sxs-lookup"><span data-stu-id="f8244-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="f8244-121">**Förder**</span><span class="sxs-lookup"><span data-stu-id="f8244-121">**SUPPORT**</span></span>  
 <span data-ttu-id="f8244-122">Der Wert in der Spalte entspricht der Gewichtung oder dem Fallreplikationsfaktor des zugeordneten Wertes.</span><span class="sxs-lookup"><span data-stu-id="f8244-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8244-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8244-123">See Also</span></span>  
 <span data-ttu-id="f8244-124">[Inhaltstypen &#40;Data Mining-&#41;](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f8244-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="f8244-125">[Mining Strukturen &#40;Analysis Services Data Mining-&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f8244-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="f8244-126">Datentypen &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f8244-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
