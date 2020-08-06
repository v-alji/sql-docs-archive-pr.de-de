---
title: Semiadditives Verhalten definieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618382"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="e6b4b-102">Semiadditives Verhalten definieren</span><span class="sxs-lookup"><span data-stu-id="e6b4b-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="e6b4b-103">Semiadditive Measures, die nicht in allen Dimensionen einheitlich aggregiert werden, kommen in vielen Geschäftsszenarien sehr häufig vor.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="e6b4b-104">Jeder Cube, der auf Momentaufnahmen von Bilanzen über einen Zeitraum basiert, weist dieses Problem auf.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="e6b4b-105">Sie finden diese Momentaufnahmen in Anwendungen, die mit Wertpapiere, Kontostände, Budgetierung, Humanressourcen, Versicherungspolicen, Schadensansprüchen und viele andere Geschäftsfelder behandeln.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="e6b4b-106">Fügen Sie semiadditives Verhalten einem Cube hinzu, um eine Aggregationsmethode für einzelne Measures oder Elemente eines Kontotypattributs zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="e6b4b-107">Wenn der Cube eine Kontodimension enthält, können Sie automatisch semiadditives Verhalten auf der Basis des Kontotyps festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="e6b4b-108">Öffnen Sie einen Cube im Cube-Designer, und wählen Sie im Menü Cube die Option **Business Intelligence hinzufügen** aus, um semiadditives Verhalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="e6b4b-109">Wählen Sie im Business Intelligence-Assistenten auf der Seite **Erweiterung auswählen** die Option **Semiadditives Verhalten definieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="e6b4b-110">Dieser Assistent führt Sie anschließend durch die Schritte zum Identifizieren der Measures, die semiadditives Verhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="e6b4b-111">Mit Ausnahme von LastChild, das in der Standard Edition verfügbar ist, ist semiadditives Verhalten nur in der Business Intelligence Edition oder der Enterprise Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="e6b4b-112">Semiadditives Verhalten definieren</span><span class="sxs-lookup"><span data-stu-id="e6b4b-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="e6b4b-113">Auf der Seite **Semiadditives Verhalten definieren** des Assistenten können Sie durch Auswählen einer der folgenden Optionen auswählen, wie semiadditiv definiert werden soll:</span><span class="sxs-lookup"><span data-stu-id="e6b4b-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="e6b4b-114">**Semiadditives Verhalten deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="e6b4b-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="e6b4b-115">Deaktiviert das semiadditive Verhalten für einen Cube, für den vorher semiadditives Verhalten definiert war.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="e6b4b-116">Durch Auswählen dieser Option wird ein Measure auf `SUM` zurückgesetzt, wenn es auf einen der folgenden Aggregationsfunktionstypen festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="e6b4b-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="e6b4b-117">By Account</span><span class="sxs-lookup"><span data-stu-id="e6b4b-117">By Account</span></span>  
  
-   <span data-ttu-id="e6b4b-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="e6b4b-118">Average of Children</span></span>  
  
-   <span data-ttu-id="e6b4b-119">First Child</span><span class="sxs-lookup"><span data-stu-id="e6b4b-119">First Child</span></span>  
  
-   <span data-ttu-id="e6b4b-120">Last Child</span><span class="sxs-lookup"><span data-stu-id="e6b4b-120">Last Child</span></span>  
  
