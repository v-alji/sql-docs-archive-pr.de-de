---
title: Auslösen und Definieren von Ereignissen in einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697002"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="aa7c7-102">Auslösen und Definieren von Ereignissen in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="aa7c7-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="aa7c7-103">Komponentenentwickler können eine Teilmenge der Ereignisse, die in der <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>-Schnittstelle definiert sind, auslösen, indem sie die in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>-Eigenschaft verfügbaren Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="aa7c7-104">Außerdem können Sie benutzerdefinierte Ereignisse mit der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>-Auflistung definieren und sie während der Ausführung mit der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>-Methode auslösen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="aa7c7-105">In diesem Abschnitt wird beschrieben, wie Sie ein Ereignis erstellen und auslösen können und es werden Richtlinien bereitgestellt, wann Ereignisse zur Entwurfszeit ausgelöst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="aa7c7-106">Auslösen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="aa7c7-106">Raising Events</span></span>
 <span data-ttu-id="aa7c7-107">Komponenten lösen Ereignisse mit den **Fire\<X>** -Methoden der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="aa7c7-108">Sie können während des Entwurfs und der Ausführung von Komponenten Ereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="aa7c7-109">In der Regel werden während der Überprüfung beim Entwurf der Komponenten die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>- und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>-Methoden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="aa7c7-110">Diese Ereignisse zeigen Meldungen im Bereich **Fehlerliste** von [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] an und stellen für die Benutzer der Komponente Feedback bereit, wenn eine Komponente nicht richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="aa7c7-111">Komponenten können auch zu einem beliebigen Zeitpunkt während der Ausführung Ereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="aa7c7-112">Ereignisse ermöglichen es Komponentenentwicklern, während der Ausführung einer Komponente Feedback für deren Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="aa7c7-113">Bei Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>-Methode während der Ausführung ist ein Versagen des Pakets wahrscheinlich.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="aa7c7-114">Definieren und Auslösen von benutzerdefinierten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="aa7c7-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="aa7c7-115">Definieren eines benutzerdefinierten Ereignisses</span><span class="sxs-lookup"><span data-stu-id="aa7c7-115">Defining a Custom Event</span></span>
 <span data-ttu-id="aa7c7-116">Benutzerdefinierte Ereignisse werden erstellt, indem die <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>-Auflistung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="aa7c7-117">Diese Auflistung wird durch den Datenflusstask festgelegt und dem Komponentenentwickler über die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse als Eigenschaft bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="aa7c7-118">Diese Klasse enthält durch den Datenflusstask definierte sowie durch die Komponente während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>-Methode definierte benutzerdefinierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="aa7c7-119">Die benutzerdefinierten Ereignisse einer Komponente werden nicht permanent im Paket-XML beibehalten.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="aa7c7-120">Daher wird sowohl während der Entwicklung als auch während der Ausführung die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>-Methode aufgerufen, um der Komponente die Definition der von ihr ausgelösten Ereignisse zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="aa7c7-121">Der *allowEventHandlers*-Parameter der <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A>-Methode gibt an, ob die Komponente die Erstellung von <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekten für das Ereignis zulässt.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="aa7c7-122">Beachten Sie, dass <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> synchron sind.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="aa7c7-123">Daher setzt die Komponente die Ausführung erst dann fort, wenn ein an das benutzerdefinierte Ereignis angefügter <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> die Ausführung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="aa7c7-124">Wenn der Parameter " *zugsweventhandlers* " ist `true` , wird jeder Parameter des Ereignisses automatisch allen <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> Objekten über Variablen zur Verfügung gestellt, die automatisch von der Laufzeit erstellt und aufgefüllt werden [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa7c7-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="aa7c7-125">Auslösen eines benutzerdefinierten Ereignisses</span><span class="sxs-lookup"><span data-stu-id="aa7c7-125">Raising a Custom Event</span></span>
 <span data-ttu-id="aa7c7-126">Komponenten lösen benutzerdefinierter Ereignisse durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>-Methode aus, und stellen den Namen, den Text und die Parameter des Ereignisses bereit.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="aa7c7-127">Wenn der Parameter " *zugsweventhandlers* " ist `true` , <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> werden alle, die für das benutzerdefinierte Ereignis erstellt werden, von der [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Lauf Zeit-Engine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="aa7c7-128">Beispiel für ein benutzerdefiniertes Ereignis</span><span class="sxs-lookup"><span data-stu-id="aa7c7-128">Custom Event Sample</span></span>
 <span data-ttu-id="aa7c7-129">Im folgenden Codebeispiel wird eine Komponente gezeigt, die während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>-Methode ein benutzerdefiniertes Ereignis definiert und dann durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>-Methode das Ereignis zur Laufzeit auslöst.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="aa7c7-130">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="aa7c7-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="aa7c7-131">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="aa7c7-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="aa7c7-132">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="aa7c7-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="aa7c7-133">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aa7c7-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa7c7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa7c7-134">See Also</span></span>
 <span data-ttu-id="aa7c7-135">[Integration Services &#40;SSIS-&#41; Ereignishandler](../../integration-services-ssis-event-handlers.md) einen [Ereignis Handler zu einem Paket hinzufügen](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="aa7c7-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


