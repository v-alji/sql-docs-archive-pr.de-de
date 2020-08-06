---
title: Verwenden von Fehlerausgaben in einer Datenflusskomponente | Microsoft-Dokumentation
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
- errors [Integration Services], alternative outputs
- synchronous error outputs [Integration Services]
- alternative error outputs [Integration Services]
- custom data flow components [Integration Services], error outputs
- data flow components [Integration Services], error outputs
- populating error columns [Integration Services]
- redirecting error output [Integration Services]
- error outputs [Integration Services]
- asynchronous error outputs [Integration Services]
ms.assetid: a2a3e7c8-1de2-45b3-97fb-60415d3b0934
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a05a41065c52fadbe7f7fc065771727310e58149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607901"
---
# <a name="using-error-outputs-in-a-data-flow-component"></a><span data-ttu-id="7b970-102">Verwenden von Fehlerausgaben in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="7b970-102">Using Error Outputs in a Data Flow Component</span></span>
  <span data-ttu-id="7b970-103">Spezielle <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>-Objekte, die als Fehlerausgaben bezeichnet werden, können zu Komponenten hinzugefügt werden, sodass die Komponente Zeilen, die bei der Ausführung nicht verarbeitet werden können, umleiten kann.</span><span class="sxs-lookup"><span data-stu-id="7b970-103">Special <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects called error outputs can be added to components to let the component redirect rows that it cannot process during execution.</span></span> <span data-ttu-id="7b970-104">Die Probleme, die bei einer Komponente auftreten können, lassen sich meist in Fehler oder abgeschnittene Daten einteilen und sind komponentenspezifisch.</span><span class="sxs-lookup"><span data-stu-id="7b970-104">The problems a component may encounter are generally categorized as errors or truncations, and are specific to each component.</span></span> <span data-ttu-id="7b970-105">Komponenten, die Fehlerausgaben bereitstellen, bieten den Benutzern der Komponente die Flexibilität, Fehlerbedingungen durch Herausfiltern von Fehlerzeilen aus dem Resultset, durch Behandeln der Komponente als fehlerhaft, wenn ein Problem auftritt, oder durch Ignorieren von Fehlern und Fortsetzen des Vorgangs zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="7b970-105">Components that provide error outputs give users of the component the flexibility to handle error conditions by filtering error rows out of the result set, by failing the component when a problem occurs, or by ignoring errors and continuing.</span></span>  
  
 <span data-ttu-id="7b970-106">Um Fehlerausgaben in einer Komponente zu implementieren oder zu unterstützen müssen Sie zunächst die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A>-Eigenschaft der Komponente auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b970-106">To implement and support error outputs in a component, you must first set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A> property of the component to `true`.</span></span> <span data-ttu-id="7b970-107">Dann müssen Sie eine Ausgabe zu der Komponente hinzufügen, bei der die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b970-107">Then you must add an output to the component that has its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property set to `true`.</span></span> <span data-ttu-id="7b970-108">Zuletzt muss die Komponente Code enthalten, der Zeilen an die Fehlerausgabe umleitet, wenn Fehler auftreten oder Daten abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="7b970-108">Finally, the component must contain code that redirects rows to the error output when errors or truncations occur.</span></span> <span data-ttu-id="7b970-109">In diesem Thema werden diese drei Schritte beschrieben und die Unterschiede zwischen synchronen und asynchronen Fehlerausgaben erklärt.</span><span class="sxs-lookup"><span data-stu-id="7b970-109">This topic covers these three steps and explains the differences between synchronous and asynchronous error outputs.</span></span>  
  
