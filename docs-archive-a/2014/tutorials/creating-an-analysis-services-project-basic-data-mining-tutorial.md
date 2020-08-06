---
title: Erstellen eines Analysis Services Projekts (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608975"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="d011e-102">Erstellen eines Analysis Services-Projekts (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="d011e-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="d011e-103">Jedes [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Projekt definiert die Objekte in einer einzelnen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d011e-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="d011e-104">Eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank kann viele verschiedene Objekttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d011e-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="d011e-105">Mehrdimensionale Modelle (Cubes)</span><span class="sxs-lookup"><span data-stu-id="d011e-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="d011e-106">Miningstrukturen und Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="d011e-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="d011e-107">Unterstützende Objekte wie Datenquellen, Datenquellensichten und benutzerdefinierte Assemblys</span><span class="sxs-lookup"><span data-stu-id="d011e-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="d011e-108">Beachten Sie, dass für das Data Mining **kein** Cube erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d011e-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="d011e-109">Wenn Sie Data Mining-Funktionen für einen vorhandenen Cube ausführen müssen, sollten Sie die Data Mining-Modelle demselben Projekt hinzufügen, das Sie zum Erstellen des Cubes verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d011e-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="d011e-110">In den meisten Fällen können Sie die Modelle jedoch für relationale Datenquellen erstellen, z. B. ein Data Warehouse, und eine bessere Leistung erzielen, wenn kein Cube verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d011e-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="d011e-111">In diesem Lernprogramm verwenden Sie das relationale Data Warehouse [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]als Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="d011e-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="d011e-112">Sie stellen alle Ihre Data Mining-Objekte in einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank mit dem Namen `BasicDataMining` bereit, die ausschließlich für Data Mining verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d011e-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="d011e-113">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] verwendet standardmäßig die **localhost** -Instanz für neue Projekte.</span><span class="sxs-lookup"><span data-stu-id="d011e-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="d011e-114">Wenn Sie eine benannte Instanz oder einen anderen Server verwenden, müssen Sie zunächst das Projekt erstellen und öffnen und anschließend den Instanznamen ändern.</span><span class="sxs-lookup"><span data-stu-id="d011e-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="d011e-115">Weitere Informationen zu [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekten finden Sie unter [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="d011e-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="d011e-116">So erstellen Sie ein Analysis Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="d011e-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="d011e-117">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d011e-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d011e-118">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d011e-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="d011e-119">Überprüfen Sie, ob **Business Intelligence-Projekte** im Bereich **Projekttypen** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="d011e-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="d011e-120">Wählen Sie im Bereich **Vorlagen** die Vorlage für mehrdimensionale Projekte bzw. Data Mining-Projekte von Analysis Services \*\*\*\* aus.</span><span class="sxs-lookup"><span data-stu-id="d011e-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="d011e-121">Benennen Sie **Name** das neue Projekt in das Feld Name `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="d011e-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="d011e-122">So ändern Sie die Instanz, in der die Data Mining-Objekte gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="d011e-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="d011e-123">Wählen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Menü **Projekt** den Befehl **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="d011e-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d011e-124">Klicken Sie auf der linken Seite des Bereichs **Eigenschaftenseiten** unter **Konfigurationseigenschaften**auf **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="d011e-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="d011e-125">Überprüfen Sie, ob auf der rechten Seite des Bereichs **Eigenschaftenseiten** unter **Ziel**der **Servername\*\*\*\*localhost**angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d011e-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="d011e-126">Wenn Sie eine andere Instanz verwenden, geben Sie den Namen der Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="d011e-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d011e-127">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="d011e-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d011e-128">Erstellen einer Datenquelle &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="d011e-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d011e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d011e-129">See Also</span></span>  
 <span data-ttu-id="d011e-130">[Erstellen von Analysis Services Projekten &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="d011e-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="d011e-131">Erstellen eines Analysis Services-Projekts &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="d011e-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
