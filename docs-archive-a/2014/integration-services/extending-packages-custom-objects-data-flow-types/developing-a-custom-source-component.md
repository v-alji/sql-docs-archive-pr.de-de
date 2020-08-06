---
title: Entwickeln einer benutzerdefinierten Quellkomponente | Microsoft-Dokumentation
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
- validation [Integration Services], components
- external data sources [Integration Services]
- data flow components [Integration Services], source components
- output columns [Integration Services]
- custom data flow components [Integration Services], source components
- custom sources [Integration Services]
- source components [Integration Services]
ms.assetid: 4dc0f631-8fd6-4007-b573-ca67f58ca068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6679b28463a09efe069235a5aef9dca54a381d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721642"
---
# <a name="developing-a-custom-source-component"></a><span data-ttu-id="178fe-102">Entwickeln einer benutzerdefinierten Quellkomponente</span><span class="sxs-lookup"><span data-stu-id="178fe-102">Developing a Custom Source Component</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="178fe-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ermöglicht es Entwicklern, in Quellkomponenten zu schreiben, die Verbindungen mit benutzerdefinierten Datenquellen herstellen und anderen Komponenten im Datenflusstask Daten aus diesen Quellen zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="178fe-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write source components that can connect to custom data sources and supply data from those sources to other components in a data flow task.</span></span> <span data-ttu-id="178fe-104">Die Möglichkeit, benutzerdefinierte Quellen zu erstellen, ist hilfreich, wenn Sie Verbindungen zu Datenquellen herstellen müssen, auf die Sie über keine der bestehenden [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Quellen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="178fe-104">The ability to create custom sources is valuable when you must connect to data sources that cannot be accessed by using one of the existing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources.</span></span>

 <span data-ttu-id="178fe-105">Quellkomponenten verfügen über eine oder mehrere Ausgaben und keine Eingabe.</span><span class="sxs-lookup"><span data-stu-id="178fe-105">Source components have one or more outputs and zero inputs.</span></span> <span data-ttu-id="178fe-106">Zur Entwurfszeit dienen Quellkomponenten zur Erstellung und Konfiguration von Verbindungen, zum Lesen von Spaltenmetadaten aus der externen Datenquelle und zur Konfiguration der Ausgabespalten der Quelle basierend auf der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="178fe-106">At design time, source components are used to create and configure connections, read column metadata from the external data source, and configure the source's output columns based on the external data source.</span></span> <span data-ttu-id="178fe-107">Während der Ausführung stellen sie eine Verbindung mit der externen Datenquelle her und fügen einem Ausgabepuffer Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="178fe-107">During execution they connect to the external data source and add rows to an output buffer.</span></span> <span data-ttu-id="178fe-108">Der Datenflusstask stellt dann Downstreamkomponenten diesen Puffer mit Datenzeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="178fe-108">The data flow task then provides this buffer of data rows to downstream components.</span></span>

 <span data-ttu-id="178fe-109">Einen allgemeinen Überblick über die Entwicklung von Datenflusskomponenten finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="178fe-109">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="178fe-110">Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="178fe-110">Design Time</span></span>
 <span data-ttu-id="178fe-111">Zur Implementierung der Entwurfszeitfunktionen einer Quellkomponente müssen Sie eine Verbindung mit einer externen Datenquelle festlegen, der Datenquelle entsprechende Ausgabespalten hinzufügen und konfigurieren sowie überprüfen, ob die Komponente zur Ausführung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="178fe-111">Implementing the design-time functionality of a source component involves specifying a connection to an external data source, adding and configuring output columns that reflect the data source, and validating that the component is ready to execute.</span></span> <span data-ttu-id="178fe-112">Definitionsgemäß verfügt eine Quellkomponente über keine Eingabe und eine oder mehrere asynchrone Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="178fe-112">By definition, a source component has zero inputs and one or more asynchronous outputs.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="178fe-113">Erstellen der Komponente</span><span class="sxs-lookup"><span data-stu-id="178fe-113">Creating the Component</span></span>
 <span data-ttu-id="178fe-114">Quellkomponenten stellen mithilfe in einem Paket definierter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekte eine Verbindung mit externen Datenquellen her.</span><span class="sxs-lookup"><span data-stu-id="178fe-114">Source components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="178fe-115">Um auf die Notwendigkeit eines Verbindungs-Managers zu verweisen, wird der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>-Auflistung der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>-Eigenschaft ein Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="178fe-115">They indicate their requirement for a connection manager by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="178fe-116">Diese Sammlung erfüllt zweierlei Zwecke: Sie enthält Verweise auf Verbindungs-Manager im Paket, die von der Komponente genutzt werden, und zeigt dem Designer den Bedarf für einen Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="178fe-116">This collection serves two purposes-to hold references to connection managers in the package used by the component, and to advertise the need for a connection manager to the designer.</span></span> <span data-ttu-id="178fe-117">Beim Hinzufügen eines <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100>-Typs zur Auflistung wird im **Erweiterten Editor** die Registerkarte **Verbindungseigenschaften** angezeigt, um den Benutzer aufzufordern, im Paket eine Verbindung auszuwählen oder zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="178fe-117">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> has been added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, which lets users select or create a connection in the package.</span></span>

 <span data-ttu-id="178fe-118">Im folgenden Codebeispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> gezeigt, die eine Ausgabe sowie ein <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100>-Objekt zur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="178fe-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an output, and adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using System.Collections;