## <a name="creating-an-error-output"></a><span data-ttu-id="7b970-110">Erstellen einer Fehlerausgabe</span><span class="sxs-lookup"><span data-stu-id="7b970-110">Creating an Error Output</span></span>  
 <span data-ttu-id="7b970-111">Sie erstellen eine Fehlerausgabe, indem Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A> aufrufen und dann die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A>-Eigenschaft der neuen Ausgabe auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b970-111">You create an error output by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A>, and then setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property of the new output to `true`.</span></span> <span data-ttu-id="7b970-112">Wenn die Ausgabe asynchron ist, müssen keine weiteren Schritte für die Ausgabe durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b970-112">If the output is asynchronous, nothing else must be done to the output.</span></span> <span data-ttu-id="7b970-113">Wenn die Ausgabe synchron ist und wenn eine andere Ausgabe vorhanden ist, die mit dieser Eingabe synchron ist, müssen Sie auch die Eigenschaften <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b970-113">If the output is synchronous, and there is another output that is synchronous to the same input, you must also set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> properties.</span></span> <span data-ttu-id="7b970-114">Beide Eigenschaften müssen dieselben Werte wie die andere Ausgabe aufweisen, die mit dieser Eingabe synchron ist.</span><span class="sxs-lookup"><span data-stu-id="7b970-114">Both properties should have the same values as the other output that is synchronous to the same input.</span></span> <span data-ttu-id="7b970-115">Wenn diese Eigenschaften nicht auf einen Wert ungleich null festgelegt werden, werden die von der Eingabe bereitgestellten Zeilen an die beiden Ausgaben gesendet, die mit der Eingabe synchron sind.</span><span class="sxs-lookup"><span data-stu-id="7b970-115">If these properties are not set to a non-zero value, the rows provided by the input are sent to both outputs that are synchronous to the input.</span></span>  
  
 <span data-ttu-id="7b970-116">Wenn bei einer Komponente während der Ausführung Fehler auftreten oder Daten abgeschnitten werden, setzt die Komponente den Vorgang anhand der Einstellungen der Eigenschaften <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> der Eingabe oder Ausgabe oder Eingabe- oder Ausgabespalte fort, an der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7b970-116">When a component encounters an error or truncation during execution, it proceeds based on the settings of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> properties of the input or output, or input or output column, where the error occurred.</span></span> <span data-ttu-id="7b970-117">Der Wert dieser Eigenschaften muss standardmäßig auf <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7b970-117">The value of these properties should be set by default to <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed>.</span></span> <span data-ttu-id="7b970-118">Wenn die Fehlerausgabe der Komponente mit einer Downstreamkomponente verbunden ist, wird diese Eigenschaft vom Benutzer der Komponente festgelegt, sodass der Benutzer bestimmen kann, wie die Komponente den Fehler oder die abgeschnittenen Daten behandelt.</span><span class="sxs-lookup"><span data-stu-id="7b970-118">When the error output of the component is connected to a downstream component, this property is set by the user of the component and lets the user control how the component handles the error or truncation.</span></span>  
  
