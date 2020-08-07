---
title: Programmieren und Debuggen der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619218"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="5ed55-102">Codieren und Debuggen der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="5ed55-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="5ed55-103">Im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer weist die Skriptkomponente zwei Modi auf: Metadatenentwurfsmodus und Codeentwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="5ed55-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="5ed55-104">Wenn Sie den **Transformations-Editor für Skripterstellung** öffnen, befindet sich die Komponente im Metadatenentwurfsmodus, in dem Metadaten konfiguriert und Komponenteneigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="5ed55-105">Nachdem Sie die Eigenschaften der Skriptkomponente festgelegt und die Eingaben und Ausgaben im Metadatenentwurfsmodus konfiguriert haben, können Sie zum Schreiben des benutzerdefinierten Skripts in den Codeentwurfsmodus wechseln.</span><span class="sxs-lookup"><span data-stu-id="5ed55-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="5ed55-106">Weitere Informationen zum Metadatenentwurfsmodus und zum Codeentwurfsmodus finden Sie unter [Configuring the Script Component in the Script Component Editor (Konfigurieren der Skriptkomponente im Skriptkomponenten-Editor)](configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="5ed55-107">Schreiben des Skripts im Codeentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="5ed55-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="5ed55-108">Skriptkomponenten-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="5ed55-108">Script Component Development Environment</span></span>
 <span data-ttu-id="5ed55-109">Klicken Sie zum Schreiben des Skripts im **Transformations-Editor für Skripterstellung** auf der Seite **Skript** auf **Skript bearbeiten**, um die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications-IDE (VSTA) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="5ed55-110">Die VSTA IDE enthält alle Standardfunktionen der [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET-Umgebung wie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Editor mit Farbcodierung, IntelliSense und den Objektkatalog.</span><span class="sxs-lookup"><span data-stu-id="5ed55-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="5ed55-111">Skriptcode wird in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ed55-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="5ed55-112">Sie geben die Skriptsprache an, indem Sie die **ScriptLanguage**-Eigenschaft im **Transformations-Editor für Skripterstellung** festlegen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="5ed55-113">Falls Sie lieber eine andere Programmiersprache verwenden möchten, können Sie in Ihrer bevorzugten Sprache eine benutzerdefinierte Assembly entwickeln und ihre Funktionen aus dem Code in der Skriptkomponente aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="5ed55-114">Das in der Skriptkomponente erstellte Skript wird in der Paketdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5ed55-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="5ed55-115">Es gibt keine separate Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="5ed55-115">There is no separate script file.</span></span> <span data-ttu-id="5ed55-116">Deshalb hat die Verwendung der Skriptkomponente keinen Einfluss auf die Paketbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5ed55-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ed55-117">Beim Entwurf des Pakets wird der Skriptcode vorübergehend in eine Projektdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ed55-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="5ed55-118">Da das Speichern vertraulicher Informationen in einer Datei ein Sicherheitsrisiko darstellt, sollte der Skriptcode keine vertraulichen Daten wie Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="5ed55-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="5ed55-119">Standardmäßig ist `Option Strict` in der IDE deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5ed55-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="5ed55-120">Skriptkomponenten-Projektstruktur</span><span class="sxs-lookup"><span data-stu-id="5ed55-120">Script Component Project Structure</span></span>
 <span data-ttu-id="5ed55-121">Die Leistungsfähigkeit der Skriptkomponente rührt daher, dass Infrastrukturcode erstellt werden kann, mit dem der erforderliche Codeumfang reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ed55-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="5ed55-122">Für diese Funktion ist es erforderlich, dass Eingaben und Ausgaben mit den zugehörigen Spalten und Eigenschaften festgelegt und im Voraus bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="5ed55-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="5ed55-123">Aus diesem Grund können nachträgliche Änderungen an den Metadaten der Komponente dazu führen, dass der von Ihnen geschriebene Code ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="5ed55-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="5ed55-124">Dies verursacht während der Ausführung des Pakets Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="5ed55-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="5ed55-125">Projektelemente und -klassen im Skriptkomponentenprojekt</span><span class="sxs-lookup"><span data-stu-id="5ed55-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="5ed55-126">Wenn Sie in den Codeentwurfsmodus wechseln, wird die VSTA IDE geöffnet und zeigt das `ScriptMain`-Projektelement an.</span><span class="sxs-lookup"><span data-stu-id="5ed55-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="5ed55-127">Das `ScriptMain`-Projektelement enthält die bearbeitbare `ScriptMain`-Klasse, die als Einstiegspunkt für das Skript dient und in die der Code geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5ed55-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="5ed55-128">Die Codeelemente in der Klasse variieren abhängig davon, welche Programmiersprache Sie für den Skripttask gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="5ed55-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="5ed55-129">Das Skriptprojekt enthält zwei zusätzliche, automatisch generierte und schreibgeschützte Projektelemente:</span><span class="sxs-lookup"><span data-stu-id="5ed55-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="5ed55-130">Das `ComponentWrapper`-Projektelement enthält drei Klassen:</span><span class="sxs-lookup"><span data-stu-id="5ed55-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="5ed55-131">Die `UserComponent`-Klasse, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> erbt und die Methoden und Eigenschaften enthält, die Sie verwenden, um Daten zu verarbeiten und mit dem Paket zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="5ed55-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="5ed55-132">Die `ScriptMain`-Klasse erbt von der `UserComponent`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5ed55-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="5ed55-133">Eine `Connections`-Auflistungsklasse mit Verweisen zu den im Transformations-Editor für Skripterstellung auf der Seite Verbindungs-Manager ausgewählten Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="5ed55-134">Eine Auflistungs `Variables` Klasse, die Verweise auf die Variablen enthält, die `ReadOnlyVariable` `ReadWriteVariables` auf der Seite **Skript** des **Transformations-Editors für Skript**Erstellung in den Eigenschaften und eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="5ed55-135">Das- `BufferWrapper` Projekt Element enthält eine Klasse, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> für jede auf der Seite **Eingaben und Ausgaben** des **Transformations-Editors für Skript**Erstellung konfigurierte Eingabe und Ausgabe erbt.</span><span class="sxs-lookup"><span data-stu-id="5ed55-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="5ed55-136">Jede dieser Klassen enthält typisierte Accessoreigenschaften, die mit den konfigurierten Eingabe- und Ausgabespalten übereinstimmen, sowie die Datenflusspuffer, in denen sich diese Spalten befinden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="5ed55-137">Weitere Informationen zur Verwendung dieser Objekte, Methoden und Eigenschaften finden Sie unter [Understanding the Script Component Object Model (Grundlegendes zum Objektmodell der Skriptkomponente)](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="5ed55-138">Informationen darüber, wie die Methoden und Eigenschaften dieser Klassen in einem bestimmten Skriptkomponententyp zu verwenden sind, finden Sie unter [Additional Script Component Examples (Zusätzliche Skriptkomponentenbeispiele)](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="5ed55-139">Die Beispielthemen enthalten auch vollständige Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="5ed55-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="5ed55-140">Bei der Konfiguration der Skriptkomponente als Transformation enthält das `ScriptMain`-Projektelement den folgenden automatisch generierten Code.</span><span class="sxs-lookup"><span data-stu-id="5ed55-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="5ed55-141">Die Codevorlage bietet auch eine Übersicht über die Skriptkomponente und zusätzliche Informationen über das Abrufen und Bearbeiten von SSIS-Objekten, z. B. Variablen, Ereignisse und Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="5ed55-142">Zusätzliche Projektelemente im Skriptkomponentenprojekt</span><span class="sxs-lookup"><span data-stu-id="5ed55-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="5ed55-143">Das Skriptkomponentenprojekt kann neben dem Standardelement `ScriptMain` noch weitere Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="5ed55-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="5ed55-144">Sie können dem Projekt Klassen, Module, Codedateien und Ordner hinzufügen und die Ordner zum Organisieren von Elementgruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="5ed55-145">Alle Elemente, die Sie hinzufügen, werden im Paket beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5ed55-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="5ed55-146">Verweise im Skriptkomponentenprojekt</span><span class="sxs-lookup"><span data-stu-id="5ed55-146">References in the Script Component Project</span></span>
 <span data-ttu-id="5ed55-147">Sie können Verweise auf verwaltete Assemblys hinzufügen, indem Sie im **Projektexplorer** mit der rechten Maustaste auf das Skripttaskprojekt und anschließend auf **Verweis hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="5ed55-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="5ed55-148">Weitere Informationen finden Sie unter [Verweisen auf andere Assemblys in Skriptlösungen](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="5ed55-149">Sie können Projektverweise in der VSTA-IDE in der **Klassenansicht** oder im **Projektexplorer** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="5ed55-150">Diese Fenster öffnen Sie über das Menü **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="5ed55-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="5ed55-151">Einen neuen Verweis können Sie über das Menü **Projekt**, den **Projektexplorer** oder die **Klassenansicht** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="5ed55-152">Interagieren mit Paketen in der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="5ed55-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="5ed55-153">Das benutzerdefinierte Skript, das in der Skriptkomponente geschrieben wird, kann mithilfe von stark typisierten  Accessoren in automatisch generierten Basisklassen auf Variablen und Verbindungs-Manager aus dem entsprechenden Paket zugreifen und diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="5ed55-154">Die Variablen und Verbindungs-Manager müssen vor dem Wechseln in den Codeentwurfsmodus konfiguriert werden, wenn sie für das Skript zur Verfügung stehen sollen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="5ed55-155">Sie können auch Ereignisse auslösen und die Protokollierung von Ihrem Skriptkomponentencode ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="5ed55-156">Die automatisch generierten Projektelemente im Skriptkomponentenprojekt stellen die folgenden Objekte, Methoden und Eigenschaften zum Interagieren mit dem Paket bereit.</span><span class="sxs-lookup"><span data-stu-id="5ed55-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="5ed55-157">Funktion des Pakets</span><span class="sxs-lookup"><span data-stu-id="5ed55-157">Package Feature</span></span>|<span data-ttu-id="5ed55-158">Zugriffsmethode</span><span class="sxs-lookup"><span data-stu-id="5ed55-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="5ed55-159">Variables</span><span class="sxs-lookup"><span data-stu-id="5ed55-159">Variables</span></span>|<span data-ttu-id="5ed55-160">Verwenden Sie die benannten, typisierten Accessoreigenschaften in der `Variables`-Auflistungsklasse im `ComponentWrapper`-Projektelement, die über die `Variables`-Eigenschaft der `ScriptMain`-Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="5ed55-161">Die `PreExecute`-Methode kann nur auf schreibgeschützte Variablen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="5ed55-162">Die `PostExecute`-Methode kann sowohl auf schreibgeschützte als auch auf Lese-/Schreibvariablen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="5ed55-163">Verbindungen</span><span class="sxs-lookup"><span data-stu-id="5ed55-163">Connections</span></span>|<span data-ttu-id="5ed55-164">Verwenden Sie die benannten, typisierten Accessoreigenschaften in der `Connections`-Auflistungsklasse im `ComponentWrapper`-Projektelement, die über die `Connections`-Eigenschaft der `ScriptMain`-Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="5ed55-165">Events</span><span class="sxs-lookup"><span data-stu-id="5ed55-165">Events</span></span>|<span data-ttu-id="5ed55-166">Lösen Sie Ereignisse mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> -Eigenschaft der `ScriptMain` -Klasse und **der \<X> Fire** -Methoden der- <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="5ed55-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="5ed55-167">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="5ed55-167">Logging</span></span>|<span data-ttu-id="5ed55-168">Protokollierungen werden mit der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>-Methode der `ScriptMain`-Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ed55-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="5ed55-169">Debuggen der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="5ed55-169">Debugging the Script Component</span></span>
 <span data-ttu-id="5ed55-170">Legen Sie zum Debuggen des Codes in der Skriptkomponente mindestens einen Breakpoint fest, und schließen Sie dann die VSTA IDE, um das Paket in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5ed55-171">Wenn die Ausführung der Skriptkomponente beginnt, wird die VSTA IDE erneut geöffnet und der Code schreibgeschützt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ed55-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="5ed55-172">Nachdem die Ausführung den Breakpoint erreicht hat, können Sie die Variablenwerte untersuchen und den übrigen Code schrittweise durchgehen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ed55-173">Sie können eine Skriptkomponente nicht debuggen, wenn sie als Teil eines untergeordneten Pakets in einem Task Paket ausführen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5ed55-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="5ed55-174">Breakpoints, die Sie in der Skriptkomponente im untergeordneten Paket festlegen, werden unter diesen Umständen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5ed55-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="5ed55-175">Sie können das untergeordnete Paket normalerweise debuggen, indem Sie es getrennt ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ed55-176">Wenn Sie ein Paket debuggen, das mehrere Skriptkomponenten enthält, debuggt der Debugger eine Skriptkomponente.</span><span class="sxs-lookup"><span data-stu-id="5ed55-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="5ed55-177">Das System kann eine andere Skriptkomponente debuggen, wenn der Debugger wie im Fall eines Foreach- oder For-Schleifencontainers abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="5ed55-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="5ed55-178">Sie können die Ausführung der Skriptkomponente auch mit den folgenden Methoden überwachen:</span><span class="sxs-lookup"><span data-stu-id="5ed55-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="5ed55-179">Unterbrechen Sie die Ausführung, und zeigen Sie mithilfe der- `MessageBox.Show` Methode im **System. Windows. Forms** -Namespace eine modale Meldung an.</span><span class="sxs-lookup"><span data-stu-id="5ed55-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="5ed55-180">(Entfernen Sie diesen Code, nachdem der Debugprozess abgeschlossen wurde.)</span><span class="sxs-lookup"><span data-stu-id="5ed55-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="5ed55-181">Lösen Sie Ereignisse für Informationsmeldungen, Warnungen und Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="5ed55-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="5ed55-182">Die Methoden FireInformation, FireWarning und FireError zeigen die Ereignisbeschreibung im Fenster **Ausgabe** von Visual Studio an.</span><span class="sxs-lookup"><span data-stu-id="5ed55-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="5ed55-183">Die Methoden FireProgress, Console.Write und Console.WriteLine zeigen hingegen keine Informationen im Fenster **Ausgabe** an.</span><span class="sxs-lookup"><span data-stu-id="5ed55-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="5ed55-184">Meldungen des FireProgress-Ereignisses werden auf der Registerkarte **Status** des [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ed55-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="5ed55-185">Weitere Informationen finden Sie unter [Raising Events in the Script Component (Auslösen von Ereignissen in der Skriptkomponente)](../../data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="5ed55-186">Protokollieren Sie Ereignisse oder benutzerdefinierte Meldungen an aktivierte Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="5ed55-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="5ed55-187">Weitere Informationen finden Sie unter [Logging in the Script Component (Protokollieren in der Skriptkomponente)](logging-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="5ed55-188">Wenn Sie lediglich die Ausgabe einer Skriptkomponente überprüfen möchten, die als Quelle oder Transformation konfiguriert ist, und die Daten nicht in einem Ziel speichern möchten, können Sie den Datenfluss mit einer [Transformation für Zeilenanzahl](../../data-flow/transformations/row-count-transformation.md) unterbrechen und der Ausgabe der Skriptkomponente einen Daten-Viewer anfügen.</span><span class="sxs-lookup"><span data-stu-id="5ed55-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="5ed55-189">Informationen zu Daten-Viewern finden Sie unter [Debugging Data Flow (Debuggen des Datenflusses)](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="5ed55-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5ed55-190">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5ed55-190">In This Section</span></span>
 <span data-ttu-id="5ed55-191">Weitere Informationen zum Codieren der Skriptkomponente finden Sie in den folgenden Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5ed55-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="5ed55-192">Grundlegendes [zum Skript Component Object Model](understanding-the-script-component-object-model.md) Erläutert, wie die in der Skript Komponente verfügbaren Objekte, Methoden und Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ed55-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="5ed55-193">[Verweisen auf andere Assemblys in Skript Lösungen](../referencing-other-assemblies-in-scripting-solutions.md) Erläutert, wie auf-Objekte aus der- [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Klassenbibliothek in der Skript Komponente verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5ed55-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="5ed55-194">[Simulieren einer Fehlerausgabe für die Skript Komponente](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Erläutert das Simulieren einer Fehlerausgabe für Zeilen, die während der Verarbeitung von der Skript Komponente Fehler ausgeben.</span><span class="sxs-lookup"><span data-stu-id="5ed55-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="5ed55-195">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5ed55-195">External Resources</span></span>

-   <span data-ttu-id="5ed55-196">Blogeintrag: [VSTA setup and configuration troubles for SSIS 2008 and R2 installations (Probleme mit der VSTA-Einrichtung und -Konfiguration bei SSIS 2008- und R2-Installationen)](https://go.microsoft.com/fwlink/?LinkId=215661) (auf blogs.msdn.com).</span><span class="sxs-lookup"><span data-stu-id="5ed55-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="5ed55-197">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="5ed55-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5ed55-198">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="5ed55-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5ed55-199">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="5ed55-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5ed55-200">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5ed55-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed55-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ed55-201">See Also</span></span>
 [<span data-ttu-id="5ed55-202">Konfigurieren der Skriptkomponente im Skriptkomponenten-Editor</span><span class="sxs-lookup"><span data-stu-id="5ed55-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


