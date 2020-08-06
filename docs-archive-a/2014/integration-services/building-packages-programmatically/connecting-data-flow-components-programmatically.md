---
title: Programmgesteuertes Verbinden von Datenflusskomponenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39494fee5314f309b79abfd30303fdd607fd3c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616644"
---
# <a name="connecting-data-flow-components-programmatically"></a><span data-ttu-id="25bd9-102">Programmgesteuertes Verbinden von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="25bd9-102">Connecting Data Flow Components Programmatically</span></span>
  <span data-ttu-id="25bd9-103">Nachdem Sie dem Datenflusstask Komponenten hinzugefügt haben, verbinden Sie diese, um eine Ausführungsstruktur zu erstellen. Diese spiegelt den Datenfluss von den Quellen über Transformationen bis hin zu den Zielen wider.</span><span class="sxs-lookup"><span data-stu-id="25bd9-103">After you have added components to the data flow task, you connect them to create an execution tree that represents the flow of data from sources through transformations to destinations.</span></span> <span data-ttu-id="25bd9-104">Sie verwenden <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>-Objekte, um die Komponenten im Datenfluss zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="25bd9-104">You use <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects to connect the components in the data flow.</span></span>  
  
## <a name="creating-a-path"></a><span data-ttu-id="25bd9-105">Erstellen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="25bd9-105">Creating a Path</span></span>  
 <span data-ttu-id="25bd9-106">Rufen Sie die neue Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe>-Schnittstelle auf, um einen neuen Pfad zu erstellen, und fügen Sie diesen der Pfadauflistung im Datenflusstask hinzu.</span><span class="sxs-lookup"><span data-stu-id="25bd9-106">Call the New method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface to create a new path and add it to the collection of paths in the data flow task.</span></span> <span data-ttu-id="25bd9-107">Diese Methode gibt ein neues, getrenntes <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>-Objekt zurück. Sie verwenden dieses anschließend, um zwei Komponenten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="25bd9-107">This method returns a new, disconnected <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, which you then use to connect two components.</span></span>  
  
 <span data-ttu-id="25bd9-108">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A>-Methode auf, um den Pfad zu verbinden und die Komponenten im Pfad über die Verbindung in Kenntnis zu setzen.</span><span class="sxs-lookup"><span data-stu-id="25bd9-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> method to connect the path and to notify the components participating in the path that they have been connected.</span></span> <span data-ttu-id="25bd9-109">Diese Methode akzeptiert eine <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> der Upstreamkomponente sowie eine <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> der Downstreamkomponente als Parameter.</span><span class="sxs-lookup"><span data-stu-id="25bd9-109">This method accepts an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the upstream component and an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> of the downstream component as parameters.</span></span> <span data-ttu-id="25bd9-110">Standardmäßig wird durch den Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>-Methode der Komponente eine einzelne Eingabe für Komponenten, die über Eingaben verfügen, und eine einzelne Ausgabe für Komponenten, die über Ausgaben verfügen, erstellt.</span><span class="sxs-lookup"><span data-stu-id="25bd9-110">By default, the call to the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method creates a single input for components that have inputs, and a single output for components that have outputs.</span></span> <span data-ttu-id="25bd9-111">Im folgenden Beispiel wird diese Standardeinstellung für die Ausgabe der Quelle und die Eingabe des Ziels verwendet.</span><span class="sxs-lookup"><span data-stu-id="25bd9-111">The following example uses this default output of the source and input of the destination.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="25bd9-112">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="25bd9-112">Next Step</span></span>  
 <span data-ttu-id="25bd9-113">Nachdem Sie einen Pfad zwischen zwei Komponenten eingerichtet haben, ist der nächste Schritt, Eingabespalten in der Downstreamkomponente zuzuordnen. Dieser Vorgang wird im nächsten Thema – [Programmgesteuertes Auswählen von Eingabespalten](../building-packages-programmatically/selecting-input-columns-programmatically.md) – erläutert.</span><span class="sxs-lookup"><span data-stu-id="25bd9-113">After you establish a path between two components, the next step is to map input columns in the downstream component, which is discussed in the next topic, [Selecting Input Columns Programmatically](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="25bd9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25bd9-114">Sample</span></span>  
 <span data-ttu-id="25bd9-115">Im folgenden Codebeispiel wird die Einrichtung eines Pfads zwischen zwei Komponenten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="25bd9-115">The following code sample shows how to establish a path between two components.</span></span>  
  
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
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 <span data-ttu-id="25bd9-116">}</span><span class="sxs-lookup"><span data-stu-id="25bd9-116">}</span></span>  
  
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
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="25bd9-117">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="25bd9-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="25bd9-118">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="25bd9-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="25bd9-119">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="25bd9-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="25bd9-120">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25bd9-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25bd9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25bd9-121">See Also</span></span>  
 [<span data-ttu-id="25bd9-122">Programmgesteuertes Auswählen von Eingabespalten</span><span class="sxs-lookup"><span data-stu-id="25bd9-122">Selecting Input Columns Programmatically</span></span>](../building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