## <a name="populating-error-columns"></a><span data-ttu-id="7b970-119">Auffüllen von Fehlerspalten</span><span class="sxs-lookup"><span data-stu-id="7b970-119">Populating Error Columns</span></span>  
 <span data-ttu-id="7b970-120">Beim Erstellen einer Fehlerausgabe fügt der Datenflusstask automatisch zwei Spalten zur Ausgabespaltenauflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b970-120">When an error output is created, the data flow task automatically adds two columns to the output column collection.</span></span> <span data-ttu-id="7b970-121">Diese Spalten werden von Komponenten verwendet, um die ID der Spalte anzugeben, die den Fehler oder die abgeschnittenen Daten verursacht hat, und um den komponentenspezifischen Fehlercode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b970-121">These columns are used by components to specify the ID of the column that caused the error or truncation, and to provide the component-specific error code.</span></span> <span data-ttu-id="7b970-122">Diese Spalten werden automatisch erstellt. Die in den Spalten enthaltenen Werte müssen jedoch von der Komponente festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7b970-122">These columns are generated automatically, but the values contained in the columns must be set by the component.</span></span>  
  
 <span data-ttu-id="7b970-123">Welche Methode zum Festlegen der Werte dieser Spalten verwendet wird, hängt davon ab, ob es sich um eine synchrone oder asynchrone Fehlerausgabe handelt.</span><span class="sxs-lookup"><span data-stu-id="7b970-123">The method used to set the values of these columns depends on whether the error output is synchronous or asynchronous.</span></span> <span data-ttu-id="7b970-124">Komponenten mit synchronen Ausgaben rufen die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>-Methode auf, die im nächsten Abschnitt ausführlich beschrieben wird, und stellen den Fehlercode und die Fehlerspaltenwerte als Parameter bereit.</span><span class="sxs-lookup"><span data-stu-id="7b970-124">Components with synchronous outputs call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method, discussed in more detail in the next section, and provide the error code and error column values as parameters.</span></span> <span data-ttu-id="7b970-125">Bei Komponenten mit asynchronen Ausgaben gibt es zwei Möglichkeiten zum Festlegen der Werte dieser Spalten.</span><span class="sxs-lookup"><span data-stu-id="7b970-125">Components with asynchronous outputs have two choices for setting the values of these columns.</span></span> <span data-ttu-id="7b970-126">Sie können entweder die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>-Methode des Ausgabepuffers aufrufen und die Werte bereitstellen, oder die Fehlerspalten mithilfe von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> im Puffer suchen und die Werte für die Spalten direkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b970-126">They can either call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method of the output buffer and supply the values, or locate the error columns in the buffer by using <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> and set the values for the columns directly.</span></span> <span data-ttu-id="7b970-127">Da sich die Namen der Spalten oder der Speicherort in der Ausgabespaltenauflistung jedoch möglicherweise geändert haben, stellt die zweite Möglichkeit keine zuverlässige Methode dar.</span><span class="sxs-lookup"><span data-stu-id="7b970-127">However, because the names of the columns may have been changed, or their location in the output column collection may have been modified, the latter method may not be reliable.</span></span> <span data-ttu-id="7b970-128">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>-Methode legt die Werte automatisch in diesen Fehlerspalten fest, ohne dass sie manuell gesucht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7b970-128">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method automatically sets the values in these error columns without having to locate them manually.</span></span>  
  
 <span data-ttu-id="7b970-129">Wenn Sie die Fehlerbeschreibung zu einem bestimmten Fehlercode abrufen müssen, können Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle verwenden, die über die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>-Eigenschaft der Komponente verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7b970-129">If you need to obtain the error description that corresponds to a specific error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span>  
  
 <span data-ttu-id="7b970-130">In den folgenden Codebeispielen wird eine Komponente gezeigt, die über eine Eingabe und zwei Ausgaben, darunter eine Fehlerausgabe, verfügt.</span><span class="sxs-lookup"><span data-stu-id="7b970-130">The following code examples show a component that has an input and two outputs, including an error output.</span></span> <span data-ttu-id="7b970-131">Im ersten Beispiel wird gezeigt, wie eine zur Eingabe synchrone Fehlerausgabe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b970-131">The first example shows how to create an error output that is synchronous to the input.</span></span> <span data-ttu-id="7b970-132">Im zweiten Beispiel wird gezeigt, wie eine asynchrone Fehlerausgabe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b970-132">The second example shows how to create an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
    output.SynchronousInputID = input.ID;  
    output.ExclusionGroup = 1;  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.IsErrorOut = true;  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.SynchronousInputID = input.ID;  
    errorOutput.ExclusionGroup = 1;  
  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the input.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the default output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 output.SynchronousInputID = input.ID   
 output.ExclusionGroup = 1   
  
 ' Create the error output.  
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.IsErrorOut = True   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.SynchronousInputID = input.ID   
 errorOutput.ExclusionGroup = 1   
  
