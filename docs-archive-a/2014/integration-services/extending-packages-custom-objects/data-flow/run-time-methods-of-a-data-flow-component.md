---
title: Runtime-Methoden einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718592"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="bdf8d-102">Laufzeitmethoden einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="bdf8d-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="bdf8d-103">Zur Laufzeit wird vom Datenflusstask die Reihenfolge von Komponenten überprüft, ein Ausführungsplan vorbereitet und ein Pool von Arbeitsthreads verwaltet, die den Arbeitsplan ausführen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="bdf8d-104">Der Task lädt Datenzeilen aus Quellen, verarbeitet diese durch Transformationen und speichert sie dann in Zielen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="bdf8d-105">Reihenfolge der Methodenausführung</span><span class="sxs-lookup"><span data-stu-id="bdf8d-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="bdf8d-106">Während der Ausführung einer Datenflusskomponente, wird eine Untergruppe der Methoden in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="bdf8d-107">Die Methoden und die Reihenfolge, in der diese aufgerufen werden, sind immer gleich, mit Ausnahme der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode und der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="bdf8d-108">Diese beiden Methoden werden basierend auf dem Vorhandensein und der Konfiguration des <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>-Objekts und des <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>-Objekts einer Komponente aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="bdf8d-109">In der folgenden Liste sind die Methoden in der Reihenfolge veranschaulicht, in der sie während der Komponentenausführung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="bdf8d-110">Beachten Sie, dass <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> im Falle eines Aufrufs immer vor <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="bdf8d-111">PrimeOutput-Methode</span><span class="sxs-lookup"><span data-stu-id="bdf8d-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="bdf8d-112">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A>-Methode wird aufgerufen, wenn eine Komponente mindestens eine Ausgabe aufweist, die über ein <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>-Objekt an eine Downstreamkomponente angefügt ist, und die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>-Eigenschaft der Ausgabe 0 (null) beträgt.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="bdf8d-113">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A>-Methode wird für Quellkomponenten und Transformationen mit asynchronen Ausgaben aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="bdf8d-114">Im Gegensatz zu der weiter unten beschriebenen <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode wird die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode nur einmal für jede Komponente aufgerufen, für die dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="bdf8d-115">ProcessInput-Methode</span><span class="sxs-lookup"><span data-stu-id="bdf8d-115">ProcessInput Method</span></span>  
 <span data-ttu-id="bdf8d-116">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A>-Methode wird für Komponenten aufgerufen, die über mindestens eine Eingabe verfügen, die durch ein <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>-Objekt an eine Upstreamkomponente angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="bdf8d-117">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A>-Methode wird für Zielkomponenten und Transformationen mit synchronen Ausgaben aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="bdf8d-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> wird wiederholt aufgerufen, bis keine Zeilen von Upstreamkomponenten mehr vorhanden sind, die verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="bdf8d-119">Arbeiten mit Eingaben und Ausgaben</span><span class="sxs-lookup"><span data-stu-id="bdf8d-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="bdf8d-120">Zur Laufzeit werden die folgenden Tasks von Datenflusskomponenten ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="bdf8d-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="bdf8d-121">Quellkomponenten fügen Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="bdf8d-122">Transformationskomponenten mit synchronen Ausgaben empfangen von Quellkomponenten bereitgestellte Zeilen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="bdf8d-123">Transformationskomponenten mit asynchronen Ausgaben empfangen Zeilen und fügen Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="bdf8d-124">Zielkomponenten empfangen Zeilen und laden sie dann in ein Ziel.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="bdf8d-125">Während der Ausführung ordnet der Datenflusstask <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekte zu, die alle Spalten enthalten, die in der Ausgabespaltenauflistung einer Sequenz von Komponenten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="bdf8d-126">Wenn jede der vier Komponenten in einem Datenflusstask beispielsweise seiner Ausgabespaltenauflistung eine Ausgabespalte hinzufügt, enthält der Puffer, der jeder Komponente bereitgestellt wird, vier Spalten, eine für jede Ausgabespalte pro Komponente.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="bdf8d-127">Aufgrund dieses Verhaltens empfängt eine Komponente manchmal Puffer, die Spalten enthalten, die nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="bdf8d-128">Da die von der Komponente empfangenen Puffer Spalten enthalten können, die von der Komponente nicht verwendet werden, müssen Sie die Spalten, die Sie in den Eingabe- und Ausgabespaltenauflistungen der Komponente verwenden möchten, in dem Puffer suchen, der der Komponente von dem Datenflusstask bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="bdf8d-129">Dazu steht Ihnen die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>-Eigenschaft zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="bdf8d-130">Aus Leistungsgründen wird dieser Task in der Regeln nur während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode ausgeführt und nicht in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> oder <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="bdf8d-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> wird vor der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode und der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode aufgerufen. Dies ist auch die erste Gelegenheit für eine Komponente, diese Arbeit auszuführen, nachdem <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> für diese Komponente verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="bdf8d-132">Während dieser Methode sollte die Komponente ihre Spalten in den Puffern suchen und diese Informationen intern speichern, sodass die Spalten in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode oder der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="bdf8d-133">Im folgenden Codebeispiel wird veranschaulicht, wie eine Transformationskomponente mit synchroner Ausgabe ihre Eingabespalten während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode im Puffer sucht.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="bdf8d-134">Hinzufügen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="bdf8d-134">Adding Rows</span></span>  
 <span data-ttu-id="bdf8d-135">Komponenten liefern Zeilen für Downstreamkomponenten, indem <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekten Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="bdf8d-136">Der Datenflusstask stellt ein Array von Ausgabepuffern – einen für jedes <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>-Objekt, das mit einer Downstreamkomponente verbunden ist – als Parameter für die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="bdf8d-137">Quellkomponenten und Transformationskomponenten mit asynchronen Ausgaben fügen den Puffern Zeilen hinzu und rufen die  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>-Methode auf, wenn das Hinzufügen der Zeilen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="bdf8d-138">Der Datenflusstask verwaltet die Ausgabepuffer, die er den Komponenten bereitstellt und verschiebt die Zeilen in dem Puffer automatisch zur nächsten Komponente, wenn der Puffer voll ist.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="bdf8d-139">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode wird, im Gegensatz zur <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode, die wiederholt aufgerufen wird, einmal pro Komponente aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="bdf8d-140">Im folgenden Codebeispiel wird veranschaulicht, wie eine Komponente ihrem Ausgabepuffer Zeilen während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode hinzufügt und dann die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="bdf8d-141">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Quellkomponente](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) und [Entwickeln einer benutzerdefinierten Transformationskomponente mit asynchronen Ausgaben](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="bdf8d-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="bdf8d-142">Empfangen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="bdf8d-142">Receiving Rows</span></span>  
 <span data-ttu-id="bdf8d-143">Komponenten empfangen Zeilen von Upstreamkomponenten in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="bdf8d-144">Der Datenflusstask stellt ein <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekt, das die dem Datenfluss von Upstreamkomponenten hinzugefügten Zeilen enthält, einer <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode als Parameter bereit.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="bdf8d-145">Dieser Eingabepuffer kann verwendet werden, um die Zeilen und Spalten in dem Puffer zu überprüfen und zu ändern, er kann jedoch nicht verwendet werden, um Zeilen hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="bdf8d-146">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode wird immer wieder aufgerufen, bis keine verfügbaren Puffer mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="bdf8d-147">Beim letzten Aufruf ist die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>-Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="bdf8d-148">Sie können eine Iteration durch die Auflistung von Zeilen in dem Puffer mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>-Methode durchführen, durch die der Puffer zur nächsten Zeile bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="bdf8d-149">Diese Methode gibt `false` zurück, wenn sich der Puffer in der letzten Zeile der Auflistung befindet.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="bdf8d-150">Sie müssen die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>-Eigenschaft nicht überprüfen, außer Sie müssen eine weitere Aktion ausführen, nachdem die letzte Datenzeile verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="bdf8d-151">Im folgenden Text wird das korrekte Muster für die Verwendung <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>-Methode und der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="bdf8d-152">Im folgenden Codebeispiel wird veranschaulicht, wie eine Komponente die Zeilen in Eingabepuffern während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="bdf8d-153">Weitere Informationen zum Entwickeln von Komponenten, die Zeilen in Eingabepuffern empfangen, finden Sie unter [Entwickeln einer benutzerdefinierten Zielkomponente](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) und [Entwickeln einer benutzerdefinierten Transformationskomponente mit synchronen Ausgaben](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="bdf8d-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="bdf8d-154">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="bdf8d-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bdf8d-155">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="bdf8d-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bdf8d-156">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="bdf8d-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bdf8d-157">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bdf8d-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf8d-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdf8d-158">See Also</span></span>  
 [<span data-ttu-id="bdf8d-159">Entwurfszeitmethoden einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="bdf8d-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