using System.Data;
using System.Data.SqlClient;
using System.Data.OleDb;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "MySourceComponent",ComponentType = ComponentType.SourceAdapter)]
    public class MyComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
            output.Name = "Output";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.NET";
        }
```

```vb
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Runtime
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper

<DtsPipelineComponent(DisplayName:="MySourceComponent", ComponentType:=ComponentType.SourceAdapter)> _
Public Class MySourceComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Allow for resetting the component.
        RemoveAllInputsOutputsAndCustomProperties()
        ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()
        output.Name = "Output"

        Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
        connection.Name = "ADO.NET"

    End Sub
End Class
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="178fe-119">Herstellen einer Verbindung mit einer externen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="178fe-119">Connecting to an External Data Source</span></span>
 <span data-ttu-id="178fe-120">Nachdem eine Verbindung zur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> hinzugefügt wurde, überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methode, um eine Verbindung mit der externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="178fe-120">After a connection has been added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="178fe-121">Diese Methode wird sowohl zur Entwurfs- als auch zur Ausführungszeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="178fe-121">This method is called during both design and execution time.</span></span> <span data-ttu-id="178fe-122">Die Komponente sollte eine Verbindung mit dem von der Laufzeitverbindung festgelegten Verbindungs-Manager und anschließend mit der externen Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="178fe-122">The component should establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span>

 <span data-ttu-id="178fe-123">Nachdem die Verbindung hergestellt ist, sollte sie von der Komponente intern zwischengespeichert und freigegeben werden, wenn die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="178fe-123">After the connection is established, it should be cached internally by the component and released when the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called.</span></span> <span data-ttu-id="178fe-124">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>-Methode wird zur Entwurfs- und Ausführungszeit ebenso aufgerufen wie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="178fe-124">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called at design and execution time, like the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method.</span></span> <span data-ttu-id="178fe-125">Entwickler überschreiben diese Methode und geben die Verbindung, die von der Komponente während <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> hergestellt wurde, frei.</span><span class="sxs-lookup"><span data-stu-id="178fe-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span>

 <span data-ttu-id="178fe-126">Im folgenden Codebeispiel wird eine Komponente gezeigt, die in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methode eine Verbindung mit einer ADO.NET-Verbindung herstellt und die Verbindung in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>-Methode beendet.</span><span class="sxs-lookup"><span data-stu-id="178fe-126">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method and closes the connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method.</span></span>

