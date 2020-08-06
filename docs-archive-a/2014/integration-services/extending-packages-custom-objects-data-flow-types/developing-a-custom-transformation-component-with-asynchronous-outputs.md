---
title: Entwickeln einer benutzerdefinierten Transformationskomponente mit asynchronen Ausgaben | Microsoft-Dokumentation
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
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721637"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="77880-102">Entwickeln einer benutzerdefinierten Transformationskomponente mit asynchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="77880-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="77880-103">Verwenden Sie eine Komponente mit asynchronen Ausgaben dann, wenn eine Transformation keine Zeilen ausgeben kann, solange die Komponente nicht alle ihre Eingabezeilen empfangen hat, oder wenn die Transformation nicht genau eine Ausgabezeile für jede als Eingabe empfangene Zeile erstellt.</span><span class="sxs-lookup"><span data-stu-id="77880-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="77880-104">Die Transformation für das Aggregieren kann z. B. erst dann eine Summe über mehrere Zeilen errechnen, wenn sie alle Zeilen gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="77880-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="77880-105">Dagegen können Sie jederzeit eine Komponente mit synchronen Ausgaben verwenden, wenn Sie jede Datenzeile beim Durchlaufen verändern.</span><span class="sxs-lookup"><span data-stu-id="77880-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="77880-106">Sie können die Daten für jede vorhandene Zeile verändern, oder Sie können eine oder mehrere neue Spalten erstellen, wovon jede einen Wert für jede einzelne der Eingabzeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="77880-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="77880-107">Weitere Informationen zu den Unterschieden zwischen synchronen und asynchronen Komponenten finden Sie unter [Grundlegendes zu synchronen und asynchronen Transformationen](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="77880-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="77880-108">Transformationskomponenten mit asynchronen Ausgaben sind eindeutig, da sie gleichzeitig als Ziel- und als Quellkomponenten fungieren.</span><span class="sxs-lookup"><span data-stu-id="77880-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="77880-109">Diese Art der Komponente empfängt Zeilen von Upstreamkomponenten und fügt Zeilen hinzu, die von Downstreamkomponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77880-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="77880-110">Keine andere Datenflusskomponente führt beide dieser Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="77880-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="77880-111">Die Spalten von Upstreamkomponenten, die einer Komponente mit synchronen Ausgaben zur Verfügung stehen, stehen den Komponenten, die sich unterhalb der Komponente befinden, automatisch zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="77880-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="77880-112">Daher muss eine Komponente mit synchronen Ausgaben keine Ausgabespalten definieren, um für die nächste Komponente Spalten und Zeilen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="77880-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="77880-113">Komponenten mit asynchronen Ausgaben müssen dagegen Ausgabespalten definieren, und Zeilen für die Downstreamkomponenten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="77880-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="77880-114">Daher muss eine Komponente mit asynchronen Ausgaben sowohl in der Entwurfs- als auch in der Ausführungszeit mehr Tasks ausführen, und der Komponentenentwickler muss mehr Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="77880-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="77880-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthält mehrere Transformationen mit asynchronen Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="77880-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="77880-116">So erfordert z. B. die Transformation zum Sortieren alle Zeilen, bevor sie sie sie sortieren kann, wobei sie asynchrone Ausgaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="77880-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="77880-117">Nachdem sie alle Zeilen empfangen hat, sortiert sie sie und fügt sie der Ausgabe hinzu.</span><span class="sxs-lookup"><span data-stu-id="77880-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="77880-118">Dieser Abschnitt erklärt im Detail, wie Transformationen mit asynchronen Ausgaben entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="77880-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="77880-119">Weitere Informationen zur Entwicklung von Quellkomponenten finden Sie unter [Entwickeln einer benutzerdefinierten Quellkomponente](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="77880-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="77880-120">Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="77880-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="77880-121">Erstellen der Komponente</span><span class="sxs-lookup"><span data-stu-id="77880-121">Creating the Component</span></span>
 <span data-ttu-id="77880-122">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> -Eigenschaft des <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>-Objekts identifiziert, ob eine Ausgabe synchron oder asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="77880-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="77880-123">Um eine asynchrone Ausgabe zu erstellen, fügen Sie die Ausgabe der Komponente hinzu, und legen Sie <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="77880-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="77880-124">Durch Festlegen dieser Eigenschaft wird außerdem bestimmt, ob der Datenflusstask <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekte sowohl für die Eingabe als auch für die Ausgabe der Komponente zuordnet, oder ob ein einzelner Puffer zugewiesen wird, den die beiden Objekte gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="77880-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="77880-125">Im folgenden Beispielcode wird eine Komponente, die in ihrer <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Implementierung eine asynchrone Ausgabe erstellt, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="77880-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="77880-126">Erstellen und Konfigurieren von Ausgabespalten</span><span class="sxs-lookup"><span data-stu-id="77880-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="77880-127">Wie bereits erwähnt, fügt eine asynchrone Komponente Spalten zu ihrer Ausgabespaltenauflistung hinzu, um Spalten für die Downstreamkomponenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="77880-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="77880-128">Je nach den Anforderungen der Komponente stehen mehrere Entwurfszeitmethoden zur Wahl.</span><span class="sxs-lookup"><span data-stu-id="77880-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="77880-129">Zur Übergabe aller Spalten der Upstreamkomponenten an die Downstreamkomponenten würden Sie z. B. die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A>-Methode überschreiben, um die Spalten hinzuzufügen, da dies die erste Methode ist, in der die Eingabespalten für die Komponenten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="77880-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="77880-130">Wenn die Komponente basierend auf den für ihre Eingabe ausgewählten Spalten Ausgabespalten erstellt, überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A>-Methode, um die Ausgabespalten auszuwählen und anzugeben, wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77880-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="77880-131">Wenn eine Komponente mit asynchronen Ausgaben basierend auf den Spalten von einer Upstreamkomponente Ausgabespalten erstellt und die verfügbaren Upstreamspalten sich ändern, dann sollte die Komponente ihre Ausgabespaltenauflistung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="77880-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="77880-132">Diese Änderungen sollten von der Komponente während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> erkannt und während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="77880-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="77880-133">Wenn eine Ausgabespalte von der Ausgabespaltenauflistung entfernt wird, dann werden die Downstreamkomponenten im Datenfluss, die auf die Spalte verweisen, beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="77880-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="77880-134">Die Ausgabespalte muss repariert werden, ohne dass die Spalte entfernt und wieder erstellt wird, um eine Beschädigung der Downstreamkomponenten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="77880-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="77880-135">Wenn sich z. B. der Datentyp der Spalte geändert hat, müssen Sie den Datentyp aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="77880-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="77880-136">Das folgende Codebeispiel zeigt eine Komponente, die für jede von der Upstreamkomponente verfügbare Spalte eine Ausgabespalte zu ihrer Ausgabespaltenauflistung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="77880-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="77880-137">Runtime</span><span class="sxs-lookup"><span data-stu-id="77880-137">Run Time</span></span>
 <span data-ttu-id="77880-138">Komponenten mit asynchronen Ausgaben führen während der Laufzeit ebenfalls eine andere Sequenz von Methoden aus als andere Komponententypen.</span><span class="sxs-lookup"><span data-stu-id="77880-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="77880-139">Zunächst sind sie die einzigen Komponenten, die sowohl bei der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>- als auch der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="77880-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="77880-140">Komponenten mit asynchronen Ausgaben benötigen ebenfalls Zugang zu allen eingehenden Zeilen, bevor sie mit der Verarbeitung beginnen können; daher müssen sie die Eingabezeilen intern zwischenspeichern, bis alle Zeilen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="77880-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="77880-141">Schließlich empfangen Komponenten mit asynchronen Ausgaben im Gegensatz zu anderen Komponenten sowohl einen Eingabe- als auch einen Ausgabepuffer.</span><span class="sxs-lookup"><span data-stu-id="77880-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="77880-142">Grundlegendes zu den Puffern</span><span class="sxs-lookup"><span data-stu-id="77880-142">Understanding the Buffers</span></span>
 <span data-ttu-id="77880-143">Der Eingabepuffer wird von der Komponente während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> empfangen.</span><span class="sxs-lookup"><span data-stu-id="77880-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="77880-144">Dieser Puffer enthält die dem Puffer von Upstreamkomponenten hinzugefügten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77880-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="77880-145">Der Puffer enthält zusätzlich zu den Spalten, die in der Ausgabe einer Upstreamkomponente bereitgestellt wurden, jedoch nicht zu der asynchronen Eingabeauflistung der Komponente hinzugefügt wurden, auch die Spalten der Ausgabe der Komponente.</span><span class="sxs-lookup"><span data-stu-id="77880-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="77880-146">Der Ausgabepuffer, der der Komponente in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> zur Verfügung gestellt wird, enthält anfänglich keine Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77880-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="77880-147">Die Komponente fügt Zeilen zu diesem Puffer hinzu und stellt den Puffer Downstreamkomponenten zur Verfügung, wenn dieser voll ist.</span><span class="sxs-lookup"><span data-stu-id="77880-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="77880-148">Der Ausgabepuffer enthält zusätzlich zu den Spalten, die andere Downstreamkomponenten zu ihren Ausgaben hinzugefügt haben, die in der Ausgabespaltenauflistung der Komponente definierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="77880-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="77880-149">Dieses Verhalten unterscheidet sich von dem der Komponenten mit synchronen Ausgaben, die einen einzelnen, gemeinsam verwendeten Puffer empfangen.</span><span class="sxs-lookup"><span data-stu-id="77880-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="77880-150">Der gemeinsam verwendete Puffer einer Komponente mit synchronen Ausgaben enthält zusätzlich zu den Spalten, die zu den Ausgaben der Upstream- und Downstreamkomponenten hinzugefügt wurden, sowohl die Eingabe- als auch Ausgabespalten der Komponente.</span><span class="sxs-lookup"><span data-stu-id="77880-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="77880-151">Verarbeiten von Zeilen</span><span class="sxs-lookup"><span data-stu-id="77880-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="77880-152">Zwischenspeichern von Eingabezeilen</span><span class="sxs-lookup"><span data-stu-id="77880-152">Caching Input Rows</span></span>
 <span data-ttu-id="77880-153">Wenn Sie eine Komponente mit asynchronen Ausgaben schreiben, dann stehen Ihnen drei Optionen für das Hinzufügen von Zeilen zum Ausgabepuffer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="77880-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="77880-154">Sie können diese hinzufügen, sowie die Eingabezeilen empfangen werden, Sie können sie zwischenspeichern, bis die Komponente alle Zeilen von der Upstreamkomponente erhalten hat, oder Sie können sie zu einem für die Komponente geeigneten Zeitpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="77880-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="77880-155">Die von Ihnen gewählte Methode hängt von den Anforderungen der Komponente ab.</span><span class="sxs-lookup"><span data-stu-id="77880-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="77880-156">Zum Beispiel müssen bei der Komponente zum Sortieren zunächst alle Upstreamzeilen empfangen wurden, bevor diese sortiert werden können.</span><span class="sxs-lookup"><span data-stu-id="77880-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="77880-157">Deshalb wartet sie, bis alle Zeilen gelesen sind, bevor sie Zeilen zum Ausgabepuffer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="77880-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="77880-158">Die im Eingabepuffer empfangenen Zeilen müssen intern von der Komponente zwischengespeichert werden, bis sie bereit ist, diese zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="77880-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="77880-159">Die eingehenden Pufferzeilen können in einer Datentabelle, einem multidimensionalem Array oder einer beliebigen anderen internen Struktur zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="77880-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="77880-160">Hinzufügen von Ausgabezeilen</span><span class="sxs-lookup"><span data-stu-id="77880-160">Adding Output Rows</span></span>
 <span data-ttu-id="77880-161">Unabhängig davon, ob Sie Zeilen zum Ausgabepuffer hinzufügen, sobald diese empfangen werden oder nachdem alle Zeilen empfangen wurden, rufen Sie dazu die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A>-Methode für den Ausgabepuffer auf.</span><span class="sxs-lookup"><span data-stu-id="77880-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="77880-162">Nachdem Sie die Zeile hinzugefügt haben, legen Sie die Werte jeder Spalte in der neuen Zeile fest.</span><span class="sxs-lookup"><span data-stu-id="77880-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="77880-163">Da sich in manchen Fällen mehr Spalten im Ausgabepuffer als in der Ausgabespaltenauflistung der Komponente befinden, müssen Sie den Index der geeigneten Spalte im Puffer finden, bevor Sie seinen Wert festlegen können.</span><span class="sxs-lookup"><span data-stu-id="77880-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="77880-164">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>-Eigenschaft gibt den Index der Spalte in der Pufferzeile mit der angegebenen Herkunfts-ID zurück, die dann verwendet wird, um der Pufferspalte den Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="77880-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="77880-165">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode, die vor der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode oder der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode aufgerufen wird, ist die erste Methode, bei der die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>-Eigenschaft verfügbar ist, und sie bietet die erste Möglichkeit, die Indizes der Spalten in den Eingabe- und Ausgabepuffern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="77880-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="77880-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77880-166">Sample</span></span>
 <span data-ttu-id="77880-167">Im folgenden Beispiel wird eine einfache Transformationskomponente mit asynchronen Ausgaben gezeigt, die Zeilen zum Ausgabepuffer hinzufügt, sowie sie erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="77880-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="77880-168">In diesem Beispiel werden nicht alle Methoden und Funktionen dargestellt, die in diesem Thema erläutert wurden.</span><span class="sxs-lookup"><span data-stu-id="77880-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="77880-169">Es veranschaulicht die wichtigen Methoden, die jede benutzerdefinierte Transformationskomponente mit asynchronen Ausgaben überschreiben muss, enthält jedoch keinen Code für eine Überprüfung zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="77880-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="77880-170">Außerdem wird im Code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> vorausgesetzt, dass die Ausgabespaltenauflistung für jede Spalte in der Eingabenspaltenauflistung eine Spalte aufweist.</span><span class="sxs-lookup"><span data-stu-id="77880-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="77880-171">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="77880-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="77880-172">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="77880-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="77880-173">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="77880-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="77880-174">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="77880-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="77880-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77880-175">See Also</span></span>
 <span data-ttu-id="77880-176">[Entwickeln einer benutzerdefinierten Transformations Komponente mit synchronen Ausgaben](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) Grundlegendes zu [synchronen und asynchronen Transformationen](../understanding-synchronous-and-asynchronous-transformations.md) [Erstellen einer asynchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="77880-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


