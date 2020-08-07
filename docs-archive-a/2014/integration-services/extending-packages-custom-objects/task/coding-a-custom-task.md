---
title: Codieren eines benutzerdefinierten Tasks | Microsoft-Dokumentation
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
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619224"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="ecf48-102">Codieren eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-102">Coding a Custom Task</span></span>
  <span data-ttu-id="ecf48-103">Nachdem Sie eine Klasse erstellt haben, die von der Basisklasse [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) erbt, und das <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attribut auf die Klasse angewendet haben, müssen Sie die Implementierung der Eigenschaften und Methoden der Basisklasse überschreiben, um die benutzerdefinierte Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="ecf48-104">Konfigurieren des Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="ecf48-105">Überprüfen des Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-105">Validating the Task</span></span>
 <span data-ttu-id="ecf48-106">Wenn Sie ein [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Paket entwerfen, können Sie die Validierung verwenden, um Einstellungen für die einzelnen Tasks zu überprüfen, sodass falsche oder unpassende Einstellungen gleich nach dem Festlegen abgefangen werden können und nicht erst zur Laufzeit auffallen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="ecf48-107">Der Sinn und Zweck der Validierung besteht darin zu bestimmen, ob der Task ungültige Einstellungen oder Verbindungen umfasst, durch die das erfolgreiche Ausführen verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="ecf48-108">Auf diese Weise wird sichergestellt, dass das Paket nur Tasks enthält, bei denen die Wahrscheinlichkeit groß ist, dass sie beim ersten Versuch korrekt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="ecf48-109">Sie können die Validierung mithilfe der `Validate`-Methode in benutzerdefiniertem Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="ecf48-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="ecf48-110">Die Runtime-Engine überprüft einen Task, indem die `Validate`-Methode im Task aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="ecf48-111">Der Taskentwickler ist dafür verantwortlich, die Kriterien zu definieren, die eine erfolgreiche oder fehlgeschlagene Taskvalidierung ausmachen, und eine Benachrichtigung an die Runtime-Engine mit dem Ergebnis dieser Auswertung auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ecf48-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="ecf48-112">Abstrakte Basisklasse des Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="ecf48-113">Die abstrakte Basisklasse [Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) stellt die `Validate` Methode bereit, die jeder Task überschreibt, um seine Validierungs Kriterien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ecf48-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="ecf48-114">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer ruft die `Validate`-Methode automatisch mehrere Male während des Paketentwurfs auf und bietet dem Benutzer visuelle Hinweise, wenn Warnungen oder Fehler auftreten, sodass Probleme mit der Konfiguration des Tasks ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="ecf48-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="ecf48-115">Die Validierungsergebnisse von Tasks werden bereitgestellt, indem ein Wert aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Enumeration zurückgegeben wird und Warnungs- und Fehlerereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="ecf48-116">Diese Ereignisse enthalten Informationen, die dem Benutzer im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="ecf48-117">Nachfolgend finden Sie einige Beispiele für Validierungen:</span><span class="sxs-lookup"><span data-stu-id="ecf48-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="ecf48-118">Ein Verbindungs-Manager validiert den spezifischen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="ecf48-119">Ein Verbindungs-Manager überprüft, dass der Typ der Eingabe der erwartete Typ ist, beispielsweise eine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="ecf48-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="ecf48-120">Ein Task, der eine Datenbankeingabe erwartet, überprüft, dass keine Daten von einer Nicht-Datenbankverbindung empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="ecf48-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="ecf48-121">Ein Task garantiert, dass keine seiner Eigenschaften mit anderen Eigenschaften, die für den gleichen Task festgelegt wurden, in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="ecf48-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="ecf48-122">Ein Task garantiert, dass alle erforderlichen Ressourcen, die von dem Task bei der Ausführung verwendet werden, verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ecf48-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="ecf48-123">Bei der Bestimmung, was validiert wird, spielt die Leistung eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="ecf48-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="ecf48-124">Die Eingabe für einen Task kann beispielsweise eine Verbindung über ein Netzwerk mit niedriger Bandbreite oder hohem Datenverkehr sein.</span><span class="sxs-lookup"><span data-stu-id="ecf48-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="ecf48-125">Die Validierung kann möglicherweise mehrere Sekunden dauern, wenn Sie festlegen, dass überprüft werden soll, ob die Ressource verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ecf48-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="ecf48-126">Eine andere Validierung kann möglicherweise zu einem Roundtrip zu einem stark beanspruchten Server führen, und die Validierungsroutine kann langsam sein.</span><span class="sxs-lookup"><span data-stu-id="ecf48-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="ecf48-127">Obwohl es viele Eigenschaften und Einstellungen gibt, die überprüft werden können, ist es nicht ratsam, alles zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="ecf48-128">Der Code in der `Validate`-Methode wird auch von <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> aufgerufen, bevor der Task ausgeführt wird, und <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> bricht die Ausführung ab, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="ecf48-129">Überlegungen zur Benutzeroberfläche während der Validierung</span><span class="sxs-lookup"><span data-stu-id="ecf48-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="ecf48-130">Die [Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) enthält eine <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> Schnittstelle als Parameter für die `Validate` Methode.</span><span class="sxs-lookup"><span data-stu-id="ecf48-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="ecf48-131">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>-Schnittstelle umfasst die Methoden, die von dem Task aufgerufen werden, um Ereignisse für die Runtime-Engine auszulösen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="ecf48-132">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>-Methode und die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>-Methode werden aufgerufen, wenn eine Warnung oder eine Fehlerbedingung während der Validierung auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="ecf48-133">Für beide Warnungsmethoden sind die gleichen Parameter erforderlich. Dazu gehören ein Fehlercode, eine Quellkomponente, eine Beschreibung, eine Hilfedatei sowie Hilfekontextinformationen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="ecf48-134">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer verwendet diese Informationen, um visuelle Hinweise auf der Entwurfsoberfläche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="ecf48-135">Die vom Designer bereitgestellten visuellen Hinweise enthalten ein Ausrufezeichen, das neben dem Task auf der Entwurfsoberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="ecf48-136">Dieser visuelle Hinweis signalisiert dem Benutzer, dass der Task zusätzliche Konfiguration erfordert, bevor die Ausführung fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecf48-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="ecf48-137">Mit dem Ausrufezeichen wird auch eine QuickInfo angezeigt, die eine Fehlermeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="ecf48-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="ecf48-138">Die Fehlermeldung wird vom Task im Beschreibungsparameter des Ereignisses bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="ecf48-139">Fehlermeldungen werden auch in der **Aufgabenliste** von [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] angezeigt, sodass der Benutzer einen zentralen Ort zur Anzeige aller Validierungsfehler erhält.</span><span class="sxs-lookup"><span data-stu-id="ecf48-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="ecf48-140">Beispiel für die Validierung</span><span class="sxs-lookup"><span data-stu-id="ecf48-140">Validation Example</span></span>
 <span data-ttu-id="ecf48-141">Im folgenden Codebeispiel wird ein Task mit einer `UserName`-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ecf48-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="ecf48-142">Diese Eigenschaft wurde angegeben, da sie für eine erfolgreiche Validierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ecf48-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="ecf48-143">Wenn die Eigenschaft nicht festgelegt wird, gibt der Task einen Fehler aus und gibt einen <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="ecf48-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="ecf48-144">Die `Validate`-Methode wird in einem try/catch-Block umschlossen und führt zu einem Fehler bei der Validierung, wenn eine Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="ecf48-145">Beibehalten des Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-145">Persisting the Task</span></span>
 <span data-ttu-id="ecf48-146">In der Regel müssen Sie keine benutzerdefinierte Persistenz für einen Task implementieren.</span><span class="sxs-lookup"><span data-stu-id="ecf48-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="ecf48-147">Die benutzerdefinierte Persistenz ist nur erforderlich, wenn die Eigenschaften eines Objekts komplexe Datentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="ecf48-148">Weitere Informationen finden Sie unter [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Entwickeln von benutzerdefinierten Objekten für Integration Services).</span><span class="sxs-lookup"><span data-stu-id="ecf48-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="ecf48-149">Ausführen des Tasks</span><span class="sxs-lookup"><span data-stu-id="ecf48-149">Executing the Task</span></span>
 <span data-ttu-id="ecf48-150">In diesem Abschnitt wird beschrieben, wie die `Execute`-Methode verwendet wird, die von Tasks geerbt und überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="ecf48-151">In diesem Abschnitt werden auch verschiedene Methoden zum Bereitstellen von Informationen zu den Ergebnissen der Taskausführung erläutert.</span><span class="sxs-lookup"><span data-stu-id="ecf48-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="ecf48-152">Execute-Methode</span><span class="sxs-lookup"><span data-stu-id="ecf48-152">Execute Method</span></span>
 <span data-ttu-id="ecf48-153">Tasks, die in einem Paket enthalten sind, werden ausgeführt, wenn ihre `Execute`-Methode von der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Laufzeit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="ecf48-154">Die grundlegende Geschäftslogik und Funktionalität von Tasks ist in dieser Methode implementiert. Die Ergebnisse der Ausführung werden durch Ausgeben von Meldungen, Zurückgeben eines Werts aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Enumeration und Überschreiben der `get`-Eigenschaft der `ExecutionValue`-Eigenschaft bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="ecf48-155">Die Basisklasse [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) stellt eine Standardimplementierung der <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>-Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="ecf48-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="ecf48-156">Die benutzerdefinierten Tasks überschreiben diese Methode, um ihre Laufzeitfunktionalität zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ecf48-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="ecf48-157">Das <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt umschließt den Task, sodass dieser von der Runtime-Engine und den anderen Objekten in dem Paket isoliert wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="ecf48-158">Aufgrund dieser Isolation erkennt der Task seine Stelle in dem Paket bezüglich der Ausführungsreihenfolge nicht und wird nur ausgeführt, wenn er durch die Laufzeit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="ecf48-159">Durch diese Architektur werden Probleme verhindert, die auftreten können, wenn Tasks während der Ausführung das Paket ändern.</span><span class="sxs-lookup"><span data-stu-id="ecf48-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="ecf48-160">Der Task erhält nur durch die Objekte, die ihm in der <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>-Methode als Parameter bereitgestellt werden, Zugriff auf die anderen Objekte in dem Paket.</span><span class="sxs-lookup"><span data-stu-id="ecf48-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="ecf48-161">Mithilfe dieser Parameter können Tasks Ereignisse auslösen, Einträge in das Ereignisprotokoll schreiben, auf die Variablenauflistung zugreifen und Verbindungen zu Datenquellen in Transaktionen eintragen, während gleichzeitig die Isolation beibehalten wird, die erforderlich ist, um die Stabilität und Zuverlässigkeit des Pakets zu garantieren.</span><span class="sxs-lookup"><span data-stu-id="ecf48-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="ecf48-162">In der folgenden Tabelle sind die für den Task in der <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>-Methode bereitgestellten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="ecf48-163">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecf48-163">Parameter</span></span>|<span data-ttu-id="ecf48-164">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecf48-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="ecf48-165">Enthält eine Auflistung von <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekten, die für den Task verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ecf48-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="ecf48-166">Enthält die Variablen, die für den Task verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ecf48-166">Contains the variables available to the task.</span></span> <span data-ttu-id="ecf48-167">Die Tasks verwenden Variablen durch den VariableDispenser; die Tasks verwenden keine Variablen direkt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="ecf48-168">Der VariableDispenser sperrt und entsperrt Variablen und verhindert Deadlocks oder Überschreibungen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="ecf48-169">Enthält die Methoden, die von dem Task zum Auslösen von Ereignissen in der Runtime-Engine aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="ecf48-170">Enthält Methoden und Eigenschaften, die von dem Task zum Schreiben von Ereignissen in das Ereignisprotokoll verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="ecf48-171">Object</span><span class="sxs-lookup"><span data-stu-id="ecf48-171">Object</span></span>|<span data-ttu-id="ecf48-172">Enthält ggf. das Transaktionsobjekt, von dem der Container ein Teil ist.</span><span class="sxs-lookup"><span data-stu-id="ecf48-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="ecf48-173">Dieser Wert wird als Parameter an die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode eines <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekts übergeben.</span><span class="sxs-lookup"><span data-stu-id="ecf48-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="ecf48-174">Bereitstellen von Feedback zur Ausführung</span><span class="sxs-lookup"><span data-stu-id="ecf48-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="ecf48-175">Bei Tasks wird der Code in `try/catch`-Blöcke eingebunden, um zu verhindern, dass Ausnahmen in der Runtime-Engine ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="ecf48-176">Dadurch wird sichergestellt, dass das Paket die Ausführung abschließt und nicht unerwartet beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="ecf48-177">Die Runtime-Engine bietet jedoch andere Mechanismen zur Behandlung von Fehlerbedingungen, die während der Ausführung eines Tasks auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ecf48-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="ecf48-178">Dazu gehört das Ausgeben von Fehler- und Warnmeldungen, das Zurückgeben eines Werts aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Struktur, das Ausgeben von Meldungen, das Zurückgeben des <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Werts sowie das Offenlegen von Informationen zu den Ergebnissen der Taskausführung durch die <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ecf48-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="ecf48-179">Die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>-Schnittstelle enthält die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>-Methode und die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>-Methode, die von dem Task aufgerufen werden können, um Fehler- und Warnmeldungen für die Runtime-Engine auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ecf48-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="ecf48-180">Für beide Methoden sind Parameter wie der Fehlercode, die Quellkomponente, die Beschreibung, die Hilfedatei sowie Hilfekontextinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ecf48-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="ecf48-181">Je nach der Konfiguration des Tasks reagiert die Laufzeit auf diese Meldungen, indem Ereignisse und Breakpoints ausgelöst oder Informationen in das Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ecf48-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="ecf48-182">Das <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt stellt auch die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>-Eigenschaft bereit, die verwendet werden kann, um zusätzliche Informationen zu den Ergebnissen der Ausführung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ecf48-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="ecf48-183">Wenn ein Task beispielsweise Zeilen aus einer Tabelle als Teil seiner `Execute`-Methode löscht, wird möglicherweise die Anzahl von gelöschten Zeilen als Wert der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ecf48-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="ecf48-184">Darüber hinaus stellt das <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="ecf48-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="ecf48-185">Mithilfe dieser Eigenschaft kann der Benutzer den von dem Task zurückgegebenen <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>-Wert einer Variablen zuordnen, die für den Task sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ecf48-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="ecf48-186">Die angegebene Variable kann dann verwendet werden, um Rangfolgeneinschränkungen zwischen Tasks einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ecf48-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="ecf48-187">Ausführungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="ecf48-187">Execution Example</span></span>
 <span data-ttu-id="ecf48-188">Im folgenden Codebeispiel wird eine Implementierung der `Execute`-Methode veranschaulicht, und es wird eine überschriebene `ExecutionValue`-Eigenschaft gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf48-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="ecf48-189">Der Task löscht die Datei, die von der `fileName`-Eigenschaft des Tasks angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ecf48-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="ecf48-190">Der Task gibt eine Warnung aus, wenn die Datei nicht vorhanden oder die `fileName`-Eigenschaft eine leere Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="ecf48-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="ecf48-191">Der Task gibt eine `Boolean`-Wert in der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>-Eigenschaft zurück, um anzugeben, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="ecf48-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="ecf48-192">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="ecf48-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ecf48-193">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="ecf48-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ecf48-194">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="ecf48-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ecf48-195">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ecf48-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecf48-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecf48-196">See Also</span></span>
 <span data-ttu-id="ecf48-197">[Erstellen einer benutzerdefinierten](creating-a-custom-task.md) Aufgabe [Codieren eines](coding-a-custom-task.md) benutzerdefinierten Tasks [Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="ecf48-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


