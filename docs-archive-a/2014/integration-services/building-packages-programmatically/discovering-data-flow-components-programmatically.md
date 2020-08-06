---
title: Programmgesteuertes Auffinden von Datenflusskomponenten | Microsoft-Dokumentation
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
- PipelineComponentInfos collection
- data flow task [Integration Services], components
- discovering data flow components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: ff92a96a-8af6-4532-82cc-c0bbff92401b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a18102f38f1ad06e918efe2ca529185d40deef9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700148"
---
# <a name="discovering-data-flow-components-programmatically"></a><span data-ttu-id="8ba20-102">Programmgesteuertes Auffinden von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="8ba20-102">Discovering Data Flow Components Programmatically</span></span>
  <span data-ttu-id="8ba20-103">Nachdem Sie einem Paket einen Datenflusstask hinzugefügt haben, besteht der nächste Schritt darin zu bestimmen, welche Datenflusskomponenten für Sie zur Verwendung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8ba20-103">After you have added a data flow task to a package, your next step may be to determine what data flow components are available for your use.</span></span> <span data-ttu-id="8ba20-104">Sie können die Datenflussquellen, Transformationen und Ziele, die auf dem lokalen Computer installiert und verfügbar sind, programmgesteuert auffinden.</span><span class="sxs-lookup"><span data-stu-id="8ba20-104">You can programmatically discover the data flow sources, transformations, and destinations that are installed and available on the local computer.</span></span> <span data-ttu-id="8ba20-105">Informationen zum Hinzufügen eines Datenflusstasks zum Paket finden Sie unter [Programmgesteuertes Hinzufügen des Datenflusstasks](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="8ba20-105">For information about adding a data flow task to the package, see [Adding the Data Flow Task Programmatically](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span></span>  
  
## <a name="discovering-components"></a><span data-ttu-id="8ba20-106">Auffinden von Komponenten</span><span class="sxs-lookup"><span data-stu-id="8ba20-106">Discovering Components</span></span>  
 <span data-ttu-id="8ba20-107">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse stellt die <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A>-Auflistung bereit, die ein <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo>-Objekt für die einzelnen Komponenten enthält, die korrekt auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8ba20-107">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class provides the <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> collection, which contains a <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> object for each component correctly installed on the local computer.</span></span> <span data-ttu-id="8ba20-108"><xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> enthält Informationen zu einer Komponente, z. B. ihren Namen, eine Beschreibung und ihren Erstellungsnamen.</span><span class="sxs-lookup"><span data-stu-id="8ba20-108">Each <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contains information about a component such as its name, description, and creation name.</span></span> <span data-ttu-id="8ba20-109">Sie können den in der <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A>-Eigenschaft zurückgegebenen Wert verwenden, um die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>-Eigenschaft von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> festzulegen, wenn Sie einem Paket eine Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ba20-109">You can use the value returned in the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property to set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> when you add a component to a package.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8ba20-110">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8ba20-110">Next Step</span></span>  
 <span data-ttu-id="8ba20-111">Nach dem Auffinden verfügbarer Komponenten besteht der nächste Schritt darin, die Komponenten hinzuzufügen und zu konfigurieren. Dies wird im nächsten Thema – [Programmgesteuertes Hinzufügen von Datenflusskomponenten](../building-packages-programmatically/adding-data-flow-components-programmatically.md) – beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ba20-111">After discovering available components, the next step is to add and configure the components, which is discussed in the next topic, [Adding Data Flow Components Programmatically](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="8ba20-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ba20-112">Sample</span></span>  
 <span data-ttu-id="8ba20-113">Im folgenden Codebeispiel wird gezeigt, wie die <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos>-Auflistung des <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Objekts aufgezählt wird, um die auf dem lokalen Computer verfügbaren Datenflusskomponenten programmgesteuert aufzufinden.</span><span class="sxs-lookup"><span data-stu-id="8ba20-113">The following code sample shows how to enumerate the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object to programmatically discover the data flow components available on the local computer.</span></span> <span data-ttu-id="8ba20-114">Für dieses Beispiel ist ein Verweis auf die Microsoft.SqlServer.ManagedDTS-Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ba20-114">This sample requires a reference to the Microsoft.SqlServer.ManagedDTS assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application application = new Application();  
      PipelineComponentInfos componentInfos = application.PipelineComponentInfos;  
  
      foreach (PipelineComponentInfo componentInfo in componentInfos)  
      {  
        Console.WriteLine("Name: " + componentInfo.Name + "\n" +  
          " CreationName: " + componentInfo.CreationName + "\n");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim application As Application = New Application()  
  
    Dim componentInfos As PipelineComponentInfos = application.PipelineComponentInfos  
  
    For Each componentInfo As PipelineComponentInfo In componentInfos  
      Console.WriteLine("Name: " & componentInfo.Name & vbCrLf & _  
        " CreationName: " & componentInfo.CreationName & vbCrLf)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="8ba20-115">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="8ba20-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8ba20-116">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="8ba20-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8ba20-117">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="8ba20-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8ba20-118">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ba20-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba20-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ba20-119">See Also</span></span>  
 [<span data-ttu-id="8ba20-120">Programmgesteuertes Hinzufügen von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="8ba20-120">Adding Data Flow Components Programmatically</span></span>](../building-packages-programmatically/adding-data-flow-components-programmatically.md)  
  
  
