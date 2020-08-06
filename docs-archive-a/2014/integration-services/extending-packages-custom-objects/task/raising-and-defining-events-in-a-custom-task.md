---
title: Auslösen und Definieren von Ereignissen in einem benutzerdefinierten Task | Microsoft-Dokumentation
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
- SSIS events, custom
- status information [SQL Server], task events
- custom tasks [Integration Services], events
- SSIS custom tasks, events
- IDTSComponentEvents interface
- events [Integration Services], custom
- events [Integration Services], runtime
- custom events [Integration Services]
- SSIS events, runtime
- IDTSEvents interface
ms.assetid: e0898aa1-e90c-4c4e-99d4-708a76efddfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb41ee60543a05b6cf10b3acda43372e20288d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619956"
---
# <a name="raising-and-defining-events-in-a-custom-task"></a><span data-ttu-id="61677-102">Auslösen und Definieren von Ereignissen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="61677-102">Raising and Defining Events in a Custom Task</span></span>
  <span data-ttu-id="61677-103">Die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Runtime-Engine bietet eine Auflistung von Ereignissen, die Statusinformationen zu dem Fortschritt eines Tasks liefern, während der Task überprüft und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61677-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine provides a collection of events that provide status on the progress of a task as the task is validated and executed.</span></span> <span data-ttu-id="61677-104">Diese Ereignisse werden durch die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>-Schnittstelle definiert. Sie wird Tasks als Parameter für die <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>-Methode und die <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>-Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="61677-104">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface defines these events, and is provided to tasks as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="61677-105">Es gibt eine weitere Gruppe von Ereignissen, die in der <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>-Schnittstelle definiert sind und von Seiten des Tasks von <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="61677-105">There is another set of events, which are defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface, that are raised on behalf of the task by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="61677-106">Der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> löst Ereignisse aus, die vor und nach der Validierung und Ausführung auftreten, wohingegen der Task die Ereignisse auslöst, die während der Ausführung und Validierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="61677-106">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> raises events that occur before and after validation and execution, whereas the task raises the events that occur during execution and validation.</span></span>  
  
