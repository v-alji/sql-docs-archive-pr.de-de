---
title: Entwickeln einer benutzerdefinierten Zielkomponente | Microsoft-Dokumentation
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
- validation [Integration Services], components
- destinations [Integration Services], components
- ProcessInput method
- external data sources [Integration Services]
- custom data flow components [Integration Services], destination components
- data flow components [Integration Services], destination components
ms.assetid: 24619363-9535-4c0e-8b62-1d22c6630e40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6979d14afa0490638162c35bb660f15506803484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694657"
---
# <a name="developing-a-custom-destination-component"></a><span data-ttu-id="d14f4-102">Entwickeln einer benutzerdefinierten Zielkomponente</span><span class="sxs-lookup"><span data-stu-id="d14f4-102">Developing a Custom Destination Component</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d14f4-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] bietet Entwicklern die Möglichkeit, benutzerdefinierte Zielkomponenten zu schreiben, die eine Verbindung mit einer beliebigen benutzerdefinierten Datenquelle herstellen und Daten in dieser speichern können.</span><span class="sxs-lookup"><span data-stu-id="d14f4-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write custom destination components that can connect to and store data in any custom data source.</span></span> <span data-ttu-id="d14f4-104">Benutzerdefinierte Zielkomponenten sind hilfreich, wenn Sie Verbindungen zu Datenquellen herstellen müssen, auf die nicht über eine der vorhandenen Quellkomponenten, die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthalten sind, zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d14f4-104">Custom destination components are useful when you need to connect to data sources that cannot be accessed by using one of the existing source components included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="d14f4-105">Zielkomponenten verfügen über eine oder mehrere Eingaben und keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d14f4-105">Destination components have one or more inputs and zero outputs.</span></span> <span data-ttu-id="d14f4-106">Zur Entwurfszeit erstellen und konfigurieren sie Verbindungen und lesen Spaltenmetadaten aus der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="d14f4-106">At design time, they create and configure connections and read column metadata from the external data source.</span></span> <span data-ttu-id="d14f4-107">Während der Ausführung stellen sie eine Verbindung zu ihrer externen Datenquelle her und fügen Zeilen, die von den Komponenten upstream im Datenfluss empfangen wurden, zur externen Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="d14f4-107">During execution, they connect to their external data source and add rows that are received from the components upstream in the data flow to the external data source.</span></span> <span data-ttu-id="d14f4-108">Wenn die externe Datenquelle vor der Ausführung der Komponente besteht, dann muss die Zielkomponente außerdem sicherstellen, dass die Datentypen der Spalten, die die Komponente empfängt, zu den Datentypen der Spalten der externen Datenquelle passen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-108">If the external data source exists prior to execution of the component, the destination component must also ensure that the data types of the columns that the component receives match the data types of the columns at the external data source.</span></span>

 <span data-ttu-id="d14f4-109">In diesem Abschnitt wird im Detail auf die Entwicklung von Zielkomponenten eingegangen, und es werden zur Verdeutlichung wichtiger Konzepte Codebeispiele bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d14f4-109">This section discusses the details of how to develop destination components, and provides code examples to clarify important concepts.</span></span> <span data-ttu-id="d14f4-110">Einen allgemeinen Überblick über die Entwicklung von Datenflusskomponenten finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d14f4-110">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="d14f4-111">Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="d14f4-111">Design Time</span></span>
 <span data-ttu-id="d14f4-112">Zur Implementierung der Entwurfszeitfunktionen einer Zielkomponente müssen Sie eine Verbindung mit einer externen Datenquelle festlegen und überprüfen, ob die Komponente richtig konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d14f4-112">Implementing the design-time functionality of a destination component involves specifying a connection to an external data source and validating that the component has been correctly configured.</span></span> <span data-ttu-id="d14f4-113">Definitionsgemäß verfügt eine Zielkomponente über einen Eingang und möglicherweise eine Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="d14f4-113">By definition, a destination component has one input and possibly one error output.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="d14f4-114">Erstellen der Komponente</span><span class="sxs-lookup"><span data-stu-id="d14f4-114">Creating the Component</span></span>
 <span data-ttu-id="d14f4-115">Zielkomponenten stellen mithilfe von in einem Paket definierten <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekten eine Verbindung mit externen Datenquellen her.</span><span class="sxs-lookup"><span data-stu-id="d14f4-115">Destination components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="d14f4-116">Die Zielkomponente zeigt an, dass ein Verbindungs-Manager für den [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer und andere Benutzer der Komponente durch Hinzufügen eines Elements zur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>-Auflistung von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d14f4-116">The destination component indicates its requirement for a connection manager to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, and to users of the component, by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="d14f4-117">Diese Auflistung erfüllt zweierlei Zwecke: erstens zeigt sie dem [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer den Bedarf für einen Verbindungs-Manager an und zweitens enthält sie, nachdem der Benutzer einen Verbindungs-Manager ausgewählt oder erstellt hat, einen Verweis zum Verbindungs-Manager im Paket, das von der Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d14f4-117">This collection serves two purposes: first, it advertises the need for a connection manager to [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer; then, after the user has selected or created a connection manager, it holds a reference to the connection manager in the package that is being used by the component.</span></span> <span data-ttu-id="d14f4-118">Beim Hinzufügen eines <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100>-Typs zur Auflistung wird im **Erweiterten Editor** die Registerkarte **Verbindungseigenschaften** angezeigt, um den Benutzer aufzufordern, im Paket für die Komponente eine Verbindung auszuwählen oder zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-118">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> is added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, to prompt the user to select or create a connection in the package for use by the component.</span></span>

 <span data-ttu-id="d14f4-119">Im folgenden Codebeispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> gezeigt, die eine Eingabe und dann ein <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100>-Objekt zu <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d14f4-119">The following code sample shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an input, and then adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "Destination Component",ComponentType =ComponentType.DestinationAdapter)]
    public class DestinationComponent : PipelineComponent 
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSInput100 input = ComponentMetaData.InputCollection.New();
            input.Name = "Input";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.net";
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="Destination Component", ComponentType:=ComponentType.DestinationAdapter)> _
    Public Class DestinationComponent
        Inherits PipelineComponent

        Public Overrides Sub ProvideComponentProperties()

            ' Reset the component.
            Me.RemoveAllInputsOutputsAndCustomProperties()
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()
            input.Name = "Input"

            Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
            connection.Name = "ADO.net"

        End Sub
    End Class
End Namespace
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="d14f4-120">Herstellen einer Verbindung mit einer externen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d14f4-120">Connecting to an External Data Source</span></span>
 <span data-ttu-id="d14f4-121">Nachdem eine Verbindung zur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> hinzugefügt wurde, überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methode, um eine Verbindung mit der externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-121">After a connection is added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="d14f4-122">Diese Methode wird zur Entwurfs- und zur Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-122">This method is called at design time and at run time.</span></span> <span data-ttu-id="d14f4-123">Die Komponente muss eine Verbindung mit dem von der Laufzeitverbindung festgelegten Verbindungs-Manager und anschließend mit der externen Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-123">The component must establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span> <span data-ttu-id="d14f4-124">Sobald die Verbindung hergestellt ist, sollte sie von der Komponente intern zwischengespeichert und freigegeben werden, wenn <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d14f4-124">Once established, the component should cache the connection internally and release it when <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> is called.</span></span> <span data-ttu-id="d14f4-125">Entwickler überschreiben diese Methode und geben die Verbindung, die von der Komponente während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> hergestellt wurde, frei.</span><span class="sxs-lookup"><span data-stu-id="d14f4-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="d14f4-126">Die beiden Methoden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> werden zur Entwurfs- und zur Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-126">Both of these methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, are called at design time and at run time.</span></span>

 <span data-ttu-id="d14f4-127">Im folgenden Codebeispiel wird eine Komponente gezeigt, die in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methode eine Verbindung mit einer ADO.NET-Verbindung herstellt und die Verbindung dann in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> beendet.</span><span class="sxs-lookup"><span data-stu-id="d14f4-127">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method, and then closes the connection in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) = False Then

        Dim cm As ConnectionManager = DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject,ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If IsNothing(sqlConnection) = False And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="d14f4-128">Überprüfen der Komponente</span><span class="sxs-lookup"><span data-stu-id="d14f4-128">Validating the Component</span></span>
 <span data-ttu-id="d14f4-129">Zielkomponentenentwickler sollten Überprüfungen wie in [Überprüfen einer Datenflusskomponente](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md) beschrieben ausführen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-129">Destination component developers should perform validation as described in [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span> <span data-ttu-id="d14f4-130">Darüber hinaus sollten sie überprüfen, ob die Datentypeigenschaften der in den Eingabespaltenauflistungen der Komponente definierten Spalten denjenigen bei der externen Datenquelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-130">In addition, they should verify that the data type properties of the columns defined in the component's input column collection match the columns at the external data source.</span></span> <span data-ttu-id="d14f4-131">Manchmal ist der Abgleich der Eingabespalten mit der externen Datenquelle nicht möglich oder unerwünscht, z. B. wenn die Komponente oder der [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer sich im Offline-Zustand befinden oder Roundtrips zum Server nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d14f4-131">At times, verifying the input columns against the external data source can be impossible or undesirable, such as when the component or the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is in a disconnected state, or when round trips to the server are not acceptable.</span></span> <span data-ttu-id="d14f4-132">In solchen Fällen können die Spalten in der Eingabespaltenauflistung dennoch mithilfe von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> des Eingabeobjekts überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="d14f4-132">In these situations, the columns in the input column collection can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> of the input object.</span></span>

 <span data-ttu-id="d14f4-133">Diese Auflistung ist sowohl für Eingabe- als auch für Ausgabeobjekte vorhanden und muss vom Komponentenentwickler mit den Spalten der externen Datenquelle gefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="d14f4-133">This collection exists on both input and output objects and must be populated by the component developer from the columns at the external data source.</span></span> <span data-ttu-id="d14f4-134">Mithilfe dieser Auflistung können die Eingabespalten überprüft werden, wenn der [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer offline ist, die Verbindung mit der Komponente getrennt ist oder wenn die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A>-Eigenschaft `false` lautet.</span><span class="sxs-lookup"><span data-stu-id="d14f4-134">This collection can be used to validate the input columns when the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>

 <span data-ttu-id="d14f4-135">Im folgenden Beispielcode wird eine externe Metadatenspalte auf Grundlage einer vorhandenen Eingabespalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d14f4-135">The following sample code adds an external metadata column based on an existing input column.</span></span>

```csharp
private void AddExternalMetaDataColumn(IDTSInput100 input,IDTSInputColumn100 inputColumn)
{
    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = input.ExternalMetadataColumnCollection.New();
    externalColumn.Name = inputColumn.Name;
    externalColumn.Precision = inputColumn.Precision;
    externalColumn.Length = inputColumn.Length;
    externalColumn.DataType = inputColumn.DataType;
    externalColumn.Scale = inputColumn.Scale;

    // Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID;
}
```

```vb
Private Sub AddExternalMetaDataColumn(ByVal input As IDTSInput100, ByVal inputColumn As IDTSInputColumn100)

    ' Set the properties of the external metadata column.
    Dim externalColumn As IDTSExternalMetadataColumn100 = input.ExternalMetadataColumnCollection.New()
    externalColumn.Name = inputColumn.Name
    externalColumn.Precision = inputColumn.Precision
    externalColumn.Length = inputColumn.Length
    externalColumn.DataType = inputColumn.DataType
    externalColumn.Scale = inputColumn.Scale

    ' Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID

End Sub
```

## <a name="run-time"></a><span data-ttu-id="d14f4-136">Runtime</span><span class="sxs-lookup"><span data-stu-id="d14f4-136">Run Time</span></span>
 <span data-ttu-id="d14f4-137">Während der Ausführung wird die Zielkomponente jedes Mal bei der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode aufgerufen, wenn eine voller <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> von der Upstreamkomponente verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d14f4-137">During execution, the destination component receives a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method each time a full <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> is available from the upstream component.</span></span> <span data-ttu-id="d14f4-138">Diese Methode wird immer wieder aufgerufen, bis keine Puffer mehr verfügbar sind und die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>-Eigenschaft `true` ist.</span><span class="sxs-lookup"><span data-stu-id="d14f4-138">This method is called repeatedly until there are no more buffers available and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="d14f4-139">Bei dieser Methode lesen Zielkomponenten die Spalten und Zeilen im Puffer und fügen sie zur externen Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="d14f4-139">During this method, destination components read columns and rows in the buffer, and add them to the external data source.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="d14f4-140">Suchen von Spalten im Puffer</span><span class="sxs-lookup"><span data-stu-id="d14f4-140">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="d14f4-141">Der Eingabepuffer für eine Komponente enthält alle der in den Ausgabespaltenauflistungen der Komponenten upstream von der Komponente im Datenfluss definierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="d14f4-141">The input buffer for a component contains all the columns defined in the output column collections of the components upstream from the component in the data flow.</span></span> <span data-ttu-id="d14f4-142">Falls beispielsweise eine Quellkomponente drei Spalten in ihrer Ausgabe bereitstellt und die nächste Komponente eine weitere Ausgabespalte hinzufügt, enthält der Puffer, der für die Zielkomponente bereitgestellt wird, vier Spalten, selbst wenn die Zielkomponente nur zwei Spalten schreibt.</span><span class="sxs-lookup"><span data-stu-id="d14f4-142">For example, if a source component provides three columns in its output, and the next component adds an additional output column, the buffer provided to the destination component contains four columns, even if the destination component will write only two columns.</span></span>

 <span data-ttu-id="d14f4-143">Die Reihenfolge der Spalten im Eingabepuffer wird nicht vom Index der Spalte in der Eingabespaltenauflistung der Zielkomponente definiert.</span><span class="sxs-lookup"><span data-stu-id="d14f4-143">The order of the columns in the input buffer is not defined by the index of the column in the input column collection of the destination component.</span></span> <span data-ttu-id="d14f4-144">Die genaue Position von Spalten in einer Pufferzeile kann nur mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>-Methode des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="d14f4-144">Columns can be reliably located in a buffer row only by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="d14f4-145">Diese Methode sucht die Spalte anhand der angegebenen Herkunfts-ID im jeweiligen Puffer und gibt ihre Position in der Zeile zurück.</span><span class="sxs-lookup"><span data-stu-id="d14f4-145">This method locates the column that has the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="d14f4-146">Die Indizes der Eingabespalten werden in der Regel während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode gesucht und vom Entwickler für die spätere Verwendung während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="d14f4-146">The indexes of the input columns are typically located during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and cached by the developer for use later during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>

 <span data-ttu-id="d14f4-147">Im folgenden Codebeispiel wird die Position der Eingabespalten im Puffer während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> bestimmt und speichert diese in einem Array.</span><span class="sxs-lookup"><span data-stu-id="d14f4-147">The following code example finds the location of the input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> and stores them in an array.</span></span> <span data-ttu-id="d14f4-148">Das Array wird anschließend während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> verwendet, um die Werte der Spalten im Puffer zu lesen.</span><span class="sxs-lookup"><span data-stu-id="d14f4-148">The array is subsequently used during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> to read the values of the columns in the buffer.</span></span>

```csharp
int[] cols;

public override void PreExecute()
{
    IDTSInput100 input = ComponentMetaData.InputCollection[0];

    cols = new int[input.InputColumnCollection.Count];

    for (int x = 0; x < input.InputColumnCollection.Count; x++)
    {
        cols[x] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[x].LineageID);
    }
}
```

```vb
Private cols As Integer()

Public Overrides Sub PreExecute()

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)

    ReDim cols(input.InputColumnCollection.Count)

    For x As Integer = 0 To input.InputColumnCollection.Count

        cols(x) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(x).LineageID)
    Next x

End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="d14f4-149">Verarbeiten von Zeilen</span><span class="sxs-lookup"><span data-stu-id="d14f4-149">Processing Rows</span></span>
 <span data-ttu-id="d14f4-150">Sobald die Position der Eingabespalten im Puffer bestimmt wurde, können diese gelesen und in die externe Datanquelle geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d14f4-150">Once the input columns have been located in the buffer, they can be read and written to the external data source.</span></span>

 <span data-ttu-id="d14f4-151">Während die Zielkomponente Zeilen in die externe Datenquelle schreibt, sollten Sie die Leistungsindikatoren "Gelesene Zeilen" oder "Gelesene BLOB-Bytes" durch Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>-Methode aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d14f4-151">While the destination component writes rows to the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="d14f4-152">Weitere Informationen finden Sie unter [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d14f4-152">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="d14f4-153">Im folgenden Beispiel wird eine Komponente dargestellt, die Zeilen aus dem in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> bereitgestellten Puffer liest.</span><span class="sxs-lookup"><span data-stu-id="d14f4-153">The following example shows a component that reads rows from the buffer provided in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="d14f4-154">Die Positionen der Indizes der Spalten im Puffer wurden während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> im vorangehenden Codebeispiel bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d14f4-154">The indexes of the columns in the buffer were located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the preceding code example.</span></span>

```csharp
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
        while (buffer.NextRow())
        {
            foreach (int col in cols)
            {
                if (!buffer.IsNull(col))
                {
                    //  TODO: Read the column data.
                }
            }
        }
}
```

```vb
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

        While (buffer.NextRow())

            For Each col As Integer In cols

                If buffer.IsNull(col) = False Then

                    '  TODO: Read the column data.
                End If

            Next col
        End While
