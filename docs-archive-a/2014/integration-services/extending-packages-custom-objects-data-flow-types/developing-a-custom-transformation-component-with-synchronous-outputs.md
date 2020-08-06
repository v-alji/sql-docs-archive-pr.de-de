---
title: Entwickeln einer benutzerdefinierten Transformationskomponente mit synchronen Ausgaben | Microsoft-Dokumentation
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
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721638"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="1be69-102">Entwickeln einer benutzerdefinierten Transformationskomponente mit synchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="1be69-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="1be69-103">Transformationskomponenten mit synchronen Ausgaben empfangen Zeilen von Upstreamkomponenten und lesen oder modifizieren die Werte in den Spalten der betreffenden Zeilen bei der Weitergabe dieser Zeilen an Downstreamkomponenten.</span><span class="sxs-lookup"><span data-stu-id="1be69-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="1be69-104">Sie können auch zusätzliche Ausgabespalten definieren, die sich aus den von den Upstreamkomponenten erhaltenen Spalten ableiten. Es werden dem Datenfluss jedoch keine zusätzlichen Zeilen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1be69-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="1be69-105">Weitere Informationen zu den Unterschieden zwischen synchronen und asynchronen Komponenten finden Sie unter [Grundlegendes zu synchronen und asynchronen Transformationen](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="1be69-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="1be69-106">Diese Komponentenart ist für Aufgaben geeignet, bei denen die Daten nach der Bereitstellung für die Komponente inline modifiziert werden und die Komponente nicht alle Zeilen erkennen muss, um Daten verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="1be69-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="1be69-107">Es ist die am einfachsten zu entwickelnde Komponente, da Transformationen mit synchronen Ausgaben normalerweise keine Verbindung zu externen Datenquellen herstellen, keine externen Metadatenspalten verwalten oder Ausgabepuffern Zeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1be69-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="1be69-108">Das Erstellen einer Transformationskomponente mit synchronen Ausgaben umfasst auch das Hinzufügen von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> mit den für die Komponente ausgewählten Upstreamspalten und eines <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>-Objekts, das von der Komponente erstellte, abgeleitete Spalten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1be69-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="1be69-109">Dazu gehören auch das Implementieren der Entwurfszeitmethoden und das Bereitstellen von Code, der die Spalten der eingehenden Pufferzeilen während der Ausführung liest oder modifiziert.</span><span class="sxs-lookup"><span data-stu-id="1be69-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="1be69-110">In diesem Abschnitt finden Sie Informationen, die zum Implementieren einer benutzerdefinierten Transformationskomponente benötigt werden, und stellt Codebeispiele für ein besseres Verständnis der Konzepte bereit.</span><span class="sxs-lookup"><span data-stu-id="1be69-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="1be69-111">Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="1be69-111">Design Time</span></span>  
 <span data-ttu-id="1be69-112">Zum Entwurfszeitcode dieser Komponente zählt auch das Erstellen von Ein- und Ausgaben, das Hinzufügen der von der Komponente generierten zusätzlichen Ausgabespalten und das Überprüfen der Konfiguration dieser Komponente.</span><span class="sxs-lookup"><span data-stu-id="1be69-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="1be69-113">Erstellen der Komponente</span><span class="sxs-lookup"><span data-stu-id="1be69-113">Creating the Component</span></span>  
 <span data-ttu-id="1be69-114">Die Eingaben, Ausgaben und benutzerdefinierten Eigenschaften der Komponente werden normalerweise während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="1be69-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="1be69-115">Es gibt zwei Möglichkeiten zum Hinzufügen der Ein- und Ausgaben einer Transformationskomponente mit synchronen Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="1be69-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="1be69-116">Sie können die Basisklassenimplementierung der Methode verwenden und die damit erstellten Standardein- und -ausgaben dann modifizieren, oder Sie können die Ein- und Ausgabe selbst explizit hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1be69-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="1be69-117">Im folgenden Codebeispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> gezeigt, die die Ein- und Ausgabeobjekte explizit hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1be69-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="1be69-118">Der Aufruf der Basisklasse hätte dasselbe Ergebnis zur Folge und ist in einem Kommentar enthalten.</span><span class="sxs-lookup"><span data-stu-id="1be69-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="1be69-119">Erstellen und Konfigurieren von Ausgabespalten</span><span class="sxs-lookup"><span data-stu-id="1be69-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="1be69-120">Auch wenn von Transformationskomponenten mit synchronen Ausgaben Puffern keine Zeilen hinzugefügt werden, können ihrer Ausgabe darüber zusätzliche Ausgabespalten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="1be69-121">Wenn eine Komponente eine Ausgabespalte hinzufügt, werden die Werte für die neue Ausgabespalte normalerweise zur Laufzeit von den Daten in einer oder mehrerer der Spalten abgeleitet, die von einer Upstreamkomponente bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="1be69-122">Nachdem eine Ausgabespalte erstellt wurde, müssen die dazugehörigen Datentypeigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="1be69-123">Das Festlegen der Datentypeigenschaften einer Ausgabespalte erfordert spezielle Schritte und wird durch das Aufrufen der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>-Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1be69-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="1be69-124">Diese Methode ist erforderlich, da die Eigenschaften <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> im Einzelnen schreibgeschützt sind und jede Eigenschaft von den Einstellungen der anderen abhängt.</span><span class="sxs-lookup"><span data-stu-id="1be69-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="1be69-125">Diese Methode stellt sicher, dass die Werte der Eigenschaften konsistent festgelegt werden, und der Datenflusstask überprüft diese korrekte Festlegung.</span><span class="sxs-lookup"><span data-stu-id="1be69-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="1be69-126">Der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> der Spalte bestimmt die Werte, die für die anderen Eigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="1be69-127">Die folgende Tabelle zeigt die Anforderungen an die abhängigen Eigenschaften für jeden <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="1be69-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="1be69-128">Bei den nicht aufgelisteten Datentypen sind die abhängigen Eigenschaften auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1be69-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="1be69-129">DataType</span><span class="sxs-lookup"><span data-stu-id="1be69-129">DataType</span></span>|<span data-ttu-id="1be69-130">Länge</span><span class="sxs-lookup"><span data-stu-id="1be69-130">Length</span></span>|<span data-ttu-id="1be69-131">Skalieren</span><span class="sxs-lookup"><span data-stu-id="1be69-131">Scale</span></span>|<span data-ttu-id="1be69-132">Precision</span><span class="sxs-lookup"><span data-stu-id="1be69-132">Precision</span></span>|<span data-ttu-id="1be69-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="1be69-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="1be69-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="1be69-134">DT_DECIMAL</span></span>|<span data-ttu-id="1be69-135">0</span><span class="sxs-lookup"><span data-stu-id="1be69-135">0</span></span>|<span data-ttu-id="1be69-136">Größer 0 und kleiner oder gleich 28</span><span class="sxs-lookup"><span data-stu-id="1be69-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="1be69-137">0</span><span class="sxs-lookup"><span data-stu-id="1be69-137">0</span></span>|<span data-ttu-id="1be69-138">0</span><span class="sxs-lookup"><span data-stu-id="1be69-138">0</span></span>|  