```csharp
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
Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If Not IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) Then

        Dim cm As ConnectionManager = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject, ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If Not IsNothing(sqlConnection) And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="178fe-127">Erstellen und Konfigurieren von Ausgabespalten</span><span class="sxs-lookup"><span data-stu-id="178fe-127">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="178fe-128">Die Ausgabespalten einer Quellkomponente spiegeln die Spalten der externen Datenquelle, welche die Komponente bei der Ausführung dem Datenfluss hinzufügt, wider.</span><span class="sxs-lookup"><span data-stu-id="178fe-128">The output columns of a source component reflect the columns from the external data source that the component adds to the data flow during execution.</span></span> <span data-ttu-id="178fe-129">Zur Entwurfszeit fügen Sie, nachdem eine Verbindung der Komponente mit einer externen Datenquelle konfiguriert wurde, Ausgabespalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="178fe-129">At design time, you add output columns after the component has been configured to connect to an external data source.</span></span> <span data-ttu-id="178fe-130">Die Methode, die eine Komponente zur Entwurfszeit zum Hinzufügen der Spalten zu ihrer output-Auflistung verwendet, kann abhängig von den Anforderungen der Komponente variieren. Sie sollten jedoch nicht während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>- oder <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>-Methoden hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-130">The design-time method that a component uses to add the columns to its output collection can vary based on the needs of the component, although they should not be added during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="178fe-131">Eine Komponente, die beispielsweise eine SQL-Anweisung in einer benutzerdefinierten Eigenschaft zur Kontrolle des Datasets der Komponente enthält, könnte ihre Ausgabespalten während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A>-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="178fe-131">For example, a component that contains a SQL statement in a custom property that controls the data set for the component may add its output columns during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A> method.</span></span> <span data-ttu-id="178fe-132">Die Komponente prüft, ob sie über eine zwischengespeicherte Verbindung verfügt. Falls dies der Fall ist, stellt sie eine Verbindung mit der Datenquelle her und erstellt die Ausgabespalten.</span><span class="sxs-lookup"><span data-stu-id="178fe-132">The component checks to see whether it has a cached connection, and, if it does, connects to the data source and generates its output columns.</span></span>

 <span data-ttu-id="178fe-133">Nachdem eine Ausgabespalte erstellt wurde, legen Sie ihre Datentypeigenschaften fest, indem Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="178fe-133">After an output column has been created, set its data type properties by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="178fe-134">Diese Methode ist erforderlich, da die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>-, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>-, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>- und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A>-Eigenschaften schreibgeschützt sind und jede Eigenschaft von den Einstellungen der anderen abhängt.</span><span class="sxs-lookup"><span data-stu-id="178fe-134">This method is necessary because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are read-only and each property is dependent on the settings of the other.</span></span> <span data-ttu-id="178fe-135">Diese Methode erzwingt eine konsistente Festlegung der Werte, die anschließend durch den Datenflusstask geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="178fe-135">This method enforces the need for these values to be set consistently, and the data flow task validates that they are set correctly.</span></span>

 <span data-ttu-id="178fe-136">Der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> der Spalte bestimmt die Werte, die für die anderen Eigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="178fe-137">Die folgende Tabelle zeigt die Anforderungen an die abhängigen Eigenschaften für jeden <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="178fe-137">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="178fe-138">Bei den nicht aufgelisteten Datentypen sind die abhängigen Eigenschaften auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="178fe-138">The data types not listed have their dependent properties set to zero.</span></span>

|<span data-ttu-id="178fe-139">DataType</span><span class="sxs-lookup"><span data-stu-id="178fe-139">DataType</span></span>|<span data-ttu-id="178fe-140">Länge</span><span class="sxs-lookup"><span data-stu-id="178fe-140">Length</span></span>|<span data-ttu-id="178fe-141">Skalieren</span><span class="sxs-lookup"><span data-stu-id="178fe-141">Scale</span></span>|<span data-ttu-id="178fe-142">Precision</span><span class="sxs-lookup"><span data-stu-id="178fe-142">Precision</span></span>|<span data-ttu-id="178fe-143">CodePage</span><span class="sxs-lookup"><span data-stu-id="178fe-143">CodePage</span></span>|
|--------------|------------|-----------|---------------|--------------|
|<span data-ttu-id="178fe-144">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="178fe-144">DT_DECIMAL</span></span>|<span data-ttu-id="178fe-145">0</span><span class="sxs-lookup"><span data-stu-id="178fe-145">0</span></span>|<span data-ttu-id="178fe-146">Größer 0 und kleiner oder gleich 28</span><span class="sxs-lookup"><span data-stu-id="178fe-146">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="178fe-147">0</span><span class="sxs-lookup"><span data-stu-id="178fe-147">0</span></span>|<span data-ttu-id="178fe-148">0</span><span class="sxs-lookup"><span data-stu-id="178fe-148">0</span></span>|
|<span data-ttu-id="178fe-149">DT_CY</span><span class="sxs-lookup"><span data-stu-id="178fe-149">DT_CY</span></span>|<span data-ttu-id="178fe-150">0</span><span class="sxs-lookup"><span data-stu-id="178fe-150">0</span></span>|<span data-ttu-id="178fe-151">0</span><span class="sxs-lookup"><span data-stu-id="178fe-151">0</span></span>|<span data-ttu-id="178fe-152">0</span><span class="sxs-lookup"><span data-stu-id="178fe-152">0</span></span>|<span data-ttu-id="178fe-153">0</span><span class="sxs-lookup"><span data-stu-id="178fe-153">0</span></span>|
|<span data-ttu-id="178fe-154">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="178fe-154">DT_NUMERIC</span></span>|<span data-ttu-id="178fe-155">0</span><span class="sxs-lookup"><span data-stu-id="178fe-155">0</span></span>|<span data-ttu-id="178fe-156">Größer 0 und kleiner oder gleich 28 sowie kleiner als Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="178fe-156">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="178fe-157">Größer oder gleich 1 und kleiner oder gleich 38</span><span class="sxs-lookup"><span data-stu-id="178fe-157">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="178fe-158">0</span><span class="sxs-lookup"><span data-stu-id="178fe-158">0</span></span>|
|<span data-ttu-id="178fe-159">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="178fe-159">DT_BYTES</span></span>|<span data-ttu-id="178fe-160">Größer 0</span><span class="sxs-lookup"><span data-stu-id="178fe-160">Greater than 0.</span></span>|<span data-ttu-id="178fe-161">0</span><span class="sxs-lookup"><span data-stu-id="178fe-161">0</span></span>|<span data-ttu-id="178fe-162">0</span><span class="sxs-lookup"><span data-stu-id="178fe-162">0</span></span>|<span data-ttu-id="178fe-163">0</span><span class="sxs-lookup"><span data-stu-id="178fe-163">0</span></span>|
|<span data-ttu-id="178fe-164">DT_STR</span><span class="sxs-lookup"><span data-stu-id="178fe-164">DT_STR</span></span>|<span data-ttu-id="178fe-165">Größer als 0 und kleiner als 8000</span><span class="sxs-lookup"><span data-stu-id="178fe-165">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="178fe-166">0</span><span class="sxs-lookup"><span data-stu-id="178fe-166">0</span></span>|<span data-ttu-id="178fe-167">0</span><span class="sxs-lookup"><span data-stu-id="178fe-167">0</span></span>|<span data-ttu-id="178fe-168">Nicht 0 und eine gültige Codepage</span><span class="sxs-lookup"><span data-stu-id="178fe-168">Not 0, and a valid code page.</span></span>|
|<span data-ttu-id="178fe-169">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="178fe-169">DT_WSTR</span></span>|<span data-ttu-id="178fe-170">Größer 0 und kleiner 4000</span><span class="sxs-lookup"><span data-stu-id="178fe-170">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="178fe-171">0</span><span class="sxs-lookup"><span data-stu-id="178fe-171">0</span></span>|<span data-ttu-id="178fe-172">0</span><span class="sxs-lookup"><span data-stu-id="178fe-172">0</span></span>|<span data-ttu-id="178fe-173">0</span><span class="sxs-lookup"><span data-stu-id="178fe-173">0</span></span>|

 <span data-ttu-id="178fe-174">Da die Beschränkungen der Datentypeigenschaften vom Datentyp der Ausgabespalte abhängen, müssen Sie bei der Arbeit mit verwalteten Typen den richtigen [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Datentyp wählen.</span><span class="sxs-lookup"><span data-stu-id="178fe-174">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="178fe-175">Die Basisklasse stellt drei Hilfsmethoden, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, die Entwickler verwalteter Komponenten bei der Auswahl eines [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Datentyps für einen verwalteten Typ unterstützen.</span><span class="sxs-lookup"><span data-stu-id="178fe-175">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, to assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="178fe-176">Diese Methoden wandeln verwaltete Datentypen in [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Datentypen um und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="178fe-176">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>

 <span data-ttu-id="178fe-177">Im folgenden Codebeispiel wird gezeigt, wie die Ausgabenspaltenauflistung einer Komponente basierend auf einem Tabellenschema aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="178fe-177">The following code example shows how the output column collection of a component is populated based on the schema of a table.</span></span> <span data-ttu-id="178fe-178">Die Hilfsmethoden der Basisklasse dienen dazu, den Datentyp der Spalte festzulegen, und die abhängigen Eigenschaften werden basierend auf dem Datentyp festgelegt.</span><span class="sxs-lookup"><span data-stu-id="178fe-178">The helper methods of the base class are used to set the data type of the column, and the dependent properties are set based on the data type.</span></span>

```csharp
SqlCommand sqlCommand;