End Sub  
```  
  
 <span data-ttu-id="7b970-133">Mit dem folgenden Beispielcode wird eine asynchrone Fehlerausgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="7b970-133">The following code example creates an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.IsErrorOut = true;  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 ' Create the input.  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the default output.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the error output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.IsErrorOut = True   
  
End Sub  
```  
  
## <a name="redirecting-a-row-to-an-error-output"></a><span data-ttu-id="7b970-134">Umleiten einer Zeile an eine Fehlerausgabe</span><span class="sxs-lookup"><span data-stu-id="7b970-134">Redirecting a Row to an Error Output</span></span>  
 <span data-ttu-id="7b970-135">Nach dem Hinzufügen einer Fehlerausgabe zu einer Komponente müssen Sie Code bereitstellen, der den Fehler oder die abgeschnittenen Daten je nach Komponente behandelt und die Zeilen mit dem Fehler oder den abgeschnittenen Daten an die Fehlerausgabe umleitet.</span><span class="sxs-lookup"><span data-stu-id="7b970-135">After adding an error output to a component, you must provide code that handles the error or truncation conditions specific to the component and redirects the error or truncation rows to the error output.</span></span> <span data-ttu-id="7b970-136">Hierzu haben Sie zwei Möglichkeiten, je nachdem, ob es sich um eine synchrone oder asynchrone Fehlerausgabe handelt.</span><span class="sxs-lookup"><span data-stu-id="7b970-136">You can do this in two ways, depending on whether the error output is synchronous or asynchronous.</span></span>  
  
### <a name="redirecting-a-row-with-synchronous-outputs"></a><span data-ttu-id="7b970-137">Umleiten einer Zeile mit synchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="7b970-137">Redirecting a Row with Synchronous Outputs</span></span>  
 <span data-ttu-id="7b970-138">Zeilen werden an synchrone Ausgaben gesendet, indem die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>-Klasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7b970-138">Rows are sent to synchronous outputs by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> class.</span></span> <span data-ttu-id="7b970-139">Der Methodenaufruf enthält die ID der Fehlerausgabe, den komponentendefinierten Fehlercode und den Index der Spalte, die von der Komponente nicht verarbeitet werden konnte, als Parameter.</span><span class="sxs-lookup"><span data-stu-id="7b970-139">The method call includes as parameters the ID of the error output, the component-defined error code, and the index of the column that the component was unable to process.</span></span>  
  
 <span data-ttu-id="7b970-140">Im folgenden Codebeispiel wird gezeigt, wie eine Zeile in einem Puffer mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>-Methode an eine synchrone Fehlerausgabe geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7b970-140">The following code example demonstrates how to direct a row in a buffer to a synchronous error output using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput(int inputID, PipelineBuffer buffer)  
{  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
  
        // This code sample assumes the component has two outputs, one the default,  
        // the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
        // is 0, then the default output is the second output in the collection.  
        int defaultOutputID = -1;  
        int errorOutputID = -1;  
        int errorOutputIndex = -1;  
  
        GetErrorOutputInfo(ref errorOutputID,ref errorOutputIndex);  
  
        if (errorOutputIndex == 0)  
            defaultOutputID = ComponentMetaData.OutputCollection[1].ID;  
        else  
            defaultOutputID = ComponentMetaData.OutputCollection[0].ID;  
  
        while (buffer.NextRow())  
        {  
            try  
            {  
                // TODO: Implement code to process the columns in the buffer row.  
  
                // Ideally, your code should detect potential exceptions before they occur, rather  
                // than having a generic try/catch block such as this.   
                // However, because the error or truncation implementation is specific to each component,  
                // this sample focuses on actually directing the row, and not a single error or truncation.  
  
                // Unless an exception occurs, direct the row to the default   
                buffer.DirectRow(defaultOutputID);  
            }  
            catch  
            {  
                // Yes, has the user specified to redirect the row?  
                if (input.ErrorRowDisposition == DTSRowDisposition.RD_RedirectRow)  
                {  
                    // Yes, direct the row to the error output.  
                    // TODO: Add code to include the errorColumnIndex.  
                    buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex);  
                }  
                else if (input.ErrorRowDisposition == DTSRowDisposition.RD_FailComponent || input.ErrorRowDisposition == DTSRowDisposition.RD_NotUsed)  
                {  
                    // No, the user specified to fail the component, or the error row disposition was not set.  
                    throw new Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.");  
                }  
                else  
                {  
                    // No, the user specified to ignore the failure so   
                    // direct the row to the default output.  
                    buffer.DirectRow(defaultOutputID);  
                }  
  
            }  
        }  
}  
```  
  
```vb  
Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)   
  
   ' This code sample assumes the component has two outputs, one the default,  
   ' the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
   ' is 0, then the default output is the second output in the collection.  
   Dim defaultOutputID As Integer = -1   
   Dim errorOutputID As Integer = -1   
   Dim errorOutputIndex As Integer = -1   
  
   GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
  
   If errorOutputIndex = 0 Then   
     defaultOutputID = ComponentMetaData.OutputCollection(1).ID   
   Else   
     defaultOutputID = ComponentMetaData.OutputCollection(0).ID   
   End If   
  
   While buffer.NextRow   
     Try   
       ' TODO: Implement code to process the columns in the buffer row.  
  
       ' Ideally, your code should detect potential exceptions before they occur, rather  
       ' than having a generic try/catch block such as this.   
       ' However, because the error or truncation implementation is specific to each component,  
       ' this sample focuses on actually directing the row, and not a single error or truncation.  
  
       ' Unless an exception occurs, direct the row to the default   
       buffer.DirectRow(defaultOutputID)   
     Catch   
       ' Yes, has the user specified to redirect the row?  
       If input.ErrorRowDisposition = DTSRowDisposition.RD_RedirectRow Then   
         ' Yes, direct the row to the error output.  
         ' TODO: Add code to include the errorColumnIndex.  
         buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex)   
       Else   
         If input.ErrorRowDisposition = DTSRowDisposition.RD_FailComponent OrElse input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed Then   
           ' No, the user specified to fail the component, or the error row disposition was not set.  
           Throw New Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.")   
         Else   
           ' No, the user specified to ignore the failure so   
           ' direct the row to the default output.  
           buffer.DirectRow(defaultOutputID)   
         End If   
       End If   
     End Try   
   End While   
