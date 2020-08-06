---
title: Programmgesteuertes Hinzufügen von Datenflusskomponenten | Microsoft-Dokumentation
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: c06065cf-43e5-4b6b-9824-7309d7f5e35e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 807e758e42b738c4b0bf64b1d6f48bc29649ae6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616651"
---
# <a name="adding-data-flow-components-programmatically"></a><span data-ttu-id="46de3-102">Programmgesteuertes Hinzufügen von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="46de3-102">Adding Data Flow Components Programmatically</span></span>
  <span data-ttu-id="46de3-103">Wenn Sie einen Datenfluss erstellen, beginnen Sie, indem Sie Komponenten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="46de3-103">When you build a data flow, you start by adding components.</span></span> <span data-ttu-id="46de3-104">Anschließend werden diese Komponenten konfiguriert und miteinander verbunden, um den Datenfluss zur Laufzeit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="46de3-104">Then you configure those components and connect them together to establish the flow of data at run time.</span></span> <span data-ttu-id="46de3-105">In diesem Abschnitt wird das Hinzufügen einer Komponente zum Datenflusstask, das Erstellen der Entwurfszeitinstanz der Komponente und das anschließende Konfigurieren der Komponente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46de3-105">This section describes adding a component to the data flow task, creating the design-time instance of the component, and then configuring the component.</span></span> <span data-ttu-id="46de3-106">Informationen zum Verbinden von Komponenten finden Sie unter [Programmgesteuertes Verbinden von Datenflusskomponenten](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="46de3-106">For information about how to connect components, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-component"></a><span data-ttu-id="46de3-107">Hinzufügen einer Komponente</span><span class="sxs-lookup"><span data-stu-id="46de3-107">Adding a Component</span></span>  
 <span data-ttu-id="46de3-108">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A>-Auflistung auf, um eine neue Komponente zu erstellen und diese dem Datenflusstask hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46de3-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> collection to create a new component and add it to the data flow task.</span></span> <span data-ttu-id="46de3-109">Diese Methode gibt die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle der Komponente zurück.</span><span class="sxs-lookup"><span data-stu-id="46de3-109">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component.</span></span> <span data-ttu-id="46de3-110">An diesem Punkt enthält die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle jedoch keine spezifischen Informationen zu einer der Komponenten.</span><span class="sxs-lookup"><span data-stu-id="46de3-110">However, at this point, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> does not contain information specific to any one component.</span></span> <span data-ttu-id="46de3-111">Legen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>-Eigenschaft so fest, dass der Typ der Komponente identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="46de3-111">Set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property to identify the type of component.</span></span> <span data-ttu-id="46de3-112">Der Datenflusstask verwendet den Wert dieser Eigenschaft zum Erstellen einer Instanz der Komponente zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="46de3-112">The data flow task uses the value of this property to create an instance of the component at run time.</span></span>  
  
 <span data-ttu-id="46de3-113">Der in der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>-Eigenschaft angegebene Wert kann die CLSID, PROGID oder <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A>-Eigenschaft der Komponente sein.</span><span class="sxs-lookup"><span data-stu-id="46de3-113">The value specified in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property can be the CLSID, PROGID, or <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property of the component.</span></span> <span data-ttu-id="46de3-114">Die CLSID wird in der Regel im Eigenschaftenfenster als Wert der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>-Eigenschaft der Komponente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46de3-114">The CLSID is normally displayed in the Properties window as the value of the component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="46de3-115">Informationen zum Erhalten dieser Eigenschaft und anderer Eigenschaften verfügbarer Komponenten finden Sie unter [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md) (Programmgesteuertes Auffinden von Datenflusskomponenten).</span><span class="sxs-lookup"><span data-stu-id="46de3-115">For information about obtaining this property and other properties of available components, see [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-managed-component"></a><span data-ttu-id="46de3-116">Hinzufügen einer verwalteten Komponente</span><span class="sxs-lookup"><span data-stu-id="46de3-116">Adding a Managed Component</span></span>  
 <span data-ttu-id="46de3-117">Sie können die CLSID oder PROGID nicht verwenden, um dem Datenfluss eine der verwalteten Datenflusskomponenten hinzuzufügen, da diese Werte auf einen Wrapper und nicht auf die Komponente selbst zeigen.</span><span class="sxs-lookup"><span data-stu-id="46de3-117">You cannot use the CLSID or PROGID to add one the managed data flow components to the data flow, because these values point to a wrapper and not to the component itself.</span></span> <span data-ttu-id="46de3-118">Stattdessen können Sie die `CreationName`-Eigenschaft oder die `AssemblyQualifiedName`-Eigenschaft verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="46de3-118">Instead you can use the `CreationName` property or the `AssemblyQualifiedName` property as shown in the following sample.</span></span>  
  
 <span data-ttu-id="46de3-119">Wenn Sie die `AssemblyQualifiedName`-Eigenschaft verwenden möchten, müssen Sie in Ihrem [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Projekt einen Verweis auf die Assembly hinzufügen, die die verwaltete Komponente enthält.</span><span class="sxs-lookup"><span data-stu-id="46de3-119">If you intend to use the `AssemblyQualifiedName` property, then you must add a reference in your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] project to the assembly that contains the managed component.</span></span> <span data-ttu-id="46de3-120">Diese Assemblys sind nicht auf der Registerkarte für .NET des Dialogfelds **Verweis hinzufügen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="46de3-120">These assemblies are not listed on the .NET tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="46de3-121">Normalerweise finden Sie die Assembly im Ordner **C:\Programme\Microsoft SQL Server\100\DTS\PipelineComponents**.</span><span class="sxs-lookup"><span data-stu-id="46de3-121">Normally you must browse to locate the assembly in the **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents** folder.</span></span>  
  
 <span data-ttu-id="46de3-122">Die integrierten verwalteten Datenflusskomponenten umfassen:</span><span class="sxs-lookup"><span data-stu-id="46de3-122">The built-in managed data flow components include:</span></span>  
  
