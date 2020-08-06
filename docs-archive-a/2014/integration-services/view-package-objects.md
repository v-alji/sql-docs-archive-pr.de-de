---
title: Anzeigen von Paketobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619898"
---
# <a name="view-package-objects"></a><span data-ttu-id="8f822-102">Anzeigen von Paketobjekten</span><span class="sxs-lookup"><span data-stu-id="8f822-102">View Package Objects</span></span>
  <span data-ttu-id="8f822-103">Im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer stellt die Registerkarte **Paket-Explorer** eine Explorer-Sicht des Pakets bereit.</span><span class="sxs-lookup"><span data-stu-id="8f822-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="8f822-104">Diese Sicht gibt die Containerhierarchie der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Architektur wieder.</span><span class="sxs-lookup"><span data-stu-id="8f822-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="8f822-105">Der Paketcontainer befindet sich ganz oben in der Hierarchie, und Sie erweitern das Paket, um die Verbindungen, ausführbaren Dateien, Ereignishandler, Protokollanbieter, Rangfolgeneinschränkungen und Variablen im Paket anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f822-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="8f822-106">Die ausführbaren Dateien, also die Container und Tasks im Paket, können Ereignishandler, Rangfolgeneinschränkungen und Variablen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8f822-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8f822-107">unterstützt eine geschachtelte Hierarchie von Containern, und der For-Schleifencontainer, der Foreach-Schleifencontainer und der Sequenzcontainer können andere ausführbare Dateien einschließen.</span><span class="sxs-lookup"><span data-stu-id="8f822-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="8f822-108">Falls ein Paket einen Datenfluss enthält, wird im **Paket-Explorer** der Datenflusstask aufgelistet, und er enthält den Ordner **Komponenten** , in dem die Datenflusskomponenten aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="8f822-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="8f822-109">Auf der Registerkarte **Paket-Explorer** können Sie Objekte in einem Paket löschen und auf das Fenster **Eigenschaften** zugreifen, um Objekteigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f822-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="8f822-110">Das folgende Diagramm zeigt eine Strukturansicht eines einfachen Pakets.</span><span class="sxs-lookup"><span data-stu-id="8f822-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="8f822-111">![Screenshot der Registerkarte „Paket-Explorer“](media/packageexplorer.gif "Screenshot der Registerkarte „Paket-Explorer“")</span><span class="sxs-lookup"><span data-stu-id="8f822-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="8f822-112">So zeigen Sie den Paketinhalt an</span><span class="sxs-lookup"><span data-stu-id="8f822-112">To view package content</span></span>

-   [<span data-ttu-id="8f822-113">Anzeigen von Paketobjekten im Paket-Explorer</span><span class="sxs-lookup"><span data-stu-id="8f822-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="8f822-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f822-114">See Also</span></span>
 <span data-ttu-id="8f822-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Container](control-flow/integration-services-containers.md) Rang folgen [Einschränkungen](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS-&#41; Variablen](integration-services-ssis-variables.md) Integration Services &#40;von SSIS- [&#41; Ereignis Handlern](integration-services-ssis-event-handlers.md) Integration Services &#40;[Protokollierung von SSIS&#41;](performance/integration-services-ssis-logging.md)</span><span class="sxs-lookup"><span data-stu-id="8f822-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>