|<span data-ttu-id="1be69-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="1be69-139">DT_CY</span></span>|<span data-ttu-id="1be69-140">0</span><span class="sxs-lookup"><span data-stu-id="1be69-140">0</span></span>|<span data-ttu-id="1be69-141">0</span><span class="sxs-lookup"><span data-stu-id="1be69-141">0</span></span>|<span data-ttu-id="1be69-142">0</span><span class="sxs-lookup"><span data-stu-id="1be69-142">0</span></span>|<span data-ttu-id="1be69-143">0</span><span class="sxs-lookup"><span data-stu-id="1be69-143">0</span></span>|  
|<span data-ttu-id="1be69-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="1be69-144">DT_NUMERIC</span></span>|<span data-ttu-id="1be69-145">0</span><span class="sxs-lookup"><span data-stu-id="1be69-145">0</span></span>|<span data-ttu-id="1be69-146">Größer 0 und kleiner oder gleich 28 sowie kleiner als Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="1be69-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="1be69-147">Größer oder gleich 1 und kleiner oder gleich 38</span><span class="sxs-lookup"><span data-stu-id="1be69-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="1be69-148">0</span><span class="sxs-lookup"><span data-stu-id="1be69-148">0</span></span>|  
|<span data-ttu-id="1be69-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="1be69-149">DT_BYTES</span></span>|<span data-ttu-id="1be69-150">Größer 0</span><span class="sxs-lookup"><span data-stu-id="1be69-150">Greater than 0.</span></span>|<span data-ttu-id="1be69-151">0</span><span class="sxs-lookup"><span data-stu-id="1be69-151">0</span></span>|<span data-ttu-id="1be69-152">0</span><span class="sxs-lookup"><span data-stu-id="1be69-152">0</span></span>|<span data-ttu-id="1be69-153">0</span><span class="sxs-lookup"><span data-stu-id="1be69-153">0</span></span>|  
|<span data-ttu-id="1be69-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="1be69-154">DT_STR</span></span>|<span data-ttu-id="1be69-155">Größer als 0 und kleiner als 8000</span><span class="sxs-lookup"><span data-stu-id="1be69-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="1be69-156">0</span><span class="sxs-lookup"><span data-stu-id="1be69-156">0</span></span>|<span data-ttu-id="1be69-157">0</span><span class="sxs-lookup"><span data-stu-id="1be69-157">0</span></span>|<span data-ttu-id="1be69-158">Nicht 0 und eine gültige Codepage</span><span class="sxs-lookup"><span data-stu-id="1be69-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="1be69-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="1be69-159">DT_WSTR</span></span>|<span data-ttu-id="1be69-160">Größer 0 und kleiner 4000</span><span class="sxs-lookup"><span data-stu-id="1be69-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="1be69-161">0</span><span class="sxs-lookup"><span data-stu-id="1be69-161">0</span></span>|<span data-ttu-id="1be69-162">0</span><span class="sxs-lookup"><span data-stu-id="1be69-162">0</span></span>|<span data-ttu-id="1be69-163">0</span><span class="sxs-lookup"><span data-stu-id="1be69-163">0</span></span>|  
  
 <span data-ttu-id="1be69-164">Da die Beschränkungen der Datentypeigenschaften vom Datentyp der Ausgabespalte abhängen, müssen Sie bei der Arbeit mit verwalteten Typen den richtigen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Datentyp wählen.</span><span class="sxs-lookup"><span data-stu-id="1be69-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="1be69-165">Die Basisklasse stellt drei Hilfsmethoden bereit, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, die Entwickler verwalteter Komponenten bei der Auswahl eines [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Datentyps für einen verwalteten Typ unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1be69-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="1be69-166">Diese Methoden wandeln verwaltete Datentypen in [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Datentypen um und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="1be69-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="1be69-167">Runtime</span><span class="sxs-lookup"><span data-stu-id="1be69-167">Run Time</span></span>  
 <span data-ttu-id="1be69-168">Generell wird die Implementierung der Laufzeitkomponente zwei Kategorien zugeordnet. Diese sind das Suchen der Ein- und Ausgabespalten der Komponente im Puffer und das Lesen oder Schreiben dieser Spaltenwerte in den eingehenden Pufferzeilen.</span><span class="sxs-lookup"><span data-stu-id="1be69-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="1be69-169">Suchen von Spalten im Puffer</span><span class="sxs-lookup"><span data-stu-id="1be69-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="1be69-170">Die Anzahl der Spalten in den Puffern, die bei der Ausführung für eine Komponente bereitgestellt werden, ist wahrscheinlich höher als die Anzahl der Spalten in den Ein- oder Ausgabeauflistungen der Komponente.</span><span class="sxs-lookup"><span data-stu-id="1be69-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="1be69-171">Dies liegt daran, dass jeder Puffer alle Ausgabespalten enthält, die in den Komponenten in einem Datenfluss definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="1be69-172">Komponentenentwickler müssen die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>-Methode des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> verwenden, um sicherzustellen, dass die Pufferspalten den Spalten für die Ein- und Ausgabe korrekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1be69-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="1be69-173">Diese Methode lokalisiert eine Spalte im angegebenen Puffer mithilfe seiner Herkunfts-ID.</span><span class="sxs-lookup"><span data-stu-id="1be69-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="1be69-174">Normalerweise werden Spalten während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> gesucht, da dies die erste Laufzeitmethode ist, bei der die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>-Eigenschaft verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1be69-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="1be69-175">Das folgende Codebeispiel zeigt eine Komponente, die Indizes der Spalten in der Auflistung ihrer Eingabe- und Ausgabespalte während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> sucht.</span><span class="sxs-lookup"><span data-stu-id="1be69-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="1be69-176">Die Spaltenindizes werden in einem Array mit ganzen Zahlen gespeichert, und die Komponente kann während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1be69-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="1be69-177">Verarbeiten von Zeilen</span><span class="sxs-lookup"><span data-stu-id="1be69-177">Processing Rows</span></span>  
 <span data-ttu-id="1be69-178">Komponenten empfangen <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Objekte, die Zeilen und Spalten in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="1be69-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="1be69-179">Bei dieser Methode werden die Zeilen im Puffer durchlaufen, und die während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> erkannten Spalten werden gelesen und modifiziert.</span><span class="sxs-lookup"><span data-stu-id="1be69-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="1be69-180">Diese Methode wird vom Datenflusstask wiederholt aufgerufen, bis von der Upstreamkomponente keine Zeilen mehr bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1be69-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="1be69-181">Eine einzelne Spalte im Puffer wird mithilfe der Indexerzugriffsmethode für Arrays oder mit der `Get`- bzw. `Set`-Methode gelesen oder geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1be69-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="1be69-182">Die `Get`-Methode und die `Set`-Methode sind effizienter und sollten dann verwendet werden, wenn der Datentyp der Spalte in dem Puffer bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="1be69-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="1be69-183">Im folgenden Codebeispiel wird eine Implementierung der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode zur Verarbeitung von eingehenden Zeilen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1be69-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="1be69-184">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1be69-184">Sample</span></span>  
 <span data-ttu-id="1be69-185">Im folgenden Beispiel wird eine einfache Transformationskomponente mit synchronen Ausgaben gezeigt, die die Werte aller Zeichenfolgenzeilen in Großbuchstaben umwandelt.</span><span class="sxs-lookup"><span data-stu-id="1be69-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="1be69-186">In diesem Beispiel werden nicht alle Methoden und Funktionen dargestellt, die in diesem Thema erläutert wurden.</span><span class="sxs-lookup"><span data-stu-id="1be69-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="1be69-187">Es veranschaulicht die wichtigen Methoden, die jede benutzerdefinierte Transformationskomponente mit synchronen Ausgaben überschreiben muss, enthält jedoch keinen Code für eine Überprüfung zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="1be69-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="1be69-188">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="1be69-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1be69-189">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="1be69-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1be69-190">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="1be69-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1be69-191">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1be69-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be69-192">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1be69-192">See Also</span></span>  
 <span data-ttu-id="1be69-193">[Entwickeln einer benutzerdefinierten Transformations Komponente mit asynchronen Ausgaben](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="1be69-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="1be69-194">[Grundlegendes zu synchronen und asynchronen Transformationen](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1be69-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="1be69-195">Erstellen einer synchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="1be69-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
