---
title: Data Mining-Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696290"
---
# <a name="data-mining-programming"></a><span data-ttu-id="2dcb8-102">Data Mining-Programmierung</span><span class="sxs-lookup"><span data-stu-id="2dcb8-102">Data Mining Programming</span></span>
  <span data-ttu-id="2dcb8-103">Wenn die integrierten Tools und Viewer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Ihren Anforderungen nicht entsprechen, können Sie die Effektivität von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] durch Codieren eigener Erweiterungen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="2dcb8-104">Dabei haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2dcb8-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="2dcb8-105">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="2dcb8-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="2dcb8-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]unterstützt XML for Analysis (XMLA) als Protokoll für die Kommunikation mit Client Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="2dcb8-107">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] unterstützt zusätzliche Befehle, die die XML for Analysis-Spezifikation erweitern.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="2dcb8-108">Weil in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] für die Datendefinition, Datenbearbeitung und Datenkontrolle XMLA verwendet, können Sie Miningstrukturen und Miningmodelle mithilfe der in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] bereitgestellten visuellen Tools erstellen und anschließend die erstellten Data Mining-Objekte mithilfe der Data Mining Extensions (DMX)- und Analysis Services Scripting Language (ASSL)-Skripts erweitern.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="2dcb8-109">Sie können Data Mining-Objekte vollständig in XMLA-Skripts erstellen und ändern und aus Ihren eigenen Anwendungen programmgesteuert Vorhersageabfragen für die Modelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="2dcb8-110">**Analysis Management Objects (AMO)**</span><span class="sxs-lookup"><span data-stu-id="2dcb8-110">**Analysis Management Objects (AMO)**</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="2dcb8-111">stellt außerdem ein vollständiges Framework bereit, das Data Mining-Drittanbietern die Integration der Data Mining-Objekte in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-111">also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="2dcb8-112">Sie können Miningstrukturen und Miningmodelle mithilfe von AMO erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="2dcb8-113">Siehe die folgenden Beispiele in CodePlex:</span><span class="sxs-lookup"><span data-stu-id="2dcb8-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="2dcb8-114">AMO-Browser</span><span class="sxs-lookup"><span data-stu-id="2dcb8-114">AMO Browser</span></span>  
  
         <span data-ttu-id="2dcb8-115">Stellt eine Verbindung mit der angegebenen SSAS-Instanz her und listet alle Serverobjekte und deren Eigenschaften auf, einschließlich Miningstruktur und Miningmodelle.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="2dcb8-116">AMO Simple Sample</span><span class="sxs-lookup"><span data-stu-id="2dcb8-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="2dcb8-117">Im AS Simple Sample werden folgende Verfahren behandelt: programmgesteuerter Zugriff auf die meisten Hauptobjekte, Durchsuchen von Metadaten und Zugriff auf Werte in Objekten.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="2dcb8-118">Das Beispiel veranschaulicht auch, wie Sie eine Data Mining-Struktur und ein Data Mining-Modell erstellen und verarbeiten und wie ein vorhandenes Data Mining-Modell durchsucht wird.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="2dcb8-119">**DMX**</span><span class="sxs-lookup"><span data-stu-id="2dcb8-119">**DMX**</span></span>  
  
     <span data-ttu-id="2dcb8-120">DMX kann verwendet werden, um Befehlsanweisungen, Vorhersageabfragen und Metadatenabfragen zu kapseln und Ergebnisse im Tabellenformat zurückzugeben, vorausgesetzt, Sie haben eine Verbindung mit einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Server hergestellt.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dcb8-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2dcb8-121">In This Section</span></span>  
 [<span data-ttu-id="2dcb8-122">OLE DB für Data Mining</span><span class="sxs-lookup"><span data-stu-id="2dcb8-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="2dcb8-123">Beschreibt Erweiterungen der Spezifikation zur Unterstützung von Data Mining und mehrdimensionalen Daten: neue Schemarowsets und -spalten, Data Mining Extensions (DMX)-Sprache zum Erstellen und Verwalten von Miningstrukturen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="2dcb8-124">Verwandter Verweis</span><span class="sxs-lookup"><span data-stu-id="2dcb8-124">Related Reference</span></span>  
 [<span data-ttu-id="2dcb8-125">Entwickeln mit ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="2dcb8-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="2dcb8-126">Bietet eine Einführung in ADOMD.NET-Client- und Server-Programmierobjekte.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="2dcb8-127">Entwickeln mit Analysis Management Objects &#40;AMO&#41;</span><span class="sxs-lookup"><span data-stu-id="2dcb8-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="2dcb8-128">Stellt die AMO-Programmierbibliothek vor.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="2dcb8-129">Entwickeln mit Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="2dcb8-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="2dcb8-130">Gibt eine Einführung in XML for Analysis (XMLA) und die zugehörigen Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="2dcb8-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcb8-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2dcb8-131">See Also</span></span>  
 <span data-ttu-id="2dcb8-132">[Entwicklerhandbuch &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="2dcb8-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="2dcb8-133">Data Mining-Erweiterungen &#40;DMX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="2dcb8-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
