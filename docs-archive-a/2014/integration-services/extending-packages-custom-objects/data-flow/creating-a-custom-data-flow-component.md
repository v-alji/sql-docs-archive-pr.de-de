---
title: Erstellen einer benutzerdefinierten Datenflusskomponente | Microsoft-Dokumentation
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
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619229"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="94c57-102">Erstellen einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="94c57-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="94c57-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] stellt der Datenflusstask ein Objektmodell zur Verfügung, das Entwicklern das Erstellen von benutzerdefinierten Datenflusskomponenten (Quellen, Transformationen und Ziele) anhand von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] und verwaltetem Code ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="94c57-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="94c57-104">Ein Datenflusstask besteht aus Komponenten, die eine <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle und eine Auflistung von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>-Objekten enthalten, die die Verschiebung von Daten zwischen Komponenten definieren.</span><span class="sxs-lookup"><span data-stu-id="94c57-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94c57-105">Wenn Sie einen benutzerdefinierten Anbieter erstellen, müssen Sie die Datei "ProviderDescriptors.xml" mit den Metadatenspaltenwerten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="94c57-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="94c57-106">Entwurfszeit und Laufzeit</span><span class="sxs-lookup"><span data-stu-id="94c57-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="94c57-107">Vor der Ausführung befindet sich der Datenflusstask im so genannten Entwurfszeitstatus, während er inkrementelle Änderungen durchläuft.</span><span class="sxs-lookup"><span data-stu-id="94c57-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="94c57-108">Zu den Änderungen kann das Hinzufügen oder Entfernen von Komponenten, das Hinzufügen oder Entfernen von Pfadobjekten zur Verbindung von Komponenten sowie Änderungen an den Metadaten der Komponenten gehören.</span><span class="sxs-lookup"><span data-stu-id="94c57-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="94c57-109">Wenn Metadaten-Änderungen auftreten, kann die Komponente die Änderungen überwachen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="94c57-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="94c57-110">Zum Beispiel kann eine Komponente bestimmte Änderungen nicht zulassen oder zusätzliche Änderungen als Reaktion auf eine Änderung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="94c57-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="94c57-111">Zur Entwurfszeit interagiert der Designer mit einer Komponente durch die Entwurfszeitschnittstelle <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="94c57-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="94c57-112">Zur Ausführungszeit wird vom Datenflusstask die Reihenfolge von Komponenten überprüft, ein Ausführungsplan vorbereitet und ein Pool von Arbeitsthreads verwaltet, die den Arbeitsplan ausführen.</span><span class="sxs-lookup"><span data-stu-id="94c57-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="94c57-113">Auch wenn jeder Arbeitsthread einige interne Arbeiten im Datenflusstask ausführt, besteht die Hauptaufgabe des Arbeitsthread darin, die Methoden der Komponenten über die Laufzeitschnittstelle <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="94c57-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="94c57-114">Erstellen einer Komponente</span><span class="sxs-lookup"><span data-stu-id="94c57-114">Creating a Component</span></span>  
 <span data-ttu-id="94c57-115">Zum Erstellen einer Datenflusskomponente leiten Sie eine Klasse von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse ab, wenden die <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>-Klasse an und überschreiben dann die entsprechenden Methoden der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="94c57-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="94c57-116">Mit <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> werden die Schnittstellen <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> implementiert und die Methoden zum Überschreiben in der Komponente zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="94c57-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="94c57-117">Abhängig von den in der Komponente verwendeten Objekten erfordert Ihr Projekt Verweise auf einige oder alle der folgenden Assemblys:</span><span class="sxs-lookup"><span data-stu-id="94c57-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="94c57-118">Funktion</span><span class="sxs-lookup"><span data-stu-id="94c57-118">Feature</span></span>|<span data-ttu-id="94c57-119">Verweis auf Assembly</span><span class="sxs-lookup"><span data-stu-id="94c57-119">Assembly to reference</span></span>|<span data-ttu-id="94c57-120">Zu importierender Namespace</span><span class="sxs-lookup"><span data-stu-id="94c57-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="94c57-121">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="94c57-121">Data flow</span></span>|<span data-ttu-id="94c57-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="94c57-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="94c57-123">Datenfluss-Wrapper</span><span class="sxs-lookup"><span data-stu-id="94c57-123">Data flow wrapper</span></span>|<span data-ttu-id="94c57-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="94c57-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="94c57-125">Typ</span><span class="sxs-lookup"><span data-stu-id="94c57-125">Runtime</span></span>|<span data-ttu-id="94c57-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="94c57-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="94c57-127">Laufzeit-Wrapper</span><span class="sxs-lookup"><span data-stu-id="94c57-127">Runtime wrapper</span></span>|<span data-ttu-id="94c57-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="94c57-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="94c57-129">Im folgenden Codebeispiel werden eine einfache, von der Basisklasse abgeleitete Komponente veranschaulicht und <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> angewendet.</span><span class="sxs-lookup"><span data-stu-id="94c57-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="94c57-130">Sie müssen einen Verweis auf die DTSPipelineWrap-Assembly hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="94c57-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="94c57-131">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="94c57-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="94c57-132">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="94c57-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="94c57-133">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="94c57-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="94c57-134">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="94c57-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c57-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94c57-135">See Also</span></span>  
 [<span data-ttu-id="94c57-136">Entwickeln einer Benutzeroberfläche für eine Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="94c57-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
