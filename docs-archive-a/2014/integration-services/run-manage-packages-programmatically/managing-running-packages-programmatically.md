---
title: Programmgesteuerte Verwaltung von ausgeführten Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723989"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="8cb8f-102">Programmgesteuerte Verwaltung von ausgeführten Paketen</span><span class="sxs-lookup"><span data-stu-id="8cb8f-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="8cb8f-103">Wenn Sie programmgesteuert mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen arbeiten, möchten Sie u. U. bestimmen, welche Pakete gerade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="8cb8f-104">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse des <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace stellt Methoden und Klassen bereit, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="8cb8f-105">Weitere Informationen zum Überwachen von Paketen finden Sie unter [Paketverwaltung &#40;SSIS-Dienst&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="8cb8f-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="8cb8f-106">Alle in diesem Thema erläuterten Methoden erfordern einen Verweis auf die `Microsoft.SqlServer.ManagedDTS`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="8cb8f-107">Nachdem Sie den Verweis in einem neuen Projekt hinzugefügt haben, importieren Sie den <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace mit einer `using`- oder `Imports`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8cb8f-108">Die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse zum Arbeiten mit dem SSIS-Paketspeicher unterstützen nur „.“, localhost oder den Namen des lokalen Servers.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="8cb8f-109">Sie können "(local)" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="8cb8f-110">Bestimmen, welche Pakete zurzeit ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="8cb8f-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="8cb8f-111">Um zu bestimmen, welche Pakete gerade auf dem angegebenen Server ausgeführt werden, rufen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="8cb8f-112">Diese Methode gibt eine <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>-Auflistung von <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8cb8f-113">Administratoren können alle Pakete sehen, die zurzeit auf dem Computer ausgeführt werden; allen anderen Benutzern werden nur die Pakete angezeigt, die sie gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="8cb8f-114">Arbeiten mit ausgeführten Paketen</span><span class="sxs-lookup"><span data-stu-id="8cb8f-114">Working with Running Packages</span></span>  
 <span data-ttu-id="8cb8f-115">Nachdem Sie bestimmt haben, welche Pakete zurzeit ausgeführt werden, können Sie Informationen zu den Pakten abrufen und anfordern, dass ein Paket gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="8cb8f-116">Abrufen von Informationen über ein ausgeführtes Paket</span><span class="sxs-lookup"><span data-stu-id="8cb8f-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="8cb8f-117">Beim Durchlaufen der <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>-Auflistung können Sie mithilfe der Eigenschaften des <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>-Objekts ein Paket suchen oder zusätzliche Informationen zu den Paketen, die ausgeführt werden, erhalten:</span><span class="sxs-lookup"><span data-stu-id="8cb8f-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="8cb8f-118">Beenden eines ausgeführten Pakets</span><span class="sxs-lookup"><span data-stu-id="8cb8f-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="8cb8f-119">Sie können die <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A>-Methode eines <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>-Objekts aufrufen, um anzufordern, dass das Paket beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="8cb8f-120">Möglicherweise gibt es eine Zeitverzögerung zwischen der Ausgabe der Stop-Anforderung und dem tatsächlichen Beenden des Pakets.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="8cb8f-121">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="8cb8f-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8cb8f-122">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="8cb8f-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8cb8f-123">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="8cb8f-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8cb8f-124">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8cb8f-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb8f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8cb8f-125">See Also</span></span>  
 <span data-ttu-id="8cb8f-126">[Paketverwaltung &#40;SSIS-Dienst&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="8cb8f-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="8cb8f-127">Enumerating Available Packages Programmatically</span><span class="sxs-lookup"><span data-stu-id="8cb8f-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