End Sub
```

## <a name="sample"></a><span data-ttu-id="d14f4-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d14f4-155">Sample</span></span>
 <span data-ttu-id="d14f4-156">Das folgende Beispiel zeigt eine einfache Zielkomponente, die über einen Dateiverbindungs-Manager binäre Daten aus dem Datenfluss in Dateien speichert.</span><span class="sxs-lookup"><span data-stu-id="d14f4-156">The following sample shows a simple destination component that uses a File connection manager to save binary data from the data flow into files.</span></span> <span data-ttu-id="d14f4-157">In diesem Beispiel werden nicht alle Methoden und Funktionen dargestellt, die in diesem Thema erläutert wurden.</span><span class="sxs-lookup"><span data-stu-id="d14f4-157">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="d14f4-158">Es veranschaulicht die Hauptmethoden, die jede benutzerdefinierte Zielkomponente überschreiben muss, enthält jedoch keinen Code für eine Überprüfung zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="d14f4-158">It demonstrates the important methods that every custom destination component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace BlobDst
{
  [DtsPipelineComponent(DisplayName = "BLOB Extractor Destination", Description = "Writes values of BLOB columns to files")]
  public class BlobDst : PipelineComponent
  {
    string m_DestDir;
    int m_FileNameColumnIndex = -1;
    int m_BlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection.New();
      input.Name = "BLOB Extractor Destination Input";
      input.HasSideEffects = true;

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_DestDir = (string)conn.ConnectionManager.AcquireConnection(null);

      if (m_DestDir.Length > 0 && m_DestDir[m_DestDir.Length - 1] != '\\')
        m_DestDir += "\\";
    }

    public override IDTSInputColumn100 SetUsageType(int inputID, IDTSVirtualInput100 virtualInput, int lineageID, DTSUsageType usageType)
    {
      IDTSInputColumn100 inputColumn = base.SetUsageType(inputID, virtualInput, lineageID, usageType);
      IDTSCustomProperty100 custProp;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsFileName";
      custProp.Value = (object)false;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsBLOB";
      custProp.Value = (object)false;

      return inputColumn;
    }

    public override void PreExecute()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection[0];
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;
      IDTSCustomProperty100 custProp;

      foreach (IDTSInputColumn100 column in inputColumns)
      {
        custProp = column.CustomPropertyCollection["IsFileName"];
        if ((bool)custProp.Value == true)
        {
          m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }

        custProp = column.CustomPropertyCollection["IsBLOB"];
        if ((bool)custProp.Value == true)
        {
          m_BlobColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }
      }
    }

    public override void ProcessInput(int inputID, PipelineBuffer buffer)
    {
      while (buffer.NextRow())
      {
        string strFileName = buffer.GetString(m_FileNameColumnIndex);
        int blobLength = (int)buffer.GetBlobLength(m_BlobColumnIndex);
        byte[] blobData = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength);

        strFileName = TranslateFileName(strFileName);

        // Make sure directory exists before creating file.
        FileInfo fi = new FileInfo(strFileName);
        if (!fi.Directory.Exists)
          fi.Directory.Create();

        // Write the data to the file.
        FileStream fs = new FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None);
        fs.Write(blobData, 0, blobLength);
        fs.Close();
      }
    }

    private string TranslateFileName(string fileName)
    {
      if (fileName.Length > 2 && fileName[1] == ':')
        return m_DestDir + fileName.Substring(3, fileName.Length - 3);
      else
        return m_DestDir + fileName;
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Namespace BlobDst 

 <DtsPipelineComponent(DisplayName="BLOB Extractor Destination", Description="Writes values of BLOB columns to files")> _ 
 Public Class BlobDst 
 Inherits PipelineComponent 
   Private m_DestDir As String 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_BlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New 
     input.Name = "BLOB Extractor Destination Input" 
     input.HasSideEffects = True 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_DestDir = CType(conn.ConnectionManager.AcquireConnection(Nothing), String) 
     If m_DestDir.Length > 0 AndAlso Not (m_DestDir(m_DestDir.Length - 1) = "\"C) Then 
       m_DestDir += "\" 
     End If 
   End Sub 

   Public  Overrides Function SetUsageType(ByVal inputID As Integer, ByVal virtualInput As IDTSVirtualInput100, ByVal lineageID As Integer, ByVal usageType As DTSUsageType) As IDTSInputColumn100 
     Dim inputColumn As IDTSInputColumn100 = MyBase.SetUsageType(inputID, virtualInput, lineageID, usageType) 
     Dim custProp As IDTSCustomProperty100 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsFileName" 
     custProp.Value = CType(False, Object) 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsBLOB" 
     custProp.Value = CType(False, Object) 
     Return inputColumn 
   End Function 

   Public  Overrides Sub PreExecute() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0) 
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection 
     Dim custProp As IDTSCustomProperty100 
     For Each column As IDTSInputColumn100 In inputColumns 
       custProp = column.CustomPropertyCollection("IsFileName") 
       If CType(custProp.Value, Boolean) = True Then 
         m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
       custProp = column.CustomPropertyCollection("IsBLOB") 
       If CType(custProp.Value, Boolean) = True Then 
         m_BlobColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
     Next 
   End Sub 

   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
     While buffer.NextRow 
       Dim strFileName As String = buffer.GetString(m_FileNameColumnIndex) 
       Dim blobLength As Integer = CType(buffer.GetBlobLength(m_BlobColumnIndex), Integer) 
       Dim blobData As Byte() = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength) 
       strFileName = TranslateFileName(strFileName) 
       Dim fi As FileInfo = New FileInfo(strFileName) 
       ' Make sure directory exists before creating file.
       If Not fi.Directory.Exists Then 
         fi.Directory.Create 
       End If 
       ' Write the data to the file.
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None) 
       fs.Write(blobData, 0, blobLength) 
       fs.Close 
     End While 
   End Sub 

   Private Function TranslateFileName(ByVal fileName As String) As String 
     If fileName.Length > 2 AndAlso fileName(1) = ":"C Then 
       Return m_DestDir + fileName.Substring(3, fileName.Length - 3) 
     Else 
       Return m_DestDir + fileName 
     End If 
   End Function 
 End Class 
End Namespace
```

<span data-ttu-id="d14f4-159">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d14f4-159">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d14f4-160">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d14f4-160">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d14f4-161">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d14f4-161">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d14f4-162">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d14f4-162">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d14f4-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d14f4-163">See Also</span></span>
 <span data-ttu-id="d14f4-164">[Entwickeln einer benutzerdefinierten Quell Komponente](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Erstellen eines Ziels mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="d14f4-164">[Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span></span>


