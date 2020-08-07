---
title: Erstellen eines Ziels mit der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619958"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="d8544-102">Erstellen eines Ziels mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d8544-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="d8544-103">Zielkomponenten dienen im Datenfluss eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets dazu, von Upstreamquellen empfangene Daten und Transformationen in einer Datenquelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d8544-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="d8544-104">Gewöhnlich stellt die Zielkomponente über einen vorhandenen Verbindungs-Manager eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="d8544-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="d8544-105">Eine Übersicht über die Skript Komponente finden Sie unter [Erweitern des Datenflusses mit der Skript Komponente] (.). /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="d8544-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="d8544-106">Die Skriptkomponente und der Infrastrukturcode, den sie generieren, erleichtern Ihnen die Entwicklung benutzerdefinierter Datenflusskomponenten deutlich.</span><span class="sxs-lookup"><span data-stu-id="d8544-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="d8544-107">Zum Verständnis der Funktionsweise dieser Skriptkomponente kann es jedoch hilfreich sein, sich mit den im Abschnitt [Developing a Custom Data Flow Component (Entwickeln einer benutzerdefinierten Datenflusskomponente)](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) beschriebenen Schritten für die Entwicklung einer benutzerdefinierten Datenflusskomponente vertraut zu machen, und zwar insbesondere mit [Developing a Custom Destination Component (Entwickeln einer benutzerdefinierten Zielkomponente)](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="d8544-108">Erste Schritte mit einer Zielkomponente</span><span class="sxs-lookup"><span data-stu-id="d8544-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="d8544-109">Wenn Sie zur Registerkarte „Datenfluss“ des [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designers eine Skriptkomponente hinzufügen, wird das Dialogfeld **Skriptkomponententyp auswählen** geöffnet, und Sie werden zur Auswahl des Skripts **Quelle**, **Ziel** oder **Transformation** aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d8544-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="d8544-110">Wählen Sie in diesem Dialogfeld **Ziel** aus.</span><span class="sxs-lookup"><span data-stu-id="d8544-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="d8544-111">Verbinden Sie anschließend die Ausgabe einer Transformation mit der Zielkomponente im [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer.</span><span class="sxs-lookup"><span data-stu-id="d8544-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="d8544-112">Für Tests können Sie ohne Transformationen direkt eine Quelle mit einem Ziel verbinden.</span><span class="sxs-lookup"><span data-stu-id="d8544-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="d8544-113">Konfigurieren einer Zielkomponente im Metadatenentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="d8544-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="d8544-114">Nachdem Sie die Option zur Erstellung einer Zielkomponente ausgewählt haben, konfigurieren Sie die Komponente mit dem **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="d8544-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="d8544-115">Weitere Informationen finden Sie unter [Configuring the Script Component in the Script Component Editor (Konfigurieren der Skriptkomponente im Skriptkomponenten-Editor)](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="d8544-116">Legen Sie die **ScriptLanguage**-Eigenschaft auf der Seite **Skript** im Dialogfeld **Transformations-Editor für Skripterstellung** fest, um die Skriptsprache auszuwählen, die das Skriptziel verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="d8544-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="d8544-117">Verwenden Sie im Dialogfeld **Optionen** auf der Seite **Allgemein** die Option **Skriptsprache**, um die Standardskriptsprache für die Skriptkomponente festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d8544-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="d8544-118">Weitere Informationen finden Sie unter [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="d8544-119">Eine Datenflusszielkomponente verfügt über eine Eingabe und keine Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="d8544-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="d8544-120">Die Konfiguration der Eingabe für die Komponente ist einer der Schritte, den Sie mit dem **Transformations-Editor für Skripterstellung** im Metadatenentwurfsmodus abschließen müssen, bevor Sie das benutzerdefinierte Skript schreiben.</span><span class="sxs-lookup"><span data-stu-id="d8544-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="d8544-121">Hinzufügen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="d8544-121">Adding Connection Managers</span></span>
 <span data-ttu-id="d8544-122">Eine Zielkomponente verwendet normalerweise einen vorhandenen Verbindungs-Manager zum Herstellen einer Verbindung mit der Datenquelle, in der sie die Daten aus dem Datenfluss speichert.</span><span class="sxs-lookup"><span data-stu-id="d8544-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="d8544-123">Klicken Sie im **Transformations-Editor für Skripterstellung** auf der Seite **Verbindungs-Manager** auf **Hinzufügen**, um den passenden Verbindungs-Manager hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8544-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="d8544-124">Ein Verbindungs-Manager ist jedoch nur eine praktische Einheit, die die Informationen kapselt und speichert, die benötigt werden, um eine Verbindung mit einem bestimmten Datenquellentyp herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8544-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="d8544-125">Um Daten zu laden und zu speichern und möglicherweise auch eine Verbindung mit der Datenquelle herzustellen und diese zu beenden, müssen Sie Ihren eigenen benutzerdefinierten Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="d8544-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="d8544-126">Allgemeine Informationen zum Verwenden von Verbindungs-Managern mit der Skriptkomponente finden Sie unter [Connecting to Data Sources in the Script Component (Herstellen einer Verbindung mit Datenquellen in der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="d8544-127">Weitere Informationen über die Seite **Verbindungs-Manager** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Connection Managers Page) (Transformations-Editor für Skripterstellung (Seite „Verbindungs-Manager“))](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="d8544-128">Konfigurieren von Eingaben und Eingabespalten</span><span class="sxs-lookup"><span data-stu-id="d8544-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="d8544-129">Eine Zielkomponente verfügt über eine Eingabe und keine Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="d8544-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="d8544-130">Die Spaltenliste auf der Seite **Eingabespalten** im **Transformations-Editor für Skripterstellung** zeigt die von der Ausgabe der Upstreamkomponente im Datenfluss verfügbaren Spalten an.</span><span class="sxs-lookup"><span data-stu-id="d8544-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="d8544-131">Wählen Sie die Spalten aus, die Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d8544-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="d8544-132">Weitere Informationen über die Seite **Eingabespalten** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Input Columns Page) (Transformations-Editor für Skripterstellung (Seite „Eingabespalten“))](../script-transformation-editor-input-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="d8544-133">Auf der Seite **Eingaben und Ausgaben** im **Transformations-Editor für Skripterstellung** wird eine einzelne Eingabe angezeigt, die Sie umbenennen können.</span><span class="sxs-lookup"><span data-stu-id="d8544-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="d8544-134">Verwenden Sie die im automatisch generierten Code erstellte Accessoreigenschaft, um mit dem Namen in Ihrem Skript auf die Eingabe zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d8544-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="d8544-135">Weitere Informationen über die Seite **Eingaben und Ausgaben** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Inputs and Outputs Page) (Transformations-Editor für Skripterstellung (Seite „Eingaben und Ausgaben“))](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="d8544-136">Hinzufügen von Variablen</span><span class="sxs-lookup"><span data-stu-id="d8544-136">Adding Variables</span></span>
 <span data-ttu-id="d8544-137">Wenn Sie vorhandene Variablen in Ihrem Skript verwenden möchten, können Sie diese in den `ReadOnlyVariables` `ReadWriteVariables` Eigenschaften Feldern und auf der Seite **Skript** des Transformations- **Editors für Skript**Erstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8544-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="d8544-138">Wenn Sie mehrere Variablen in die Eigenschaftsfelder hinzufügen, trennen Sie die Variablennamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="d8544-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="d8544-139">Sie können auch mehrere Variablen auswählen, indem Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben den `ReadOnlyVariables` `ReadWriteVariables` Eigenschaften Feldern und klicken und dann die Variablen im Dialogfeld **Variablen auswählen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="d8544-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="d8544-140">Allgemeine Informationen über das Verwenden von Variablen mit der Skriptkomponente finden Sie unter [Using Variables in the Script Component (Verwenden von Variablen in der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="d8544-141">Weitere Informationen über die Seite **Skript** im **Transformations-Editor für Skripterstellung** finden Sie unter [Script Transformation Editor (Script Page) (Transformations-Editor für Skripterstellung (Seite „Skript“))](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="d8544-142">Schreiben einer Zielkomponente im Codeentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="d8544-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="d8544-143">Nachdem Sie die Metadaten für Ihre Komponente konfiguriert haben, können Sie das benutzerdefinierte Skript schreiben.</span><span class="sxs-lookup"><span data-stu-id="d8544-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="d8544-144">Klicken Sie auf der Seite **Skript** im **Transformations-Editor für Skripterstellung** auf **Skript bearbeiten**, um die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications-IDE (VSTA) zu öffnen und Ihr benutzerdefiniertes Skript hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8544-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="d8544-145">Welche Skriptsprache Sie verwenden, hängt davon ab, ob Sie auf der Seite **Skript**[!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# als Skriptsprache für die **ScriptLanguage**-Eigenschaft festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="d8544-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="d8544-146">Wichtige Informationen, die alle Arten von Komponenten betreffen, die mithilfe der Skriptkomponente erstellt wurden, finden Sie unter [Coding and Debugging the Script Component (Codieren und Debuggen der Skriptkomponente)](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8544-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="d8544-147">Grundlegendes zum automatisch generierten Code</span><span class="sxs-lookup"><span data-stu-id="d8544-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="d8544-148">Wenn Sie nach der Erstellung und Konfiguration einer Zielkomponente die VSTA IDE öffnen, wird die bearbeitbare `ScriptMain`-Klasse im Code-Editor mit einem Stub für die `ProcessInputRow`-Methode angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8544-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="d8544-149">In der `ScriptMain`-Klasse schreiben Sie Ihren benutzerdefinierten Code, und `ProcessInputRow` ist die wichtigste Methode in einer Zielkomponente.</span><span class="sxs-lookup"><span data-stu-id="d8544-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="d8544-150">Wenn Sie das Fenster **Projekt Explorer** in VSTA öffnen, können Sie sehen, dass die Skript Komponente auch schreibgeschützte- `BufferWrapper` und- `ComponentWrapper` Projekt Elemente generiert hat.</span><span class="sxs-lookup"><span data-stu-id="d8544-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="d8544-151">Die `ScriptMain`-Klasse erbt von der `UserComponent`-Klasse im `ComponentWrapper`-Projektelement.</span><span class="sxs-lookup"><span data-stu-id="d8544-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="d8544-152">Zur Laufzeit ruft die Datenfluss-Engine die `ProcessInput`-Methode in der `UserComponent`-Klasse auf, die die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A>-Methode der übergeordneten <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Klasse überschreibt.</span><span class="sxs-lookup"><span data-stu-id="d8544-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="d8544-153">Die `ProcessInput`-Methode durchläuft der Reihe nach in Schleifen die Zeilen im Eingabepuffer und ruft für jede Zeile einmal die `ProcessInputRow`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d8544-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="d8544-154">Schreiben von benutzerdefiniertem Code</span><span class="sxs-lookup"><span data-stu-id="d8544-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="d8544-155">Um die Erstellung einer benutzerdefinierten Zielkomponente zu beenden, empfiehlt sich ggf. das Schreiben von Skript in den folgenden Methoden, die in der `ScriptMain`-Klasse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d8544-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="d8544-156">Überschreiben Sie die `AcquireConnections`-Methode, um eine Verbindung mit der externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8544-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="d8544-157">Extrahieren Sie das Verbindungsobjekt bzw. die erforderlichen Verbindungsinformationen vom Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="d8544-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="d8544-158">Überschreiben Sie als Vorbereitung zur Speicherung der Daten die `PreExecute`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d8544-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="d8544-159">Zum Beispiel könnte es sein, dass Sie `SqlCommand` und die entsprechenden Parameter in dieser Methode erstellen und konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d8544-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="d8544-160">Verwenden Sie die überschriebene `ProcessInputRow`-Methode, um jede Eingabezeile in die externe Datenquelle zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="d8544-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="d8544-161">Zum Beispiel können Sie für ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel die Spaltenwerte in die Parameter eines `SqlCommand` kopieren und den Befehl jeweils einmal pro Zeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8544-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="d8544-162">Für ein Flatfileziel können Sie die Werte für jede Spalte in einen `StreamWriter` schreiben, wobei die Werte durch Spaltentrennzeichen voneinander getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="d8544-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="d8544-163">Überschreiben Sie bei Bedarf zur Trennung von der externen Datenbank und um alle weiteren erforderlichen Cleanups durchzuführen die `PostExecute`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d8544-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="d8544-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d8544-164">Examples</span></span>
 <span data-ttu-id="d8544-165">In den folgenden Beispielen wird der Code veranschaulicht, der in der `ScriptMain`-Klasse zur Erstellung einer Zielkomponente erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d8544-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="d8544-166">In diesen Beispielen wird die Tabelle **Person. Address** in der `AdventureWorks` -Beispieldatenbank verwendet und die erste und vierte Spalte, die Spalten **int \* adressssid**\* und **nvarchar (30) City** , durch den Datenfluss übergeben.</span><span class="sxs-lookup"><span data-stu-id="d8544-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="d8544-167">Die gleichen Daten werden in den Quellen-, Transformations- und Zielbeispielen in diesem Abschnitt verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8544-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="d8544-168">Zusätzliche Voraussetzungen und Annahmen werden für jedes Beispiel dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="d8544-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="d8544-169">Beispiel ADO.NET-Ziel</span><span class="sxs-lookup"><span data-stu-id="d8544-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="d8544-170">Dieses Beispiel zeigt eine Zielkomponente, die einen vorhandenen [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager zum Speichern von Daten aus dem Datenfluss in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8544-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="d8544-171">Wenn Sie den Beispielcode ausführen möchten, müssen Sie das Paket und die Komponente folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d8544-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="d8544-172">Erstellen Sie einen [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager, der mithilfe des `SqlClient`-Anbieters eine Verbindung mit der `AdventureWorks`-Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="d8544-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="d8544-173">Erstellen Sie eine Zieltabelle, indem Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehl in der `AdventureWorks`-Datenbank ausführen:</span><span class="sxs-lookup"><span data-stu-id="d8544-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="d8544-174">Fügen Sie der Oberfläche des Datenfluss-Designers eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Ziel.</span><span class="sxs-lookup"><span data-stu-id="d8544-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="d8544-175">Verbinden Sie die Ausgabe einer Upstreamquelle oder Transformation mit der Zielkomponente im [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer.</span><span class="sxs-lookup"><span data-stu-id="d8544-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="d8544-176">(Sie können eine Quelle ohne Transformationen direkt mit einem Ziel verbinden.) Diese Ausgabe sollte Daten aus der Tabelle **Person. Address** der `AdventureWorks` Beispieldatenbank bereitstellen, die mindestens die Spalten **adressssid** und **City** enthält.</span><span class="sxs-lookup"><span data-stu-id="d8544-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="d8544-177">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="d8544-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="d8544-178">Wählen Sie auf der Seite **Eingabespalten** die Eingabespalten **AddressID** und **City** aus.</span><span class="sxs-lookup"><span data-stu-id="d8544-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="d8544-179">Geben Sie der Eingabe auf der Seite **Eingaben und Ausgaben** einen aussagekräftigeren Namen, z.B. **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="d8544-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="d8544-180">Fügen Sie auf der Seite **Verbindungs-Manager** den [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Verbindungs-Manager mit einem Namen wie **MyADONETConnectionManager** hinzu, oder erstellen Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="d8544-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="d8544-181">Klicken Sie auf der Seite **Skript** auf **Skript bearbeiten**, und geben Sie das folgende Skript ein.</span><span class="sxs-lookup"><span data-stu-id="d8544-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="d8544-182">Schließen Sie dann die Skriptentwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="d8544-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="d8544-183">Schließen Sie den **Transformations-Editor für Skripterstellung**, und führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="d8544-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="d8544-184">Beispiel für das Flatfileziel</span><span class="sxs-lookup"><span data-stu-id="d8544-184">Flat File Destination Example</span></span>
 <span data-ttu-id="d8544-185">Dieses Beispiel zeigt eine Zielkomponente, die einen vorhandenen Verbindungs-Manager für Flatfiles zum Speichern von Daten aus einem Datenfluss in eine Flatfile verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8544-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="d8544-186">Wenn Sie den Beispielcode ausführen möchten, müssen Sie das Paket und die Komponente folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d8544-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="d8544-187">Erstellen Sie einen Verbindungs-Manager für Flatfiles, der eine Verbindung mit einer Zieldatei herstellt.</span><span class="sxs-lookup"><span data-stu-id="d8544-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="d8544-188">Die Datei muss nicht vorhanden sein; sie wird durch die Zielkomponente erstellt.</span><span class="sxs-lookup"><span data-stu-id="d8544-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="d8544-189">Konfigurieren Sie die Zieldatei als durch Trennzeichen getrennte Datei, die die Spalten **AddressID** und **City** enthält.</span><span class="sxs-lookup"><span data-stu-id="d8544-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="d8544-190">Fügen Sie der Oberfläche des Datenfluss-Designers eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Ziel.</span><span class="sxs-lookup"><span data-stu-id="d8544-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="d8544-191">Verbinden Sie die Ausgabe einer Upstreamquelle oder Transformation mit der Zielkomponente im [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer.</span><span class="sxs-lookup"><span data-stu-id="d8544-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="d8544-192">(Sie können eine Quelle ohne Transformationen direkt mit einem Ziel verbinden.) Diese Ausgabe sollte Daten aus der Tabelle **Person. Address** der `AdventureWorks` Beispieldatenbank bereitstellen und sollte mindestens die Spalten **adressssid** und **City** enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8544-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="d8544-193">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="d8544-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="d8544-194">Wählen Sie auf der Seite **Eingabespalten** die Spalten **AddressID** und **City** aus.</span><span class="sxs-lookup"><span data-stu-id="d8544-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="d8544-195">Geben Sie der Eingabe auf der Seite **Eingaben und Ausgaben** einen aussagekräftigeren Namen, z.B. **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="d8544-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="d8544-196">Fügen Sie auf der Seite **Verbindungs-Manager** den Verbindungs-Manager für Flatfiles mit einem aussagekräftigen Namen hinzu, z.B. **MyFlatFileDestConnectionManager**, oder erstellen Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="d8544-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="d8544-197">Klicken Sie auf der Seite **Skript** auf **Skript bearbeiten**, und geben Sie das folgende Skript ein.</span><span class="sxs-lookup"><span data-stu-id="d8544-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="d8544-198">Schließen Sie dann die Skriptentwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="d8544-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="d8544-199">Schließen Sie den **Transformations-Editor für Skripterstellung**, und führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="d8544-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="d8544-200">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d8544-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d8544-201">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d8544-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d8544-202">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d8544-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d8544-203">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d8544-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8544-204">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8544-204">See Also</span></span>
 <span data-ttu-id="d8544-205">[Erstellen einer Quelle mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Entwickeln einer benutzerdefinierten Zielkomponente](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="d8544-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


