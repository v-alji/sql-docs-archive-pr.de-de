---
title: Codieren und Debuggen des Skripttasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695854"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="9b965-102">Codieren und Debuggen des Skripttasks</span><span class="sxs-lookup"><span data-stu-id="9b965-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="9b965-103">Nach dem Konfigurieren des Skripttasks im **Skripttask-Editor** schreiben Sie den benutzerdefinierten Code in der Skripttask-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="9b965-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="9b965-104">Skripttask-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="9b965-104">Script Task Development Environment</span></span>
 <span data-ttu-id="9b965-105">Der Skripttask verwendet [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Tools für Anwendungen (VSTA) als Entwicklungsumgebung für das Skript selbst.</span><span class="sxs-lookup"><span data-stu-id="9b965-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="9b965-106">Skriptcode wird in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b965-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="9b965-107">Sie geben die Skriptsprache an, indem Sie die **ScriptLanguage**-Eigenschaft im **Skripttask-Editor** festlegen.</span><span class="sxs-lookup"><span data-stu-id="9b965-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="9b965-108">Falls Sie lieber eine andere Programmiersprache verwenden möchten, können Sie in Ihrer bevorzugten Sprache eine benutzerdefinierte Assembly entwickeln und ihre Funktionen aus dem Code im Skripttask aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9b965-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="9b965-109">Das im Skripttask erstellte Skript wird in der Paketdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9b965-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="9b965-110">Es gibt keine separate Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="9b965-110">There is no separate script file.</span></span> <span data-ttu-id="9b965-111">Deshalb hat die Verwendung des Skripttasks keinen Einfluss auf die Paketbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9b965-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b965-112">Wenn Sie das Paket entwerfen und das Skript debuggen, wird der Skriptcode vorübergehend in eine Projektdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b965-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="9b965-113">Da das Speichern vertraulicher Informationen in einer Datei ein Sicherheitsrisiko darstellt, sollte der Skriptcode keine vertraulichen Daten wie Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="9b965-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="9b965-114">Standardmäßig ist `Option Strict` in der IDE deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9b965-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="9b965-115">Skripttask-Projektstruktur</span><span class="sxs-lookup"><span data-stu-id="9b965-115">Script Task Project Structure</span></span>
 <span data-ttu-id="9b965-116">Wenn Sie das in einem Skripttask enthaltene Skript erstellen oder ändern, öffnet VSTA ein neues leeres Projekt oder erneut das vorhandene Projekt.</span><span class="sxs-lookup"><span data-stu-id="9b965-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="9b965-117">Die Erstellung dieses VSTA-Projekts wirkt sich nicht auf die Paketbereitstellug aus, da das Projekt in der Paketdatei gespeichert wird. Der Skripttask erstellt keine weiteren Dateien.</span><span class="sxs-lookup"><span data-stu-id="9b965-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="9b965-118">Projektelemente und -klassen im Skripttaskprojekt</span><span class="sxs-lookup"><span data-stu-id="9b965-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="9b965-119">Standardmäßig umfasst das im VSTA-Fenster &lt;legacyBold&gt;Projektexplorer&lt;/legacyBold&gt; angezeigte Skripttaskprojekt nur ein Element, nämlich `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="9b965-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="9b965-120">Das `ScriptMain`-Element enthält wiederum eine einzelne Klasse, die ebenfalls `ScriptMain` heißt.</span><span class="sxs-lookup"><span data-stu-id="9b965-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="9b965-121">Die Codeelemente in der Klasse variieren abhängig davon, welche Programmiersprache Sie für den Skripttask gewählt haben:</span><span class="sxs-lookup"><span data-stu-id="9b965-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="9b965-122">Wenn der Skripttask für die Programmiersprache [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] konfiguriert ist, enthält die `ScriptMain`-Klasse eine öffentliche Unterroutine namens `Main`.</span><span class="sxs-lookup"><span data-stu-id="9b965-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="9b965-123">Die `ScriptMain.Main`-Unterroutine ist die Methode, die die Laufzeit beim Ausführen des Skripttasks aufruft.</span><span class="sxs-lookup"><span data-stu-id="9b965-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="9b965-124">Standardmäßig enthält die `Main`-Unterroutine eines neuen Skripts als einzigen Code die Zeile `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="9b965-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="9b965-125">Diese Zeile informiert die Laufzeit, dass der Task erfolgreich durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b965-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="9b965-126">Die- `Dts.TaskResult` Eigenschaft wird unter [zurückgeben von Ergebnissen aus dem Skript Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="9b965-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="9b965-127">Wenn der Skripttask für die Programmiersprache Visual C# konfiguriert ist, enthält die `ScriptMain`-Klasse die öffentliche Methode `Main`.</span><span class="sxs-lookup"><span data-stu-id="9b965-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="9b965-128">Die Methode wird aufgerufen, wenn der Skripttask ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b965-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="9b965-129">Standardmäßig enthält die `Main`-Methode die Zeile `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="9b965-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="9b965-130">Diese Zeile informiert die Laufzeit, dass der Task erfolgreich durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b965-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="9b965-131">Das `ScriptMain`-Element kann zusätzlich zur `ScriptMain`-Klasse weitere Klassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9b965-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="9b965-132">Klassen stehen nur dem Skripttask, in dem sie sich befinden, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9b965-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="9b965-133">Standardmäßig enthält das `ScriptMain`-Projektelement den folgenden automatisch generierten Code.</span><span class="sxs-lookup"><span data-stu-id="9b965-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="9b965-134">Die Codevorlage bietet auch eine Übersicht über den Skripttask, und zusätzliche Informationen über das Abrufen und Bearbeiten von SSIS-Objekten, z. B. Variablen, Ereignisse und Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="9b965-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="9b965-135">Zusätzliche Projektelemente im Skripttaskprojekt</span><span class="sxs-lookup"><span data-stu-id="9b965-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="9b965-136">Das Skripttaskprojekt kann neben dem Standardelement `ScriptMain` noch weitere Elemente einschließen.</span><span class="sxs-lookup"><span data-stu-id="9b965-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="9b965-137">Sie können Klassen, Module und Codedateien zum Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b965-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="9b965-138">Außerdem können Sie Ordner verwenden, um Elementgruppen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="9b965-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="9b965-139">Alle Elemente, die Sie hinzufügen, werden im Paket beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9b965-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="9b965-140">Verweise im Skripttaskprojekt</span><span class="sxs-lookup"><span data-stu-id="9b965-140">References in the Script Task Project</span></span>
 <span data-ttu-id="9b965-141">Sie können Verweise auf verwaltete Assemblys hinzufügen, indem Sie im **Projektexplorer** mit der rechten Maustaste auf das Skripttaskprojekt und anschließend auf **Verweis hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="9b965-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="9b965-142">Weitere Informationen finden Sie unter [Verweisen auf andere Assemblys in Skriptlösungen](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="9b965-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="9b965-143">Sie können Projektverweise in der VSTA-IDE in der **Klassenansicht** oder im **Projektexplorer** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9b965-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="9b965-144">Diese Fenster öffnen Sie über das Menü **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="9b965-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="9b965-145">Einen neuen Verweis können Sie über das Menü **Projekt**, den **Projektexplorer** oder die **Klassenansicht** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b965-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="9b965-146">Interagieren mit Paketen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="9b965-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="9b965-147">Ein Skripttask interagiert mit dem entsprechenden Paket und der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Laufzeit über das globale `Dts`-Objekt, eine Instanz der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>-Klasse, und ihre Elemente.</span><span class="sxs-lookup"><span data-stu-id="9b965-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="9b965-148">Die folgende Tabelle enthält die wichtigsten öffentlichen Elemente der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>-Klasse, die für den Skripttaskcode über das globale `Dts`-Objekt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="9b965-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="9b965-149">In den Themen in diesem Abschnitt wird die Verwendung dieser Elemente detaillierter erläutert.</span><span class="sxs-lookup"><span data-stu-id="9b965-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="9b965-150">Member</span><span class="sxs-lookup"><span data-stu-id="9b965-150">Member</span></span>|<span data-ttu-id="9b965-151">Zweck</span><span class="sxs-lookup"><span data-stu-id="9b965-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="9b965-152">Bietet Zugriff auf im Paket definierte Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9b965-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="9b965-153">Liefert eine Ereignisschnittstelle, damit der Skripttask Fehler, Warnungen und Informationsmeldungen auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="9b965-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="9b965-154">Bietet eine einfache Möglichkeit, ein einzelnes Objekt (zusätzlich zu `TaskResult`) an die Laufzeit auszugeben, das auch für die Workflowverzweigung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9b965-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="9b965-155">Protokolliert Informationen wie den Taskstatus und die Ergebnisse bei aktivierten Protokollanbietern.</span><span class="sxs-lookup"><span data-stu-id="9b965-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="9b965-156">Meldet den Erfolg oder Misserfolg des Tasks.</span><span class="sxs-lookup"><span data-stu-id="9b965-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="9b965-157">Stellt ggf. die Transaktion bereit, innerhalb derer der Taskcontainer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b965-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="9b965-158">Bietet Zugriff auf die Variablen in den Taskeigenschaften `ReadOnlyVariables` und `ReadWriteVariables` zur Verwendung im Skript.</span><span class="sxs-lookup"><span data-stu-id="9b965-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="9b965-159">Die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>-Klasse enthält auch einige öffentliche Elemente, die Sie wahrscheinlich nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b965-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="9b965-160">Member</span><span class="sxs-lookup"><span data-stu-id="9b965-160">Member</span></span>|<span data-ttu-id="9b965-161">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b965-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="9b965-162">Die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft ermöglicht einen einfacheren Zugriff auf Variablen.</span><span class="sxs-lookup"><span data-stu-id="9b965-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="9b965-163">Sie können zwar <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> verwenden, müssen jedoch explizit Methoden aufrufen, um Variablen für das Lesen und Schreiben zu sperren und die Sperre wieder aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="9b965-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="9b965-164">Der Skripttask erledigt die Sperrsemantik für Sie, wenn Sie die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b965-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="9b965-165">Debuggen des Skripttasks</span><span class="sxs-lookup"><span data-stu-id="9b965-165">Debugging the Script Task</span></span>
 <span data-ttu-id="9b965-166">Legen Sie zum Debuggen des Codes im Skripttask mindestens einen Breakpoint fest, und schließen Sie dann die VSTA IDE, um das Paket in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9b965-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9b965-167">Wenn die Ausführung des Skripttasks beginnt, wird die VSTA IDE erneut geöffnet und der Code schreibgeschützt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b965-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="9b965-168">Nachdem die Ausführung den Breakpoint erreicht hat, können Sie die Variablenwerte untersuchen und den übrigen Code schrittweise durchgehen.</span><span class="sxs-lookup"><span data-stu-id="9b965-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="9b965-169">Sie können den Skripttask debuggen, wenn Sie das Paket im 64-Bit-Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b965-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b965-170">Sie müssen das Paket ausführen, um den Skripttask zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="9b965-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="9b965-171">Wenn Sie nur den einzelnen Task ausführen, werden Breakpoints im Skripttaskcode ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9b965-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b965-172">Sie können einen Skripttask nicht debuggen, wenn Sie ihn als Teil eines untergeordneten Pakets aus dem Task Paket ausführen ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b965-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="9b965-173">Breakpoints, die Sie im Skripttask in dem untergeordneten Paket festlegen, werden unter diesen Umständen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9b965-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="9b965-174">Sie können das untergeordnete Paket normalerweise debuggen, indem Sie es getrennt ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b965-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b965-175">Wenn Sie ein Paket debuggen, das mehrere Skripttasks enthält, debuggt der Debugger einen Skripttask.</span><span class="sxs-lookup"><span data-stu-id="9b965-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="9b965-176">Das System kann einen anderen Skripttask debuggen, wenn der Debugger wie im Fall eines Foreach- oder For-Schleifencontainers abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="9b965-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="9b965-177">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9b965-177">External Resources</span></span>

-   <span data-ttu-id="9b965-178">Blogeintrag: [VSTA setup and configuration troubles for SSIS 2008 and R2 installations (Probleme mit der VSTA-Einrichtung und -Konfiguration bei SSIS 2008- und R2-Installationen)](https://go.microsoft.com/fwlink/?LinkId=215661) (auf blogs.msdn.com).</span><span class="sxs-lookup"><span data-stu-id="9b965-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="9b965-179">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="9b965-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9b965-180">Die neuesten Downloads, Artikel, Beispiele und Videos von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] sowie ausgewählte Lösungen aus der Community finden Sie auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Seite auf MSDN:</span><span class="sxs-lookup"><span data-stu-id="9b965-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9b965-181">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="9b965-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9b965-182">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9b965-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b965-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b965-183">See Also</span></span>
 <span data-ttu-id="9b965-184">[Verweisen auf andere Assemblys in Skript Lösungen](../referencing-other-assemblies-in-scripting-solutions.md) [Konfigurieren des Skript Tasks im Skript Task-Editor](configuring-the-script-task-in-the-script-task-editor.md)</span><span class="sxs-lookup"><span data-stu-id="9b965-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