## <a name="creating-custom-events"></a><span data-ttu-id="61677-107">Erstellen von benutzerdefinierten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="61677-107">Creating Custom Events</span></span>  
 <span data-ttu-id="61677-108">Entwickler von benutzerdefinierten Tasks können neue, benutzerdefinierte Ereignisse definieren, indem sie eine neue <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> in der überschriebenen Implementierung der <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A>-Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="61677-108">Custom task developers can define new, custom events by creating a new <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> in their overridden implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A> method.</span></span> <span data-ttu-id="61677-109">Nachdem die <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> erstellt wurde, wird sie der `EventInfos`-Auflistung mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="61677-109">After the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> is created, it is added to the `EventInfos` collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method.</span></span> <span data-ttu-id="61677-110">Die Methodensignatur der <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A>-Methode lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="61677-110">The method signature of the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method is as follows:</span></span>  
  
 `public void Add(string eventName, string description, bool allowEventHandlers, string[] parameterNames, TypeCode[] parameterTypes, string[] parameterDescriptions);`  
  
 <span data-ttu-id="61677-111">Im folgenden Codebeispiel ist die `InitializeTask`-Methode eines benutzerdefinierten Tasks dargestellt. Es werden zwei benutzerdefinierte Ereignisse erstellt und ihre Eigenschaften festgelegt.</span><span class="sxs-lookup"><span data-stu-id="61677-111">The following code sample shows the `InitializeTask` method of a custom task, where two custom events are created and their properties are set.</span></span> <span data-ttu-id="61677-112">Die neuen Ereignisse werden dann der <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="61677-112">The new events are then added to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection.</span></span>  
  
 <span data-ttu-id="61677-113">Das erste benutzerdefinierte Ereignis hat den Ereignisnamen (*eventName*) **OnBeforeIncrement** und die Beschreibung (*description\*\*\*Fires after the initial value is updated.*\*</span><span class="sxs-lookup"><span data-stu-id="61677-113">The first custom event has an *eventName* of "**OnBeforeIncrement**" and *description* of "**Fires after the initial value is updated.**"</span></span> <span data-ttu-id="61677-114">Der nächste Parameter, der `true`-Wert, gibt an, dass dieses Ereignis die Erstellung eines Ereignishandlercontainer zulässt, um das Ereignis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="61677-114">The next parameter, the `true` value, indicates that this event should allow an event handler container to be created to handle the event.</span></span> <span data-ttu-id="61677-115">Bei dem Ereignishandler handelt es sich um einen Container für die Strukturen in Paketen und Dienste für Tasks, wie andere Container, z. B. Paketcontainer, Sequenzcontainer, For-Schleifencontainer und ForEach-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="61677-115">The event handler is a container that provides structure in a package and services to tasks, like other containers such as the package, Sequence, ForLoop, and ForEachLoop.</span></span> <span data-ttu-id="61677-116">Wenn der Parameter "- *Zuweisung* " lautet `true` , werden- <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> Objekte für das-Ereignis erstellt.</span><span class="sxs-lookup"><span data-stu-id="61677-116">When the *allowEventHandlers* parameter is `true`, <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are created for the event.</span></span> <span data-ttu-id="61677-117">Alle Parameter, die für das Ereignis definiert wurden, sind nun für den <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> in der Variablenauflistung des <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="61677-117">Any parameters that were defined for the event are now available to the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> in the variables collection of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span></span>  
  
```csharp  
public override void InitializeTask(Connections connections,  
   VariableDispenser variables, IDTSInfoEvents events,  
   IDTSLogging log, EventInfos eventInfos,  
   LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
{  
    this.eventInfos = eventInfos;  
    string[] paramNames = new string[1];  
    TypeCode[] paramTypes = new TypeCode[1]{TypeCode.Int32};  
    string[] paramDescriptions = new string[1];  
  
    paramNames[0] = "InitialValue";  
    paramDescriptions[0] = "The value before it is incremented.";  
  
    this.eventInfos.Add("OnBeforeIncrement",   
      "Fires before the task increments the value.",  
      true,paramNames,paramTypes,paramDescriptions);  
    this.onBeforeIncrement = this.eventInfos["OnBeforeIncrement"];  
  
    paramDescriptions[0] = "The value after it has been incremented.";  
    this.eventInfos.Add("OnAfterIncrement",  
      "Fires after the initial value is updated.",  
      true,paramNames, paramTypes,paramDescriptions);  
    this.onAfterIncrement = this.eventInfos["OnAfterIncrement"];  
}  
```  
  
```vb  
Public Overrides Sub InitializeTask(ByVal connections As Connections, _  
ByVal variables As VariableDispenser, ByVal events As IDTSInfoEvents, _  
ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, _  
ByVal logEntryInfos As LogEntryInfos, ByVal refTracker As ObjectReferenceTracker)   
  
    Dim paramNames(0) As String  
    Dim paramTypes(0) As TypeCode = {TypeCode.Int32}  
    Dim paramDescriptions(0) As String  
  
    Me.eventInfos = eventInfos  
  
    paramNames(0) = "InitialValue"  
    paramDescriptions(0) = "The value before it is incremented."  
  
    Me.eventInfos.Add("OnBeforeIncrement", _  
      "Fires before the task increments the value.", _  
      True, paramNames, paramTypes, paramDescriptions)  
    Me.onBeforeIncrement = Me.eventInfos("OnBeforeIncrement")  
  
    paramDescriptions(0) = "The value after it has been incremented."  
    Me.eventInfos.Add("OnAfterIncrement", _  
      "Fires after the initial value is updated.", True, _  
      paramNames, paramTypes, paramDescriptions)  
    Me.onAfterIncrement = Me.eventInfos("OnAfterIncrement")  
  
End Sub  
```  
  
## <a name="raising-custom-events"></a><span data-ttu-id="61677-118">Auslösen von benutzerdefinierten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="61677-118">Raising Custom Events</span></span>  
 <span data-ttu-id="61677-119">Benutzerdefinierte Ereignisse werden erstellt, indem die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61677-119">Custom events are raised by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="61677-120">Die folgende Codezeile löst ein benutzerdefiniertes Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="61677-120">The following line of code raises a custom event.</span></span>  
  
```csharp  
componentEvents.FireCustomEvent(this.onBeforeIncrement.Name,  
   this.onBeforeIncrement.Description, ref arguments,  
   null, ref bFireOnBeforeIncrement);  
```  
  
```vb  
componentEvents.FireCustomEvent(Me.onBeforeIncrement.Name, _  
Me.onBeforeIncrement.Description, arguments, _  
Nothing,  bFireOnBeforeIncrement)  
```  
  
## <a name="sample"></a><span data-ttu-id="61677-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61677-121">Sample</span></span>  
 <span data-ttu-id="61677-122">Im folgenden Beispiel ist ein Task dargestellt, der ein benutzerdefiniertes Ereignis in der `InitializeTask`-Methode definiert, das benutzerdefinierte Ereignis der <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>-Auflistung hinzufügt und dann das benutzerdefinierte Ereignis während der `Execute`-Methode durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>-Methode auslöst.</span><span class="sxs-lookup"><span data-stu-id="61677-122">The following example shows a task that defines a custom event in the `InitializeTask` method, adds the custom event to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection, and then raises the custom event during its `Execute` method by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span>  
  
```csharp  
[DtsTask(DisplayName = "CustomEventTask")]  
    public class CustomEventTask : Task  
    {  
        public override DTSExecResult Execute(Connections connections,   
          VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,  
           IDTSLogging log, object transaction)  
        {  
            bool fireAgain;  
            object[] args = new object[1] { "The value of the parameter." };  
            componentEvents.FireCustomEvent( "MyCustomEvent",   
              "Firing the custom event.", ref args,  
              "CustomEventTask" , ref fireAgain );  
            return DTSExecResult.Success;  
        }  
  
        public override void InitializeTask(Connections connections,  
          VariableDispenser variableDispenser, IDTSInfoEvents events,  
          IDTSLogging log, EventInfos eventInfos,  
          LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
        {  
            string[] names = new string[1] {"Parameter1"};  
            TypeCode[] types = new TypeCode[1] {TypeCode.String};  
            string[] descriptions = new string[1] {"Parameter description." };  
  
            eventInfos.Add("MyCustomEvent",  
             "Fires when my interesting event happens.",  
             true, names, types, descriptions);  
  
        }  
   }  
```  
  
```vb  
<DtsTask(DisplayName = "CustomEventTask")> _   
    Public Class CustomEventTask  
     Inherits Task  
        Public Overrides Function Execute(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser, _  
          ByVal componentEvents As IDTSComponentEvents, _  
          ByVal log As IDTSLogging, ByVal transaction As Object) _  
          As DTSExecResult  
  
            Dim fireAgain As Boolean  
            Dim args() As Object =  New Object(1) {"The value of the parameter."}  
  
            componentEvents.FireCustomEvent("MyCustomEvent", _  
              "Firing the custom event.", args, _  
              "CustomEventTask" ,  fireAgain)  
            Return DTSExecResult.Success  
        End Function  
  
        Public Overrides  Sub InitializeTask(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser,  
          ByVal events As IDTSInfoEvents,  
          ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, ByVal logEnTryInfos As LogEnTryInfos, ByVal refTracker As ObjectReferenceTracker)  
  
            Dim names() As String =  New String(1) {"Parameter1"}  
            Dim types() As TypeCode =  New TypeCode(1) {TypeCode.String}  
            Dim descriptions() As String =  New String(1) {"Parameter description."}  
  
            eventInfos.Add("MyCustomEvent", _  
              "Fires when my interesting event happens.", _  
              True, names, types, descriptions)  
  
        End Sub  
  
    End Class  
```  
  
<span data-ttu-id="61677-123">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="61677-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="61677-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="61677-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="61677-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="61677-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="61677-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="61677-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61677-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61677-127">See Also</span></span>  
 <span data-ttu-id="61677-128">[Integration Services-Ereignishandler &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="61677-128">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="61677-129">Hinzufügen eines Ereignishandlers zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="61677-129">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
