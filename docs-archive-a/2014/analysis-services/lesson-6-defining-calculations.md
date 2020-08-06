---
title: 'Lektion 6: Definieren von Berechnungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e0a1e354-e879-4eb8-bb2b-6c3809e32cb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e0b3f7e925a11146204dc6c55e9ddd6820ecb802
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616778"
---
# <a name="lesson-6-defining-calculations"></a><span data-ttu-id="9e785-102">Lektion 6: Definieren von Berechnungen</span><span class="sxs-lookup"><span data-stu-id="9e785-102">Lesson 6: Defining Calculations</span></span>
  <span data-ttu-id="9e785-103">In dieser Lektion erfahren Sie, wie Berechnungen definiert werden, bei denen es sich um MDX-Ausdrücke oder -Skripts (Multidimensional Expressions) handelt.</span><span class="sxs-lookup"><span data-stu-id="9e785-103">In this lesson, you learn to define calculations, which are Multidimensional Expressions (MDX) expressions or scripts.</span></span> <span data-ttu-id="9e785-104">Berechnungen ermöglichen es Ihnen, berechnete Elemente und benannte Mengen zu definieren und weitere Skriptbefehle auszuführen, um die Fähigkeiten eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Cubes zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="9e785-104">Calculations enable you to define calculated members, named sets, and execute other script commands to extend the capabilities of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span> <span data-ttu-id="9e785-105">Sie können z. B. einen Skriptbefehl ausführen, um einen Teilcube zu definieren und dann den Zellen im Teilcube eine Berechnung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9e785-105">For example, you can run a script command to define a subcube and then assign a calculation to the cells in the subcube.</span></span>  
  
 <span data-ttu-id="9e785-106">Wenn Sie eine neue Berechnung im Cube-Designer definieren, wird die Berechnung dem Bereich **Skriptplaner** der Registerkarte **Berechnungen** im Cube-Designer hinzugefügt, und die Felder für den jeweiligen Berechnungstyp werden in einem Berechnungsformular im Bereich **Berechnungsausdrücke** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e785-106">When you define a new calculation in Cube Designer, the calculation is added to the **Script Organizer** pane of the **Calculations** tab of Cube Designer, and the fields for the particular calculation type are displayed in a calculations form in the **Calculation Expressions** pane.</span></span> <span data-ttu-id="9e785-107">Berechnungen werden in der Reihenfolge ausgeführt, in der sie im Bereich **Skriptplaner** aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="9e785-107">Calculations are executed in the order in which they are listed in the **Script Organizer** pane.</span></span> <span data-ttu-id="9e785-108">Durch Klicken mit der rechten Maustaste auf eine bestimmte Berechnung und Auswählen von **Nach oben** oder **Nach unten**oder durch Klicken auf eine bestimmte Berechnung und Verwenden der Symbole **Nach oben** oder **Nach unten** auf der Symbolleiste der Registerkarte **Berechnungen** können Sie die Reihenfolge der Berechnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="9e785-108">You can reorder the calculations by right-clicking on a particular calculation and then selecting **Move Up** or **Move Down**, or by clicking a particular calculation and then using the **Move Up** or **Move Down** icons on the toolbar of the **Calculations** tab.</span></span>  
  
 <span data-ttu-id="9e785-109">Auf der Registerkarte **Berechnungen** können Sie neue Berechnungen hinzufügen und anzeigen oder vorhandene Berechnungen in einer der folgenden Ansichten im Bereich **Berechnungsausdrücke** bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="9e785-109">On the **Calculations** tab, you can add new calculations and view or edit existing calculations in the following views in the **Calculation Expressions** pane:</span></span>  
  
-   <span data-ttu-id="9e785-110">Formularansicht.</span><span class="sxs-lookup"><span data-stu-id="9e785-110">Form view.</span></span> <span data-ttu-id="9e785-111">In dieser Ansicht werden die Ausdrücke und Eigenschaften eines einzelnen Befehls in einem Grafikformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e785-111">This view shows the expressions and properties for a single command in a graphical format.</span></span> <span data-ttu-id="9e785-112">Beim Bearbeiten eines MDX-Skripts wird in der Formularansicht ein Ausdrucksfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e785-112">When you edit an MDX script, an expression box fills the Form view.</span></span>  
  