private void CreateColumnsFromDataTable()
{
    // Get the output.
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    // Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll();
    output.ExternalMetadataColumnCollection.RemoveAll();

    this.sqlCommand = sqlConnection.CreateCommand();
    this.sqlCommand.CommandType = CommandType.Text;
    this.sqlCommand.CommandText = (string)ComponentMetaData.CustomPropertyCollection["SqlStatement"].Value;
    SqlDataReader schemaReader = this.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly);
    DataTable dataTable = schemaReader.GetSchemaTable();

    // Walk the columns in the schema, 
    // and for each data column create an output column and an external metadata column.
    foreach (DataRow row in dataTable.Rows)
    {
        IDTSOutputColumn100 outColumn = output.OutputColumnCollection.New();
        IDTSExternalMetadataColumn100 exColumn = output.ExternalMetadataColumnCollection.New();

        // Set column data type properties.
        bool isLong = false;
        DataType dt = DataRecordTypeToBufferType((Type)row["DataType"]);
        dt = ConvertBufferDataTypeToFitManaged(dt, ref isLong);
        int length = 0;
        int precision = (short)row["NumericPrecision"];
        int scale = (short)row["NumericScale"];
        int codepage = dataTable.Locale.TextInfo.ANSICodePage;

        switch (dt)
        {
            // The length cannot be zero, and the code page property must contain a valid code page.
            case DataType.DT_STR:
            case DataType.DT_TEXT:
                length = precision;
                precision = 0;
                scale = 0;
                break;

            case DataType.DT_WSTR:
                length = precision;
                codepage = 0;
                scale = 0;
                precision = 0;
                break;

            case DataType.DT_BYTES:
                precision = 0;
                scale = 0;
                codepage = 0;
                break;

            case DataType.DT_NUMERIC:
                length = 0;
                codepage = 0;

                if (precision > 38)
                    precision = 38;

                if (scale > 6)
                    scale = 6;
                break;

            case DataType.DT_DECIMAL:
                length = 0;
                precision = 0;
                codepage = 0;
                break;

            default:
                length = 0;
                precision = 0;
                codepage = 0;
                scale = 0;
                break;

        }

        // Set the properties of the output column.
        outColumn.Name = (string)row["ColumnName"];
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage);
    }
}
```

```vb
Private sqlCommand As SqlCommand