End Sub  
```  
  
### <a name="redirecting-a-row-with-asynchronous-outputs"></a><span data-ttu-id="7b970-141">Umleiten einer Zeile mit asynchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="7b970-141">Redirecting a Row with Asynchronous Outputs</span></span>  
 <span data-ttu-id="7b970-142">Komponenten mit asynchronen Ausgaben senden Zeilen anders als Komponenten mit synchronen Fehlerausgaben an eine Fehlerausgabe, indem sie eine Zeile explizit zur Ausgabe <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b970-142">Instead of directing rows to an output, as is done with synchronous error outputs, components with asynchronous outputs send a row to an error output by explicitly adding a row to the output <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span></span> <span data-ttu-id="7b970-143">Beim Implementieren einer Komponente, die asynchrone Fehlerausgaben verwendet, müssen Spalten, die Downstreamkomponenten bereitgestellt werden, zur Fehlerausgabe hinzugefügt werden. Zudem muss der Ausgabepuffer für die Fehlerausgabe, die der Komponente während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode bereitgestellt wird, im Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7b970-143">Implementing a component that uses asynchronous error outputs requires adding columns to the error output that are provided to downstream components, and caching the output buffer for the error output that is provided to the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="7b970-144">Die Einzelheiten zur Implementierung einer Komponente mit asynchronen Ausgängen werden im Thema [Entwickeln einer benutzerdefinierten Transformationskomponente mit asynchronen Ausgaben](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) ausführlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="7b970-144">The details of implementing a component with asynchronous outputs are covered in detail in the topic [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span> <span data-ttu-id="7b970-145">Wenn der Fehlerausgabe Spalten nicht explizit hinzugefügt werden, enthält die dem Ausgabepuffer hinzugefügte Pufferzeile nur die beiden Fehlerspalten.</span><span class="sxs-lookup"><span data-stu-id="7b970-145">If columns are not explicitly added to the error output, the buffer row that is added to the output buffer contains only the two error columns.</span></span>  
  
 <span data-ttu-id="7b970-146">Um eine Zeile an eine asynchrone Fehlerausgabe zu senden, müssen Sie eine Zeile zum Fehlerausgabepuffer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b970-146">To send a row to an asynchronous error output, you must add a row to the error output buffer.</span></span> <span data-ttu-id="7b970-147">Es kann vorkommen, dass eine Zeile bereits zum Nichtfehlerausgabepuffer hinzugefügt wurde. In diesem Fall müssen Sie diese Zeile mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A>-Methode entfernen.</span><span class="sxs-lookup"><span data-stu-id="7b970-147">Sometimes, a row may have already been added to the non-error output buffer and you must remove this row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A> method.</span></span> <span data-ttu-id="7b970-148">Als Nächstes legen Sie die Werte der Ausgabepufferspalten fest. Abschließend rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>-Methode auf, um den komponentenspezifischen Fehlercode und den Fehlerspaltenwert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b970-148">Next you set the output buffer columns values, and finally, you call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method to provide the component-specific error code and the error column value.</span></span>  
  
 <span data-ttu-id="7b970-149">Im folgenden Beispiel wird die Verwendung einer Fehlerausgabe für eine Komponente mit asynchronen Ausgaben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7b970-149">The following example demonstrates how to use an error output for a component with asynchronous outputs.</span></span> <span data-ttu-id="7b970-150">Wenn der simulierte Fehler auftritt, fügt die Komponente eine Zeile zum Fehlerausgabepuffer hinzu, kopiert die Werte, die zuvor zum Nichtfehlerausgabepuffer hinzugefügt wurden, in den Fehlerausgabepuffer, entfernt die Zeile, die zum Nichtfehlerausgabepuffer hinzugefügt wurde, und legt abschließend den Fehlercode und die Fehlerspaltenwerte durch Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>-Methode fest.</span><span class="sxs-lookup"><span data-stu-id="7b970-150">When the simulated error occurs, the component adds a row to the error output buffer, copies the values that were previously added to the non-error output buffer to the error output buffer, removes the row that was added to the non-error output buffer, and, finally, sets the error code and error column values by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method.</span></span>  
  
```csharp  
int []columnIndex;  
int errorOutputID = -1;  
int errorOutputIndex = -1;  
  
