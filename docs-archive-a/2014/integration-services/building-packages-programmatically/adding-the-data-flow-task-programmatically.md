---
title: Programmgesteuertes Hinzufügen des Datenflusstasks | Microsoft-Dokumentation
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
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616648"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="99c1e-102">Programmgesteuertes Hinzufügen des Datenflusstasks</span><span class="sxs-lookup"><span data-stu-id="99c1e-102">Adding the Data Flow Task Programmatically</span></span>
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="99c1e-103">umfasst einen Task namens Datenflusstask, der durch den <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>-Namespace im Objektmodell dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="99c1e-103">includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="99c1e-104">Der Datenflusstask ist ein spezialisierter Hochleistungstask, der dem Transformieren und Verschieben von Daten bei der Paketausführung dient.</span><span class="sxs-lookup"><span data-stu-id="99c1e-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="99c1e-105">Genau wie andere Tasks ist der Datenflusstask vom <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt umschlossen, und aus Sicht der Runtime-Engine ist dieser Task nur einer der Tasks im Paket.</span><span class="sxs-lookup"><span data-stu-id="99c1e-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="99c1e-106">Der Datenfluss enthält jedoch zusätzliche Objekte, die so genannten Datenflusskomponenten.</span><span class="sxs-lookup"><span data-stu-id="99c1e-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="99c1e-107">Diese Komponenten bewirken, dass Daten von einer Quelle an ein Ziel verschoben werden, was manchmal durch eine Transformation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="99c1e-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="99c1e-108">Die Komponenten definieren sowohl die Richtung des Verschiebens als auch die Art der Datentransformation.</span><span class="sxs-lookup"><span data-stu-id="99c1e-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="99c1e-109">Zum Konfigurieren des Datenflusstasks müssen dem Task Komponenten hinzugefügt und anschließend verbunden werden, damit der Datenfluss eingerichtet und die beabsichtigte Transformation erzielt wird.</span><span class="sxs-lookup"><span data-stu-id="99c1e-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="99c1e-110">In einem Datenflusstask gibt es drei Arten von Komponenten: **Datenflussquellen**, **Datenflusstransformationen** und **Datenflussziele**, die in dieser Reihenfolge in der [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer-Toolbox angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="99c1e-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="99c1e-111">Diese Typen werden auch einfacher als Quellen, Transformationen oder Ziele bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="99c1e-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="99c1e-112">Wie die Namen nahe legen, fließen Daten von einer Quelle zu einer Transformation und dann zu einem Ziel.</span><span class="sxs-lookup"><span data-stu-id="99c1e-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="99c1e-113">Dies ist eine vereinfachte Beschreibung des Datenflusses zur Veranschaulichung des Konzepts. Der Datenflusstask ist jedoch flexibel und leistungsfähig genug, um mehrere Quellen zu verarbeiten und zahlreiche Transformationen miteinander zu verbinden, die Ausgabe an mehrere Ziele senden.</span><span class="sxs-lookup"><span data-stu-id="99c1e-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="99c1e-114">Der Datenflusstask wird einem Paket auf die gleiche Weise wie andere Tasks hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="99c1e-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="99c1e-115">Nachdem der Task hinzugefügt wurde, wird er durch Hinzufügen von Komponenten zum Datenflusstask sowie Konfigurieren und Verbinden von Komponenten im Task konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="99c1e-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="99c1e-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99c1e-116">Sample</span></span>  
 <span data-ttu-id="99c1e-117">Im folgenden Codebeispiel wird gezeigt, wie einem Paket ein Datenflusstask hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="99c1e-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="99c1e-118">Für dieses Beispiel ist ein Verweis auf die Microsoft.SqlServer.PipelineHost-, Microsoft.SqlServer.DTSPipelineWrap- und Microsoft.SqlServer.ManagedDTS-Assemblys erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99c1e-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
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
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="99c1e-119">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="99c1e-119">External Resources</span></span>  
 <span data-ttu-id="99c1e-120">Blogbeitrag, [EzAPI – Updated for SQL Server 2012 (EzAPI: für SQL Server 2012 aktualisiert)](https://go.microsoft.com/fwlink/?LinkId=243223), auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="99c1e-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="99c1e-121">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="99c1e-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="99c1e-122">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="99c1e-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="99c1e-123">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="99c1e-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="99c1e-124">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="99c1e-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c1e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99c1e-125">See Also</span></span>  
 [<span data-ttu-id="99c1e-126">Programmgesteuertes Auffinden von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="99c1e-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