-   <span data-ttu-id="e6b4b-121">Last Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="e6b4b-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="e6b4b-122">First Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="e6b4b-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="e6b4b-123">Keine</span><span class="sxs-lookup"><span data-stu-id="e6b4b-123">None</span></span>  
  
 <span data-ttu-id="e6b4b-124">Mit dieser Option werden keine Measures mit einer regulären Aggregations Funktion geändert: `Sum` , `Min` , `Max` , `Count` oder `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="e6b4b-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="e6b4b-125">**Die Konto Dimension "Account", die Semiadditives Elemente enthält, wurde vom Assistenten erkannt. Die Elemente dieser Dimension werden vom Server gemäß dem semiadditiven Verhalten aggregiert, das für jeden Kontotyp angegeben ist.**</span><span class="sxs-lookup"><span data-stu-id="e6b4b-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="e6b4b-126">Bewirkt, dass alle Measures aus einer Measuregruppe, die durch eine Dimension des Typs Account dimensioniert wurden, vom System auf die Aggregationsfunktion By Account festgelegt und Elemente dieser Dimension gemäß dem semiadditiven Verhalten, das für den jeweiligen Kontotyp angegeben ist, vom Server aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6b4b-127">Diese Option wird standardmäßig ausgewählt, wenn der Assistent eine Dimension des Typs Account erkennt.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="e6b4b-128">**Semiadditives Verhalten für einzelne Measures definieren**</span><span class="sxs-lookup"><span data-stu-id="e6b4b-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="e6b4b-129">Wählt das semiadditive Verhalten für jedes Measure einzeln aus.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="e6b4b-130">Die Standardeinstellung ist `SUM` (vollständig additiv).</span><span class="sxs-lookup"><span data-stu-id="e6b4b-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6b4b-131">Diese Option wird standardmäßig ausgewählt, wenn der Assistent keine Dimension des Typs Account erkennt.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="e6b4b-132">Für die einzelnen Measures können Sie einen der Typen der semiadditiven Funktionalität auswählen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="e6b4b-133">Semiadditive Funktion</span><span class="sxs-lookup"><span data-stu-id="e6b4b-133">Semiadditive function</span></span>|<span data-ttu-id="e6b4b-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6b4b-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="e6b4b-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="e6b4b-135">Average of Children</span></span>|<span data-ttu-id="e6b4b-136">Die Aggregation eines Elements ist der Durchschnitt seiner untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="e6b4b-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="e6b4b-137">ByAccount</span></span>|<span data-ttu-id="e6b4b-138">Das System liest das für den Kontotyp angegebene semiadditive Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="e6b4b-139">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e6b4b-139">Count</span></span>|<span data-ttu-id="e6b4b-140">Die Aggregation ist eine Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="e6b4b-141">Distinct Count</span><span class="sxs-lookup"><span data-stu-id="e6b4b-141">Distinct Count</span></span>|<span data-ttu-id="e6b4b-142">Die Aggregation ist eine Anzahl von eindeutigen Elementen.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="e6b4b-143">First Child</span><span class="sxs-lookup"><span data-stu-id="e6b4b-143">First Child</span></span>|<span data-ttu-id="e6b4b-144">Der Elementwert wird als der Wert seines ersten untergeordneten Elements in der Zeitdimension ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="e6b4b-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="e6b4b-145">FirstNonEmpty</span></span>|<span data-ttu-id="e6b4b-146">Der Elementwert wird als der Wert seines ersten untergeordneten Elements in der Zeitdimension ausgewertet, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="e6b4b-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="e6b4b-147">LastChild</span></span>|<span data-ttu-id="e6b4b-148">Der Elementwert wird als der Wert seines letzten untergeordneten Elements in der Zeitdimension ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="e6b4b-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="e6b4b-149">LastNonEmpty</span></span>|<span data-ttu-id="e6b4b-150">Der Elementwert wird als der Wert seines letzten untergeordneten Elements in der Zeitdimension ausgewertet, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="e6b4b-151">Max</span><span class="sxs-lookup"><span data-stu-id="e6b4b-151">Max</span></span>|<span data-ttu-id="e6b4b-152">Die Standardfunktion für maximale Aggregation wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="e6b4b-153">Min.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-153">Min</span></span>|<span data-ttu-id="e6b4b-154">Die Standardfunktion für minimale Aggregation wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="e6b4b-155">Keine</span><span class="sxs-lookup"><span data-stu-id="e6b4b-155">None</span></span>|<span data-ttu-id="e6b4b-156">Keine Aggregation wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="e6b4b-157">SUM</span><span class="sxs-lookup"><span data-stu-id="e6b4b-157">Sum</span></span>|<span data-ttu-id="e6b4b-158">Die Standardfunktion zur Summierung wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="e6b4b-159">Vorhandenes semiadditive Verhalten wird nach Abschluss des Assistenten überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
