---
title: Entwickeln bestimmter Typen von Datenflusskomponenten | Microsoft-Dokumentation
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
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721630"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="6c874-102">Entwickeln bestimmter Arten von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="6c874-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="6c874-103">Dieser Abschnitt befasst sich mit den Besonderheiten der Entwicklung von Quellkomponenten, Transformationskomponenten mit synchronen und asynchronen Ausgaben sowie Zielkomponenten.</span><span class="sxs-lookup"><span data-stu-id="6c874-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="6c874-104">Weitere Informationen zur Entwicklung von Komponenten im Allgemeinen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6c874-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c874-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c874-105">In This Section</span></span>  
 [<span data-ttu-id="6c874-106">Entwickeln einer benutzerdefinierten Quellkomponente</span><span class="sxs-lookup"><span data-stu-id="6c874-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="6c874-107">Enthält Informationen zur Entwicklung einer Komponente, die auf Daten einer externen Datenquelle zugreift und diese Downstreamkomponenten im Datenfluss zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="6c874-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="6c874-108">Entwickeln einer benutzerdefinierten Transformationskomponente mit synchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="6c874-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="6c874-109">Enthält Informationen zur Entwicklung einer Transformationskomponente, deren Ausgaben synchron zu den Eingaben sind.</span><span class="sxs-lookup"><span data-stu-id="6c874-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="6c874-110">Diese Komponenten fügen dem Datenfluss keine Daten hinzu, sondern verarbeiten durchlaufende Daten.</span><span class="sxs-lookup"><span data-stu-id="6c874-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="6c874-111">Entwickeln einer benutzerdefinierten Transformationskomponente mit asynchronen Ausgaben</span><span class="sxs-lookup"><span data-stu-id="6c874-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="6c874-112">Enthält Informationen zur Entwicklung einer Transformationskomponente, deren Ausgaben nicht synchron zu den Eingaben sind.</span><span class="sxs-lookup"><span data-stu-id="6c874-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="6c874-113">Diese Komponenten empfangen Daten von Upstreamkomponenten, fügen jedoch dem Datenfluss auch Daten hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c874-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="6c874-114">Entwickeln einer benutzerdefinierten Zielkomponente</span><span class="sxs-lookup"><span data-stu-id="6c874-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="6c874-115">Enthält Informationen zur Entwicklung einer Komponente, die Zeilen von Upstreamkomponenten im Datenfluss erhält und diese in eine externe Datenquelle schreibt.</span><span class="sxs-lookup"><span data-stu-id="6c874-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6c874-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="6c874-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="6c874-117">Enthält die Klassen und Schnittstellen zur Erstellung benutzerdefinierter Datenflusskomponenten.</span><span class="sxs-lookup"><span data-stu-id="6c874-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="6c874-118">Enthält die nicht verwalteten Klassen und Schnittstellen des Datenflusstasks.</span><span class="sxs-lookup"><span data-stu-id="6c874-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="6c874-119">Entwickler verwenden diese sowie den verwalteten <xref:Microsoft.SqlServer.Dts.Pipeline>-Namespace bei der programmgesteuerten Erstellung eines Datenflusses oder von benutzerdefinierten Datenflusskomponenten.</span><span class="sxs-lookup"><span data-stu-id="6c874-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="6c874-120">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="6c874-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6c874-121">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="6c874-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6c874-122">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="6c874-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6c874-123">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6c874-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c874-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c874-124">See Also</span></span>  
 <span data-ttu-id="6c874-125">[Vergleichen von Skript Lösungen und benutzerdefinierten Objekten](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="6c874-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="6c874-126">Entwickeln bestimmter Arten von Skriptkomponenten</span><span class="sxs-lookup"><span data-stu-id="6c874-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