Private Sub CreateColumnsFromDataTable()

    ' Get the output.
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    ' Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll()
    output.ExternalMetadataColumnCollection.RemoveAll()

    Me.sqlCommand = sqlConnection.CreateCommand()
    Me.sqlCommand.CommandType = CommandType.Text
    Me.sqlCommand.CommandText = CStr(ComponentMetaData.CustomPropertyCollection("SqlStatement").Value)

    Dim schemaReader As SqlDataReader = Me.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly)
    Dim dataTable As DataTable = schemaReader.GetSchemaTable()

    ' Walk the columns in the schema, 
    ' and for each data column create an output column and an external metadata column.
    For Each row As DataRow In dataTable.Rows

        Dim outColumn As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        Dim exColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()

        ' Set column data type properties.
        Dim isLong As Boolean = False
        Dim dt As DataType = DataRecordTypeToBufferType(CType(row("DataType"), Type))
        dt = ConvertBufferDataTypeToFitManaged(dt, isLong)
        Dim length As Integer = 0
        Dim precision As Integer = CType(row("NumericPrecision"), Short)
        Dim scale As Integer = CType(row("NumericScale"), Short)
        Dim codepage As Integer = dataTable.Locale.TextInfo.ANSICodePage

        Select Case dt

            ' The length cannot be zero, and the code page property must contain a valid code page.
            Case DataType.DT_STR
            Case DataType.DT_TEXT
                length = precision
                precision = 0
                scale = 0

            Case DataType.DT_WSTR
                length = precision
                codepage = 0
                scale = 0
                precision = 0

            Case DataType.DT_BYTES
                precision = 0
                scale = 0
                codepage = 0

            Case DataType.DT_NUMERIC
                length = 0
                codepage = 0

                If precision > 38 Then
                    precision = 38
                End If

                If scale > 6 Then
                    scale = 6
                End If

            Case DataType.DT_DECIMAL
                length = 0
                precision = 0
                codepage = 0

            Case Else
                length = 0
                precision = 0
                codepage = 0
                scale = 0
        End Select

        ' Set the properties of the output column.
        outColumn.Name = CStr(row("ColumnName"))
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage)
    Next
