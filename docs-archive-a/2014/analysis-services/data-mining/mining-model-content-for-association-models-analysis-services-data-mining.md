---
title: Mining Modell Inhalt von Zuordnungs Modellen (Analysis Services-Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616834"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="31c0c-102">Miningmodellinhalt von Zuordnungsmodellen (Analysis Services – Data Mining)</span><span class="sxs-lookup"><span data-stu-id="31c0c-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="31c0c-103">In diesem Thema wird der Miningmodellinhalt beschrieben, der Modellen eigen ist, die den [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules-Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="31c0c-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="31c0c-104">Eine Erläuterung der allgemeinen Miningmodellinhalte, die für alle Modelltypen gelten, und Statistikterminologie finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="31c0c-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="31c0c-105">Grundlegendes zur Struktur von Zuordnungsmodellen</span><span class="sxs-lookup"><span data-stu-id="31c0c-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="31c0c-106">Ein Zuordnungsmodell besitzt eine einfache Struktur.</span><span class="sxs-lookup"><span data-stu-id="31c0c-106">An association model has a simple structure.</span></span> <span data-ttu-id="31c0c-107">Jedes Modell verfügt über einen einzigen übergeordneten Knoten, der das Modell und seine Metadaten darstellt, und jeder übergeordnete Knoten enthält eine einfache Liste der Itemsets und Regeln.</span><span class="sxs-lookup"><span data-stu-id="31c0c-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="31c0c-108">Die Itemsets und Regeln werden nicht in Baumstrukturen dargestellt, sie werden, wie im folgenden Diagramm gezeigt, zuerst nach Itemsets und anschließend nach Regeln geordnet.</span><span class="sxs-lookup"><span data-stu-id="31c0c-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="31c0c-109">![Struktur des Modellinhalts für Zuordnungsmodelle](../media/modelcontentstructure-assoc.gif "Struktur des Modellinhalts für Zuordnungsmodelle")</span><span class="sxs-lookup"><span data-stu-id="31c0c-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="31c0c-110">Jedes Itemset ist in seinem eigenen Knoten (NODE_TYPE = 7) enthalten.</span><span class="sxs-lookup"><span data-stu-id="31c0c-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="31c0c-111">Der *Knoten* enthält die Definition des Itemsets, die Anzahl der Fälle, die dieses Itemset enthalten, sowie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="31c0c-112">Auch jede Regel ist in ihrem eigenen Knoten (NODE_TYPE = 8) enthalten.</span><span class="sxs-lookup"><span data-stu-id="31c0c-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="31c0c-113">Eine *Regel* beschreibt ein allgemeines Muster dafür, wie Elemente zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31c0c-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="31c0c-114">Eine Regel ist wie eine IF-THEN-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="31c0c-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="31c0c-115">Die linke Seite der Regel enthält eine vorhandene Bedingung oder einen Satz von Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="31c0c-116">Die rechte Seite der Regel enthält das Element des Datasets, das normalerweise den Bedingungen auf der linken Seite zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="31c0c-117">**Hinweis** Wenn Sie die Regeln oder die Itemsets extrahieren möchten, können Sie eine Abfrage einsetzen, die nur den gewünschten Knotentyp zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="31c0c-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="31c0c-118">Weitere Informationen finden Sie unter [Beispiele für Zuordnungsmodellabfragen](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="31c0c-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="31c0c-119">Modellinhalt eines Zuordnungsmodells</span><span class="sxs-lookup"><span data-stu-id="31c0c-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="31c0c-120">In diesem Abschnitt werden nur diejenigen Spalten des Miningmodellinhalts detaillierter und anhand von Beispielen erläutert, die für Zuordnungsmodelle relevant sind.</span><span class="sxs-lookup"><span data-stu-id="31c0c-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="31c0c-121">Informationen zu den allgemeinen Spalten im Schemarowset, z.B. MODEL_CATALOG und MODEL_NAME, finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="31c0c-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="31c0c-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="31c0c-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="31c0c-123">Name der Datenbank, in der das Modell gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="31c0c-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="31c0c-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="31c0c-124">MODEL_NAME</span></span>  
 <span data-ttu-id="31c0c-125">Name des Modells.</span><span class="sxs-lookup"><span data-stu-id="31c0c-125">Name of the model.</span></span>  
  
 <span data-ttu-id="31c0c-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="31c0c-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="31c0c-127">Die Namen der Attribute, die diesem Knoten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="31c0c-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="31c0c-128">NODE_NAME</span></span>  
 <span data-ttu-id="31c0c-129">Der Name des Knotens.</span><span class="sxs-lookup"><span data-stu-id="31c0c-129">The name of the node.</span></span> <span data-ttu-id="31c0c-130">Bei einem Zuordnungsmodell enthält diese Spalte den gleichen Wert wie NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="31c0c-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="31c0c-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="31c0c-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="31c0c-132">Der eindeutige Name des Knotens.</span><span class="sxs-lookup"><span data-stu-id="31c0c-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="31c0c-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="31c0c-133">NODE_TYPE</span></span>  
 <span data-ttu-id="31c0c-134">Ein Zuordnungsmodell gibt nur die folgenden Knotentypen aus:</span><span class="sxs-lookup"><span data-stu-id="31c0c-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="31c0c-135">Knotentyp-ID</span><span class="sxs-lookup"><span data-stu-id="31c0c-135">Node Type ID</span></span>|<span data-ttu-id="31c0c-136">type</span><span class="sxs-lookup"><span data-stu-id="31c0c-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="31c0c-137">1 (Model)</span><span class="sxs-lookup"><span data-stu-id="31c0c-137">1 (Model)</span></span>|<span data-ttu-id="31c0c-138">Stammknoten oder übergeordneter Knoten</span><span class="sxs-lookup"><span data-stu-id="31c0c-138">Root or parent node.</span></span>|  
|<span data-ttu-id="31c0c-139">7 (Itemset)</span><span class="sxs-lookup"><span data-stu-id="31c0c-139">7 (Itemset)</span></span>|<span data-ttu-id="31c0c-140">Ein Itemset oder Auflistung von Attribut/Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="31c0c-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="31c0c-141">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="31c0c-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="31c0c-142">oder</span><span class="sxs-lookup"><span data-stu-id="31c0c-142">or</span></span><br /><br /> <span data-ttu-id="31c0c-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="31c0c-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="31c0c-144">8 (Regel)</span><span class="sxs-lookup"><span data-stu-id="31c0c-144">8 (Rule)</span></span>|<span data-ttu-id="31c0c-145">Eine Regel, die definiert, in welcher Beziehung Elemente zueinander stehen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="31c0c-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31c0c-146">Example:</span></span><br /><br /> <span data-ttu-id="31c0c-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="31c0c-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="31c0c-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="31c0c-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="31c0c-149">Eine Bezeichnung oder Beschriftung, die dem Knoten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="31c0c-150">**Itemsetknoten** Eine durch Trennzeichen getrennte Liste von Elementen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="31c0c-151">**Regelknoten** Enthält die linke und die rechte Seite der Regel.</span><span class="sxs-lookup"><span data-stu-id="31c0c-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="31c0c-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="31c0c-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="31c0c-153">Gibt die Anzahl von untergeordneten Elementen des aktuellen Knotens an.</span><span class="sxs-lookup"><span data-stu-id="31c0c-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="31c0c-154">**Übergeordneter Knoten** Gibt die Gesamtzahl von Itemsets plus Regeln an.</span><span class="sxs-lookup"><span data-stu-id="31c0c-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31c0c-155">Eine Aufschlüsselung der Anzahl von Itemsets und Regeln finden Sie unter NODE_DESCRIPTION für den Stammknoten des Modells.</span><span class="sxs-lookup"><span data-stu-id="31c0c-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="31c0c-156">**Itemset- oder Regelknoten** Stets 0.</span><span class="sxs-lookup"><span data-stu-id="31c0c-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="31c0c-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="31c0c-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="31c0c-158">Der eindeutige Name des dem Knoten übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="31c0c-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="31c0c-159">Über **geordneter Knoten** Immer NULL.</span><span class="sxs-lookup"><span data-stu-id="31c0c-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="31c0c-160">**Itemset- oder Regelknoten** Stets 0.</span><span class="sxs-lookup"><span data-stu-id="31c0c-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="31c0c-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31c0c-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="31c0c-162">Eine benutzerfreundliche Beschreibung des Knoteninhalts.</span><span class="sxs-lookup"><span data-stu-id="31c0c-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="31c0c-163">**Übergeordneter Knoten** Enthält eine durch Trennzeichen getrennte Liste der folgenden Informationen über das Modell:</span><span class="sxs-lookup"><span data-stu-id="31c0c-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="31c0c-164">Element</span><span class="sxs-lookup"><span data-stu-id="31c0c-164">Item</span></span>|<span data-ttu-id="31c0c-165">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="31c0c-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="31c0c-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="31c0c-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="31c0c-167">Anzahl aller Itemsets im Modell.</span><span class="sxs-lookup"><span data-stu-id="31c0c-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="31c0c-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="31c0c-168">RULE_COUNT</span></span>|<span data-ttu-id="31c0c-169">Anzahl aller Regeln im Modell.</span><span class="sxs-lookup"><span data-stu-id="31c0c-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="31c0c-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="31c0c-170">MIN_SUPPORT</span></span>|<span data-ttu-id="31c0c-171">Die minimale Unterstützung für jedes einzelnes Itemset.</span><span class="sxs-lookup"><span data-stu-id="31c0c-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="31c0c-172">**Hinweis** Dieser Wert kann sich von dem Wert unterscheiden, den Sie für den *MINIMUM_SUPPORT* -Parameter festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="31c0c-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="31c0c-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="31c0c-173">MAX_SUPPORT</span></span>|<span data-ttu-id="31c0c-174">Die maximale Unterstützung für jedes einzelne Itemset.</span><span class="sxs-lookup"><span data-stu-id="31c0c-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="31c0c-175">**Hinweis** Dieser Wert kann sich von dem Wert unterscheiden, den Sie für den *MAXIMUM_SUPPORT* -Parameter festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="31c0c-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="31c0c-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="31c0c-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="31c0c-177">Die Größe des kleinsten Itemsets, die als Anzahl von Elementen dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31c0c-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="31c0c-178">Ein Wert von 0 gibt an, dass der `Missing`-Status als unabhängiges Element behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="31c0c-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="31c0c-179">**Hinweis** Der Standardwert des *MINIMUM_ITEMSET_SIZE* -Parameters ist 1.</span><span class="sxs-lookup"><span data-stu-id="31c0c-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="31c0c-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="31c0c-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="31c0c-181">Gibt die Größe des größten Itemsets an, das gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="31c0c-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="31c0c-182">**Hinweis** Dieser Wert wird durch den Wert beschränkt, den Sie bei der Erstellung des Modells für den *MAX_ITEMSET_SIZE* -Parameter festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="31c0c-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="31c0c-183">Der erste Wert kann den anderen Wert nie übersteigen, aber er kann kleiner sein.</span><span class="sxs-lookup"><span data-stu-id="31c0c-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="31c0c-184">Der Standardwert ist 3.</span><span class="sxs-lookup"><span data-stu-id="31c0c-184">The default value is 3.</span></span>|  
|<span data-ttu-id="31c0c-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="31c0c-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="31c0c-186">Die minimale Wahrscheinlichkeit, die für jedes einzelne Itemset oder eine Regel im Modell erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="31c0c-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="31c0c-187">Beispiel: 0,400390625</span><span class="sxs-lookup"><span data-stu-id="31c0c-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="31c0c-188">**Hinweis** Bei Itemsets ist dieser Wert immer größer als der Wert, den Sie bei der Erstellung des Modells für den *MINIMUM_PROBABILITY* -Parameter festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="31c0c-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="31c0c-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="31c0c-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="31c0c-190">Die maximale Wahrscheinlichkeit, die für jedes einzelnes Itemset oder eine Regel im Modell erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="31c0c-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="31c0c-191">Beispiel: 1</span><span class="sxs-lookup"><span data-stu-id="31c0c-191">Example: 1</span></span><br /><br /> <span data-ttu-id="31c0c-192">**Hinweis** Es gibt keinen Parameter, der die maximale Wahrscheinlichkeit von Itemsets einschränkt.</span><span class="sxs-lookup"><span data-stu-id="31c0c-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="31c0c-193">Wenn Sie Elemente ausschließen möchten, die zu häufig vorkommen, verwenden Sie stattdessen den *MAXIMUM_SUPPORT* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="31c0c-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="31c0c-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="31c0c-194">MIN_LIFT</span></span>|<span data-ttu-id="31c0c-195">Die Mindestmenge an Lift, die vom Modell für ein beliebiges Itemset bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31c0c-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="31c0c-196">Beispiel: 0,4309369632511</span><span class="sxs-lookup"><span data-stu-id="31c0c-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="31c0c-197">Hinweis: Wenn Sie den minimalen Lift kennen, können Sie leichter bestimmen, ob der Lift für irgendein einzelnes Itemset signifikant ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="31c0c-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="31c0c-198">MAX_LIFT</span></span>|<span data-ttu-id="31c0c-199">Die Höchstmenge an Lift, die vom Modell für ein beliebiges Itemset bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31c0c-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="31c0c-200">Beispiel: 1,95758227647523 **Hinweis** Wenn Sie den maximalen Lift kennen, können Sie leichter bestimmen, ob der Lift für irgendein einzelnes Itemset signifikant ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="31c0c-201">**Itemsetknoten** Diese Knoten enthalten eine Liste der Elemente, die als durch Trennzeichen getrennte Textzeichenfolge angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="31c0c-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="31c0c-202">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31c0c-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="31c0c-203">Dies bedeutet, Trekkingreifen und Wasserflasche wurden zusammen gekauft.</span><span class="sxs-lookup"><span data-stu-id="31c0c-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="31c0c-204">**Regelknoten** Diese Knoten enthalten die linke und die rechte Seite der Regel, die durch einen Pfeil voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="31c0c-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="31c0c-205">Beispiel: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span><span class="sxs-lookup"><span data-stu-id="31c0c-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="31c0c-206">Das bedeutet, dass jemand, der die Artikel Trekkingreifen und Wasserflasche kauft, wahrscheinlich auch den Artikel Fahrradkappe kauft.</span><span class="sxs-lookup"><span data-stu-id="31c0c-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="31c0c-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="31c0c-207">NODE_RULE</span></span>  
 <span data-ttu-id="31c0c-208">Ein XML-Fragment, das die Regel oder das Itemset beschreibt, die bzw. das im Knoten eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="31c0c-209">**Übergeordneter Knoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-210">**Itemsetknoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-211">**Regelknoten** Das XML-Fragment enthält zusätzliche nützliche Informationen über die Regel, beispielsweise Unterstützung, Vertrauen und die Anzahl der Elemente und die ID des Knotens, der die linke Seite der Regel darstellt.</span><span class="sxs-lookup"><span data-stu-id="31c0c-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="31c0c-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="31c0c-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="31c0c-213">Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-213">Blank.</span></span>  
  
 <span data-ttu-id="31c0c-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="31c0c-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="31c0c-215">Ein Wahrscheinlichkeits- oder ein Vertrauenswert, der dem Itemset oder der Regel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="31c0c-216">**Übergeordneter Knoten** Stets 0.</span><span class="sxs-lookup"><span data-stu-id="31c0c-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="31c0c-217">**Itemsetknoten** Wahrscheinlichkeit des Itemsets.</span><span class="sxs-lookup"><span data-stu-id="31c0c-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="31c0c-218">**Regelknoten** Vertrauenswert für die Regel.</span><span class="sxs-lookup"><span data-stu-id="31c0c-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="31c0c-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="31c0c-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="31c0c-220">Identisch mit NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="31c0c-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="31c0c-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="31c0c-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="31c0c-222">Die Tabelle enthält sehr unterschiedliche Informationen, je nachdem, ob der Knoten ein Itemset oder eine Regel ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="31c0c-223">**Übergeordneter Knoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-224">**Itemsetknoten** Listet jedes Element im Itemset zusammen mit einem Wahrscheinlichkeits- und Unterstützungswert auf.</span><span class="sxs-lookup"><span data-stu-id="31c0c-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="31c0c-225">Wenn das Itemset beispielsweise zwei Itemset enthält, wird der Name jedes Produkts zusammen mit der Anzahl der Fälle aufgeführt, die jedes Produkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="31c0c-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="31c0c-226">**Regelknoten** Enthält zwei Zeilen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="31c0c-227">Die erste Zeile enthält das Attribut von der rechten Seite der Regel, d. das vorhergesagte Element zusammen mit einem Vertrauenswert.</span><span class="sxs-lookup"><span data-stu-id="31c0c-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="31c0c-228">Die zweite Zeile ist Zuordnungsmodellen eigen. Sie enthält einen Zeiger auf das Itemset auf der rechten Seite der Regel.</span><span class="sxs-lookup"><span data-stu-id="31c0c-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="31c0c-229">Der Zeiger wird in der ATTRIBUTE_VALUE-Spalte als ID des Itemset dargestellt, das nur das Element von der rechten Seite enthält.</span><span class="sxs-lookup"><span data-stu-id="31c0c-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="31c0c-230">Wenn die Regel beispielsweise `If {A,B} Then {C}`lautet, enthält die Tabelle den Namen des Elements `{C}`und die ID des Knotens, der das Itemset für Element C enthält.</span><span class="sxs-lookup"><span data-stu-id="31c0c-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="31c0c-231">Dieser Zeiger ist nützlich, weil Sie anhand des Itemsetknotens bestimmen können, wie viele Fälle insgesamt das Produkt von der rechten Seite beinhalten.</span><span class="sxs-lookup"><span data-stu-id="31c0c-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="31c0c-232">Die Fälle, für welche die Regel `If {A,B} Then {C}` gilt, stellen eine Teilmenge der Fälle dar, die im Itemset für `{C}`aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="31c0c-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="31c0c-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="31c0c-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="31c0c-234">Die Anzahl der Fälle, die diesen Knoten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="31c0c-235">**Übergeordneter Knoten** Die Anzahl der Fälle im Modell.</span><span class="sxs-lookup"><span data-stu-id="31c0c-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="31c0c-236">**Itemsetknoten** Anzahl der Fälle, die alle im Itemset befindlichen Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="31c0c-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="31c0c-237">**Regelknoten** Die Anzahl der Fälle, die alle in der Regel enthaltenen Elemente umfassen.</span><span class="sxs-lookup"><span data-stu-id="31c0c-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="31c0c-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="31c0c-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="31c0c-239">Enthält unterschiedliche Informationen, je nachdem, ob der Knoten ein Itemset oder eine Regel ist.</span><span class="sxs-lookup"><span data-stu-id="31c0c-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="31c0c-240">**Übergeordneter Knoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-241">**Itemsetknoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-242">**Regelknoten** Die ID des Itemset, das die Elemente von der linken Seite der Regel enthält.</span><span class="sxs-lookup"><span data-stu-id="31c0c-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="31c0c-243">Wenn die Regel beispielsweise `If {A,B} Then {C}`lautet, enthält diese Spalte die ID des Itemsets, das nur `{A,B}`enthält.</span><span class="sxs-lookup"><span data-stu-id="31c0c-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="31c0c-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="31c0c-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="31c0c-245">**Übergeordneter Knoten** Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="31c0c-246">**Itemsetknoten** Wichtigkeitsbewertung für das Itemset.</span><span class="sxs-lookup"><span data-stu-id="31c0c-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="31c0c-247">**Regelknoten** Wichtigkeitsbewertung für das Itemset.</span><span class="sxs-lookup"><span data-stu-id="31c0c-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31c0c-248">Die Wichtigkeit wird für Itemsets und Regeln auf unterschiedliche Weise berechnet.</span><span class="sxs-lookup"><span data-stu-id="31c0c-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="31c0c-249">Weitere Informationen finden Sie unter [Technische Referenz für den Microsoft Association-Algorithmus](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="31c0c-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="31c0c-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="31c0c-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="31c0c-251">Leer.</span><span class="sxs-lookup"><span data-stu-id="31c0c-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c0c-252">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31c0c-252">See Also</span></span>  
 <span data-ttu-id="31c0c-253">[Mining Modell Inhalt &#40;Analysis Services Data Mining-&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="31c0c-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="31c0c-254">[Microsoft Association-Algorithmus](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="31c0c-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="31c0c-255">Beispiele für Zuordnungsmodellabfragen</span><span class="sxs-lookup"><span data-stu-id="31c0c-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
