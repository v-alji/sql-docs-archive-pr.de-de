---
title: Bereitstellen von Unterstützung für das Debuggen in einem benutzerdefinierten Task | Microsoft-Dokumentation
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
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619227"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="4e98f-102">Bereitstellen von Unterstützung für das Debuggen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="4e98f-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="4e98f-103">Die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Runtime-Engine ermöglicht das Anhalten der Ausführung von Paketen, Tasks und anderen Arten von Containern mithilfe von Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="4e98f-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="4e98f-104">Mit Breakpoints können Sie Überprüfungen durchführen und Fehler beheben, die verhindern, dass die Anwendung oder die Tasks korrekt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e98f-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="4e98f-105">Die Breakpointarchitektur ermöglicht es dem Client, den Laufzeitwert von Objekten im Paket an definierten Ausführungpunkten auszuwerten, während die Verarbeitung des Tasks angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="4e98f-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="4e98f-106">Entwickler benutzerdefinierter Tasks können mit dieser Architektur über die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>-Schnittstelle und ihre übergeordnete Schnittstelle, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>, benutzerdefinierte Breakpointziele erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="4e98f-107">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>-Schnittstelle definiert die Interaktion zwischen der Runtime-Engine und dem Task zur Erstellung und Verwaltung benutzerdefinierter Breakpointorte oder -ziele.</span><span class="sxs-lookup"><span data-stu-id="4e98f-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="4e98f-108">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>-Schnittstelle bietet Methoden und Eigenschaften, die von der Runtime-Engine aufgerufen werden, um den Task anzuhalten oder seine Ausführung fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="4e98f-109">Breakpointorte oder -ziele sind Punkte in der Taskausführung, an denen die Verarbeitung angehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e98f-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="4e98f-110">Benutzer können im Dialogfeld **Breakpoints festlegen** unter den verfügbaren Breakpointzielen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="4e98f-111">Zusätzlich zu den standardmäßigen Breakpointoptionen bietet beispielsweise der Foreach-Schleifencontainer die Option Am Anfang jeder Iteration der Schleife unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="4e98f-112">Wenn ein Task während der Ausführung ein Breakpointziel erreicht, wertet er dieses aus, um festzustellen, ob ein Breakpoint aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e98f-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="4e98f-113">Damit wird angezeigt, dass der Benutzer die Ausführung an diesem Breakpoint beenden möchte.</span><span class="sxs-lookup"><span data-stu-id="4e98f-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="4e98f-114">Wenn der Breakpoint aktiviert ist, löst der Task das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>-Ereignis bei der Runtime-Engine aus.</span><span class="sxs-lookup"><span data-stu-id="4e98f-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="4e98f-115">Die Runtime-Engine reagiert auf das Ereignis durch Aufruf der `Suspend`-Methode für alle Tasks, die derzeit im Paket ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e98f-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="4e98f-116">Die Ausführung des Tasks wird fortgesetzt, wenn die Laufzeit die `ResumeExecution`-Methode des angehaltenen Tasks aufruft.</span><span class="sxs-lookup"><span data-stu-id="4e98f-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="4e98f-117">Tasks, die keine Breakpoints verwenden, sollten dennoch die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>- und <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>-Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="4e98f-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="4e98f-118">Dadurch wird sichergestellt, dass der Task ordnungsgemäß angehalten wird, wenn andere Objekte im Paket <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>-Ereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="4e98f-119">IDTSBreakpointSite-Schnittstelle und BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="4e98f-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="4e98f-120">Tasks erstellen Breakpointziele durch Aufruf der <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A>-Methode des <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, indem sie eine ganzzahlige ID und eine Zeichenfolgenbeschreibung als Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="4e98f-121">Wenn ein Task den Punkt im Code erreicht, der ein Breakpointziel enthält, überprüft er mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A>-Methode, ob der Breakpoint aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e98f-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="4e98f-122">Falls der Wert `true` lautet, benachrichtigt der Task die Runtime-Engine, indem er das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="4e98f-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="4e98f-123">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>-Schnittstelle definiert eine Methode, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, die von der Runtime-Engine während der Taskerstellung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4e98f-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="4e98f-124">Diese Methode stellt als Parameter das <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>-Objekt bereit, das anschließend vom Task zur Erstellung und Verwaltung der Breakpoints verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e98f-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="4e98f-125">Tasks sollten den <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> zur Verwendung während der `Validate`- und `Execute`-Methoden lokal speichern.</span><span class="sxs-lookup"><span data-stu-id="4e98f-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="4e98f-126">Im folgenden Codebeispiel wird das Erstellen eines Breakpointziels mithilfe des <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4e98f-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="4e98f-127">Im Beispiel wird die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>-Methode aufgerufen, um das Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="4e98f-128">IDTSSuspend-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e98f-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="4e98f-129">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>-Schnittstelle definiert die Methoden, die von der Runtime-Engine aufgerufen werden, um den Task anzuhalten oder seine Ausführung fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4e98f-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="4e98f-130">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>-Schnittstelle wird von der <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>-Schnittstelle implementiert, und ihre `Suspend`- und `ResumeExecution`-Methoden werden meist durch den benutzerdefinierten Task überschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e98f-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="4e98f-131">Wenn die Runtime-Engine ein `OnBreakpointHit`-Ereignis von einem Task empfängt, ruft sie die `Suspend`-Methode für alle derzeit ausgeführten Tasks auf und veranlasst sie, die Ausführung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="4e98f-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="4e98f-132">Wenn der Client die Ausführung fortsetzt, ruft die Runtime-Engine die `ResumeExecution`-Methode der angehaltenen Tasks auf.</span><span class="sxs-lookup"><span data-stu-id="4e98f-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="4e98f-133">Das Anhalten und Fortsetzen der Taskausführung schließt das Anhalten und Fortsetzen des Ausführungsthreads des Tasks ein.</span><span class="sxs-lookup"><span data-stu-id="4e98f-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="4e98f-134">In verwaltetem Code erreichen Sie dies mit der `ManualResetEvent`-Klasse im `System.Threading`-Namespace von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e98f-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="4e98f-135">Im folgenden Codebeispiel wird die Unterbrechung und Wiederaufnahme der Taskausführung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4e98f-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="4e98f-136">Beachten Sie dabei, dass sich die `Execute`-Methode gegenüber dem letzten Codebeispiel geändert hat und der Ausführungsthread angehalten wird, wenn der Breakpoint ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4e98f-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="4e98f-137">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="4e98f-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4e98f-138">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="4e98f-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4e98f-139">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="4e98f-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4e98f-140">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e98f-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e98f-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e98f-141">See Also</span></span>  
 [<span data-ttu-id="4e98f-142">Debuggen der Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="4e98f-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
