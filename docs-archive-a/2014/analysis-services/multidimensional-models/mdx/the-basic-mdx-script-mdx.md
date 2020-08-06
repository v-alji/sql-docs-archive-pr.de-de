---
title: Das grundlegende MDX-Skript (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721898"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="1e72e-102">Grundlegendes MDX-Skript (MDX)</span><span class="sxs-lookup"><span data-stu-id="1e72e-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="1e72e-103">Ein MDX-Skript (Multidimensional Expressions) definiert den Berechnungsprozess für einen Cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e72e-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="1e72e-104">Es gibt zwei Arten von MDX-Skripts:</span><span class="sxs-lookup"><span data-stu-id="1e72e-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="1e72e-105">**Das MDX-Standardskript**</span><span class="sxs-lookup"><span data-stu-id="1e72e-105">**The default MDX script**</span></span>  
 <span data-ttu-id="1e72e-106">In dem Moment, in dem Sie einen Cube erstellen, erstellt [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ein MDX-Standardskript für den Cube.</span><span class="sxs-lookup"><span data-stu-id="1e72e-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="1e72e-107">In diesem Skript ist ein Berechnungsdurchlauf für den gesamten Cube definiert.</span><span class="sxs-lookup"><span data-stu-id="1e72e-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="1e72e-108">**Benutzerdefiniertes MDX-Skript**</span><span class="sxs-lookup"><span data-stu-id="1e72e-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="1e72e-109">Nachdem Sie einen Cube erstellt haben, können Sie benutzerdefinierte MDX-Skripts hinzufügen, um die Berechnungsmöglichkeiten für den Cube zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1e72e-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="1e72e-110">Das MDX-Standardskript</span><span class="sxs-lookup"><span data-stu-id="1e72e-110">The Default MDX Script</span></span>  
 <span data-ttu-id="1e72e-111">Das MDX-Standardskript, das [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] erstellt, wenn Sie einen Cube definieren, enthält eine einzige CALCULATE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e72e-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="1e72e-112">Diese einzige CALCULATE-Anweisung befindet sich am Anfang des MDX-Standardskripts und gibt an, dass beim ersten Berechnungsdurchlauf der gesamte Cube berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e72e-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="1e72e-113">Das MDX-Standardskript enthält außerdem die Skriptbefehle, die benannte Mengen, Zuweisungen und berechnete Elemente erstellen, die im Cube-Designer erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="1e72e-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="1e72e-114">fügt dem MDX-Standardskript Skriptbefehle direkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e72e-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="1e72e-115">Für jede benannte Menge im Cube gibt es im MDX-Standardskript eine entsprechende CREATE SET-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e72e-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="1e72e-116">Für jedes berechnete Element, das im Cube definiert ist, gibt es im MDX-Standardskript eine entsprechende CREATE MEMBER-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e72e-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="1e72e-117">Die Reihenfolge, die die Skriptbefehle, benannten Mengen und berechneten Elemente im MDX-Standardskript haben, können Sie im Cube-Designer über die Registerkarte **Berechnungen** festlegen.</span><span class="sxs-lookup"><span data-stu-id="1e72e-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="1e72e-118">Weitere Informationen zum Definieren von Berechnungen, die im MDX-Standardskript gespeichert werden, finden Sie unter [Berechnungen in mehrdimensionalen Modellen](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="1e72e-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="1e72e-119">Ist einem Cube kein MDX-Skript zugeordnet, nimmt der Cube das MDX-Standardskript an.</span><span class="sxs-lookup"><span data-stu-id="1e72e-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="1e72e-120">Einem Cube muss mindestens ein MDX-Skript zugeordnet sein, weil ein Cube anhand des MDX-Skripts das Berechnungsverhalten ermittelt.</span><span class="sxs-lookup"><span data-stu-id="1e72e-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="1e72e-121">Dies bedeutet, dass ein Cube, dem kein oder ein leeres MDX-Skript zugeordnet wurde, keine Zellen berechnen kann.</span><span class="sxs-lookup"><span data-stu-id="1e72e-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="1e72e-122">Wenn Sie Cubes programmgesteuert erstellen, entweder mit ASSL-Befehlen (Analysis Services Scripting Language) oder mit Analysis Management Objects (AMO), empfiehlt es sich, dass Sie ein MDX-Standardskript erstellen, das eine einzige CALCULATE-Anweisung für den Cube enthält.</span><span class="sxs-lookup"><span data-stu-id="1e72e-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="1e72e-123">Inhalt eines MDX-Skripts</span><span class="sxs-lookup"><span data-stu-id="1e72e-123">MDX Script Content</span></span>  
 <span data-ttu-id="1e72e-124">Ein MDX-Skript kann die folgenden Anweisungen und Ausdrücke enthalten:</span><span class="sxs-lookup"><span data-stu-id="1e72e-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="1e72e-125">Alle MDX-Skriptanweisungen</span><span class="sxs-lookup"><span data-stu-id="1e72e-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="1e72e-126">In einem MDX-Skript steuern MDX-Skriptbefehle den Kontext und den Gültigkeitsbereich von Berechnungen und verwalten das Verhalten anderer Anweisungen im MDX-Skript.</span><span class="sxs-lookup"><span data-stu-id="1e72e-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="1e72e-127">Zu dieser Kategorie gehören die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="1e72e-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="1e72e-128">Enen</span><span class="sxs-lookup"><span data-stu-id="1e72e-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="1e72e-129">Ge</span><span class="sxs-lookup"><span data-stu-id="1e72e-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="1e72e-130">Umfang</span><span class="sxs-lookup"><span data-stu-id="1e72e-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="1e72e-131">Weitere Informationen zu MDX-Skriptanweisungen finden Sie unter [MDX-Skriptanweisungen &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="1e72e-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="1e72e-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="1e72e-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="1e72e-133">Die CREATE MEMBER-Anweisung erstellt berechnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="1e72e-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="1e72e-134">Weitere Informationen zum Erstellen berechneter Elemente finden Sie unter [Erstellen von berechneten Elementen in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="1e72e-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="1e72e-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="1e72e-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="1e72e-136">Die CREATE SET-Anweisung erstellt benannte Mengen.</span><span class="sxs-lookup"><span data-stu-id="1e72e-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="1e72e-137">Weitere Informationen zum Erstellen von benannten Mengen finden Sie unter [Erstellen von benannten Mengen in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1e72e-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="1e72e-138">Bedingungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="1e72e-138">Conditional statements</span></span>  
 <span data-ttu-id="1e72e-139">Bedingte Anweisungen erweitern MDX-Skripts um logische Befehle mit Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="1e72e-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="1e72e-140">Zu dieser Kategorie gehören die Anweisungen [CASE](/sql/mdx/case-statement-mdx) und [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="1e72e-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="1e72e-141">Zuweisungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="1e72e-141">Assignment expressions</span></span>  
 <span data-ttu-id="1e72e-142">Ein Zuweisungsausdruck weist einem eingeschränkten Teilcube einen Ausdruck (z. B. einen Wert) zu.</span><span class="sxs-lookup"><span data-stu-id="1e72e-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="1e72e-143">Ein eingeschränkter Teilcubeausdruck ist eine Auflistung eingeschränkter Mengenausdrücke, die in einem MDX-Skript die "Kanten" eines Teilcubes definieren.</span><span class="sxs-lookup"><span data-stu-id="1e72e-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="1e72e-144">Der folgende Code zeigt die Syntax für einen eingeschränkten Teilcubeausdruck:</span><span class="sxs-lookup"><span data-stu-id="1e72e-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e72e-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e72e-145">See Also</span></span>  
 <span data-ttu-id="1e72e-146">[MDX-Sprachreferenz &#40;MDX-&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="1e72e-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="1e72e-147">Grundlegendes zu MDX-Skripts &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1e72e-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
