---
title: Entwickeln eines benutzerdefinierten Tasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619957"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="f81f3-102">Entwickeln eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="f81f3-102">Developing a Custom Task</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="f81f3-103">nutzt Tasks, um Arbeitseinheiten auszuführen, die das Extrahieren, Umwandeln und Laden von Daten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f81f3-103">uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="f81f3-104">beinhaltet verschiedene Tasks, durch die häufig auftretende Aktionen ausgeführt werden, z. B. das Ausführen von SQL-Anweisungen oder das Herunterladen einer Datei von einer FTP-Site.</span><span class="sxs-lookup"><span data-stu-id="f81f3-104">includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="f81f3-105">Wenn die enthaltenen Tasks und unterstützten Aktionen Ihre Anforderungen nicht vollständig erfüllen, können Sie einen benutzerdefinierten Task erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81f3-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="f81f3-106">Zum Erstellen eines benutzerdefinierten Tasks müssen Sie eine Klasse erstellen, die von der Basisklasse [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) erbt, das <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attribut auf die neue Klasse anwenden und die Hauptmethoden und -eigenschaften der Basisklasse, einschließlich der <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>-Methode, überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f81f3-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f81f3-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f81f3-107">In This Section</span></span>  
 <span data-ttu-id="f81f3-108">In diesem Abschnitt wird beschrieben, wie Sie einen benutzerdefinierten Task und seine optionale benutzerdefinierte Benutzeroberfläche erstellen, konfigurieren und codieren.</span><span class="sxs-lookup"><span data-stu-id="f81f3-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="f81f3-109">Erstellen eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="f81f3-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="f81f3-110">Beschreibt den ersten Schritt, durch den der benutzerdefinierte Task erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f81f3-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="f81f3-111">Codieren eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="f81f3-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="f81f3-112">Beschreibt, wie die Hauptmethoden eines benutzerdefinierten Tasks codiert werden.</span><span class="sxs-lookup"><span data-stu-id="f81f3-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="f81f3-113">Herstellen einer Verbindung mit Datenquellen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="f81f3-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="f81f3-114">Beschreibt, wie Sie einen benutzerdefinierten Task mit einer Datenquelle verbinden können.</span><span class="sxs-lookup"><span data-stu-id="f81f3-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="f81f3-115">Auslösen und Definieren von Ereignissen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="f81f3-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="f81f3-116">Beschreibt, wie Ereignisse ausgelöst und benutzerdefinierte Ereignisse in dem benutzerdefinierten Task definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f81f3-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="f81f3-117">Bereitstellen von Unterstützung für das Debuggen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="f81f3-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="f81f3-118">Beschreibt, wie Breakpointziele in dem benutzerdefinierten Task erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f81f3-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="f81f3-119">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="f81f3-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="f81f3-120">Beschreibt, wie eine Benutzeroberfläche erstellt wird, die im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer angezeigt wird, um Eigenschaften für den benutzerdefinierten Task zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f81f3-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f81f3-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f81f3-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="f81f3-122">Informationen, die für alle benutzerdefinierten Objekte gelten</span><span class="sxs-lookup"><span data-stu-id="f81f3-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="f81f3-123">Informationen zu allen Arten benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f81f3-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="f81f3-124">Entwickeln benutzerdefinierter Objekte für Integration Services</span><span class="sxs-lookup"><span data-stu-id="f81f3-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="f81f3-125">Beschreibt die grundlegenden Schritte bei der Implementierung aller Arten von benutzerdefinierten Objekten in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f81f3-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="f81f3-126">Beibehalten von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="f81f3-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="f81f3-127">Beschreibt die benutzerdefinierte Persistenz und erklärt, wann diese notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="f81f3-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="f81f3-128">Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="f81f3-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="f81f3-129">Beschreibt die Techniken für das Erstellen, Signieren, Bereitstellen und Debuggen von benutzerdefinierten Objekten.</span><span class="sxs-lookup"><span data-stu-id="f81f3-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="f81f3-130">Informationen zu anderen benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="f81f3-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="f81f3-131">Informationen zu den anderen Arten benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f81f3-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="f81f3-132">Entwickeln eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="f81f3-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="f81f3-133">Erläutert die Programmierung benutzerdefinierter Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="f81f3-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="f81f3-134">Entwickeln eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="f81f3-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="f81f3-135">Erläutert die Programmierung benutzerdefinierter Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="f81f3-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="f81f3-136">Entwickeln eines benutzerdefinierten ForEach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="f81f3-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="f81f3-137">Erläutert die Programmierung benutzerdefinierter Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="f81f3-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="f81f3-138">Entwickeln einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="f81f3-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="f81f3-139">Erläutert die Programmierung benutzerdefinierter Datenflussquellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="f81f3-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="f81f3-140">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="f81f3-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f81f3-141">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="f81f3-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f81f3-142">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="f81f3-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f81f3-143">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f81f3-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81f3-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f81f3-144">See Also</span></span>  
 <span data-ttu-id="f81f3-145">[Erweitern von Paketen mithilfe des Skripttasks](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="f81f3-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="f81f3-146">Vergleichen von Skriptlösungen und benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="f81f3-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
