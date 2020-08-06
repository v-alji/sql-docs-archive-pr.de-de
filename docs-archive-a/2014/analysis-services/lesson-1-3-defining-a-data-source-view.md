---
title: Definieren einer Datenquellen Sicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608053"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="50ac7-102">Definieren einer Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="50ac7-102">Defining a Data Source View</span></span>
  <span data-ttu-id="50ac7-103">Nach dem Definieren der Datenquellen für ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt besteht der nächste Schritt im Allgemeinen im Definieren einer Datenquellensicht für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="50ac7-104">Eine Datenquellensicht ist eine einheitliche Sicht der Metadaten von den angegebenen Tabellen und Sichten, die von den Datenquellen im Projekt definiert werden.</span><span class="sxs-lookup"><span data-stu-id="50ac7-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="50ac7-105">Das Speichern der Metadaten in der Datenquellensicht ermöglicht das Arbeiten mit den Metadaten während der Entwicklung ohne offene Verbindung mit einer zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="50ac7-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="50ac7-106">Weitere Informationen finden Sie unter [Datenquellsichten in mehrdimensionalen Modellen](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="50ac7-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="50ac7-107">In der folgenden Aufgabe definieren Sie eine Datenquellensicht, die fünf Tabellen aus der Datenquelle **AdventureWorksDW2012** umfasst.</span><span class="sxs-lookup"><span data-stu-id="50ac7-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="50ac7-108">So definieren Sie eine Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="50ac7-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="50ac7-109">Klicken Sie im Projektmappen-Explorer (auf der rechten Seite des Microsoft Visual Studio-Fensters) mit der rechten Maustaste auf **Datenquellensichten**und anschließend auf **Neue Datenquellensicht**.</span><span class="sxs-lookup"><span data-stu-id="50ac7-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="50ac7-110">Klicken Sie auf der Seite **Willkommen beim Datenquellensicht-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="50ac7-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="50ac7-111">Die Seite **Datenquelle auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="50ac7-112">Unter **Relationale Datenquellen**ist die **Adventure Works DW 2012** -Datenquelle ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="50ac7-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="50ac7-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50ac7-114">Um eine auf mehreren Datenquellen basierende Datenquellensicht zu erstellen, definieren Sie zuerst eine auf einer einzelnen Datenquelle basierende Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="50ac7-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="50ac7-115">Diese Datenquelle wird dann als primäre Datenquelle bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="50ac7-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="50ac7-116">Anschließend können Sie Tabellen und Sichten aus einer sekundären Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="50ac7-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="50ac7-117">Beim Entwerfen von Dimensionen, die Attribute enthalten, die auf zugehörigen Tabellen in mehreren Datenquellen basieren, können Sie eine [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenquelle als primäre Datenquelle definieren und deren verteilte Abfrage-Engine-Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="50ac7-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="50ac7-118">Wählen Sie auf der Seite **Tabellen und Sichten auswählen** Tabellen und Sichten aus der Liste von Objekten aus, die in der ausgewählten Datenquelle verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="50ac7-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="50ac7-119">Sie können diese Liste filtern, sodass das Auswählen von Tabellen und Sichten einfacher wird.</span><span class="sxs-lookup"><span data-stu-id="50ac7-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50ac7-120">Klicken Sie auf die Schaltfläche zum Vergrößern rechts oben, sodass das Fenster im Vollbildmodus angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50ac7-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="50ac7-121">Dadurch lässt sich die vollständige Liste von verfügbaren Objekten leichter anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50ac7-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="50ac7-122">Wählen Sie in der Liste **Verfügbare Objekte** die folgenden Objekte aus.</span><span class="sxs-lookup"><span data-stu-id="50ac7-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="50ac7-123">Um mehrere Tabellen auszuwählen, halten Sie beim Klicken die STRG-TASTE gedrückt:</span><span class="sxs-lookup"><span data-stu-id="50ac7-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="50ac7-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="50ac7-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="50ac7-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="50ac7-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="50ac7-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="50ac7-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="50ac7-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="50ac7-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="50ac7-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="50ac7-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="50ac7-129">Klicken Sie **>** hierauf, um die ausgewählten Tabellen der Liste **enthaltene Objekte** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50ac7-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="50ac7-130">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="50ac7-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="50ac7-131">Stellen Sie im Namensfeld sicher, dass **Adventure Works DW 2012** angezeigt wird, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="50ac7-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="50ac7-132">Die **Adventure Works DW 2012** -Datenquellensicht wird im Ordner **Datenquellensichten** im Projektmappen-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="50ac7-133">Der Inhalt der Datenquellensicht wird auch im Datenquellensicht-Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="50ac7-134">Der Designer enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="50ac7-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="50ac7-135">Einen Bereich **Diagramm** , in dem die Tabellen und deren Beziehungen grafisch dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="50ac7-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="50ac7-136">Einen Bereich **Tabellen** , in dem die Tabellen und deren Schemaelemente in einer Strukturansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50ac7-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="50ac7-137">Einen Bereich **Diagrammplaner** , in dem Sie Unterdiagramme erstellen können, sodass Sie Untermengen der Datenquellensicht anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="50ac7-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="50ac7-138">Eine für den Datenquellensicht-Designer spezifische Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="50ac7-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="50ac7-139">Klicken Sie auf die Schaltfläche [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span><span class="sxs-lookup"><span data-stu-id="50ac7-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="50ac7-140">Zur Anzeige der Tabellen im Bereich **Diagramm** in einer 50-Prozent-Darstellung, klicken Sie auf das **Vergrößern** -Symbol in der Symbolleiste des Datenquellensicht-Designers.</span><span class="sxs-lookup"><span data-stu-id="50ac7-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="50ac7-141">Dadurch werden die Spaltendetails jeder Tabelle ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="50ac7-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="50ac7-142">Zum Ausblenden des Projektmappen-Explorers klicken Sie auf die Schaltfläche **Automatisch im Hintergrund** , bei der es sich um das Pushpin-Symbol in der Titelleiste handelt.</span><span class="sxs-lookup"><span data-stu-id="50ac7-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="50ac7-143">Um den Projektmappen-Explorer wieder anzuzeigen, positionieren Sie den Mauszeiger über der Registerkarte Projektmappen-Explorer auf der rechten Seite der Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="50ac7-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="50ac7-144">Zum Ausblenden des Projektmappen-Explorers klicken Sie erneut auf die Schaltfläche **Automatisch im Hintergrund** .</span><span class="sxs-lookup"><span data-stu-id="50ac7-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="50ac7-145">Wenn die Fenster nicht standardmäßig ausgeblendet sind, klicken Sie in der Titelleiste des Fensters für Eigenschaften sowie des Fensters des Projektmappen-Explorers auf **Automatisch im Hintergrund** .</span><span class="sxs-lookup"><span data-stu-id="50ac7-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="50ac7-146">Sie können nun alle Tabellen und deren Beziehungen im Bereich **Diagramm** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50ac7-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="50ac7-147">Beachten Sie, dass drei Beziehungen zwischen der FactInternetSales-Tabelle und der DimDate-Tabelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50ac7-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="50ac7-148">Jedem Verkauf sind drei Daten zugeordnet: ein Bestelldatum, ein Fälligkeitsdatum und ein Lieferdatum.</span><span class="sxs-lookup"><span data-stu-id="50ac7-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="50ac7-149">Um die Details einer Beziehung anzuzeigen, doppelklicken Sie auf den Beziehungspfeil im Bereich **Diagramm** .</span><span class="sxs-lookup"><span data-stu-id="50ac7-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="50ac7-150">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="50ac7-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="50ac7-151">Ändern von Standardtabellennamen</span><span class="sxs-lookup"><span data-stu-id="50ac7-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="50ac7-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50ac7-152">See Also</span></span>  
 [<span data-ttu-id="50ac7-153">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="50ac7-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
