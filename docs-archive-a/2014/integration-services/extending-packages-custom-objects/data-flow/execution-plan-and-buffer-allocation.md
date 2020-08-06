---
title: Ausführungsplan und Pufferzuordnung | Microsoft-Dokumentation
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
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697026"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="d5688-102">Ausführungsplan und Pufferzuordnung</span><span class="sxs-lookup"><span data-stu-id="d5688-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="d5688-103">Vor der Ausführung überprüft der Datenflusstask seine Komponenten und erstellt einen Ausführungsplan für jede Komponentensequenz.</span><span class="sxs-lookup"><span data-stu-id="d5688-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="d5688-104">Dieser Abschnitt enthält Einzelheiten zum Ausführungsplan, zur Anzeige des Plans und zur Zuweisung von Eingabe- und Ausgabepuffern anhand des Plans.</span><span class="sxs-lookup"><span data-stu-id="d5688-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="d5688-105">Grundlegendes zum Ausführungsplan</span><span class="sxs-lookup"><span data-stu-id="d5688-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="d5688-106">Ein Ausführungsplan enthält Quell- und Arbeitsthreads. Diese umfassen jeweils Arbeitslisten, die bei Quellthreads Ausgabearbeitslisten und bei Arbeitsthreads Eingabe- und Ausgabearbeitslisten festlegen.</span><span class="sxs-lookup"><span data-stu-id="d5688-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="d5688-107">Die Quellthreads eines Ausführungsplans stellen die Quellkomponenten im Datenfluss dar. Sie sind im Ausführungsplan durch *SourceThread\*\*n* gekennzeichnet, wobei *n* die nullbasierte Nummer des Quellthreads ist.</span><span class="sxs-lookup"><span data-stu-id="d5688-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="d5688-108">Jeder Quellthread erstellt einen Puffer, legt eine Überwachung fest und ruft die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode der Quellkomponente auf.</span><span class="sxs-lookup"><span data-stu-id="d5688-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="d5688-109">Dies ist der Punkt, an dem die Ausführung beginnt und von dem die Daten stammen. Die Quellkomponente beginnt, den Ausgabepuffern Zeilen hinzuzufügen, die vom Datenflusstask bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5688-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="d5688-110">Sobald die Quellthreads ausgeführt werden, wird die Arbeitslast auf die Arbeitsthreads aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="d5688-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="d5688-111">Ein Arbeitsthread kann sowohl Eingabe- als auch Ausgabearbeitslisten enthalten und wird im Ausführungsplan mit *WorkThread\*\*n* gekennzeichnet, wobei *n* die nullbasierte Nummer des Arbeitsthreads ist.</span><span class="sxs-lookup"><span data-stu-id="d5688-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="d5688-112">Diese Threads enthalten Ausgabearbeitslisten, wenn das Diagramm eine Komponente mit asynchronen Ausgaben enthält.</span><span class="sxs-lookup"><span data-stu-id="d5688-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="d5688-113">Das folgende Beispiel eines Ausführungsplans zeigt einen Datenfluss, der eine Quellkomponente umfasst, die mit einer Transformation mit einer asynchronen Ausgabe verbunden ist, die über eine Verbindung mit einer Zielkomponente verfügt.</span><span class="sxs-lookup"><span data-stu-id="d5688-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="d5688-114">In diesem Beispiel enthält WorkThread0 eine Ausgabearbeitsliste, da die Transformationskomponente über eine asynchrone Ausgabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="d5688-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d5688-115">Der Ausführungsplan wird bei jeder Ausführung eines Pakets generiert. Er kann aufgezeichnet werden, indem Sie dem Paket einen Protokollanbieter hinzufügen, die Protokollierung aktivieren und das **PipelineExecutionPlan**-Ereignis auswählen.</span><span class="sxs-lookup"><span data-stu-id="d5688-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="d5688-116">Grundlegendes zur Pufferzuordnung</span><span class="sxs-lookup"><span data-stu-id="d5688-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="d5688-117">Der Datenflusstask erstellt anhand des Ausführungsplans Puffer, in denen die in den Ausgaben der Datenflusskomponenten definierten Spalten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d5688-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="d5688-118">Wenn der Datenfluss die Komponentensequenz durchläuft, wird der Puffer wiederverwendet, bis eine Komponente mit asynchroner Ausgabe auftritt.</span><span class="sxs-lookup"><span data-stu-id="d5688-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="d5688-119">In diesem Fall wird ein neuer Puffer erstellt, der die Ausgabespalten der asynchronen Ausgabe sowie diejenigen der Downstreamkomponenten umfasst.</span><span class="sxs-lookup"><span data-stu-id="d5688-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="d5688-120">Während der Ausführung verfügen die Komponenten über Zugriff auf die Puffer im aktuellen Quell- oder Arbeitsthread.</span><span class="sxs-lookup"><span data-stu-id="d5688-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="d5688-121">Bei dem Puffer handelt es sich entweder um einen Eingabepuffer, der von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode bereitgestellt wird, oder um einen Ausgabepuffer, der von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d5688-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="d5688-122">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> identifiziert jeden Puffer als Eingabe- oder Ausgabepuffer.</span><span class="sxs-lookup"><span data-stu-id="d5688-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="d5688-123">Transformationskomponenten mit asynchronen Ausgaben erhalten den vorhandenen Eingabepuffer von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>-Methode sowie den neuen Ausgabepuffer von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="d5688-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="d5688-124">Transformationskomponenten mit asynchronen Ausgaben sind der einzige Datenflusskomponententyp, der sowohl Eingabe- als auch Ausgabepuffer erhält.</span><span class="sxs-lookup"><span data-stu-id="d5688-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="d5688-125">Da der Puffer, der einer Komponente bereitgestellt wird, meist über mehr Spalten verfügt als die Komponente in ihren Eingabe- oder Ausgabespaltenauflistungen, können Komponentenentwickler die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>-Methode aufrufen, um eine Spalte im Puffer durch Angabe ihrer `LineageID` zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d5688-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="d5688-126">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d5688-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d5688-127">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d5688-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d5688-128">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d5688-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d5688-129">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5688-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