-   <span data-ttu-id="9e785-113">Skriptansicht.</span><span class="sxs-lookup"><span data-stu-id="9e785-113">Script view.</span></span> <span data-ttu-id="9e785-114">In dieser Ansicht werden alle Berechnungsskripts in einem Code-Editor angezeigt, mit dem Sie die Berechnungsskripts problemlos ändern können.</span><span class="sxs-lookup"><span data-stu-id="9e785-114">This view displays all calculation scripts in a code editor, which lets you easily change the calculation scripts.</span></span> <span data-ttu-id="9e785-115">Wird der Bereich **Berechnungsausdrücke** in der Skriptansicht angezeigt, ist der **Skriptplaner** ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="9e785-115">When the **Calculation Expressions** pane is in Script view, the **Script Organizer** is hidden.</span></span> <span data-ttu-id="9e785-116">In der Skriptansicht stehen Farbcodierung, Vervollständigen von Klammern, automatische Vervollständigung und MDX-Codebereiche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9e785-116">The Script view provides color coding, parenthesis matching, auto-complete, and MDX code regions.</span></span> <span data-ttu-id="9e785-117">Zur einfacheren Bearbeitung der MDX-Codebereiche können diese erweitert oder reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="9e785-117">You can expand or collapse the MDX code regions to make editing easier.</span></span>  
  
 <span data-ttu-id="9e785-118">Wenn Sie zwischen diesen Ansichten im Bereich **Berechnungsausdrücke** wechseln möchten, klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Formularansicht** oder **Skriptansicht** .</span><span class="sxs-lookup"><span data-stu-id="9e785-118">To switch between these views in the **Calculation Expressions** pane, click **Form View** or **Script View** on the toolbar of the **Calculations** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e785-119">Wird von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ein Syntaxfehler in einer Berechnung erkannt, wird die Formularansicht erst dann wieder angezeigt, wenn der Fehler in der Skriptansicht behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="9e785-119">If [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] detects a syntax error in any calculation, the Form view will not display until the error is corrected in the Script view.</span></span>  
  
 <span data-ttu-id="9e785-120">Sie können auch den Business Intelligence-Assistenten verwenden, um einem Cube bestimmte Berechnungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e785-120">You can also use the Business Intelligence Wizard to add certain calculations to a cube.</span></span> <span data-ttu-id="9e785-121">Mithilfe des Assistenten können Sie beispielsweise einem Cube Zeitintelligenz hinzufügen, indem Sie berechnete Elemente für zeitgestützte Berechnungen definieren, wie z. B. Zeitraum bis Datum, gleitender Durchschnitt oder zeitraumbasiertes Wachstum.</span><span class="sxs-lookup"><span data-stu-id="9e785-121">For example, you can use this wizard to add time intelligence to a cube, which means defining calculated members for time-related calculations such as period-to-date, moving averages, or period over period growth.</span></span> <span data-ttu-id="9e785-122">Weitere Informationen finden Sie unter [Definieren von Zeitintelligenzberechnungen mithilfe des Business Intelligence-Assistenten](multidimensional-models/define-time-intelligence-calculations-using-the-business-intelligence-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9e785-122">For more information, see [Define Time Intelligence Calculations using the Business Intelligence Wizard](multidimensional-models/define-time-intelligence-calculations-using-the-business-intelligence-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9e785-123">Auf der Registerkarte **Berechnungen** beginnt das Berechnungsskript mit dem CALCULATE-Befehl.</span><span class="sxs-lookup"><span data-stu-id="9e785-123">On the **Calculations** tab, the calculation script starts with the CALCULATE command.</span></span> <span data-ttu-id="9e785-124">Über den CALCULATE-Befehl wird die Aggregation der Zellen im Cube gesteuert; Sie sollten diesen Befehl nur bearbeiten, wenn Sie die Aggregation der Cubezellen manuell angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9e785-124">The CALCULATE command controls the aggregation of the cells in the cube and you should edit this command only if you intend to manually specify how the cube cells should be aggregated.</span></span>  
  
 <span data-ttu-id="9e785-125">Weitere Informationen finden Sie unter [Berechnungen](multidimensional-models-olap-logical-cube-objects/calculations.md)und [Berechnungen in mehrdimensionalen Modellen](multidimensional-models/calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="9e785-125">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), and [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e785-126">Für alle Lektionen in diesem Lernprogramm sind abgeschlossene Projekte online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e785-126">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="9e785-127">Sie können jede Lektion aufrufen, indem Sie ein abgeschlossenes Projekt aus der vorherigen Lektion als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e785-127">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="9e785-128">[Klicken Sie hier](https://go.microsoft.com/fwlink/?LinkID=221866) , um die Beispielprojekte für dieses Lernprogramm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="9e785-128">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="9e785-129">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="9e785-129">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="9e785-130">Definieren berechneter Elemente</span><span class="sxs-lookup"><span data-stu-id="9e785-130">Defining Calculated Members</span></span>](lesson-6-1-defining-calculated-members.md)  
 <span data-ttu-id="9e785-131">In dieser Aufgabe erfahren Sie, wie berechnete Elemente definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e785-131">In this task, you learn to define calculated members.</span></span>  
  
 [<span data-ttu-id="9e785-132">Definieren von benannten Mengen</span><span class="sxs-lookup"><span data-stu-id="9e785-132">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
 <span data-ttu-id="9e785-133">In diesem Task erfahren Sie, wie benannte Mengen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e785-133">In this task, you learn to define named sets.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9e785-134">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="9e785-134">Next Lesson</span></span>  
 [<span data-ttu-id="9e785-135">Lektion 7: Definieren von KPIs &#40;Key Performance Indicator&#41;</span><span class="sxs-lookup"><span data-stu-id="9e785-135">Lesson 7: Defining Key Performance Indicators &#40;KPIs&#41;</span></span>](lesson-7-defining-key-performance-indicators-kpis.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e785-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e785-136">See Also</span></span>  
 <span data-ttu-id="9e785-137">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e785-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="9e785-138">[Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="9e785-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="9e785-139">[Benannte Mengen erstellen](multidimensional-models/create-named-sets.md) </span><span class="sxs-lookup"><span data-stu-id="9e785-139">[Create Named Sets](multidimensional-models/create-named-sets.md) </span></span>  
 [<span data-ttu-id="9e785-140">Erstellen von berechneten Elementen</span><span class="sxs-lookup"><span data-stu-id="9e785-140">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  