-   [!INCLUDE[vstecado](../../includes/vstecado-md.md)]<span data-ttu-id="46de3-123">-Quelle</span><span class="sxs-lookup"><span data-stu-id="46de3-123">Source</span></span>  
  
-   <span data-ttu-id="46de3-124">XML-Quelle</span><span class="sxs-lookup"><span data-stu-id="46de3-124">XML Source</span></span>  
  
-   <span data-ttu-id="46de3-125">DataReader-Ziel</span><span class="sxs-lookup"><span data-stu-id="46de3-125">DataReader Destination</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="46de3-126">Compact-Ziel</span><span class="sxs-lookup"><span data-stu-id="46de3-126">Compact Destination</span></span>  
  
-   <span data-ttu-id="46de3-127">Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="46de3-127">Script Component</span></span>  
  
 <span data-ttu-id="46de3-128">Im folgenden Codebeispiel werden beide Methoden zum Hinzufügen einer verwalteten Komponente zu einem Datenfluss veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="46de3-128">The following code sample shows both ways of adding a managed component to the data flow:</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Microsoft.SqlServer.Dts.Runtime.Package package = new Microsoft.SqlServer.Dts.Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Microsoft.SqlServer.Dts.Runtime.TaskHost thMainPipe = (Microsoft.SqlServer.Dts.Runtime.TaskHost)e;  
      MainPipe dataFlowTask = (MainPipe)thMainPipe.InnerObject;  
  
      // The Application object will be used to obtain the CreationName  
      //  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
      Application app = new Application();  
  
      // Add a first ADO NET source to the data flow.  
      //  The CreationName property requires an Application instance.  
      IDTSComponentMetaData100 component1 = dataFlowTask.ComponentMetaDataCollection.New();  
      component1.Name = "DataReader Source";  
      component1.ComponentClassID = app.PipelineComponentInfos["DataReader Source"].CreationName;  
  
      // Add a second ADO NET source to the data flow.  
      //  The AssemblyQualifiedName property requires a reference to the assembly.  
      IDTSComponentMetaData100 component2 = dataFlowTask.ComponentMetaDataCollection.New();  
      component2.Name = "DataReader Source";  
      component2.ComponentClassID = typeof(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName;  
    }  
  }  
}  
  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' The Application object will be used to obtain the CreationName  
    '  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
    Dim app As New Application()  
  
    ' Add a first ADO NET source to the data flow.  
    '  The CreationName property requires an Application instance.  
    Dim component1 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component1.Name = "DataReader Source"  
    component1.ComponentClassID = app.PipelineComponentInfos("DataReader Source").CreationName  
  
    ' Add a second ADO NET source to the data flow.  
    '  The AssemblyQualifiedName property requires a reference to the assembly.  
    Dim component2 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component2.Name = "DataReader Source"  
    component2.ComponentClassID = _  
      GetType(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName  
  
  End Sub  
  
End Module  
```  
  
## <a name="creating-the-design-time-instance-of-the-component"></a><span data-ttu-id="46de3-129">Erstellen der Entwurfszeitinstanz der Komponente</span><span class="sxs-lookup"><span data-stu-id="46de3-129">Creating the Design-time Instance of the Component</span></span>  
 <span data-ttu-id="46de3-130">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>-Methode zur Erstellung der Entwurfszeitinstanz der Komponente auf, die durch die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="46de3-130">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method to create the design time instance of the component identified by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="46de3-131">Diese Methode gibt das <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper>-Objekt zurück, das der verwaltete Wrapper für die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="46de3-131">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> object, which is the managed wrapper for the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="46de3-132">Eine Komponente sollte, wann immer möglich, mithilfe der Methoden der Entwurfszeitinstanz geändert werden und nicht durch direktes Ändern der Metadaten der Komponente.</span><span class="sxs-lookup"><span data-stu-id="46de3-132">Whenever possible, you should modify a component by using the methods of the design-time instance instead of by modifying the component metadata directly.</span></span> <span data-ttu-id="46de3-133">Es gibt zwar Elemente in den Metadaten, die Sie direkt festlegen müssen, z. B. Verbindungen, es empfiehlt sich jedoch im Allgemeinen nicht, die Metadaten direkt zu ändern, da in diesem Fall die Komponente keine Änderungen mehr überwachen und überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="46de3-133">Although there are items in the metadata that you must set directly, such as connections, generally it is inadvisable to modify the metadata directly because you bypass the ability of the component to monitor and validate changes.</span></span>  
  
## <a name="assigning-connections"></a><span data-ttu-id="46de3-134">Zuweisen von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="46de3-134">Assigning Connections</span></span>  
 <span data-ttu-id="46de3-135">Manche Komponenten, beispielsweise die OLE DB-Quellkomponente, erfordern eine Verbindung zu externen Daten und verwenden zu diesem Zweck ein vorhandenes <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekt in dem Paket.</span><span class="sxs-lookup"><span data-stu-id="46de3-135">Some components, such as the OLE DB Source component, require a connection to external data and use an existing <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object in the package for this purpose.</span></span> <span data-ttu-id="46de3-136">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A>-Eigenschaft der .<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>-Auflistung gibt die Anzahl von <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekten zur Laufzeit an, die für die Komponente erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="46de3-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection indicates the number of run-time <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects required by the component.</span></span> <span data-ttu-id="46de3-137">Wenn die Anzahl größer als 0 (null) ist, erfordert die Komponente eine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="46de3-137">If the count is greater than zero, the component requires a connection.</span></span> <span data-ttu-id="46de3-138">Weisen Sie der Komponente einen Verbindungs-Manager aus dem Paket zu, indem Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A>-Eigenschaft und die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A>-Eigenschaft der ersten Verbindung in der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> angeben.</span><span class="sxs-lookup"><span data-stu-id="46de3-138">Assign a connection manager from the package to the component by specifying the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> properties of the first connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span> <span data-ttu-id="46de3-139">Beachten Sie, dass der Name des Verbindungs-Managers in der Verbindungsauflistung zur Laufzeit dem Namen des Verbindungs-Managers entsprechen muss, auf den vom Paket verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="46de3-139">Note that the name of the connection manager in the run-time connection collection must match the name of the connection managerreferenced from the package.</span></span>  
  
## <a name="setting-the-values-of-custom-properties"></a><span data-ttu-id="46de3-140">Festlegen der Werte benutzerdefinierter Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="46de3-140">Setting the Values of Custom Properties</span></span>  
 <span data-ttu-id="46de3-141">Rufen Sie nach dem Erstellen der Entwurfszeitinstanz der Komponente die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="46de3-141">After creating the design-time instance of the component, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="46de3-142">Diese Methode ähnelt einem Konstruktor, da sie eine neu erstellte Komponente initialisiert, indem benutzerdefinierte Eigenschaften und Eingabe- und Ausgabeobjekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="46de3-142">This method is similar to a constructor because it initializes a newly created component by creating its custom properties and its input and output objects.</span></span> <span data-ttu-id="46de3-143">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>-Methode nicht mehrmals in einer Komponente auf, da sich die Komponente möglicherweise selbst zurücksetzt und alle zuvor an ihren Metadaten vorgenommenen Änderungen verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="46de3-143">Do not call <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> more than one time on a component, because the component may reset itself and lose any modifications previously made to its metadata.</span></span>  
  
 <span data-ttu-id="46de3-144">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A>-Eigenschaft der Komponente enthält eine Auflistung von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>-Objekten, die für die Komponente spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="46de3-144">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> of the component contains a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> objects specific to the component.</span></span> <span data-ttu-id="46de3-145">Im Gegensatz zu anderen Programmierungsmodellen, bei denen die Eigenschaften eines Objekts in dem Objekt immer sichtbar sind, werden die Auflistungen benutzerdefinierter Eigenschaften von Komponenten nur aufgefüllt, wenn Sie die  <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="46de3-145">Unlike other programming models, where the properties of an object are always visible on the object, components only populate their custom property collections when you call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="46de3-146">Verwenden Sie nach dem Aufrufen der Methode die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A>-Methode der Entwurfszeitinstanz der Komponente, um ihren benutzerdefinierten Eigenschaften Werte zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="46de3-146">After you call method, use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> method of the design-time instance of the component to assign values to its custom properties.</span></span> <span data-ttu-id="46de3-147">Diese Methode akzeptiert ein Name/Wert-Paar, das die benutzerdefinierte Eigenschaft identifiziert und seinen neuen Wert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="46de3-147">This method accepts a name/value pair that identifies the custom property and provides its new value.</span></span>  
  
## <a name="initializing-output-columns"></a><span data-ttu-id="46de3-148">Initialisieren von Ausgabespalten</span><span class="sxs-lookup"><span data-stu-id="46de3-148">Initializing Output Columns</span></span>  
 <span data-ttu-id="46de3-149">Nachdem Sie dem Task eine Komponente hinzugefügt und diese konfiguriert haben, initialisieren Sie die Auflistung von Spalten in <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> des Objekts.</span><span class="sxs-lookup"><span data-stu-id="46de3-149">After you add a component to the task and configure it, initialize the collection of columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the object.</span></span> <span data-ttu-id="46de3-150">Dieser Schritt ist insbesondere bei Quellkomponenten relevant. Möglicherweise werden dadurch jedoch keine Spalten für die Transformation und Zielkomponenten initialisiert, da diese im Allgemeinen von den Spalten abhängig sind, die sie von Upstreamkomponenten empfangen.</span><span class="sxs-lookup"><span data-stu-id="46de3-150">This step is especially relevant for source components, but may not initialize the columns for transformation and destination components because they generally depend on the columns that they receive from upstream components.</span></span>  
  
 <span data-ttu-id="46de3-151">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A>-Methode auf, um die Spalten in den Ausgaben einer Quellkomponente zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="46de3-151">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> method to initialize the columns in the outputs of a source component.</span></span> <span data-ttu-id="46de3-152">Da Komponenten nicht automatisch eine Verbindung zu externen Datenquellen herstellen, rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A>-Methode auf, bevor Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A>-Methode aufrufen, um der Komponente Zugriff zu ihrer externen Datenquelle zu gewähren und die Möglichkeit zu geben, ihre eigene Metadatenspalte zu füllen.</span><span class="sxs-lookup"><span data-stu-id="46de3-152">Because components do not automatically connect to external data sources, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> method before calling <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> to provide the component access to its external data source and the ability to populate its column metadata.</span></span> <span data-ttu-id="46de3-153">Um die Verbindung freizugeben, ist schließlich ein Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A>-Methode erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46de3-153">Finally, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> method to release the connection.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="46de3-154">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="46de3-154">Next Step</span></span>  
 <span data-ttu-id="46de3-155">Nach dem Hinzufügen und Konfigurieren der Komponente besteht der nächste Schritt darin, Pfade zwischen Komponenten zu erstellen. Dies wird im Thema [Creating a Path](../building-packages-programmatically/connecting-data-flow-components-programmatically.md) (Erstellen eines Pfads) erläutert.</span><span class="sxs-lookup"><span data-stu-id="46de3-155">After adding and configuring the component, the next step is to create paths between components, which is discussed in the topic, [Creating a Path Between Two Components](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="46de3-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46de3-156">Sample</span></span>  
 <span data-ttu-id="46de3-157">Im folgenden Codebeispiel werden die OLE DB-Quellkomponenten einem Datenflusstask hinzugefügt, eine Entwurfszeitinstanz der Komponente erstellt und die Eigenschaften der Komponente konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="46de3-157">The following code sample adds the OLE DB Source component to a data flow task, creates a design-time instance of the component, and configures the component's properties.</span></span> <span data-ttu-id="46de3-158">Für dieses Beispiel ist ein zusätzlicher Verweis auf die Microsoft.SqlServer.SQLTask-Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46de3-158">This example requires an additional reference to the assembly Microsoft.SqlServer.DTSRuntimeWrap.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Runtime.Package package = new Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Runtime.TaskHost thMainPipe = e as Runtime.TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLEDB connection manager to the package.  
      ConnectionManager cm = package.Connections.Add("OLEDB");  
      cm.Name = "OLEDB ConnectionManager";  
      cm.ConnectionString = "Data Source=(local);" +   
        "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" +   
        "Integrated Security=SSPI;"  
  
      // Add an OLE DB source to the data flow.  
      IDTSComponentMetaData100 component =   
        dataFlowTask.ComponentMetaDataCollection.New();  
      component.Name = "OLEDBSource";  
      component.ComponentClassID = "DTSAdapter.OleDbSource.1";  
      // You can also use the CLSID of the component instead of the PROGID.  
      //component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
      // Get the design time instance of the component.  
      CManagedComponentWrapper instance = component.Instantiate();  
  
      // Initialize the component  
      instance.ProvideComponentProperties();  
  
      // Specify the connection manager.  
      if (component.RuntimeConnectionCollection.Count > 0)  
      {  
        component.RuntimeConnectionCollection[0].ConnectionManager =   
          DtsConvert.GetExtendedInterface(package.Connections[0]);  
        component.RuntimeConnectionCollection[0].ConnectionManagerID =   
          package.Connections[0].ID;      }  
  
      // Set the custom properties.  
      instance.SetComponentProperty("AccessMode", 2);  
      instance.SetComponentProperty("SqlCommand",   
        "Select * from Production.Product");  
  
      // Reinitialize the metadata.  
      instance.AcquireConnections(null);  
      instance.ReinitializeMetaData();  
      instance.ReleaseConnections();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLEDB connection manager to the package.  
    Dim cm As ConnectionManager = package.Connections.Add("OLEDB")  
    cm.Name = "OLEDB ConnectionManager"  
    cm.ConnectionString = "Data Source=(local);" & _  
      "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;"  
  
    ' Add an OLE DB source to the data flow.  
    Dim component As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component.Name = "OLEDBSource"  
    component.ComponentClassID = "DTSAdapter.OleDbSource.1"  
    ' You can also use the CLSID of the component instead of the PROGID.  
    'component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
    ' Get the design time instance of the component.  
    Dim instance As CManagedComponentWrapper = component.Instantiate()  
  
    ' Initialize the component.  
    instance.ProvideComponentProperties()  
  
    ' Specify the connection manager.  
    If component.RuntimeConnectionCollection.Count > 0 Then  
      component.RuntimeConnectionCollection(0).ConnectionManager = _  
        DtsConvert.GetExtendedInterface(package.Connections(0))  
      component.RuntimeConnectionCollection(0).ConnectionManagerID = _  
        package.Connections(0).ID  
    End If  
  
    ' Set the custom properties.  
    instance.SetComponentProperty("AccessMode", 2)  
    instance.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Reinitialize the metadata.  
    instance.AcquireConnections(vbNull)  
    instance.ReinitializeMetaData()  
    instance.ReleaseConnections()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="46de3-159">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="46de3-159">External Resources</span></span>  
 <span data-ttu-id="46de3-160">Blogbeitrag, [EzAPI – Updated for SQL Server 2012 (EzAPI: für SQL Server 2012 aktualisiert)](https://go.microsoft.com/fwlink/?LinkId=243223), auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="46de3-160">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="46de3-161">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="46de3-161">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="46de3-162">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="46de3-162">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="46de3-163">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="46de3-163">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="46de3-164">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="46de3-164">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46de3-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46de3-165">See Also</span></span>  
 [<span data-ttu-id="46de3-166">Programmgesteuertes Verbinden von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="46de3-166">Connecting Data Flow Components Programmatically</span></span>](../building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
  
  
