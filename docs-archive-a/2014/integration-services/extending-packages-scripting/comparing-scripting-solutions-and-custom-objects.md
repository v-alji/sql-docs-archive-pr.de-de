---
title: Vergleichen von Skriptlösungen und benutzerdefinierten Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: acf6faf9cdd78e951b8298c4e3b144d3444fb1ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609361"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a><span data-ttu-id="c8da1-102">Vergleichen von Skriptlösungen und benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="c8da1-102">Comparing Scripting Solutions and Custom Objects</span></span>
  <span data-ttu-id="c8da1-103">In einem Skripttask oder einer Skriptkomponente in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] kann größtenteils die gleiche Funktionalität implementiert werden, die auch in einem benutzerdefinierten verwalteten Task oder einer Datenflusskomponente möglich ist.</span><span class="sxs-lookup"><span data-stu-id="c8da1-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task or Script component can implement much of the same functionality that is possible in a custom managed task or data flow component.</span></span> <span data-ttu-id="c8da1-104">Nachfolgend finden Sie einige Überlegungen, die Ihnen bei der Auswahl des entsprechenden Typs des Tasks für Ihre Anforderungen helfen:</span><span class="sxs-lookup"><span data-stu-id="c8da1-104">Here are some considerations to help you choose the appropriate type of task for your needs:</span></span>  
  
-   <span data-ttu-id="c8da1-105">Wenn die Konfiguration oder Funktionalität für ein einzelnes Paket spezifisch ist, sollten Sie den Skripttask oder die Skriptkomponente verwenden, anstatt ein benutzerdefiniertes Objekt zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="c8da1-105">If the configuration or functionality is specific to an individual package, you should use the Script task or the Script component instead of a developing a custom object.</span></span>  
  
-   <span data-ttu-id="c8da1-106">Wenn die Funktionalität generisch ist und künftig auch für andere Pakete und von anderen Entwicklern verwendet werden kann, sollten Sie ein benutzerdefiniertes Objekt erstellen, anstatt eine Skriptlösung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8da1-106">If the functionality is generic, and might be used in the future for other packages and by other developers, you should create a custom object instead of using a scripting solution.</span></span> <span data-ttu-id="c8da1-107">Benutzerdefinierte Objekte können in beliebigen Paketen verwendet werden, wohingegen ein Skript nur in dem Paket verwendet werden kann, für das es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8da1-107">You can use a custom object in any package, whereas a script can be used only in the package for which it was created.</span></span>  
  
-   <span data-ttu-id="c8da1-108">Wenn der Code innerhalb des gleichen Pakets wiederverwendet wird, sollten Sie erwägen, ein benutzerdefiniertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8da1-108">If the code will be reused within the same package, you should consider creating a custom object.</span></span> <span data-ttu-id="c8da1-109">Das Kopieren von einem Skripttask bzw. einer Skriptkomponente zu einem bzw. einer anderen führt zu einer schlechteren Verwaltbarkeit, da es schwieriger ist, mehrere Kopien des Codes zu verwalten und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c8da1-109">Copying code from one Script task or component to another leads to reduced maintainability by making it more difficult to maintain and update multiple copies of the code.</span></span>  
  
-   <span data-ttu-id="c8da1-110">Wenn sich die Implementierung im Laufe der Zeit ändert, sollten Sie in Erwägung ziehen, ein benutzerdefiniertes Objekt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8da1-110">If the implementation will change over time, consider using a custom object.</span></span> <span data-ttu-id="c8da1-111">Benutzerdefinierte Objekte können getrennt vom übergeordneten Paket entwickelt und bereitgestellt werden. Bei einem Update der Skriptlösung muss jedoch das gesamte Paket erneut bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8da1-111">Custom objects can be developed and deployed separately from the parent package, whereas an update made to a scripting solution requires the redeployment of the whole package.</span></span>  
  
<span data-ttu-id="c8da1-112">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="c8da1-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c8da1-113">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="c8da1-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c8da1-114">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="c8da1-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c8da1-115">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8da1-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8da1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8da1-116">See Also</span></span>  
 [<span data-ttu-id="c8da1-117">Erweitern von Paketen mit benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="c8da1-117">Extending Packages with Custom Objects</span></span>](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  
