---
title: 'Lektion 2: definieren und Bereitstellen eines Cubes | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620640"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="ae41e-102">Lektion 2: Definieren und Bereitstellen eines Cubes</span><span class="sxs-lookup"><span data-stu-id="ae41e-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="ae41e-103">Nachdem Sie eine Datenquellen Sicht im Projekt definiert [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] haben, können Sie einen anfänglichen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Cube definieren.</span><span class="sxs-lookup"><span data-stu-id="ae41e-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="ae41e-104">Sie können einen Cube und seine Dimensionen in einem Durchgang definieren, indem Sie den Cube-Assistenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae41e-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="ae41e-105">Alternativ können Sie eine oder mehrere Dimensionen definieren und dann mit dem Cube-Assistenten einen Cube definieren, der diese Dimensionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae41e-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="ae41e-106">Wenn Sie eine komplexe Projektmappe entwerfen, definieren Sie im Allgemeinen zuerst die Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="ae41e-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="ae41e-107">Weitere Informationen finden Sie unter [Dimensionen in mehrdimensionalen Modellen](multidimensional-models/dimensions-in-multidimensional-models.md) oder [Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="ae41e-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae41e-108">Für alle Lektionen in diesem Lernprogramm sind abgeschlossene Projekte online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae41e-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="ae41e-109">Sie können jede Lektion aufrufen, indem Sie ein abgeschlossenes Projekt aus der vorherigen Lektion als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae41e-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="ae41e-110">[Klicken Sie hier](https://go.microsoft.com/fwlink/?LinkID=221866) , um die Beispielprojekte für dieses Lernprogramm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ae41e-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="ae41e-111">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="ae41e-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="ae41e-112">Definieren einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="ae41e-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="ae41e-113">In dieser Aufgabe definieren Sie eine Dimension mithilfe des Dimensions-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="ae41e-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="ae41e-114">Definieren eines Cubes</span><span class="sxs-lookup"><span data-stu-id="ae41e-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="ae41e-115">In dieser Aufgabe verwenden Sie den Cube-Assistenten zum Definieren eines ersten [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Cubes.</span><span class="sxs-lookup"><span data-stu-id="ae41e-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="ae41e-116">Hinzufügen von Attributen zu Dimensionen</span><span class="sxs-lookup"><span data-stu-id="ae41e-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="ae41e-117">In dieser Aufgabe fügen Sie den Dimensionen, die Sie erstellt haben, Attribute hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae41e-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="ae41e-118">Überprüfen von Cube- und Dimensionseigenschaften</span><span class="sxs-lookup"><span data-stu-id="ae41e-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="ae41e-119">In dieser Aufgabe überprüfen Sie die Struktur des Cubes, den Sie mit dem Cube-Assistenten definiert haben.</span><span class="sxs-lookup"><span data-stu-id="ae41e-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="ae41e-120">Bereitstellen eines Analysis Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="ae41e-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="ae41e-121">In dieser Aufgabe stellen Sie das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt für Ihre lokale Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]bereit und lernen bestimmte Bereitstellungseigenschaften kennen.</span><span class="sxs-lookup"><span data-stu-id="ae41e-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="ae41e-122">Durchsuchen des Cubes</span><span class="sxs-lookup"><span data-stu-id="ae41e-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="ae41e-123">In dieser Aufgabe durchsuchen Sie die Cube- und Dimensionsdaten mit Excel oder dem MDX-Abfrage-Designer.</span><span class="sxs-lookup"><span data-stu-id="ae41e-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ae41e-124">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="ae41e-124">Next Lesson</span></span>  
 [<span data-ttu-id="ae41e-125">Lektion 3: Ändern von Measures, Attributen und Hierarchien</span><span class="sxs-lookup"><span data-stu-id="ae41e-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae41e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae41e-126">See Also</span></span>  
 <span data-ttu-id="ae41e-127">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="ae41e-128">[Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="ae41e-129">[Dimensionen in mehrdimensionalen Modellen](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="ae41e-130">[Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="ae41e-131">[Konfigurieren von Analysis Services Projekteigenschaften &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="ae41e-132">[Erstellen von Analysis Services Projekten &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="ae41e-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="ae41e-133">Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="ae41e-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
