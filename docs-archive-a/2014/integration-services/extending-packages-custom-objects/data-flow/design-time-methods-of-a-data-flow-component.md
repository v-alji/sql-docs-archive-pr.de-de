---
title: Entwurfszeitmethoden einer Datenflusskomponente | Microsoft-Dokumentation
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619962"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="e3c98-102">Entwurfszeitmethoden einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="e3c98-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="e3c98-103">Vor der Ausführung befindet sich der Datenflusstask im so genannten Entwurfszeitstatus, während er inkrementelle Änderungen durchläuft.</span><span class="sxs-lookup"><span data-stu-id="e3c98-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="e3c98-104">Zu den Änderungen kann das Hinzufügen oder Entfernen von Komponenten, das Hinzufügen oder Entfernen von Pfadobjekten zur Verbindung von Komponenten sowie Änderungen an den Metadaten der Komponenten gehören.</span><span class="sxs-lookup"><span data-stu-id="e3c98-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="e3c98-105">Wenn Metadaten-Änderungen auftreten, kann die Komponente die Änderungen überwachen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="e3c98-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="e3c98-106">Zum Beispiel kann eine Komponente bestimmte Änderungen nicht zulassen oder zusätzliche Änderungen als Reaktion auf eine Änderung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="e3c98-107">Zur Entwurfszeit interagiert der Designer mit einer Komponente durch die Entwurfszeitschnittstelle <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="e3c98-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="e3c98-108">Entwurfszeitimplementierung</span><span class="sxs-lookup"><span data-stu-id="e3c98-108">Design-Time Implementation</span></span>
 <span data-ttu-id="e3c98-109">Die Entwurfszeitschnittstelle einer Komponente wird von der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>-Schnittstelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3c98-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="e3c98-110">Auch wenn Sie diese Schnittstelle nicht explizit implementieren, sollten Sie die in der Schnittstelle definierten Methoden kennen, um zu verstehen, welche Methoden der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse den Entwurfszeitinstanzen einer Komponente entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="e3c98-111">Wenn eine Komponente in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] geladen wird, wird die Entwurfszeitinstanz der Komponente instanziiert und die Methoden der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>-Schnittstelle beim Bearbeiten der Komponente aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="e3c98-112">Die Implementierung der Basisklasse lässt Sie nur die Methoden, die die Komponente erfordert, überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e3c98-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="e3c98-113">In vielen Fällen überschreiben Sie diese Methoden um zu verhindern, dass an einer Komponente unerwünschte Bearbeitungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e3c98-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="e3c98-114">Um beispielsweise Benutzer zu hindern, eine Ausgabe zu einer Komponente hinzuzufügen, überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="e3c98-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="e3c98-115">Andernfalls wird beim Aufrufen der Implementierung dieser Methode durch die Basisklasse eine Ausgabe zur Komponente hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="e3c98-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="e3c98-116">Unabhängig vom Zweck oder der Funktion Ihrer Komponente sollten Sie die Methoden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e3c98-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="e3c98-117">Weitere Informationen zu <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> finden Sie unter [Überprüfen einer Datenflusskomponente](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e3c98-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="e3c98-118">ProvideComponentProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="e3c98-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="e3c98-119">Die Initialisierung einer Komponente erfolgt in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="e3c98-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="e3c98-120">Diese Methode wird vom [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer aufgerufen, wenn eine Komponente zum Datenflusstask hinzugefügt wird, und ist ähnlich wie ein Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="e3c98-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="e3c98-121">Komponentenentwickler sollten ihre Eingaben, Ausgaben und benutzerdefinierten Eigenschaften während dieses Methodenaufrufs initialisieren und erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="e3c98-122">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Methode unterscheidet sich von einem Konstruktor, da sie nicht jedes Mal aufgerufen wird, wenn die Entwurfszeitinstanz oder Laufzeitinstanz der Komponenten instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3c98-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="e3c98-123">Die Basisklassenimplementierung der Methode fügt eine Eingabe und eine Ausgabe zur Komponente hinzu und weist die ID der Eingabe der Eigenschaft <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> zu.</span><span class="sxs-lookup"><span data-stu-id="e3c98-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="e3c98-124">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] werden jedoch die Eingabe- und Ausgabeobjekte, die von der Basisklasse hinzugefügt werden, nicht benannt.</span><span class="sxs-lookup"><span data-stu-id="e3c98-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="e3c98-125">Pakete, die eine Komponente mit Eingabe- oder Ausgabeobjekten enthalten, deren Name-Eigenschaft nicht festgelegt ist, werden nicht erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="e3c98-126">Bei Verwendung der Basisimplementierung müssen Sie also der Name-Eigenschaft der Standardeingabe und -ausgabe explizit Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="e3c98-127">Erstellen von benutzerdefinierten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e3c98-127">Creating Custom Properties</span></span>
 <span data-ttu-id="e3c98-128">Komponentenentwickler können beim Aufrufen der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Methode der Komponente benutzerdefinierte Eigenschaften (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="e3c98-129">Benutzerdefinierte Eigenschaften verfügen nicht über eine Datentypeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e3c98-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="e3c98-130">Der Datentyp einer benutzerdefinierten Eigenschaft wird durch den Datentyp des Werts bestimmt, den Sie der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>-Eigenschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="e3c98-131">Nachdem Sie der benutzerdefinierten Eigenschaft jedoch einen Anfangswert zugeordnet haben, können Sie keinen Wert mit einem anderen Datentyp zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="e3c98-132">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>-Schnittstelle bietet eingeschränkte Unterstützung für Eigenschaftenwerte des Typs `Object`.</span><span class="sxs-lookup"><span data-stu-id="e3c98-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="e3c98-133">Das einzige Objekt, das Sie als Wert einer benutzerdefinierten Eigenschaft zuordnen können, ist ein Array einfacher Typen wie Zeichenfolgen oder Ganzzahlen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="e3c98-134">Sie können festlegen, dass die benutzerdefinierte Eigenschaft Eigenschaftsausdrücke unterstützt, indem Sie den Wert der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A>-Eigenschaft auf `CPET_NOTIFY` aus der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>-Enumeration einstellen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3c98-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="e3c98-135">Sie müssen keinen Code hinzufügen, um den vom Benutzer eingegebenen Eigenschaftsausdruck zu verarbeiten oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e3c98-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="e3c98-136">Sie können einen Standardwert für die Eigenschaft festlegen, den Wert überprüfen und den Wert normal lesen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3c98-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="e3c98-137">Mithilfe der-Eigenschaft können Sie Benutzer so einschränken, dass Sie einen benutzerdefinierten Eigenschafts Wert aus einer Enumeration auswählen <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> , wie im folgenden Beispiel gezeigt, bei dem davon ausgegangen wird, dass Sie eine öffentliche Enumeration mit dem Namen definiert haben `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="e3c98-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="e3c98-138">Weitere Informationen finden Sie unter „Verallgemeinerte Typkonvertierung“ und „Implementieren eines Typkonverters“ in der [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="e3c98-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="e3c98-139">Sie können ein benutzerdefiniertes Bearbeitungsdialogfeld für den Wert der benutzerdefinierten Eigenschaft angeben, indem Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>-Eigenschaft wie im folgenden Beispiel gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3c98-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="e3c98-140">Erstellen Sie zuerst einen benutzerdefinierten Typeditor, der von `System.Drawing.Design.UITypeEditor` erbt, falls Sie keine geeignete vorhandene Typ-Editorklasse für die Benutzeroberfläche finden.</span><span class="sxs-lookup"><span data-stu-id="e3c98-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="e3c98-141">Geben Sie danach diese Klasse als Wert der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>-Eigenschaft der benutzerdefinierten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e3c98-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="e3c98-142">Weitere Informationen finden Sie unter „Implementieren eines Typ-Editors für die Benutzeroberfläche“ in der [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="e3c98-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="e3c98-143">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="e3c98-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e3c98-144">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="e3c98-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e3c98-145">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="e3c98-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e3c98-146">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e3c98-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3c98-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3c98-147">See Also</span></span>
 [<span data-ttu-id="e3c98-148">Laufzeitmethoden einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="e3c98-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