public override void PreExecute()  
{  
    IDTSOutput100 defaultOutput = null;  
  
    this.GetErrorOutputInfo(ref errorOutputID, ref errorOutputIndex);  
    foreach (IDTSOutput100 output in ComponentMetaData.OutputCollection)  
    {  
        if (output.ID != errorOutputID)  
            defaultOutput = output;  
    }  
  
    columnIndex = new int[defaultOutput.OutputColumnCollection.Count];  
  
    for(int col =0 ; col < defaultOutput.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 column = defaultOutput.OutputColumnCollection[col];  
        columnIndex[col] = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID);  
    }  
}  
  
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        if (outputIDs[x] == errorOutputID)  
            this.errorBuffer = buffers[x];  
        else  
            this.defaultBuffer = buffers[x];  
    }  
  
    int rows = 100;  
  
    Random random = new Random(System.DateTime.Now.Millisecond);  
  
    for (int row = 0; row < rows; row++)  
    {  
        try  
        {  
            defaultBuffer.AddRow();  
  
            for (int x = 0; x < columnIndex.Length; x++)  
                defaultBuffer[columnIndex[x]] = random.Next();  
  
            // Simulate an error.  
            if ((row % 2) == 0)  
                throw new Exception("A simulated error.");  
        }  
        catch  
        {  
            // Add a row to the error buffer.  
            errorBuffer.AddRow();  
  
            // Get the values from the default buffer  
            // and copy them to the error buffer.  
            for (int x = 0; x < columnIndex.Length; x++)  
                errorBuffer[columnIndex[x]] = defaultBuffer[columnIndex[x]];  
  
            // Set the error information.  
            errorBuffer.SetErrorInfo(errorOutputID, 1, 0);  
  
            // Remove the row that was added to the default buffer.  
            defaultBuffer.RemoveRow();  
        }  
    }  
  
    if (defaultBuffer != null)  
        defaultBuffer.SetEndOfRowset();  
  
    if (errorBuffer != null)  
        errorBuffer.SetEndOfRowset();  
}  
```  
  
```vb  
Private columnIndex As Integer()   
Private errorOutputID As Integer = -1   
Private errorOutputIndex As Integer = -1   
  
