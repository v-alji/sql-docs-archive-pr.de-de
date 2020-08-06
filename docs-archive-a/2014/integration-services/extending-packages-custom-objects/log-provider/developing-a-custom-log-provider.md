---
title: Entwickeln eines benutzerdefinierten Protokollanbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609369"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="a2ed0-102">Entwickeln eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="a2ed0-102">Developing a Custom Log Provider</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="a2ed0-103">bietet umfassende Protokollierungsfunktionen, mit denen Sie bei der Paketausführung auftretende Ereignisse erfassen können.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-103">has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="a2ed0-104">beinhaltet eine Palette von Protokollanbietern, über die Protokolle erstellt und in Formaten wie XML, in Textform, in Datenbanken oder im Windows-Ereignisprotokoll gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-104">includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="a2ed0-105">Sollten die Protokollanbieter und die angebotenen Ausgabeformate Ihre Anforderungen nicht vollständig erfüllen, können Sie benutzerdefinierte Protokollanbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="a2ed0-106">Zum Erstellen eines benutzerdefinierten Protokollanbieters müssen Sie eine Klasse erstellen, die von der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>-Basisklasse erbt, das <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>-Attribut auf die neue Klasse anwenden und die Hauptmethoden und -eigenschaften der Basisklasse, einschließlich der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>-Eigenschaft und der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>-Methode, überschreibt.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a2ed0-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2ed0-107">In This Section</span></span>
 <span data-ttu-id="a2ed0-108">In diesem Abschnitt wird beschrieben, wie Sie einen benutzerdefinierten Protokollanbieter erstellen, konfigurieren und den entsprechenden Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="a2ed0-109">[Erstellen eines benutzerdefinierten Protokoll Anbieters](creating-a-custom-log-provider.md) Beschreibt, wie die Klassen für ein benutzerdefiniertes Protokoll Anbieter Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="a2ed0-110">[Codieren eines benutzerdefinierten Protokoll Anbieters](coding-a-custom-log-provider.md) Beschreibt, wie ein benutzerdefinierter Protokoll Anbieter durch Überschreiben der Methoden und Eigenschaften der Basisklasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="a2ed0-111">[Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Protokoll Anbieter](developing-a-user-interface-for-a-custom-log-provider.md) Benutzerdefinierte Benutzeroberflächen für benutzerdefinierte Protokoll Anbieter werden in nicht unterstützt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2ed0-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2ed0-112">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a2ed0-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="a2ed0-113">Informationen, die für alle benutzerdefinierten Objekte gelten</span><span class="sxs-lookup"><span data-stu-id="a2ed0-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="a2ed0-114">Informationen zu allen Arten benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a2ed0-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="a2ed0-115">[Entwickeln von benutzerdefinierten Objekten für Integration Services](../developing-custom-objects-for-integration-services.md) Beschreibt die grundlegenden Schritte zum Implementieren aller Typen von benutzerdefinierten Objekten für [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2ed0-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="a2ed0-116">Beibehalten von [benutzerdefinierten Objekten](../persisting-custom-objects.md) Beschreibt die benutzerdefinierte Persistenz und erläutert, wann dies notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="a2ed0-117">Entwickeln, bereitstellen [und Debuggen von benutzerdefinierten Objekten](../building-deploying-and-debugging-custom-objects.md) Beschreibt die Techniken zum entwickeln, signieren, bereitstellen und Debuggen von benutzerdefinierten Objekten.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="a2ed0-118">Informationen zu anderen benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="a2ed0-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="a2ed0-119">Informationen zu den anderen Typen benutzerdefinierter Objekte, die Sie in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] erstellen können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a2ed0-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="a2ed0-120">[Entwickeln eines benutzerdefinierten](../task/developing-a-custom-task.md) Tasks Erläutert, wie benutzerdefinierte Tasks programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="a2ed0-121">[Entwickeln eines benutzerdefinierten Verbindungs-Managers](../connection-manager/developing-a-custom-connection-manager.md) Erläutert, wie benutzerdefinierte Verbindungs-Manager programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="a2ed0-122">[Entwickeln eines benutzerdefinierten Foreach-Enumerators](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Erläutert, wie benutzerdefinierte Enumeratoren programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="a2ed0-123">[Entwickeln einer benutzerdefinierten Datenfluss Komponente](../data-flow/developing-a-custom-data-flow-component.md) Erläutert, wie benutzerdefinierte Datenfluss Quellen,-Transformationen und-Ziele programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="a2ed0-124">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a2ed0-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a2ed0-125">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a2ed0-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a2ed0-126">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a2ed0-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a2ed0-127">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a2ed0-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


