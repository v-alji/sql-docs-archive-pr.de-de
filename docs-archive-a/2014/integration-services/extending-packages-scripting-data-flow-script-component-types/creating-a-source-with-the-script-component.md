---
title: Erstellen einer Quelle mit der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618776"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="383cd-102">Erstellen einer Quelle mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="383cd-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="383cd-103">Quellkomponenten dienen im Datenfluss eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets dazu, Daten aus einer Datenquelle zu laden, um sie an Downstreamtransformationen und -ziele zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="383cd-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="383cd-104">Gewöhnlich stellen Sie über einen vorhandenen Verbindungs-Manager eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="383cd-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="383cd-105">Eine Übersicht über die Skript Komponente finden Sie unter [Erweitern des Datenflusses mit der Skript Komponente] (.). /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="383cd-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="383cd-106">Die Skriptkomponente und der Infrastrukturcode, den sie generieren, erleichtern Ihnen die Entwicklung benutzerdefinierter Datenflusskomponenten deutlich.</span><span class="sxs-lookup"><span data-stu-id="383cd-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="383cd-107">Um die Funktionsweise der Skriptkomponente zu verstehen, kann es jedoch hilfreich sein, sich mit den Schritten, die bei der Entwicklung einer benutzerdefinierten Datenflusskomponente durchlaufen werden, vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="383cd-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="383cd-108">Weitere Informationen finden Sie im Abschnitt [Developing a Custom Data Flow Component (Entwickeln einer benutzerdefinierten Datenflusskomponente)](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md). Beachten Sie dabei insbesondere das Thema [Developing a Custom Source Component (Entwickeln einer benutzerdefinierten Quellkomponente)](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="383cd-109">Erste Schritte mit einer Quellkomponente</span><span class="sxs-lookup"><span data-stu-id="383cd-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="383cd-110">Wenn Sie im Bereich Datenfluss des [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designers eine Skriptkomponente hinzufügen, wird das Dialogfeld **Skriptkomponententyp auswählen** geöffnet, und Sie werden zur Auswahl eines Quell-, Ziel- oder Transformationsskripts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="383cd-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="383cd-111">Klicken Sie in diesem Dialogfeld auf **Quelle**.</span><span class="sxs-lookup"><span data-stu-id="383cd-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="383cd-112">Konfigurieren einer Quellkomponente im Metadatenentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="383cd-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="383cd-113">Nachdem Sie die Erstellung einer Quellkomponente ausgewählt haben, konfigurieren Sie die Komponente mit dem **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="383cd-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="383cd-114">Weitere Informationen finden Sie unter [Configuring the Script Component in the Script Component Editor (Konfigurieren der Skriptkomponente im Skriptkomponenten-Editor)](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="383cd-115">Eine Datenflussquellkomponente verfügt über keine Eingaben und unterstützt eine oder mehrere Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="383cd-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="383cd-116">Die Konfiguration der Ausgaben für die Komponente ist einer der Schritte, den Sie mithilfe des **Transformations-Editors für Skripterstellung** im Metadatenentwurfsmodus abschließen müssen, bevor Sie das benutzerdefinierte Skript schreiben.</span><span class="sxs-lookup"><span data-stu-id="383cd-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="383cd-117">Sie können zudem die Skriptsprache über die **ScriptLanguage**-Eigenschaft auf der Seite **Skript** im **Transformations-Editor für Skripterstellung** festlegen.</span><span class="sxs-lookup"><span data-stu-id="383cd-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="383cd-118">Verwenden Sie im Dialogfeld **Optionen** auf der Seite **Allgemein** die Option **Skriptsprache**, um die Standardskriptsprache für Skriptkomponenten und Skripttasks festzulegen.</span><span class="sxs-lookup"><span data-stu-id="383cd-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="383cd-119">Weitere Informationen finden Sie unter [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="383cd-120">Hinzufügen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="383cd-120">Adding Connection Managers</span></span>
 <span data-ttu-id="383cd-121">Eine Quellkomponente verwendet normalerweise einen vorhandenen Verbindungs-Manager zum Herstellen einer Verbindung mit der Datenquelle, aus der Daten in den Datenfluss geladen werden.</span><span class="sxs-lookup"><span data-stu-id="383cd-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="383cd-122">Klicken Sie im **Transformations-Editor für Skripterstellung** auf der Seite **Verbindungs-Manager** auf **Hinzufügen**, um den passenden Verbindungs-Manager hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="383cd-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="383cd-123">Ein Verbindungs-Manager ist jedoch nur eine praktische Einheit, die Daten kapselt und speichert, die sie benötigt, um eine Verbindung mit einer bestimmten Art von Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="383cd-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="383cd-124">Sie müssen, um Daten zu laden und zu speichern sowie möglicherweise auch um eine Verbindung mit der Datenquelle herzustellen und diese zu beenden, eigenen benutzerdefinierten Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="383cd-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="383cd-125">Allgemeine Informationen zum Verwenden von Verbindungs-Managern mit der Skriptkomponente finden Sie unter [Connecting to Data Sources in the Script Component (Herstellen einer Verbindung mit Datenquellen in der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="383cd-126">Weitere Informationen über die Seite **Verbindungs-Manager** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Connection Managers Page) (Transformations-Editor für Skripterstellung (Seite „Verbindungs-Manager“))](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="383cd-127">Konfigurieren von Ausgaben und Ausgabespalten</span><span class="sxs-lookup"><span data-stu-id="383cd-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="383cd-128">Eine Quellkomponente verfügt über keine Eingaben und unterstützt eine oder mehrere Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="383cd-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="383cd-129">Auf der Seite **Eingaben und Ausgaben** im **Transformations-Editor für Skripterstellung** wurde standardmäßig eine Ausgabe, jedoch keine Ausgabespalten erstellt.</span><span class="sxs-lookup"><span data-stu-id="383cd-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="383cd-130">Auf dieser Seite des Editors haben Sie die Möglichkeit, die folgenden Elemente zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="383cd-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="383cd-131">Sie müssen Ausgabespalten für jede Ausgabe manuell hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="383cd-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="383cd-132">Wählen Sie den Ausgabespaltenordner für die jeweilige Ausgabe aus, und verwalten Sie anschließend die Ausgabespalten für alle Ausgaben der Quellkomponente mithilfe der Schaltflächen **Spalte hinzufügen** und **Spalte entfernen**.</span><span class="sxs-lookup"><span data-stu-id="383cd-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="383cd-133">Die Namen, die Sie den Ausgabespalten hier zuweisen, verwenden Sie später mithilfe der typisierten Accessoreigenschaften, die im automatisch generierten Code erstellt wurden, für Verweise im Skript.</span><span class="sxs-lookup"><span data-stu-id="383cd-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="383cd-134">Sie haben die Möglichkeit, eine oder mehrere zusätzliche Ausgaben zu erstellen, beispielsweise eine simulierte Fehlerausgabe für Zeilen, die unerwartete Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="383cd-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="383cd-135">Verwenden Sie die Schaltflächen **Ausgabe hinzufügen** und **Ausgabe entfernen**, um die Ausgaben der Quellkomponente zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="383cd-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="383cd-136">Alle Eingabezeilen werden an alle verfügbaren Ausgaben weitergeleitet, außer Sie legen einen identischen Wert ungleich Null für die `ExclusionGroup`-Eigenschaft der Ausgaben fest, bei denen Sie jede Zeile nur an eine der Ausgaben weiterleiten möchten, die denselben `ExclusionGroup`-Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="383cd-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="383cd-137">Der spezifische ganzzahlige Wert, den Sie auswählen, um die `ExclusionGroup` zu kennzeichnen, ist nicht von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="383cd-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="383cd-138">Sie können auch einen Wert ungleich Null für die `ExclusionGroup`-Eigenschaft für eine einzelne Ausgabe verwenden, wenn Sie nicht alle Zeilen ausgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="383cd-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="383cd-139">In diesem Fall müssen Sie jedoch für alle Zeilen, die an die Ausgabe gesendet werden sollen, explizit die Methode **DirectRowTo\<outputbuffer>** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="383cd-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="383cd-140">Sie können allen Ausgaben einen Anzeigenamen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="383cd-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="383cd-141">Sie verwenden die Namen der Ausgaben in Ihrem Skript später für Verweise mithilfe der typisierten Accessoreigenschaften, die im automatisch generierten Code erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="383cd-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="383cd-142">Gewöhnlich haben mehrere Ausgaben in der gleichen `ExclusionGroup` die gleichen Ausgabespalten.</span><span class="sxs-lookup"><span data-stu-id="383cd-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="383cd-143">Falls Sie eine simulierte Fehlerausgabe erstellen, sollten Sie jedoch mehrere Spalten hinzufügen, um Fehlerinformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="383cd-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="383cd-144">Informationen dazu, wie die Datenfluss-Engine Fehlerzeilen verarbeitet, finden Sie unter [Using Error Outputs in a Data Flow Component (Verwenden von Fehlerausgaben in einer Datenflusskomponente)](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="383cd-145">In der Skriptkomponente müssen Sie hingegen eigenen Code schreiben, um geeignete Fehlerinformationen für die zusätzlichen Spalten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="383cd-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="383cd-146">Weitere Informationen finden Sie unter [Simulating an Error Output for the Script Component (Simulieren einer Fehlerausgabe für die Skriptkomponente)](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="383cd-147">Weitere Informationen über die Seite **Eingaben und Ausgaben** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Inputs and Outputs Page) (Transformations-Editor für Skripterstellung (Seite „Eingaben und Ausgaben“))](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="383cd-148">Hinzufügen von Variablen</span><span class="sxs-lookup"><span data-stu-id="383cd-148">Adding Variables</span></span>
 <span data-ttu-id="383cd-149">Wenn vorhandene Variablen vorhanden sind, deren Werte Sie in Ihrem Skript verwenden möchten, können Sie diese in den `ReadOnlyVariables` `ReadWriteVariables` Eigenschaften Feldern und auf der Seite **Skript** des Transformations- **Editors für Skript**Erstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="383cd-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="383cd-150">Wenn Sie mehrere Variablen in die Eigenschaftenfelder eingeben, trennen Sie die Variablennamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="383cd-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="383cd-151">Sie können auch mehrere Variablen eingeben, indem Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben den `ReadOnlyVariables` `ReadWriteVariables` Eigenschaften Feldern und klicken und Variablen im Dialogfeld **Variablen auswählen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="383cd-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="383cd-152">Allgemeine Informationen über das Verwenden von Variablen mit der Skriptkomponente finden Sie unter [Using Variables in the Script Component (Verwenden von Variablen in der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="383cd-153">Weitere Informationen über die Seite **Skript** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Script Page) (Transformations-Editor für Skripterstellung (Seite „Skript“))](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="383cd-154">Schreiben einer Quellkomponente im Codeentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="383cd-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="383cd-155">Nachdem Sie die Metadaten für Ihre Komponente konfiguriert haben, öffnen Sie in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) die IDE, um das benutzerdefinierte Skript zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="383cd-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="383cd-156">Klicken Sie im **Transformations-Editor für Skripterstellung** auf der Seite **Skript** auf **Skript bearbeiten**, um VSTA zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="383cd-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="383cd-157">Abhängig von der Skriptsprache, die Sie für die **ScriptLanguage**-Eigenschaft ausgewählt haben, können Sie das Skript entweder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# schreiben.</span><span class="sxs-lookup"><span data-stu-id="383cd-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="383cd-158">Wichtige Informationen, die alle Arten von Komponenten betreffen, die mithilfe der Skriptkomponente erstellt wurden, finden Sie unter [Coding and Debugging the Script Component (Codieren und Debuggen der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="383cd-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="383cd-159">Grundlegendes zum automatisch generierten Code</span><span class="sxs-lookup"><span data-stu-id="383cd-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="383cd-160">Wenn Sie nach der Erstellung und Konfiguration einer Quellkomponente die VSTA IDE öffnen, wird die bearbeitbare `ScriptMain`-Klasse im Code-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="383cd-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="383cd-161">Sie schreiben den benutzerdefinierten Code in der `ScriptMain`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="383cd-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="383cd-162">Die `ScriptMain`-Klasse schließt einen Stub für die `CreateNewOutputRows`-Methode ein.</span><span class="sxs-lookup"><span data-stu-id="383cd-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="383cd-163">`CreateNewOutputRows` ist die wichtigste Methode in einer Quellkomponente.</span><span class="sxs-lookup"><span data-stu-id="383cd-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="383cd-164">Wenn Sie das Fenster **Projekt Explorer** in VSTA öffnen, können Sie sehen, dass die Skript Komponente auch schreibgeschützte- `BufferWrapper` und- `ComponentWrapper` Projekt Elemente generiert hat.</span><span class="sxs-lookup"><span data-stu-id="383cd-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="383cd-165">Die `ScriptMain`-Klasse erbt von der `UserComponent`-Klasse im `ComponentWrapper`-Projektelement.</span><span class="sxs-lookup"><span data-stu-id="383cd-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="383cd-166">Zur Laufzeit ruft die Datenfluss-Engine die `PrimeOutput`-Methode in der `UserComponent`-Klasse auf, die die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A>-Methode der übergeordneten <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Klasse überschreibt.</span><span class="sxs-lookup"><span data-stu-id="383cd-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="383cd-167">Die `PrimeOutput`-Methode ruft anschließend die folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="383cd-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="383cd-168">Die `CreateNewOutputRows`-Methode, die Sie in `ScriptMain` überschreiben können, um den Ausgabepuffern, die zunächst leer sind, Zeilen der Datenquelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="383cd-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="383cd-169">Die `FinishOutputs`-Methode, die standardmäßig leer ist.</span><span class="sxs-lookup"><span data-stu-id="383cd-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="383cd-170">Überschreiben Sie diese Methode in `ScriptMain`, um Verarbeitungsschritte auszuführen, die zum Abschluss der Ausgabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="383cd-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="383cd-171">Die private `MarkOutputsAsFinished`-Methode, welche die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A>-Methode der übergeordneten <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer>-Klasse aufruft, um die Datenfluss-Engine über die Fertigstellung der Ausgabe in Kenntnis zu setzen.</span><span class="sxs-lookup"><span data-stu-id="383cd-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="383cd-172">Sie müssen `SetEndOfRowset` nicht explizit in Ihrem eigenen Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="383cd-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="383cd-173">Schreiben von benutzerdefiniertem Code</span><span class="sxs-lookup"><span data-stu-id="383cd-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="383cd-174">Um die Erstellung einer benutzerdefinierten Quellkomponente abzuschließen, können Sie Skripts in den folgenden Methoden schreiben, die in der `ScriptMain`-Klasse zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="383cd-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="383cd-175">Überschreiben Sie die `AcquireConnections`-Methode, um eine Verbindung mit der externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="383cd-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="383cd-176">Extrahieren Sie das Verbindungsobjekt bzw. die erforderlichen Verbindungsinformationen vom Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="383cd-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="383cd-177">Überschreiben Sie die `PreExecute`-Methode, um Daten zu laden, falls Sie alle Quelldaten gleichzeitig laden können.</span><span class="sxs-lookup"><span data-stu-id="383cd-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="383cd-178">Sie können beispielsweise einen `SqlCommand` an einer [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank ausführen und alle Quelldaten gleichzeitig in einen `SqlDataReader` laden.</span><span class="sxs-lookup"><span data-stu-id="383cd-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="383cd-179">Falls Sie die Quelldaten zeilenweise laden müssen (z. B. beim Lesen einer Textdatei), können Sie die Daten beim Durchlaufen der Zeilen in `CreateNewOutputRows` laden.</span><span class="sxs-lookup"><span data-stu-id="383cd-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="383cd-180">Mithilfe der überschriebenen `CreateNewOutputRows`-Methode können Sie leere Ausgabepuffer um neue Zeilen ergänzen und die Werte der einzelnen Spalten den neuen Ausgabezeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="383cd-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="383cd-181">Verwenden Sie die `AddRow`-Methode der einzelnen Ausgabepuffer, um leere neue Zeilen hinzuzufügen, und legen Sie anschließend die Werte der einzelnen Spalten fest.</span><span class="sxs-lookup"><span data-stu-id="383cd-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="383cd-182">Üblicherweise kopieren Sie die Werte aus den Spalten, die aus der externen Quelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="383cd-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="383cd-183">Überschreiben Sie die `PostExecute`-Methode, um die Verarbeitung der Daten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="383cd-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="383cd-184">Sie können beispielsweise den `SqlDataReader` schließen, mit dem Sie die Daten geladen haben.</span><span class="sxs-lookup"><span data-stu-id="383cd-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="383cd-185">Überschreiben Sie ggf. die `ReleaseConnections`-Methode, um die Verbindung mit der externen Datenquelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="383cd-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="383cd-186">Beispiele</span><span class="sxs-lookup"><span data-stu-id="383cd-186">Examples</span></span>
 <span data-ttu-id="383cd-187">In den folgenden Beispielen wird der benutzerdefinierte Code veranschaulicht, der in der `ScriptMain`-Klasse zur Erstellung einer Quellkomponente erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="383cd-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="383cd-188">In diesen Beispielen wird die **Person. Address** -Tabelle in der `AdventureWorks` -Beispieldatenbank verwendet, und die erste und vierte Spalte, die **intadressssid** -und **nvarchar (30) City** -Spalten, werden über den Datenfluss übergeben.</span><span class="sxs-lookup"><span data-stu-id="383cd-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="383cd-189">Die gleichen Daten werden in den Quellen-, Transformations- und Zielbeispielen in diesem Abschnitt verwendet.</span><span class="sxs-lookup"><span data-stu-id="383cd-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="383cd-190">Zusätzliche Voraussetzungen und Annahmen werden für jedes Beispiel dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="383cd-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="383cd-191">ADO.NET-Quellenbeispiel</span><span class="sxs-lookup"><span data-stu-id="383cd-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="383cd-192">Dieses Beispiel zeigt eine Quellkomponente, die einen vorhandenen [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager zum Laden von Daten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle in den Datenfluss verwendet.</span><span class="sxs-lookup"><span data-stu-id="383cd-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="383cd-193">Wenn Sie den Beispielcode ausführen möchten, müssen Sie das Paket und die Komponente folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="383cd-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="383cd-194">Erstellen Sie einen [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager, der mithilfe des `SqlClient`-Anbieters eine Verbindung mit der `AdventureWorks`-Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="383cd-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="383cd-195">Fügen Sie der Datenfluss-Designeroberfläche eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Quelle.</span><span class="sxs-lookup"><span data-stu-id="383cd-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="383cd-196">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="383cd-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="383cd-197">Geben Sie auf der Seite **Eingaben und Ausgaben** der Standardausgabe einen aussagekräftigeren Namen ein, z.B. **MyAddressOutput**. Fügen Sie die zwei Ausgabespalten **AddressID** und **City** hinzu, und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="383cd-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="383cd-198">Achten Sie darauf, den Datentyp der **City**-Ausgabespalte in DT_WSTR zu ändern.</span><span class="sxs-lookup"><span data-stu-id="383cd-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="383cd-199">Fügen Sie auf der Seite **Verbindungs-Manager** den [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager hinzu, oder erstellen Sie diesen, und geben Sie ihm einen Namen wie **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="383cd-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="383cd-200">Klicken Sie auf der Seite **Skript** auf **Skript bearbeiten**, und geben Sie das folgende Skript ein.</span><span class="sxs-lookup"><span data-stu-id="383cd-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="383cd-201">Schließen Sie anschließend die Skriptentwicklungsumgebung und den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="383cd-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="383cd-202">Erstellen und konfigurieren Sie eine Zielkomponente, die die Spalten **AddressID** und **City** erwartet, z.B. ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel oder die Beispielzielkomponente, die unter [Creating a Destination with the Script Component (Erstellen eines Ziels mit der Skriptkomponente)](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="383cd-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="383cd-203">Stellen Sie anschließend eine Verbindung der Quellkomponente mit dem Ziel her.</span><span class="sxs-lookup"><span data-stu-id="383cd-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="383cd-204">(Sie können eine Quelle ohne Transformationen direkt mit einem Ziel verbinden.) Sie können eine Ziel Tabelle erstellen, indem Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] Befehl in der- `AdventureWorks` Datenbank ausführen:</span><span class="sxs-lookup"><span data-stu-id="383cd-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="383cd-205">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="383cd-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="383cd-206">Flatfilequellenbeispiel</span><span class="sxs-lookup"><span data-stu-id="383cd-206">Flat File Source Example</span></span>
 <span data-ttu-id="383cd-207">Diese Beispiel zeigt eine Quellkomponente, die einen vorhandenen Verbindungs-Manager für Flatfiles zum Laden von Daten aus einer Flatfile in den Datenfluss einsetzt.</span><span class="sxs-lookup"><span data-stu-id="383cd-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="383cd-208">Die Flatfilequelldaten werden durch einen Export aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt.</span><span class="sxs-lookup"><span data-stu-id="383cd-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="383cd-209">Wenn Sie den Beispielcode ausführen möchten, müssen Sie das Paket und die Komponente folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="383cd-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="383cd-210">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Exportieren Sie mit dem-Import/Export-Assistenten die **Person. Address** -Tabelle aus der- `AdventureWorks` Beispieldatenbank in eine durch Trennzeichen getrennte Flatfile.</span><span class="sxs-lookup"><span data-stu-id="383cd-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="383cd-211">In diesem Beispiel wird der Dateiname ExportedAddresses.txt verwendet.</span><span class="sxs-lookup"><span data-stu-id="383cd-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="383cd-212">Erstellen Sie einen Verbindungs-Manager für Flatfiles, der eine Verbindung mit der exportierten Datendatei herstellt.</span><span class="sxs-lookup"><span data-stu-id="383cd-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="383cd-213">Fügen Sie der Datenfluss-Designeroberfläche eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Quelle.</span><span class="sxs-lookup"><span data-stu-id="383cd-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="383cd-214">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="383cd-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="383cd-215">Geben Sie auf der Seite **Eingaben und Ausgaben** der Standardausgabe einen aussagekräftigeren Namen ein, z.B. **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="383cd-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="383cd-216">Fügen Sie die beiden Ausgabespalten **AddressID** und **City** hinzu, und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="383cd-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="383cd-217">Fügen Sie auf der Seite **Verbindungs-Manager** den Verbindungs-Manager für Flatfiles hinzu, oder erstellen Sie diesen, und geben Sie ihm einen aussagekräftigen Namen, z.B. **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="383cd-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="383cd-218">Klicken Sie auf der Seite **Skript** auf **Skript bearbeiten**, und geben Sie das folgende Skript ein.</span><span class="sxs-lookup"><span data-stu-id="383cd-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="383cd-219">Schließen Sie anschließend die Skriptentwicklungsumgebung und den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="383cd-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="383cd-220">Erstellen und konfigurieren Sie eine Zielkomponente, z.B. ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel oder die Beispielzielkomponente, die unter [Creating a Destination with the Script Component (Erstellen eines Ziels mit der Skriptkomponente)](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="383cd-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="383cd-221">Stellen Sie anschließend eine Verbindung der Quellkomponente mit dem Ziel her.</span><span class="sxs-lookup"><span data-stu-id="383cd-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="383cd-222">(Sie können eine Quelle ohne Transformationen direkt mit einem Ziel verbinden.) Sie können eine Ziel Tabelle erstellen, indem Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] Befehl in der- `AdventureWorks` Datenbank ausführen:</span><span class="sxs-lookup"><span data-stu-id="383cd-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="383cd-223">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="383cd-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="383cd-224">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="383cd-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="383cd-225">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="383cd-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="383cd-226">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="383cd-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="383cd-227">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="383cd-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="383cd-228">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="383cd-228">See Also</span></span>
 <span data-ttu-id="383cd-229">[Erstellen eines Ziels mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Entwickeln einer benutzerdefinierten Quell Komponente](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="383cd-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


