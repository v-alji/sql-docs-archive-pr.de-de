---
title: Entwickeln eines benutzerdefinierten Verbindungs-Managers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726085"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="a970b-102">Entwickeln eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="a970b-102">Developing a Custom Connection Manager</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="a970b-103">verwendet Verbindungs-Manager, um die erforderlichen Informationen für das Herstellen einer Verbindung mit einer externen Datenquelle zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="a970b-103">uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="a970b-104">beinhaltet verschiedene Verbindungs-Manager, die Verbindungen mit den gebräuchlichsten Datenquellen unterstützen, von Unternehmensdatenbanken bis hin zu Textdateien und Excel-Arbeitsblättern.</span><span class="sxs-lookup"><span data-stu-id="a970b-104">includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="a970b-105">Wenn die Verbindungs-Manager und von [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] unterstützten externen Datenquellen Ihre Anforderungen nicht vollständig erfüllen, können Sie einen benutzerdefinierten Verbindungs-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="a970b-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="a970b-106">Zum Erstellen eines benutzerdefinierten Verbindungs-Managers müssen Sie eine Klasse erstellen, die von der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>-Basisklasse erbt, das <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>-Attribut auf die neue Klasse anwenden und die Hauptmethoden und -eigenschaften der Basisklasse, einschließlich der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>-Eigenschaft und der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>-Methode, überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a970b-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a970b-107">Die meisten Tasks, Quellen und Ziele, die in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] integriert wurden, können nur mit bestimmten Typen integrierter Verbindungs-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a970b-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="a970b-108">Überprüfen Sie vor der Entwicklung eines benutzerdefinierten Verbindungs-Managers für die Verwendung bei integrierten Tasks und Komponenten, ob die Liste verfügbarer Verbindungs-Manager durch diese Komponenten auf einen bestimmten Typ begrenzt wird.</span><span class="sxs-lookup"><span data-stu-id="a970b-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="a970b-109">Wenn Ihre Lösung einen benutzerdefinierten Verbindungs-Manager erfordert, müssen Sie möglicherweise auch einen benutzerdefinierten Task entwickeln oder eine benutzerdefinierte Quelle oder Ziel zur Verwendung mit dem Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="a970b-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a970b-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a970b-110">In This Section</span></span>  
 <span data-ttu-id="a970b-111">In diesem Abschnitt wird beschrieben, wie Sie einen benutzerdefinierten Verbindungs-Manager und dessen optionale benutzerdefinierte Benutzeroberfläche erstellen, konfigurieren und codieren.</span><span class="sxs-lookup"><span data-stu-id="a970b-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="a970b-112">Die in diesem Abschnitt gezeigten Codeausschnitte stammen aus dem Sql Server Custom Connection Manager-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a970b-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="a970b-113">Erstellen eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="a970b-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="a970b-114">Beschreibt die Erstellung der Klassen für ein benutzerdefiniertes Verbindungs-Manager-Projekt.</span><span class="sxs-lookup"><span data-stu-id="a970b-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="a970b-115">Codieren eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="a970b-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="a970b-116">Beschreibt die Implementierung eines benutzerdefinierten Verbindungs-Managers durch Überschreiben der Methoden und Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a970b-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="a970b-117">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="a970b-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="a970b-118">Beschreibt die Implementierung der Benutzeroberflächenklasse und des Formulars, das für die Konfiguration des benutzerdefinierten Verbindungs-Managers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a970b-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a970b-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a970b-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="a970b-120">Informationen, die für alle benutzerdefinierten Objekte gelten</span><span class="sxs-lookup"><span data-stu-id="a970b-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="a970b-121">Informationen zu allen Arten benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a970b-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="a970b-122">Entwickeln benutzerdefinierter Objekte für Integration Services</span><span class="sxs-lookup"><span data-stu-id="a970b-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="a970b-123">Beschreibt die grundlegenden Schritte bei der Implementierung aller Typen von benutzerdefinierten Objekten in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a970b-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a970b-124">Beibehalten von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="a970b-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="a970b-125">Beschreibt die benutzerdefinierte Persistenz und erklärt, wann diese notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="a970b-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="a970b-126">Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="a970b-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="a970b-127">Beschreibt die Techniken für das Erstellen, Signieren, Bereitstellen und Debuggen von benutzerdefinierten Objekten.</span><span class="sxs-lookup"><span data-stu-id="a970b-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="a970b-128">Informationen zu anderen benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="a970b-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="a970b-129">Informationen zu den anderen Typen benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a970b-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="a970b-130">Entwickeln eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="a970b-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="a970b-131">Erläutert die Programmierung benutzerdefinierter Tasks.</span><span class="sxs-lookup"><span data-stu-id="a970b-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="a970b-132">Entwickeln eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="a970b-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="a970b-133">Erläutert die Programmierung benutzerdefinierter Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="a970b-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="a970b-134">Entwickeln eines benutzerdefinierten ForEach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="a970b-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="a970b-135">Erläutert die Programmierung benutzerdefinierter Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="a970b-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="a970b-136">Entwickeln einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="a970b-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="a970b-137">Erläutert die Programmierung benutzerdefinierter Datenflussquellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="a970b-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="a970b-138">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a970b-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a970b-139">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a970b-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a970b-140">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a970b-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a970b-141">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a970b-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