Public  Overrides Sub PreExecute()   
 Dim defaultOutput As IDTSOutput100 = Nothing   
 Me.GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
 For Each output As IDTSOutput100 In ComponentMetaData.OutputCollection   
   If Not (output.ID = errorOutputID) Then   
     defaultOutput = output   
   End If   
 Next   
 columnIndex = New Integer(defaultOutput.OutputColumnCollection.Count) {}   
 Dim col As Integer = 0   
 While col < defaultOutput.OutputColumnCollection.Count   
   Dim column As IDTSOutputColumn100 = defaultOutput.OutputColumnCollection(col)   
   columnIndex(col) = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID)   
   System.Math.Min(System.Threading.Interlocked.Increment(col),col-1)   
 End While   
End Sub   
  
Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())   
 Dim x As Integer = 0   
 While x < outputs   
   If outputIDs(x) = errorOutputID Then   
     Me.errorBuffer = buffers(x)   
   Else   
     Me.defaultBuffer = buffers(x)   
   End If   
   System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
 End While   
 Dim rows As Integer = 100   
 Dim random As Random = New Random(System.DateTime.Now.Millisecond)   
 Dim row As Integer = 0   
 While row < rows   
   Try   
     defaultBuffer.AddRow   
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       defaultBuffer(columnIndex(x)) = random.Next   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Simulate an error.  
     If (row Mod 2) = 0 Then   
       Throw New Exception("A simulated error.")   
     End If   
   Catch   
     ' Add a row to the error buffer.  
     errorBuffer.AddRow   
     ' Get the values from the default buffer  
     ' and copy them to the error buffer.  
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       errorBuffer(columnIndex(x)) = defaultBuffer(columnIndex(x))   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Set the error information.  
     errorBuffer.SetErrorInfo(errorOutputID, 1, 0)   
     ' Remove the row that was added to the default buffer.  
     defaultBuffer.RemoveRow   
   End Try   
   System.Math.Min(System.Threading.Interlocked.Increment(row),row-1)   
 End While   
 If Not (defaultBuffer Is Nothing) Then   
   defaultBuffer.SetEndOfRowset   
 End If   
 If Not (errorBuffer Is Nothing) Then   
   errorBuffer.SetEndOfRowset   
 End If   
End Sub  
```  
  
<span data-ttu-id="7b970-151">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="7b970-151">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7b970-152">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="7b970-152">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7b970-153">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="7b970-153">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7b970-154">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7b970-154">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b970-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b970-155">See Also</span></span>  
 <span data-ttu-id="7b970-156">[Fehlerbehandlung in Daten](../../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="7b970-156">[Error Handling in Data](../../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="7b970-157">[Using Error Outputs](using-error-outputs-in-a-data-flow-component.md) (Verwenden von Fehlerausgaben)</span><span class="sxs-lookup"><span data-stu-id="7b970-157">[Using Error Outputs](using-error-outputs-in-a-data-flow-component.md)</span></span>  
  
  
