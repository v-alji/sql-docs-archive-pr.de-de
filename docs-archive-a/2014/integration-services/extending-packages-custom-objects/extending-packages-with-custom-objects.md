---
title: Erweitern von Paketen mit benutzerdefinierten Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694649"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="d21ba-102">Erweitern von Paketen mit benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="d21ba-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="d21ba-103">Wenn die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] bereitgestellten Komponenten nicht Ihren Anforderungen entsprechen, können Sie die Effektivität von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] durch Codieren eigener Erweiterungen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d21ba-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="d21ba-104">Ihnen stehen zwei unterschiedliche Optionen zur Erweiterung der Pakete zur Verfügung: Sie können Code in die leistungsstarken Wrapper schreiben, die vom Skripttask und der Skriptkomponente bereitgestellt werden, oder benutzerdefinierte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Erweiterungen durch Ableitung von den Basisklassen, die im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Objektmodell zur Verfügung stehen, vollständig neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d21ba-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="d21ba-105">In diesem Abschnitt wird die erweiterte der beiden Optionen beschrieben: das Erweitern von Paketen mit benutzerdefinierten Objekten.</span><span class="sxs-lookup"><span data-stu-id="d21ba-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="d21ba-106">Wenn die benutzerdefinierte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Lösung mehr Flexibilität als das Skripttask und die Skriptkomponente erfordert, oder wenn Sie eine Komponente benötigen, die in mehreren Paketen wieder verwendet wird, dann ermöglicht Ihnen das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Objektmodell, benutzerdefinierte Tasks, Datenflusskomponenten und andere Paketobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d21ba-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d21ba-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d21ba-107">In This Section</span></span>  
 [<span data-ttu-id="d21ba-108">Entwickeln benutzerdefinierter Objekte für Integration Services</span><span class="sxs-lookup"><span data-stu-id="d21ba-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="d21ba-109">Erläutert die benutzerdefinierten Objekte, die für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt werden können, und fasst die wesentlichen Schritte und Einstellungen zusammen.</span><span class="sxs-lookup"><span data-stu-id="d21ba-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="d21ba-110">Beibehalten von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="d21ba-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="d21ba-111">Erläutert die Standardpersistenz benutzerdefinierter Objekte sowie den Prozess der Implementierung von benutzerdefinierter Persistenz.</span><span class="sxs-lookup"><span data-stu-id="d21ba-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="d21ba-112">Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="d21ba-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="d21ba-113">Erläutert die gebräuchlichen Verfahren des Erstellens, Bereitstellens und Testens der verschiedenen Typen benutzerdefinierter Objekte.</span><span class="sxs-lookup"><span data-stu-id="d21ba-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="d21ba-114">Entwickeln eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="d21ba-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="d21ba-115">Beschreibt den Prozess des Codierens eines benutzerdefinierten Tasks.</span><span class="sxs-lookup"><span data-stu-id="d21ba-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="d21ba-116">Entwickeln eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="d21ba-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="d21ba-117">Beschreibt den Prozess des Codierens eines benutzerdefinierten Verbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="d21ba-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="d21ba-118">Entwickeln eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="d21ba-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="d21ba-119">Beschreibt den Prozess des Codierens eines benutzerdefinierten Protokollanbieters.</span><span class="sxs-lookup"><span data-stu-id="d21ba-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="d21ba-120">Entwickeln eines benutzerdefinierten ForEach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="d21ba-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="d21ba-121">Beschreibt den Prozess des Codierens eines benutzerdefinierten Enumerators.</span><span class="sxs-lookup"><span data-stu-id="d21ba-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="d21ba-122">Entwickeln einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="d21ba-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="d21ba-123">Erläutert die Programmierung benutzerdefinierter Datenflussquellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="d21ba-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d21ba-124">Verweis</span><span class="sxs-lookup"><span data-stu-id="d21ba-124">Reference</span></span>  
 [<span data-ttu-id="d21ba-125">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="d21ba-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="d21ba-126">Listet die vordefinierten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehlercodes mit ihren symbolischen Namen und Beschreibungen auf.</span><span class="sxs-lookup"><span data-stu-id="d21ba-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d21ba-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d21ba-127">Related Sections</span></span>  
 [<span data-ttu-id="d21ba-128">Erweitern von Paketen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="d21ba-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="d21ba-129">Beschreibt, wie die Ablaufsteuerung mithilfe des Skripttasks bzw. der Datenfluss mithilfe der Skriptkomponente erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="d21ba-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="d21ba-130">Programmgesteuertes Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="d21ba-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="d21ba-131">Erläutert, wie [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete programmgesteuert erstellt, konfiguriert, ausgeführt, geladen, gespeichert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d21ba-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="d21ba-132">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d21ba-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d21ba-133">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d21ba-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d21ba-134">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d21ba-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d21ba-135">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d21ba-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21ba-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d21ba-136">See Also</span></span>  
 <span data-ttu-id="d21ba-137">[Vergleichen von Skript Lösungen und benutzerdefinierten Objekten](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d21ba-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="d21ba-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="d21ba-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
