---
title: Programmgesteuertes Verwalten von Paketrollen (SSIS-Dienst) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, roles
- roles [Integration Services]
- packages [Integration Services], roles
ms.assetid: 2e0ca0d5-d4f5-421d-b17d-a48b37b923e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff54f3f90d9e008ae21c83c2a8fdc3f7440a5c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723986"
---
# <a name="managing-package-roles-programmatically-ssis-service"></a><span data-ttu-id="5b51e-102">Programmgesteuertes Verwalten von Paketrollen (SSIS-Dienst)</span><span class="sxs-lookup"><span data-stu-id="5b51e-102">Managing Package Roles Programmatically (SSIS Service)</span></span>
  <span data-ttu-id="5b51e-103">Wenn Sie programmgesteuert mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen arbeiten, möchten Sie möglicherweise bestimmen, welche Rollen für die Anwendung auf Pakete verfügbar sind, oder die Rollen, die auf ein einzelnes Paket angewendet werden, bestimmen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="5b51e-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which roles are available to apply to packages, or to determine or set the roles applied to an individual package.</span></span> <span data-ttu-id="5b51e-104">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse des <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace stellt eine Reihe von Methoden bereit, die diese Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5b51e-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>

 <span data-ttu-id="5b51e-105">Rollen gelten nur für Pakete, die in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank **msdb** gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="5b51e-105">Roles apply only to packages stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database.</span></span> <span data-ttu-id="5b51e-106">Weitere Informationen zu Paketrollen finden Sie unter [Integration Services-Rollen &#40;SSIS-Dienst&#41;](../security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="5b51e-106">For more information about package roles, see [Integration Services Roles &#40;SSIS Service&#41;](../security/integration-services-roles-ssis-service.md).</span></span>

 <span data-ttu-id="5b51e-107">Alle in diesem Thema erläuterten Methoden erfordern einen Verweis auf die `Microsoft.SqlServer.ManagedDTS`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="5b51e-107">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="5b51e-108">Nachdem Sie den Verweis in einem neuen Projekt hinzugefügt haben, importieren Sie den <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace mithilfe einer `using`- oder `Imports`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5b51e-108">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace by using a `using` or `Imports` statement.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="5b51e-109">Die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse zum Arbeiten mit dem SSIS-Paketspeicher unterstützen nur „.“, localhost oder den Namen des lokalen Servers.</span><span class="sxs-lookup"><span data-stu-id="5b51e-109">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="5b51e-110">Sie können "(local)" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b51e-110">You cannot use "(local)".</span></span>

## <a name="determining-which-roles-are-available"></a><span data-ttu-id="5b51e-111">Bestimmen, welche Rollen verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="5b51e-111">Determining Which Roles Are Available</span></span>
 <span data-ttu-id="5b51e-112">Um zu bestimmen, welche Rollen für die auf einem bestimmten Server gespeicherten Pakete verfügbar sind, rufen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="5b51e-112">To determine which roles are available for the packages stored on a particular server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class.</span></span>

## <a name="determining-which-roles-are-assigned"></a><span data-ttu-id="5b51e-113">Bestimmen, welche Rollen zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="5b51e-113">Determining Which Roles Are Assigned</span></span>
 <span data-ttu-id="5b51e-114">Um zu bestimmen, welche Rollen einem bestimmten Paket bereits zugewiesen wurden, rufen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5b51e-114">To determine which roles have already been assigned to a particular package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A> method.</span></span> <span data-ttu-id="5b51e-115">Rufen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A>-Methode auf, um einem Paket Rollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5b51e-115">To assign roles to a package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A> method.</span></span>

<span data-ttu-id="5b51e-116">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="5b51e-116">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5b51e-117">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="5b51e-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5b51e-118">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="5b51e-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5b51e-119">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b51e-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b51e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b51e-120">See Also</span></span>
 [<span data-ttu-id="5b51e-121">Integration Services-Rollen &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="5b51e-121">Integration Services Roles &#40;SSIS Service&#41;</span></span>](../security/integration-services-roles-ssis-service.md)


