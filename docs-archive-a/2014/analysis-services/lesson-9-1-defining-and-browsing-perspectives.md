---
title: Definieren und Durchsuchen von Perspektiven | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718859"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="f4990-102">Definieren und Durchsuchen von Perspektiven</span><span class="sxs-lookup"><span data-stu-id="f4990-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="f4990-103">Mithilfe von Perspektiven kann die Ansicht eines Cubes für bestimmte Zwecke vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="f4990-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="f4990-104">Standardmäßig können Benutzer alle Elemente in einem Cube sehen, für den sie die entsprechenden Berechtigungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="f4990-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="f4990-105">Wenn Benutzer einen ganzen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Cube anzeigen, wird ihnen die Standardperspektive des Cubes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4990-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="f4990-106">Die Ansicht des gesamten Cubes kann auf Benutzer äußerst komplex wirken, vor allem dann, wenn sie nur mit einem kleinen Teil des Cubes arbeiten, um ihre Anforderungen hinsichtlich Business Intelligence und Berichterstellung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f4990-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="f4990-107">Zur Reduzierung der offensichtlichen Komplexität eines Cubes können Sie anzeigbare Teilmengen des Cubes (so genannte *Perspektiven*) erstellen, mit denen Benutzern nur ein Teil der Measuregruppen, Measures, Dimensionen, Attribute, Hierarchien, Key Performance Indicators (KPIs), Aktionen und berechneten Elemente im Cube angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4990-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="f4990-108">Dies kann insbesondere bei der Arbeit mit Clientanwendungen nützlich sein, die für eine frühere Version von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="f4990-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f4990-109">Diese Clients kennen z. B. keine Anzeigeordner oder Perspektiven, aber eine Perspektive wird auf älteren Clients wie ein Cube angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4990-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="f4990-110">Weitere Informationen finden Sie unter [Perspektiven](multidimensional-models-olap-logical-cube-objects/perspectives.md), und [Perspektiven in mehrdimensionalen Modellen](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="f4990-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4990-111">Eine Perspektive ist kein Sicherheitsmechanismus, sondern ein Tool zur Verbesserung des Verhaltens der Benutzerumgebung.</span><span class="sxs-lookup"><span data-stu-id="f4990-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="f4990-112">Die gesamte Sicherheit einer Perspektive erbt diese vom zugrunde liegenden Cube.</span><span class="sxs-lookup"><span data-stu-id="f4990-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="f4990-113">Im Rahmen der Tasks in diesem Thema definieren Sie verschiedene Perspektiven und durchsuchen dann den Cube über jede dieser neuen Perspektiven.</span><span class="sxs-lookup"><span data-stu-id="f4990-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="f4990-114">Definieren einer Internet Sales-Perspektive</span><span class="sxs-lookup"><span data-stu-id="f4990-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="f4990-115">Öffnen Sie den Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube, und klicken Sie anschließend auf die Registerkarte **Perspektiven** .</span><span class="sxs-lookup"><span data-stu-id="f4990-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="f4990-116">Alle Objekte und ihre Objekttypen werden im Bereich **Perspektiven** angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f4990-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f4990-117">![Perspektivenbereich des Cube-Designers](../../2014/tutorials/media/l9-perspectives-1.gif "Perspektivenbereich des Cube-Designers")</span><span class="sxs-lookup"><span data-stu-id="f4990-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="f4990-118">Klicken Sie auf der Symbolleiste der Registerkarte **Perspektiven** auf die Schaltfläche **Neue Perspektive** .</span><span class="sxs-lookup"><span data-stu-id="f4990-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="f4990-119">In der **Perspektivenname** -Spalte wird eine neue Perspektive mit dem Standardnamen **Perspektive**angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f4990-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="f4990-120">Die Kontrollkästchen aller Objekte sind so lange aktiviert, bis Sie eines der Kontrollkästchen für ein Objekt deaktivieren. Diese Perspektive entspricht der Standardperspektive dieses Cubes.</span><span class="sxs-lookup"><span data-stu-id="f4990-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="f4990-121">![Neue Perspektive in der Spalte "Perspektivenname"](../../2014/tutorials/media/l9-perspectives-2.gif "Neue Perspektive in der Spalte "Perspektivenname"")</span><span class="sxs-lookup"><span data-stu-id="f4990-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="f4990-122">Ändern Sie den Perspektiven Namen in `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="f4990-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="f4990-123">Legen Sie in der nächsten Zeile **Internet Sales-Sales Amount**als Standardmeasure fest.</span><span class="sxs-lookup"><span data-stu-id="f4990-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="f4990-124">Wenn Benutzer den Cube mithilfe dieser Perspektive durchsuchen, sehen sie dieses Measure, es sei denn, sie geben ein anderes Measure an.</span><span class="sxs-lookup"><span data-stu-id="f4990-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4990-125">Sie können auch das Standardmeasure für den gesamten [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube im Eigenschaftenfenster der Registerkarte **Cubestruktur** für den Cube festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4990-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="f4990-126">Deaktivieren Sie die Kontrollkästchen der folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="f4990-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f4990-127">`Reseller Sales`Measure-Gruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f4990-128">**Sales Quotas** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-129">**Sales Quotas 1** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-130">**Reseller** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-131">**Reseller Geography** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-132">**Sales Territory** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-133">**Employee** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-134">**Promotion** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-135">**Reseller Revenue** -KPI</span><span class="sxs-lookup"><span data-stu-id="f4990-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="f4990-136">Benannte Menge**Large Resellers**</span><span class="sxs-lookup"><span data-stu-id="f4990-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="f4990-137">Berechnetes Element**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="f4990-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-138">Berechnetes Element**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="f4990-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-139">Berechnetes Element**Reseller GPM**</span><span class="sxs-lookup"><span data-stu-id="f4990-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-140">Berechnetes Element**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="f4990-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-141">Berechnetes Element**Reseller Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="f4990-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-142">Berechnetes Element**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="f4990-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="f4990-143">Diese Objekte stehen nicht im Zusammenhang mit Internetverkäufen (Internet Sales).</span><span class="sxs-lookup"><span data-stu-id="f4990-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4990-144">Innerhalb der einzelnen Dimensionen können Sie zudem einzeln die benutzerdefinierten Hierarchien und Attribute auswählen, die in einer Perspektive angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4990-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="f4990-145">Definieren der Reseller Sales-Perspektive</span><span class="sxs-lookup"><span data-stu-id="f4990-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="f4990-146">Klicken Sie auf der Symbolleiste der Registerkarte **Perspektiven** auf die Schaltfläche **Neue Perspektive** .</span><span class="sxs-lookup"><span data-stu-id="f4990-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="f4990-147">Ändern Sie den Namen der neuen Perspektive in `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="f4990-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="f4990-148">Legen Sie **Reseller Sales-Sales Amount** als Standardmeasure fest.</span><span class="sxs-lookup"><span data-stu-id="f4990-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="f4990-149">Wenn Benutzer den Cube mithilfe dieser Perspektive durchsuchen, sehen sie dieses Measure, es sei denn, sie geben ein anderes Measure an.</span><span class="sxs-lookup"><span data-stu-id="f4990-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="f4990-150">Deaktivieren Sie die Kontrollkästchen der folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="f4990-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f4990-151">`Internet Sales`Measure-Gruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f4990-152">**Internet Sales Reason** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-153">**Customer** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-154">**Internet Sales Order Details** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-155">**Sales Reason** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-156">**Internet Sales Details Drillthrough Action** -Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="f4990-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="f4990-157">Berechnetes Element**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="f4990-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-158">Berechnetes Element**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="f4990-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-159">Berechnetes Element**Internet GPM**</span><span class="sxs-lookup"><span data-stu-id="f4990-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-160">Berechnetes Element**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="f4990-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-161">Berechnetes Element**Internet Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="f4990-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="f4990-162">Berechnetes Element**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="f4990-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="f4990-163">Diese Objekte stehen nicht im Zusammenhang mit Verkäufen durch Wiederverkäufer (Reseller Sales).</span><span class="sxs-lookup"><span data-stu-id="f4990-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="f4990-164">Definieren der Sales Summary-Perspektive</span><span class="sxs-lookup"><span data-stu-id="f4990-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="f4990-165">Klicken Sie auf der Symbolleiste der Registerkarte **Perspektiven** auf die Schaltfläche **Neue Perspektive** .</span><span class="sxs-lookup"><span data-stu-id="f4990-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="f4990-166">Ändern Sie den Namen der neuen Perspektive in `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="f4990-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4990-167">Es kann kein berechnetes Measure als Standardmeasure angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f4990-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="f4990-168">Deaktivieren Sie die Kontrollkästchen der folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="f4990-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f4990-169">`Internet Sales`Measure-Gruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f4990-170">`Reseller Sales`Measure-Gruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f4990-171">**Internet Sales Reason** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-172">**Sales Quotas** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-173">**Sales Quotas1** -Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="f4990-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="f4990-174">**Internet Sales Order Details** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-175">**Sales Reason** -Cubedimension</span><span class="sxs-lookup"><span data-stu-id="f4990-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="f4990-176">**Internet Sales Details Drillthrough Action** -Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="f4990-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="f4990-177">Aktivieren Sie die Kontrollkästchen der folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="f4990-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f4990-178">**Internet Sales Count** -Measure</span><span class="sxs-lookup"><span data-stu-id="f4990-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="f4990-179">**Reseller Sales Count** -Measure</span><span class="sxs-lookup"><span data-stu-id="f4990-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="f4990-180">Durchsuchen des Cubes durch die einzelnen Perspektiven</span><span class="sxs-lookup"><span data-stu-id="f4990-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="f4990-181">Klicken Sie im Menü **Erstellen** auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="f4990-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="f4990-182">Wechseln Sie nach erfolgreicher Bereitstellung zur Registerkarte **Browser** , und klicken Sie anschließend auf **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="f4990-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="f4990-183">Starten Sie Excel.</span><span class="sxs-lookup"><span data-stu-id="f4990-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="f4990-184">Durch In Excel analysieren werden Sie aufgefordert, die Perspektive auszuwählen, die beim Durchsuchen des Modells in Excel verwendet wird. Siehe dazu die folgende Abbildung.</span><span class="sxs-lookup"><span data-stu-id="f4990-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f4990-185">![Objekte für die Internet Sales-Perspektive](../../2014/tutorials/media/l9-perspectives-3.gif "Objekte für die Internet Sales-Perspektive")</span><span class="sxs-lookup"><span data-stu-id="f4990-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="f4990-186">Alternativ können Sie Excel vom Windows-Startmenü aus starten, eine Verbindung mit der Analysis Services Tutorial-Datenbank auf localhost definieren und eine Perspektive im Datenverbindungs-Assistenten auswählen, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f4990-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f4990-187">![Datenverbindungs-Assistent in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Datenverbindungs-Assistent in Excel")</span><span class="sxs-lookup"><span data-stu-id="f4990-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="f4990-188">Wählen Sie `Internet Sales` in der Liste **Perspektive** aus, und überprüfen Sie dann die Measures und Dimensionen im Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="f4990-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="f4990-189">Es werden nur die Objekte angezeigt, die für die Internet Sales-Perspektive angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="f4990-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="f4990-190">Erweitern Sie im Bereich Metadaten die Option **Measures**.</span><span class="sxs-lookup"><span data-stu-id="f4990-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="f4990-191">Beachten Sie, dass nur die `Internet Sales` Measure-Gruppe sowie die berechneten Elemente **Internet-GPM** und **Internet Sales für alle Produkte** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4990-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="f4990-192">Wählen Sie im Modell erneut Excel aus.</span><span class="sxs-lookup"><span data-stu-id="f4990-192">In the model, select Excel again.</span></span> <span data-ttu-id="f4990-193">Wählen Sie `Sales Summary`aus.</span><span class="sxs-lookup"><span data-stu-id="f4990-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="f4990-194">In jeder der Measuregruppen wird nur ein einzelnes Measure angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f4990-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f4990-195">![Measures Internet Sales und Reseller Sales](../../2014/tutorials/media/l9-perspectives-4.gif "Measures Internet Sales und Reseller Sales")</span><span class="sxs-lookup"><span data-stu-id="f4990-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f4990-196">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="f4990-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f4990-197">Definieren und Durchsuchen von Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="f4990-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4990-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4990-198">See Also</span></span>  
 <span data-ttu-id="f4990-199">[Eröffnen](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="f4990-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="f4990-200">Perspektiven in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="f4990-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
