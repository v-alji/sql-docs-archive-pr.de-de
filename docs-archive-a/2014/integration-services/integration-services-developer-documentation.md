---
title: Entwickler&#39;s Guide (Integration Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621056"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="81f3b-102">Entwickler&#39;s Guide (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="81f3b-102">Developer&#39;s Guide (Integration Services)</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="81f3b-103">umfasst ein völlig neu konzipiertes Objektmodell mit vielen verbesserten Funktionen, um das Erweitern und Programmieren von Paketen einfacher, flexibler und leistungsstärker zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="81f3b-103">includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="81f3b-104">Entwickler haben die Möglichkeit, fast jeden Aspekt von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Paketen zu erweitern und zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="81f3b-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="81f3b-105">Als [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Entwickler gibt es zwei grundlegende Ansätze, die Sie bei der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Programmierung verfolgen können:</span><span class="sxs-lookup"><span data-stu-id="81f3b-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="81f3b-106">Sie können Pakete erweitern, indem Sie Komponenten, die in [!INCLUDE[ssIS](../includes/ssis-md.md)]-Designer zur Verfügung gestellt werden, zur Bereitstellung von benutzerdefinierten Funktionen in einem Paket programmieren.</span><span class="sxs-lookup"><span data-stu-id="81f3b-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="81f3b-107">Sie können Pakete erstellen, konfigurieren und programmgesteuert aus Ihren eigenen Anwendungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="81f3b-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="81f3b-108">Wenn die integrierten Komponenten in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nicht Ihren Anforderungen entsprechen, können Sie die Effektivität von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] durch Codieren eigener Erweiterungen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="81f3b-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="81f3b-109">Dieser Ansatz bietet Ihnen zwei unterschiedliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="81f3b-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="81f3b-110">Zur sofortigen Verwendung in einem einzelnen Paket können Sie einen benutzerdefinierten Task erstellen, indem Sie Code in den Skripttask schreiben. Sie haben auch die Möglichkeit, eine benutzerdefinierte Datenflusskomponente, die Sie als Quelle, Transformation oder Ziel konfigurieren können, zu erstellen, indem Sie Code in die Skriptkomponente schreiben.</span><span class="sxs-lookup"><span data-stu-id="81f3b-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="81f3b-111">Diese leistungsstarken Wrapper schreiben den Infrastrukturcode für Sie, damit Sie sich vollständig auf die Entwicklung der benutzerdefinierten Funktionen konzentrieren können. Sie lassen sich jedoch nicht leicht an anderer Stelle wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="81f3b-112">Zur Verwendung in mehreren Paketen können Sie benutzerdefinierte [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Erweiterungen wie Verbindungs-Manager, Tasks, Enumeratoren, Protokollanbieter und Datenflusskomponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="81f3b-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="81f3b-113">Das verwaltete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Objektmodell umfasst Basisklassen, die als Startpunkt dienen und die Entwicklung benutzerdefinierter Erweiterungen bequemer als je zuvor gestalten.</span><span class="sxs-lookup"><span data-stu-id="81f3b-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="81f3b-114">Wenn Sie Pakete dynamisch erstellen oder [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Pakete außerhalb der Entwicklungsumgebung verwalten und ausführen möchten, können Sie Pakete programmgesteuert ändern.</span><span class="sxs-lookup"><span data-stu-id="81f3b-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="81f3b-115">Sie können bestehende Pakete laden, ändern und ausführen oder völlig neue Pakete programmgesteuert erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="81f3b-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="81f3b-116">Dieser Ansatz bietet Ihnen eine breite Palette von Optionen:</span><span class="sxs-lookup"><span data-stu-id="81f3b-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="81f3b-117">Laden und Ausführen eines vorhandenen Pakets ohne Änderung</span><span class="sxs-lookup"><span data-stu-id="81f3b-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="81f3b-118">Laden, Neukonfigurieren (z. B. Festlegen einer anderen Datenquelle) und Ausführen eines vorhandenen Pakets</span><span class="sxs-lookup"><span data-stu-id="81f3b-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="81f3b-119">Erstellen eines neuen Pakets, Hinzufügen und Konfigurieren von Komponenten, Vornehmen von Änderungen Objekt um Objekt und Eigenschaft um Eigenschaft, Speichern und Ausführen des Pakets</span><span class="sxs-lookup"><span data-stu-id="81f3b-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="81f3b-120">Diese Ansätze zur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Programmierung werden in diesem Abschnitt beschrieben und mit Beispielen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="81f3b-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81f3b-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81f3b-121">In This Section</span></span>  
 [<span data-ttu-id="81f3b-122">Übersicht über die Programmierung von 'Integration Services'</span><span class="sxs-lookup"><span data-stu-id="81f3b-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="81f3b-123">Beschreibt die Rollen von Ablaufsteuerung und Datenfluss bei der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="81f3b-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="81f3b-124">Grundlegendes zu synchronen und asynchronen Transformationen</span><span class="sxs-lookup"><span data-stu-id="81f3b-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="81f3b-125">Beschreibt die wichtige Unterscheidung zwischen synchronen und asynchronen Ausgaben sowie die Komponenten, von denen sie im Datenfluss verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="81f3b-126">Programmgesteuertes Arbeiten mit Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="81f3b-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="81f3b-127">Listet die Verbindungs-Manager auf, die Sie aus verwaltetem Code verwenden können, und die Werte, die Verbindungs-Manager zurückgeben, wenn der Code die `AcquireConnection`-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="81f3b-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="81f3b-128">Erweitern von Paketen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="81f3b-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="81f3b-129">Erläutert, wie die Ablaufsteuerung mithilfe des Skripttasks und der Datenfluss mithilfe der Skriptkomponente erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="81f3b-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="81f3b-130">Erweitern von Paketen mit benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="81f3b-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="81f3b-131">Beschreibt, wie benutzerdefinierte Tasks, Datenflusskomponenten und andere Paketobjekte für die Verwendung in mehreren Paketen erstellt und programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="81f3b-132">Programmgesteuertes Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="81f3b-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="81f3b-133">Erläutert, wie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Pakete programmgesteuert erstellt, konfiguriert und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="81f3b-134">Programmgesteuerte Ausführung und Verwaltung von Paketen</span><span class="sxs-lookup"><span data-stu-id="81f3b-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="81f3b-135">Beschreibt, wie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Pakete programmgesteuert aufgezählt, ausgeführt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="81f3b-136">Verweis</span><span class="sxs-lookup"><span data-stu-id="81f3b-136">Reference</span></span>  
 [<span data-ttu-id="81f3b-137">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="81f3b-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="81f3b-138">Listet die vordefinierten [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Fehlercodes sowie ihre symbolischen Namen und Beschreibungen auf.</span><span class="sxs-lookup"><span data-stu-id="81f3b-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="81f3b-139">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="81f3b-139">Related Sections</span></span>  
 [<span data-ttu-id="81f3b-140">Tools zur Problembehandlung für die Paketentwicklung</span><span class="sxs-lookup"><span data-stu-id="81f3b-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="81f3b-141">Beschreibt die Funktionen und Tools, die von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] zur Behandlung von Problemen mit Paketen während der Entwicklung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="81f3b-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="81f3b-142">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="81f3b-142">External Resources</span></span>  
  
-   <span data-ttu-id="81f3b-143">CodePlex-Beispiele, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), auf www.codeplex.com/MSFTISProdSamples</span><span class="sxs-lookup"><span data-stu-id="81f3b-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f3b-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81f3b-144">See Also</span></span>  
 [<span data-ttu-id="81f3b-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="81f3b-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