End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="178fe-179">Überprüfen der Komponente</span><span class="sxs-lookup"><span data-stu-id="178fe-179">Validating the Component</span></span>
 <span data-ttu-id="178fe-180">Sie sollten eine Quellkomponente überprüfen und sicherstellen, dass die in den Ausgabespaltenauflistungen definierten Spalten denjenigen bei der externen Datenquelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="178fe-180">You should validate a source component and verify that the columns defined in its output column collections match the columns at the external data source.</span></span> <span data-ttu-id="178fe-181">Manchmal ist der Abgleich der Ausgabespalten mit der externen Datenquelle nicht möglich, beispielsweise da keine Verbindung besteht oder zeitaufwendige Roundtrips zum Server vermieden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="178fe-181">Sometimes, verifying the output columns against the external data source can be impossible, such as in a disconnected state, or when it is preferable to avoid lengthy round trips to the server.</span></span> <span data-ttu-id="178fe-182">In solchen Fällen können die Spalten in der Ausgabe dennoch mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> des Ausgabeobjekts überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-182">In these situations, the columns in the output can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> of the output object.</span></span> <span data-ttu-id="178fe-183">Weitere Informationen zu finden Sie unter [Überprüfen einer Datenflusskomponente](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="178fe-183">For more information, see [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span>

 <span data-ttu-id="178fe-184">Diese Auflistung ist sowohl für Eingabe- als auch für Ausgabeobjekte vorhanden. Sie können sie mit den Spalten der externen Datenquelle füllen.</span><span class="sxs-lookup"><span data-stu-id="178fe-184">This collection exists on both input and output objects and you can populate it with the columns from the external data source.</span></span> <span data-ttu-id="178fe-185">Mithilfe dieser Auflistung können Sie die Ausgabespalten überprüfen, wenn [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer offline ist, die Verbindung mit der Komponente getrennt ist oder wenn die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A>-Eigenschaft `false` lautet.</span><span class="sxs-lookup"><span data-stu-id="178fe-185">You can use this collection to validate the output columns when [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span> <span data-ttu-id="178fe-186">Die Auflistung sollte zunächst zum Zeitpunkt der Erstellung der Ausgabespalten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-186">The collection should be first populated at the same time that the output columns are created.</span></span> <span data-ttu-id="178fe-187">Das Hinzufügen externer Metadatenspalten zur Auflistung ist recht einfach, da die externe Metadatenspalte zunächst der Ausgabespalte entsprechen sollte.</span><span class="sxs-lookup"><span data-stu-id="178fe-187">Adding external metadata columns to the collection is relatively easy because the external metadata column should initially match the output column.</span></span> <span data-ttu-id="178fe-188">Die Datentypeigenschaften der Spalte sollten bereits korrekt festgelegt worden sein, und die Eigenschaften können direkt in das <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100>-Objekt kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-188">The data type properties of the column should have already been set correctly, and the properties can be copied directly to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100> object.</span></span>

 <span data-ttu-id="178fe-189">Im folgenden Beispielcode wird eine externe Metadatenspalte auf Grundlage einer neu erstellten Ausgabespalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="178fe-189">The following sample code adds an external metadata column that is based on a newly created output column.</span></span> <span data-ttu-id="178fe-190">Dabei wird vorausgesetzt, dass die Ausgabespalte bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="178fe-190">It assumes that the output column has already been created.</span></span>

```csharp
private void CreateExternalMetaDataColumn(IDTSOutput100 output, IDTSOutputColumn100 outputColumn)
{

    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = output.ExternalMetadataColumnCollection.New();
    externalColumn.Name = outputColumn.Name;
    externalColumn.Precision = outputColumn.Precision;
    externalColumn.Length = outputColumn.Length;
    externalColumn.DataType = outputColumn.DataType;
    externalColumn.Scale = outputColumn.Scale;

    // Map the external column to the output column.
    outputColumn.ExternalMetadataColumnID = externalColumn.ID;

}
```

```vb
Private Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumn As IDTSOutputColumn100)

        ' Set the properties of the external metadata column.
        Dim externalColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()
        externalColumn.Name = outputColumn.Name
        externalColumn.Precision = outputColumn.Precision
        externalColumn.Length = outputColumn.Length
        externalColumn.DataType = outputColumn.DataType
        externalColumn.Scale = outputColumn.Scale

        ' Map the external column to the output column.
        outputColumn.ExternalMetadataColumnID = externalColumn.ID

    End Sub
```

## <a name="run-time"></a><span data-ttu-id="178fe-191">Runtime</span><span class="sxs-lookup"><span data-stu-id="178fe-191">Run Time</span></span>
 <span data-ttu-id="178fe-192">Bei der Ausführung fügen die Komponenten Zeilen zu Ausgabepuffern hinzu, die durch den Datenflusstask erstellt und der Komponente in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-192">During execution, components add rows to output buffers that are created by the data flow task and provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="178fe-193">Einmal für Quellkomponenten aufgerufen, erhält die Methode einen Ausgabepuffer für jede <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> der Komponente, die mit einer Downstreamkomponente verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="178fe-193">Called once for source components, the method receives an output buffer for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the component that is connected to a downstream component.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="178fe-194">Suchen von Spalten im Puffer</span><span class="sxs-lookup"><span data-stu-id="178fe-194">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="178fe-195">Der Ausgabepuffer für eine Komponente enthält die von der Komponente definierten Spalten sowie alle zur Ausgabe einer Downstreamkomponente hinzugefügten Spalten.</span><span class="sxs-lookup"><span data-stu-id="178fe-195">The output buffer for a component contains the columns defined by the component and any columns added to the output of a downstream component.</span></span> <span data-ttu-id="178fe-196">Falls beispielsweise eine Quellkomponente drei Spalten in ihrer Ausgabe bereitstellt und die nächste Komponente eine vierte Ausgabespalte hinzufügt, enthält der Ausgabepuffer, der für die Quellkomponente bereitgestellt wird, diese vier Spalten.</span><span class="sxs-lookup"><span data-stu-id="178fe-196">For example, if a source component provides three columns in its output, and the next component adds a fourth output column, the output buffer provided for use by the source component contains these four columns.</span></span>

 <span data-ttu-id="178fe-197">Die Reihenfolge der Spalten in einer Pufferzeile wird nicht vom Index der Ausgabespalte in der Ausgabespaltenauflistung definiert.</span><span class="sxs-lookup"><span data-stu-id="178fe-197">The order of the columns in a buffer row is not defined by the index of the output column in the output column collection.</span></span> <span data-ttu-id="178fe-198">Die genaue Position einer Ausgabespalte in einer Pufferzeile kann nur mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A>-Methode des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-198">An output column can only be accurately located in a buffer row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="178fe-199">Diese Methode sucht die Spalte mit der angegebenen Herkunfts-ID im jeweiligen Puffer und gibt ihre Position in der Zeile zurück.</span><span class="sxs-lookup"><span data-stu-id="178fe-199">This method locates the column with the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="178fe-200">Die Indizes der Ausgabespalten befinden sich typischerweise in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode und werden für die Verwendung während des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Schritts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="178fe-200">The indexes of the output columns are typically located in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and stored for use during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span>

 <span data-ttu-id="178fe-201">Im folgenden Codebeispiel wird die Position der Ausgabespalten im Ausgabepuffer bei einem Aufruf von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> gesucht und in einer internen Struktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="178fe-201">The following code example finds the location of the output columns in the output buffer during a call to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, and stores them in an internal structure.</span></span> <span data-ttu-id="178fe-202">Auch der Name der Spalte wird in der Struktur gespeichert und im Codebeispiel für die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode im nächsten Abschnitt dieses Themas verwendet.</span><span class="sxs-lookup"><span data-stu-id="178fe-202">The name of the column is also stored in the structure and is used in the code example for the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method in the next section of this topic.</span></span>

```csharp
ArrayList columnInformation;

private struct ColumnInfo
{
    public int BufferColumnIndex;
    public string ColumnName;
}

public override void PreExecute()
{
    this.columnInformation = new ArrayList();
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    foreach (IDTSOutputColumn100 col in output.OutputColumnCollection)
    {
        ColumnInfo ci = new ColumnInfo();
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID);
        ci.ColumnName = col.Name;
        columnInformation.Add(ci);
    }
}
```

```vb
Public Overrides Sub PreExecute()

    Me.columnInformation = New ArrayList()
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    For Each col As IDTSOutputColumn100 In output.OutputColumnCollection

        Dim ci As ColumnInfo = New ColumnInfo()
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID)
        ci.ColumnName = col.Name
        columnInformation.Add(ci)
    Next
End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="178fe-203">Verarbeiten von Zeilen</span><span class="sxs-lookup"><span data-stu-id="178fe-203">Processing Rows</span></span>
 <span data-ttu-id="178fe-204">Durch Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A>-Methode, die eine neue Pufferzeile mit leeren Werten in ihren Spalten erzeugt, können dem Ausgabepuffer Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-204">Rows are added to the output buffer by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method, which creates a new buffer row with empty values in its columns.</span></span> <span data-ttu-id="178fe-205">Die Komponente weist anschließend den einzelnen Spalten Werte zu.</span><span class="sxs-lookup"><span data-stu-id="178fe-205">The component then assigns values to the individual columns.</span></span> <span data-ttu-id="178fe-206">Der Datenflusstask erstellt und überwacht die Ausgabepuffer, die einer Komponente bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="178fe-206">The output buffers provided to a component are created and monitored by the data flow task.</span></span> <span data-ttu-id="178fe-207">Sobald sie gefüllt sind, werden die Zeilen im Puffer in die nächste Komponente verschoben.</span><span class="sxs-lookup"><span data-stu-id="178fe-207">As they become full, the rows in the buffer are moved to the next component.</span></span> <span data-ttu-id="178fe-208">Es gibt keine Möglichkeit zu ermitteln, wann ein Zeilenbatch an die nächste Komponente gesendet wird, da die Zeilenbewegungen durch den Datenflusstask für den Komponentenentwickler transparent verlaufen und die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A>-Eigenschaft in Ausgabepuffern immer den Wert Null aufweist.</span><span class="sxs-lookup"><span data-stu-id="178fe-208">There is no way to determine when a batch of rows has been sent to the next component because the movement of rows by the data flow task is transparent to the component developer, and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> property is always zero on output buffers.</span></span> <span data-ttu-id="178fe-209">Sobald eine Quellkomponente das Hinzufügen von Zeilen zum Ausgabepuffer beendet hat, benachrichtigt sie den Datenflusstask durch Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>-Methode des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, und die verbleibenden Zeilen im Puffer werden an die nächste Komponente weitergereicht.</span><span class="sxs-lookup"><span data-stu-id="178fe-209">When a source component is finished adding rows to its output buffer, it notifies the data flow task by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, and the remaining rows in the buffer are passed to the next component.</span></span>

 <span data-ttu-id="178fe-210">Während die Quellkomponente Zeilen der externen Datenquelle liest, sollten Sie die Leistungsindikatoren Gelesene Zeilen oder Gelesene BLOB-Bytes durch Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>-Methode aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="178fe-210">While the source component reads rows from the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="178fe-211">Weitere Informationen finden Sie unter [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="178fe-211">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="178fe-212">Im folgenden Codebeispiel wird eine Komponente dargestellt, die im <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Schritt Zeilen zu einem Ausgabepuffer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="178fe-212">The following code example shows a component that adds rows to an output buffer in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="178fe-213">Die Indizes der Ausgabespalten im Puffer wurden im vorangehenden Codebeispiel mithilfe von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> ermittelt.</span><span class="sxs-lookup"><span data-stu-id="178fe-213">The indexes of the output columns in the buffer were located using <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the previous code example.</span></span>

```csharp
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
{
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
    PipelineBuffer buffer = buffers[0];

    SqlDataReader dataReader = sqlCommand.ExecuteReader();

    // Loop over the rows in the DataReader, 
    // and add them to the output buffer.
    while (dataReader.Read())
    {
        // Add a row to the output buffer.
        buffer.AddRow();

        for (int x = 0; x < columnInformation.Count; x++)
        {
            ColumnInfo ci = (ColumnInfo)columnInformation[x];
            int ordinal = dataReader.GetOrdinal(ci.ColumnName);

            if (dataReader.IsDBNull(ordinal))
                buffer.SetNull(ci.BufferColumnIndex);
            else
            {
                buffer[ci.BufferColumnIndex] = dataReader[ci.ColumnName];
            }
        }
    }
    buffer.SetEndOfRowset();
}
```

```vb
Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim buffer As PipelineBuffer = buffers(0)

    Dim dataReader As SqlDataReader = sqlCommand.ExecuteReader()

    ' Loop over the rows in the DataReader, 
    ' and add them to the output buffer.
    While (dataReader.Read())

        ' Add a row to the output buffer.
        buffer.AddRow()

        For x As Integer = 0 To columnInformation.Count

            Dim ci As ColumnInfo = CType(columnInformation(x), ColumnInfo)

            Dim ordinal As Integer = dataReader.GetOrdinal(ci.ColumnName)

            If (dataReader.IsDBNull(ordinal)) Then
                buffer.SetNull(ci.BufferColumnIndex)
            Else
                buffer(ci.BufferColumnIndex) = dataReader(ci.ColumnName)

            End If
        Next

    End While

    buffer.SetEndOfRowset()
End Sub
```

## <a name="sample"></a><span data-ttu-id="178fe-214">Beispiel</span><span class="sxs-lookup"><span data-stu-id="178fe-214">Sample</span></span>
 <span data-ttu-id="178fe-215">Das folgende Beispiel zeigt eine einfache Quellkomponente, die über einen Dateiverbindungs-Manager den binären Inhalt von Dateien in den Datenfluss lädt.</span><span class="sxs-lookup"><span data-stu-id="178fe-215">The following sample shows a simple source component that uses a File connection manager to load the binary contents of files into the data flow.</span></span> <span data-ttu-id="178fe-216">In diesem Beispiel werden nicht alle Methoden und Funktionen dargestellt, die in diesem Thema erläutert wurden.</span><span class="sxs-lookup"><span data-stu-id="178fe-216">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="178fe-217">Es veranschaulicht die Hauptmethoden, die jede benutzerdefinierte Quellkomponente überschreiben muss, enthält jedoch keinen Code für eine Überprüfung zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="178fe-217">It demonstrates the important methods that every custom source component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace BlobSrc
{
  [DtsPipelineComponent(DisplayName = "BLOB Inserter Source", Description = "Inserts files into the data flow as BLOBs")]
  public class BlobSrc : PipelineComponent
  {
    IDTSConnectionManager100 m_ConnMgr;
    int m_FileNameColumnIndex = -1;
    int m_FileBlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
      output.Name = "BLOB File Inserter Output";

      IDTSOutputColumn100 column = output.OutputColumnCollection.New();
      column.Name = "FileName";
      column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0);

      column = output.OutputColumnCollection.New();
      column.Name = "FileBLOB";
      column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0);

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_ConnMgr = conn.ConnectionManager;
    }

    public override void ReleaseConnections()
    {
      m_ConnMgr = null;
    }

    public override void PreExecute()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

      m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[0].LineageID);
      m_FileBlobColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[1].LineageID);
    }

    public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
    {
      string strFileName = (string)m_ConnMgr.AcquireConnection(null);

      while (strFileName != null)
      {
        buffers[0].AddRow();

        buffers[0].SetString(m_FileNameColumnIndex, strFileName);

        FileInfo fileInfo = new FileInfo(strFileName);
        byte[] fileData = new byte[fileInfo.Length];
        FileStream fs = new FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read);
        fs.Read(fileData, 0, fileData.Length);

        buffers[0].AddBlobData(m_FileBlobColumnIndex, fileData);

        strFileName = (string)m_ConnMgr.AcquireConnection(null);
      }

      buffers[0].SetEndOfRowset();
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper 
Namespace BlobSrc 

 <DtsPipelineComponent(DisplayName="BLOB Inserter Source", Description="Inserts files into the data flow as BLOBs")> _ 
 Public Class BlobSrc 
 Inherits PipelineComponent 
   Private m_ConnMgr As IDTSConnectionManager100 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_FileBlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New 
     output.Name = "BLOB File Inserter Output" 
     Dim column As IDTSOutputColumn100 = output.OutputColumnCollection.New 
     column.Name = "FileName" 
     column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0) 
     column = output.OutputColumnCollection.New 
     column.Name = "FileBLOB" 
     column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0) 
     Dim conn As IDTSRuntimeConnection90 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_ConnMgr = conn.ConnectionManager 
   End Sub 

   Public  Overrides Sub ReleaseConnections() 
     m_ConnMgr = Nothing 
   End Sub 

   Public  Overrides Sub PreExecute() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0) 
     m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(0).LineageID), Integer) 
     m_FileBlobColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(1).LineageID), Integer) 
   End Sub 

   Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer()) 
     Dim strFileName As String = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     While Not (strFileName Is Nothing) 
       buffers(0).AddRow 
       buffers(0).SetString(m_FileNameColumnIndex, strFileName) 
       Dim fileInfo As FileInfo = New FileInfo(strFileName) 
       Dim fileData(fileInfo.Length) As Byte 
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read) 
       fs.Read(fileData, 0, fileData.Length) 
       buffers(0).AddBlobData(m_FileBlobColumnIndex, fileData) 
       strFileName = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     End While 
     buffers(0).SetEndOfRowset 
   End Sub 
 End Class 
End Namespace
```

<span data-ttu-id="178fe-218">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="178fe-218">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="178fe-219">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="178fe-219">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="178fe-220">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="178fe-220">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="178fe-221">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="178fe-221">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="178fe-222">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="178fe-222">See Also</span></span>
 <span data-ttu-id="178fe-223">[Entwickeln einer benutzerdefinierten Zielkomponente](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Erstellen einer Quelle mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="178fe-223">[Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span></span>


