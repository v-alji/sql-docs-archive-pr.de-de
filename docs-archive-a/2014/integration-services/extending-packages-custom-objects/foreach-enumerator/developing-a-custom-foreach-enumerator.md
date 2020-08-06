---
title: Entwickeln eines benutzerdefinierten Foreach-Enumerators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618209"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="921bc-102">Entwickeln eines benutzerdefinierten ForEach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="921bc-102">Developing a Custom ForEach Enumerator</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="921bc-103">verwendet Foreach-Enumeratoren, um die Elementen in einer Auflistung zu durchlaufen und die gleichen Tasks für jedes Element auszuführen.</span><span class="sxs-lookup"><span data-stu-id="921bc-103">uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="921bc-104">enthält eine Vielzahl von Foreach-Enumeratoren, die die am häufigsten verwendeten Auflistungen unterstützen. Dazu gehören alle Dateien in einem Ordner, alle Tabellen in einer Datenbank oder alle Elemente einer in einer Paketvariablen gespeicherten Liste.</span><span class="sxs-lookup"><span data-stu-id="921bc-104">includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="921bc-105">Sollten die verfügbaren Foreach-Enumeratoren und Auflistungen Ihre Anforderungen nicht vollständig erfüllen, können Sie einen benutzerdefinierten Foreach-Enumerator erstellen.</span><span class="sxs-lookup"><span data-stu-id="921bc-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="921bc-106">Zum Erstellen eines benutzerdefinierten Foreach-Enumerators müssen Sie eine Klasse erstellen, die von der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>-Basisklasse erbt, das <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>-Attribut auf die neue Klasse anwenden und die Hauptmethoden und -eigenschaften der Basisklasse, einschließlich der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>-Methode, überschreiben.</span><span class="sxs-lookup"><span data-stu-id="921bc-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="921bc-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="921bc-107">In This Section</span></span>  
 <span data-ttu-id="921bc-108">In diesem Abschnitt wird beschrieben, wie Sie einen benutzerdefinierten Foreach-Enumerator mit zugehöriger Benutzeroberfläche erstellen, konfigurieren und codieren.</span><span class="sxs-lookup"><span data-stu-id="921bc-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="921bc-109">Erstellen eines benutzerdefinierten Foreach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="921bc-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="921bc-110">Beschreibt die Erstellung der Klassen für ein benutzerdefiniertes Foreach-Enumeratorprojekt.</span><span class="sxs-lookup"><span data-stu-id="921bc-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="921bc-111">Codieren eines benutzerdefinierten Foreach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="921bc-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="921bc-112">Beschreibt die Implementierung eines benutzerdefinierten Foreach-Enumerators durch Überschreiben der Methoden und Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="921bc-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="921bc-113">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten ForEach-Enumerator</span><span class="sxs-lookup"><span data-stu-id="921bc-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="921bc-114">Beschreibt die Implementierung der Benutzeroberflächenklasse und des Formulars, das für die Konfiguration des benutzerdefinierten Foreach-Enumerators verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="921bc-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="921bc-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="921bc-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="921bc-116">Informationen, die für alle benutzerdefinierten Objekte gelten</span><span class="sxs-lookup"><span data-stu-id="921bc-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="921bc-117">Informationen zu allen Arten benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="921bc-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="921bc-118">Entwickeln benutzerdefinierter Objekte für Integration Services</span><span class="sxs-lookup"><span data-stu-id="921bc-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="921bc-119">Beschreibt die grundlegenden Schritte bei der Implementierung aller Typen von benutzerdefinierten Objekten in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="921bc-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="921bc-120">Beibehalten von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="921bc-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="921bc-121">Beschreibt die benutzerdefinierte Persistenz und erklärt, wann diese notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="921bc-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="921bc-122">Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="921bc-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="921bc-123">Beschreibt die Techniken für das Erstellen, Signieren, Bereitstellen und Debuggen von benutzerdefinierten Objekten.</span><span class="sxs-lookup"><span data-stu-id="921bc-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="921bc-124">Informationen zu anderen benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="921bc-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="921bc-125">Informationen zu den anderen Typen benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="921bc-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="921bc-126">Entwickeln eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="921bc-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="921bc-127">Erläutert die Programmierung benutzerdefinierter Tasks.</span><span class="sxs-lookup"><span data-stu-id="921bc-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="921bc-128">Entwickeln eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="921bc-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="921bc-129">Erläutert die Programmierung benutzerdefinierter Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="921bc-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="921bc-130">Entwickeln eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="921bc-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="921bc-131">Erläutert die Programmierung benutzerdefinierter Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="921bc-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="921bc-132">Entwickeln einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="921bc-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="921bc-133">Erläutert die Programmierung benutzerdefinierter Datenflussquellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="921bc-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="921bc-134">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="921bc-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="921bc-135">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="921bc-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="921bc-136">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="921bc-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="921bc-137">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="921bc-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
