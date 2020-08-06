---
title: Definieren eines Cubes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608032"
---
# <a name="defining-a-cube"></a><span data-ttu-id="7d477-102">Definieren eines Cubes</span><span class="sxs-lookup"><span data-stu-id="7d477-102">Defining a Cube</span></span>
  <span data-ttu-id="7d477-103">Der Cube-Assistent unterstützt Sie beim Definieren der Measuregruppen und Dimensionen für einen Cube.</span><span class="sxs-lookup"><span data-stu-id="7d477-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="7d477-104">In der folgenden Aufgabe verwenden Sie den Cube-Assistenten, um einen Cube zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d477-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="7d477-105">So definieren Sie einen Cube und seine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d477-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="7d477-106">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Cubes**, und klicken Sie anschließend auf **Neuer Cube**.</span><span class="sxs-lookup"><span data-stu-id="7d477-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="7d477-107">Der Cube-Assistent wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d477-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="7d477-108">Klicken Sie auf der Seite **Willkommen beim Cube-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7d477-109">Überprüfen Sie, ob die Option **Vorhandene Tabellen verwenden** auf der Seite **Erstellungsmethode auswählen** ausgewählt ist, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7d477-110">Überprüfen Sie auf der Seite **Measuregruppentabellen auswählen** , ob die **Adventure Works DW 2012** -Datenquellensicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7d477-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="7d477-111">Klicken Sie auf **Vorschlagen** , damit der Cube-Assistent Tabellen zum Erstellen der Measuregruppen vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="7d477-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="7d477-112">Der Assistent untersucht die Tabellen und schlägt **InternetSales** als Measuregruppentabelle vor.</span><span class="sxs-lookup"><span data-stu-id="7d477-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="7d477-113">Measuregruppentabellen, die auch als Faktentabellen bezeichnet werden, enthalten die für Sie interessanten Measures wie die Anzahl von verkauften Einheiten.</span><span class="sxs-lookup"><span data-stu-id="7d477-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="7d477-114">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="7d477-115">Überprüfen Sie auf der Seite **Measures auswählen** die ausgewählten Measures in der Measuregruppe **Internetverkäufe** , und deaktivieren Sie anschließend die Kontrollkästchen für die folgenden Measures:</span><span class="sxs-lookup"><span data-stu-id="7d477-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="7d477-116">**Promotion Key**</span><span class="sxs-lookup"><span data-stu-id="7d477-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="7d477-117">**Currency Key**</span><span class="sxs-lookup"><span data-stu-id="7d477-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="7d477-118">**Sales Territory Key**</span><span class="sxs-lookup"><span data-stu-id="7d477-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="7d477-119">**Revision Number**</span><span class="sxs-lookup"><span data-stu-id="7d477-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="7d477-120">Vom Assistenten werden standardmäßig als Measures alle numerischen Spalten in der Faktentabelle ausgewählt, die nicht mit Dimensionen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="7d477-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="7d477-121">Bei diesen vier Spalten handelt es sich allerdings nicht um tatsächliche Measures.</span><span class="sxs-lookup"><span data-stu-id="7d477-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="7d477-122">Die ersten drei sind Schlüsselwerte, die die Faktentabelle mit Dimensionstabellen verknüpfen, die nicht in der anfänglichen Version dieses Cubes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d477-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="7d477-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="7d477-124">Stellen Sie auf der Seite **Vorhandene Dimensionen auswählen** sicher, dass die zuvor erstellte **Date** -Dimension ausgewählt ist, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="7d477-125">Auf der Seite **Neue Dimensionen auswählen** können Sie die neue Dimension auswählen, die erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d477-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="7d477-126">Überprüfen Sie dazu, ob die Kontrollkästchen **Customer**, **Geography**und **Product** aktiviert sind, und deaktivieren Sie das Kontrollkästchen **InternetSales** .</span><span class="sxs-lookup"><span data-stu-id="7d477-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="7d477-127">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7d477-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="7d477-128">Ändern Sie auf der Seite **Assistenten abschließen** den Namen des Cubes in `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="7d477-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="7d477-129">Im Vorschaubereich können Sie die Measuregruppe **InternetSales** und ihre Measures sehen.</span><span class="sxs-lookup"><span data-stu-id="7d477-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="7d477-130">Ihnen werden auch die Dimensionen **Date**, **Customer** und **Product** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d477-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="7d477-131">Klicken Sie auf **Fertig stellen**, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7d477-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="7d477-132">Im Projektmappen-Explorer im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Tutorialprojekt wird der Cube des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Tutorials im Ordner **Cubes** angezeigt, und die Customer- und Product-Datenbankdimensionen werden im Ordner **Dimensionen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d477-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="7d477-133">Zusätzlich wird auf der Registerkarte für die Cubestruktur in der Mitte der Entwicklungsumgebung der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d477-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="7d477-134">Ändern Sie auf der Symbolleiste der Registerkarte „Cubestruktur“ den Wert für den **Zoomfaktor** auf 50 %, damit Sie die Dimensionen und Faktentabellen im Cube besser sehen können.</span><span class="sxs-lookup"><span data-stu-id="7d477-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="7d477-135">Beachten Sie, dass die Faktentabelle gelb ist und die Dimensionstabellen blau sind.</span><span class="sxs-lookup"><span data-stu-id="7d477-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="7d477-136">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="7d477-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7d477-137">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="7d477-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7d477-138">Hinzufügen von Attributen zu Dimensionen</span><span class="sxs-lookup"><span data-stu-id="7d477-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d477-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d477-139">See Also</span></span>  
 <span data-ttu-id="7d477-140">[Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="7d477-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="7d477-141">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="7d477-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
