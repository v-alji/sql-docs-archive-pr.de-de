---
title: Data Mining (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620674"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="f6de5-102">Data Mining (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f6de5-102">Data Mining (SSAS)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="f6de5-103">stellt eine integrierte Plattform für Lösungen bereit, die Data Mining integrieren.</span><span class="sxs-lookup"><span data-stu-id="f6de5-103">provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="f6de5-104">Sie können entweder relationale oder Cubedaten verwenden, um Business Intelligence-Lösungen mit Vorhersageanalysen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="f6de5-105">Vorteile des Data Minings</span><span class="sxs-lookup"><span data-stu-id="f6de5-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="f6de5-106">Beim Data Mining werden Daten unter Verwendung durchdachter statistischer Grundlagen auf Muster untersucht, um Ihnen bei komplexen Problemstellungen eine intelligente Entscheidungsfindung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="f6de5-107">Indem die in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enthaltenen Data Mining-Algorithmen auf Daten angewendet werden, können Trends vorhergesagt, Muster identifiziert, Regeln und Empfehlungen aufgestellt, die Abfolge von Ereignissen in komplexen Datasets analysiert und neue Einblicke gewonnen werden.</span><span class="sxs-lookup"><span data-stu-id="f6de5-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="f6de5-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]ist Data Mining leistungsstark, zugreifbar und integriert in die Tools, die viele für Analyse und Berichtswesen bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="f6de5-109">Um Ihr Hintergrundwissen für die ersten Schritte mit Data Mining-Funktionen zu vertiefen, informieren Sie sich in den Links in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f6de5-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="f6de5-110">Wichtige Data Mining-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f6de5-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="f6de5-111">SQL Server stellt die folgenden Funktionen zur Unterstützung integrierter Data Mining-Lösungen bereit:</span><span class="sxs-lookup"><span data-stu-id="f6de5-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="f6de5-112">Mehrere Datenquellen: Sie müssen kein Data Warehouse oder einen OLAP-Cube erstellen, um Data Mining-Funktionen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="f6de5-113">Sie können Tabellendaten externer Anbieter, aus Arbeitsblättern und sogar aus Textdateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6de5-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="f6de5-114">Darüber hinaus können Sie leicht für OLAP-Cubes, die in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]erstellt wurden, Data Mining durchführen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f6de5-115">Sie können jedoch keine Daten aus einer speicherinternen Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6de5-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="f6de5-116">Integrierte Datenbereinigung, Datenverwaltung und ETL: Data Quality Services stellen erweiterte Tools zur Profilerstellung und zum Bereinigen von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="f6de5-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="f6de5-117">Integration Services können zum Erstellen von ETL-Prozessen zum Bereinigen von Daten sowie zum Erstellen, Verarbeiten, Trainieren und Aktualisieren von Modellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6de5-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="f6de5-118">Mehrere anpassbare Algorithmen: Neben Algorithmen, beispielsweise für das Clustering, neuronale Netzwerke und Entscheidungsstrukturen, unterstützt die Plattform die Entwicklung eigener benutzerdefinierter Plug-In-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="f6de5-119">Infrastruktur zum Testen von Modellen: Testen Sie die Modelle und Datasets unter Verwendung wichtiger Statistiktools, wie Kreuzvalidierung, Klassifikationsmatrizen, Prognosegütediagramme und Punktdiagramme.</span><span class="sxs-lookup"><span data-stu-id="f6de5-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="f6de5-120">Erstellen und verwalten Sie einfach Test- und Trainingssätze.</span><span class="sxs-lookup"><span data-stu-id="f6de5-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="f6de5-121">Abfragen und Drillthrough: Erstellen Sie Vorhersageabfragen, rufen Sie Modellmuster und Statistiken ab, und führen Sie einen Drillthrough zu Falldaten aus.</span><span class="sxs-lookup"><span data-stu-id="f6de5-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="f6de5-122">Clienttools: Neben den Entwicklungs- und Entwurfsoberflächen von SQL Server können Sie mithilfe der Data Mining-Add-Ins für Excel Modelle erstellen, abfragen und durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="f6de5-123">Alternativ können Sie benutzerdefinierte Clients, einschließlich Webdienste, erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6de5-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="f6de5-124">Unterstützung von Skriptsprachen und verwaltete API: Alle Data Mining-Objekte sind vollständig programmierbar.</span><span class="sxs-lookup"><span data-stu-id="f6de5-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="f6de5-125">Skripts können mithilfe von MDX, XMLA oder der PowerShell-Erweiterungen für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6de5-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f6de5-126">Verwenden Sie die DMX-Sprache (Data Mining Extensions, Data Mining-Erweiterungen) für die schnelle Abfrageausführung und Skripterstellung.</span><span class="sxs-lookup"><span data-stu-id="f6de5-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="f6de5-127">Sicherheit und Bereitstellung: Bietet rollenbasierte Sicherheit durch [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], einschließlich separater Berechtigungen für Drillthroughs zu Modell- und Strukturdaten.</span><span class="sxs-lookup"><span data-stu-id="f6de5-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="f6de5-128">Einfache Bereitstellung von Modellen auf anderen Servern, damit Benutzer auf die Muster zugreifen oder Vorhersagen ausführen können</span><span class="sxs-lookup"><span data-stu-id="f6de5-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6de5-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f6de5-129">In This Section</span></span>  
 <span data-ttu-id="f6de5-130">In den Themen in diesem Abschnitt werden die Hauptfunktionen von SQL Server Data Mining sowie verwandte Tasks eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f6de5-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="f6de5-131">Data Mining-Konzepte</span><span class="sxs-lookup"><span data-stu-id="f6de5-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="f6de5-132">Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f6de5-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="f6de5-133">Miningstrukturen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f6de5-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="f6de5-134">Miningmodelle &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f6de5-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="f6de5-135">Tests und Überprüfung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f6de5-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="f6de5-136">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="f6de5-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="f6de5-137">Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="f6de5-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="f6de5-138">Data Mining-Tools</span><span class="sxs-lookup"><span data-stu-id="f6de5-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="f6de5-139">Data Mining-Architektur</span><span class="sxs-lookup"><span data-stu-id="f6de5-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="f6de5-140">Sicherheitsübersicht &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f6de5-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
