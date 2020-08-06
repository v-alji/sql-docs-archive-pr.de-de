---
title: Entwickeln bestimmter Typen von Skriptkomponenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618775"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="d91bb-102">Entwickeln bestimmter Arten von Skriptkomponenten</span><span class="sxs-lookup"><span data-stu-id="d91bb-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="d91bb-103">Bei der Skriptkomponente handelt es sich um ein konfigurierbares Tool, das Sie im Datenfluss eines Pakets verwenden können, um nahezu allen Anforderungen gerecht zu werden, die von den Quellen, Transformationen und Zielen nicht erfüllt werden, die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d91bb-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="d91bb-104">Dieser Abschnitt enthält Codebeispiele für Skriptkomponenten, in denen die vier Optionen zum Konfigurieren der Skriptkomponente veranschaulicht werden:</span><span class="sxs-lookup"><span data-stu-id="d91bb-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="d91bb-105">Als Quelle.</span><span class="sxs-lookup"><span data-stu-id="d91bb-105">As a source.</span></span>  
  
-   <span data-ttu-id="d91bb-106">Als Transformation mit synchronen Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="d91bb-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="d91bb-107">Als Transformation mit asynchronen Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="d91bb-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="d91bb-108">Als Ziel.</span><span class="sxs-lookup"><span data-stu-id="d91bb-108">As a destination.</span></span>  
  
 <span data-ttu-id="d91bb-109">Weitere Beispiele von Skriptkomponenten finden Sie unter [Zusätzliche Skriptkomponentenbeispiele](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="d91bb-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d91bb-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d91bb-110">In This Section</span></span>  
 [<span data-ttu-id="d91bb-111">Erstellen einer Quelle mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d91bb-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="d91bb-112">Erläutert und veranschaulicht, wie eine Datenflussquelle mithilfe der Skriptkomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d91bb-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="d91bb-113">Erstellen einer synchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d91bb-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="d91bb-114">Erläutert und veranschaulicht, wie eine Datenflusstransformation mit synchronen Ausgaben mithilfe der Skriptkomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d91bb-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="d91bb-115">Durch diese Art von Transformation werden Datenzeilen an Ort und Stelle beim Durchlaufen der Komponente geändert.</span><span class="sxs-lookup"><span data-stu-id="d91bb-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="d91bb-116">Erstellen einer asynchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d91bb-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="d91bb-117">Erläutert und veranschaulicht, wie eine Datenflusstransformation mit asynchronen Ausgaben mithilfe der Skriptkomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d91bb-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="d91bb-118">Bei dieser Art von Transformation müssen alle Datenzeilen gelesen werden, bevor den Daten, die die Komponente durchlaufen, weitere Informationen, z. B. berechnete Aggregate, hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="d91bb-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="d91bb-119">Erstellen eines Ziels mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d91bb-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="d91bb-120">Erläutert und veranschaulicht, wie ein Datenflussziel mithilfe der Skriptkomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d91bb-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="d91bb-121">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d91bb-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d91bb-122">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d91bb-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d91bb-123">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d91bb-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d91bb-124">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d91bb-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91bb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d91bb-125">See Also</span></span>  
 <span data-ttu-id="d91bb-126">[Vergleichen von Skript Lösungen und benutzerdefinierten Objekten](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d91bb-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="d91bb-127">Entwickeln bestimmter Arten von Datenflusskomponenten</span><span class="sxs-lookup"><span data-stu-id="d91bb-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
