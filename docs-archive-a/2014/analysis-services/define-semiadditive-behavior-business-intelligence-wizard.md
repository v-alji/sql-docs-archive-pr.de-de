---
title: Semiadditives Verhalten definieren (Business Intelligence-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696313"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="f3f80-102">Semiadditives Verhalten definieren (Business Intelligence-Assistent)</span><span class="sxs-lookup"><span data-stu-id="f3f80-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="f3f80-103">Verwenden Sie die Seite **Semiadditives Verhalten definieren** , um das semiadditive Verhalten für Measures zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3f80-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="f3f80-104">Das semiadditive Verhalten bestimmt, wie in einem Cube enthaltene Measures über eine Zeitdimension aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="f3f80-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3f80-105">Mit Ausnahme von LastChild, das in der Standard Edition verfügbar ist, ist semiadditives Verhalten nur in der Business Intelligence Edition oder der Enterprise Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3f80-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="f3f80-106">Da semiadditives Verhalten darüber hinaus nur für Measures und nicht für Dimensionen definiert wird, wird diese Seite im Business Intelligence-Assistenten nicht angezeigt, wenn er über den Dimensions-Designer oder durch Klicken mit der rechten Maustaste auf eine Dimension im Projektmappen-Explorer von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f3f80-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="f3f80-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f3f80-107">Options</span></span>  
 <span data-ttu-id="f3f80-108">**Semiadditives Verhalten deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="f3f80-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="f3f80-109">Deaktiviert das semiadditive Verhalten in allen Measures, die im Cube enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f3f80-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="f3f80-110">**Die \<dimension name> Konto Dimension, die Semiadditives Elemente enthält, wurde vom Assistenten erkannt. Die Elemente dieser Dimension werden vom Server gemäß dem semiadditiven Verhalten aggregiert, das für jeden Kontotyp angegeben ist.**</span><span class="sxs-lookup"><span data-stu-id="f3f80-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="f3f80-111">Aktiviert das semiadditive Verhalten für Kontodimensionen mit semiadditiven Elementen.</span><span class="sxs-lookup"><span data-stu-id="f3f80-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="f3f80-112">Wenn Sie diese Option aktivieren, wird die Aggregatfunktion von all jenen Measures in den Measuregruppen festgelegt, die die Kontodimension auf `ByAccount` verweisen.</span><span class="sxs-lookup"><span data-stu-id="f3f80-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="f3f80-113">Weitere Informationen zu Kontodimensionen finden Sie unter [Erstellen eines Finanzkontos des über- und untergeordneten Typs Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="f3f80-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="f3f80-114">**Semiadditives Verhalten für einzelne Elemente definieren**</span><span class="sxs-lookup"><span data-stu-id="f3f80-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="f3f80-115">Aktiviert Semiadditives Verhalten für bestimmte Measures und gibt die Aggregatfunktion für bestimmte Measures an.</span><span class="sxs-lookup"><span data-stu-id="f3f80-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="f3f80-116">Die Aggregatfunktion gilt für all jene Dimensionen, auf die durch die Measuregruppe mit dem Measure verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f3f80-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="f3f80-117">**Hilfs**</span><span class="sxs-lookup"><span data-stu-id="f3f80-117">**Measures**</span></span>  
 <span data-ttu-id="f3f80-118">Zeigt den Namen eines im Cube enthaltenen Measures an.</span><span class="sxs-lookup"><span data-stu-id="f3f80-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="f3f80-119">**Semiadditive Funktion**</span><span class="sxs-lookup"><span data-stu-id="f3f80-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="f3f80-120">Wählen Sie die Aggregatfunktion für das ausgewählte Measure aus.</span><span class="sxs-lookup"><span data-stu-id="f3f80-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="f3f80-121">In der folgenden Tabelle sind die verfügbaren Aggregatfunktionen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f3f80-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="f3f80-122">Wert</span><span class="sxs-lookup"><span data-stu-id="f3f80-122">Value</span></span>|<span data-ttu-id="f3f80-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f3f80-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3f80-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="f3f80-124">**AverageOfChildren**</span></span>|<span data-ttu-id="f3f80-125">Wird durch Zurückgeben des Durchschnitts der dem Measure untergeordneten Elemente aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="f3f80-126">Wird durch die Aggregatfunktion aggregiert, die dem angegebenen Kontotyp des Attributs in der Kontodimension zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f3f80-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="f3f80-127">Wird mit der `Count`-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="f3f80-128">Wird mit der `DistinctCount`-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="f3f80-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="f3f80-129">**FirstChild**</span></span>|<span data-ttu-id="f3f80-130">Wird durch Zurückgeben des ersten untergeordneten Elements des Measures über eine Zeitdimension aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="f3f80-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="f3f80-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="f3f80-132">Wird durch Zurückgeben des ersten nicht leeren Elements des Measures über eine Zeitdimension aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="f3f80-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="f3f80-133">**LastChild**</span></span>|<span data-ttu-id="f3f80-134">Wird durch Zurückgeben des letzten untergeordneten Elements des Measures über eine Zeitdimension aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="f3f80-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="f3f80-135">**LastNonEmpty**</span></span>|<span data-ttu-id="f3f80-136">Wird durch Zurückgeben des letzten nicht leeren Elements des Measures über eine Zeitdimension aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="f3f80-137">Wird mit der `Max`-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="f3f80-138">Wird mit der `Min`-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="f3f80-139">**None**</span><span class="sxs-lookup"><span data-stu-id="f3f80-139">**None**</span></span>|<span data-ttu-id="f3f80-140">Aggregation wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3f80-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="f3f80-141">Wird mit der `Sum`-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="f3f80-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f3f80-142">Die für diese Option getroffene Auswahl gilt nur, wenn **Semiadditives Verhalten für einzelne Measures definieren** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="f3f80-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f80-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3f80-143">See Also</span></span>  
 <span data-ttu-id="f3f80-144">[Business Intelligence Wizard (F1-Hilfe)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f3f80-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="f3f80-145">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f3f80-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f3f80-146">Der Dimensions-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f3f80-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
