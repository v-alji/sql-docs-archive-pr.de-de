---
title: Anzeigen von Data Mining-Modellen in Visio (Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616195"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="70770-102">Anzeigen von Data Mining-Modellen in Visio (Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="70770-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="70770-103">Mit Visio-Shapes für das Data Mining können Sie eine Verbindung mit einem Server herstellen und ein Diagramm erstellen, das ein vorhandenes Data Mining-Modell darstellt.</span><span class="sxs-lookup"><span data-stu-id="70770-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="70770-104">Die Diagramme können anschließend mithilfe von Visio-Steuerelementen angepasst werden; Sie können jedoch auch einen Drilldown auf Daten ausführen, einige der zugrunde liegenden Statistiken verfügbar machen und mit dem zugrunde liegenden Modell arbeiten.</span><span class="sxs-lookup"><span data-stu-id="70770-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="70770-105">Erstellen eines Modelldiagramms</span><span class="sxs-lookup"><span data-stu-id="70770-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="70770-106">Wenn Sie die Datei öffnen, die die Visio-Formen für Data Mining enthält, zeigt der Bereich **Formen** die folgenden Formen an.</span><span class="sxs-lookup"><span data-stu-id="70770-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="70770-107">Wenn die Data Mining-Shapes beim Öffnen von Visio nicht angezeigt werden, öffnen Sie die Vorlagendatei aus dem Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="70770-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="70770-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="70770-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="70770-109">Zum Verwenden eines Shapes ziehen Sie es auf das Zeichenblatt.</span><span class="sxs-lookup"><span data-stu-id="70770-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="70770-110">Durch jedes der Shapes wird ein bestimmter Assistent geöffnet, der Ihnen beim Auswählen von Quelldaten, beim Festlegen von Optionen für einen bestimmten Diagrammtyp sowie beim Angeben von Schattierungs- und anderen Anzeigeoptionen hilft.</span><span class="sxs-lookup"><span data-stu-id="70770-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="70770-111">In der folgenden Tabelle sind die Modelltypen aufgeführt, die Sie mit den einzelnen Diagrammtypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="70770-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="70770-112">Visio-Shape</span><span class="sxs-lookup"><span data-stu-id="70770-112">Visio shape</span></span>|<span data-ttu-id="70770-113">Unterstützte Modelle</span><span class="sxs-lookup"><span data-stu-id="70770-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="70770-114">Entscheidungsstruktur</span><span class="sxs-lookup"><span data-stu-id="70770-114">Decision Tree</span></span>|<span data-ttu-id="70770-115">Verwenden Sie dieses Shape für Modelle, die auf dem Decision Tree- oder Linear Regression-Algorithmus basieren.</span><span class="sxs-lookup"><span data-stu-id="70770-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="70770-116">Abhängigkeitsnetzwerk</span><span class="sxs-lookup"><span data-stu-id="70770-116">Dependency Network</span></span>|<span data-ttu-id="70770-117">Verwenden Sie dieses Shape für Diagramme, die auf einem der folgenden Algorithmen basieren: Naive Bayes, Decision Trees oder Association Rules.</span><span class="sxs-lookup"><span data-stu-id="70770-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="70770-118">Cluster</span><span class="sxs-lookup"><span data-stu-id="70770-118">Cluster</span></span>|<span data-ttu-id="70770-119">Verwenden Sie dieses Shape für Modelle, die auf den Clustering-Algorithmen basieren.</span><span class="sxs-lookup"><span data-stu-id="70770-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="70770-120">Abhängig vom Datentyp im Miningmodell werden vom Assistenten möglicherweise verschiedene Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70770-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="70770-121">Spalten, die fortlaufende Zahlen enthalten, werden beispielsweise anders visualisiert als Kategorievariablen.</span><span class="sxs-lookup"><span data-stu-id="70770-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="70770-122">Arbeiten mit abgeschlossenen Formen</span><span class="sxs-lookup"><span data-stu-id="70770-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="70770-123">Nach Fertigstellung des Diagramms können Sie damit das Data Mining-Modell durchsuchen, oder Sie können das Diagramm optimieren, um es in Präsentationen einzubinden.</span><span class="sxs-lookup"><span data-stu-id="70770-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="70770-124">Visio-Menüs</span><span class="sxs-lookup"><span data-stu-id="70770-124">Visio Menus</span></span>  
 <span data-ttu-id="70770-125">Visio stellt eine Vielzahl von Renderingsteuerelementen, Designs und Kontextmenüs bereit, mit denen Sie ein Diagramm optimieren können.</span><span class="sxs-lookup"><span data-stu-id="70770-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="70770-126">Verwenden Sie Visio-Designs zum Ändern von Diagrammfarben.</span><span class="sxs-lookup"><span data-stu-id="70770-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="70770-127">Ändern Sie Verbinder oder das Diagrammlayout.</span><span class="sxs-lookup"><span data-stu-id="70770-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="70770-128">Data Mining-Menüs</span><span class="sxs-lookup"><span data-stu-id="70770-128">Data Mining Menus</span></span>  
 <span data-ttu-id="70770-129">Diese Symbolleisten und Menüelemente werden von den Add-Ins bereitgestellt, die für die einzelnen Shapes oder Modelltypen spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="70770-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="70770-130">Jeder Diagrammtyp weist ein Kontextmenü für das Shape auf, über das Sie auf spezielle Optionen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="70770-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="70770-131">Obwohl viele Optionen in diesem Menü für sämtliche Visio-Shapes verwendet werden können, gelten einige ausschließlich für Data Mining-Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="70770-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="70770-132">So können Sie beispielsweise in einem Entscheidungsstrukturdiagramm auf einen einzelnen Knoten klicken und die untergeordneten Knoten reduzieren, um das Diagramm zu vereinfachen, oder die untergeordneten Knoten auf ein anderes Zeichenblatt verschieben.</span><span class="sxs-lookup"><span data-stu-id="70770-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="70770-133">Da das Shape an die Modelldaten gebunden ist, können mithilfe des Diagramms in gewissem Umfang auch Analysen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="70770-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="70770-134">Filtern der angezeigten Knoten oder Ändern der Strukturebene oder der Tiefe des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="70770-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="70770-135">Vergrößern der Anzeige bestimmter Abschnitte, Suchen nach Knoten, die ein bestimmtes Attribut enthalten, oder Filtern eines Abhängigkeitsdiagramms anhand seiner Ränder (Wahrscheinlichkeit).</span><span class="sxs-lookup"><span data-stu-id="70770-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="70770-136">Exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="70770-136">Walkthroughs</span></span>  
 <span data-ttu-id="70770-137">Beispiele zum Arbeiten mit einem fertiggestellten Diagramm und zu dessen Interpretation finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="70770-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="70770-138">Exemplarische Vorgehensweise für das Clusterdiagramm</span><span class="sxs-lookup"><span data-stu-id="70770-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="70770-139">Exemplarische Vorgehensweise für das Abhängigkeitsnetzwerkdiagramm</span><span class="sxs-lookup"><span data-stu-id="70770-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="70770-140">Exemplarische Vorgehensweise für das Entscheidungsstrukturdiagramm</span><span class="sxs-lookup"><span data-stu-id="70770-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="70770-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70770-141">See Also</span></span>  
 [<span data-ttu-id="70770-142">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="70770-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
