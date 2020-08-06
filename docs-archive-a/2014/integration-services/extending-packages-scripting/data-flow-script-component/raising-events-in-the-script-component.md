---
title: Auslösen von Ereignissen in der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619205"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="190b8-102">Auslösen von Ereignissen in der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="190b8-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="190b8-103">Ereignisse bieten eine Möglichkeit, Fehler, Warnungen und andere Informationen, wie z. B. den Fortschritt oder Status eines Tasks, an das entsprechende Paket zu melden.</span><span class="sxs-lookup"><span data-stu-id="190b8-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="190b8-104">Das Paket stellt Ereignishandler zum Verwalten von Ereignisbenachrichtigungen bereit.</span><span class="sxs-lookup"><span data-stu-id="190b8-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="190b8-105">Die Skriptkomponente kann Ereignisse durch Aufrufen der Methoden in der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>-Eigenschaft der `ScriptMain`-Klasse auslösen.</span><span class="sxs-lookup"><span data-stu-id="190b8-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="190b8-106">Weitere Informationen zum Umgang von [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Paketen mit Ereignissen finden Sie unter [Integration Services-Ereignishandler &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="190b8-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="190b8-107">Ereignisse können in jedem Protokollanbieter protokolliert werden, der im Paket aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="190b8-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="190b8-108">Protokollanbieter speichern Informationen über Ereignisse in einem Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="190b8-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="190b8-109">Die Skriptkomponente kann ebenfalls die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>-Methode verwenden, um Informationen in einem Protokollanbieter zu protokollieren, ohne ein Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="190b8-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="190b8-110">Weitere Informationen zur Verwendung der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>-Methode finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="190b8-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="190b8-111">Um ein Ereignis auszulösen, ruft der Skripttask eine der folgenden Methoden der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle auf, die von der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>-Eigenschaft verfügbar gemacht wird:</span><span class="sxs-lookup"><span data-stu-id="190b8-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="190b8-112">Ereignis</span><span class="sxs-lookup"><span data-stu-id="190b8-112">Event</span></span>|<span data-ttu-id="190b8-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="190b8-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="190b8-114">Löst ein benutzerdefiniertes Ereignis im Paket aus.</span><span class="sxs-lookup"><span data-stu-id="190b8-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="190b8-115">Informiert das Paket über eine Fehlerbedingung.</span><span class="sxs-lookup"><span data-stu-id="190b8-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="190b8-116">Stellt Informationen für den Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="190b8-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="190b8-117">Informiert das Paket über den Fortschritt der Komponente.</span><span class="sxs-lookup"><span data-stu-id="190b8-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="190b8-118">Informiert das Paket darüber, dass die Komponente einen Status aufweist, der eine Benutzerbenachrichtigung erfordert, bei dem es sich aber nicht um eine Fehlerbedingung handelt.</span><span class="sxs-lookup"><span data-stu-id="190b8-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="190b8-119">Nachfolgend finden Sie ein einfaches Beispiel zur Auslösung eines Error-Ereignisses:</span><span class="sxs-lookup"><span data-stu-id="190b8-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="190b8-120">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="190b8-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="190b8-121">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="190b8-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="190b8-122">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="190b8-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="190b8-123">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="190b8-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190b8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="190b8-124">See Also</span></span>  
 <span data-ttu-id="190b8-125">[Integration Services-Ereignishandler &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="190b8-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="190b8-126">Hinzufügen eines Ereignishandlers zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="190b8-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
