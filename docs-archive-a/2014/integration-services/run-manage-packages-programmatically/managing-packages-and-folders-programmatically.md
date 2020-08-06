---
title: Programmgesteuerte Verwaltung von Paketen und Ordnern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723982"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="490f4-102">Programmgesteuerte Verwaltung von Paketen und Ordnern</span><span class="sxs-lookup"><span data-stu-id="490f4-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="490f4-103">Beim programmgesteuerten Arbeiten mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen möchten Sie möglicherweise feststellen, ob ein einzelnes Paket oder ein einzelner Ordner vorhanden ist, oder Sie möchten die Ordner mit gespeicherten Paketen verwalten.</span><span class="sxs-lookup"><span data-stu-id="490f4-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="490f4-104">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse des <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace stellt eine Reihe von Methoden bereit, die diese Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="490f4-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="490f4-105">Bestimmen, ob ein Paket oder ein Ordner vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="490f4-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="490f4-106">Um programmgesteuert zu ermitteln, ob ein gespeichertes Paket vorhanden ist, rufen Sie eine der folgenden Methoden auf, bevor Sie versuchen, das Paket zu laden und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="490f4-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="490f4-107">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-107">Storage Location</span></span>|<span data-ttu-id="490f4-108">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-109">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="490f4-110">Um programmgesteuert zu ermitteln, ob ein Ordner vorhanden ist, rufen Sie eine der folgenden Methoden auf, bevor Sie versuchen, die in dem Ordner gespeicherten Pakete aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="490f4-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="490f4-111">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-111">Storage Location</span></span>|<span data-ttu-id="490f4-112">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-113">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="490f4-114">Verwalten von Paketen und Ordnern</span><span class="sxs-lookup"><span data-stu-id="490f4-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="490f4-115">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse des <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace stellt zusätzliche Methoden zum Verwalten von Paketen und den Ordnern, in denen diese gespeichert sind, bereit.</span><span class="sxs-lookup"><span data-stu-id="490f4-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="490f4-116">Entfernen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="490f4-116">Removing a Package</span></span>  
 <span data-ttu-id="490f4-117">Rufen Sie zum programmgesteuerten Entfernen eines gespeicherten Pakets eine der folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="490f4-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="490f4-118">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-118">Storage Location</span></span>|<span data-ttu-id="490f4-119">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-120">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="490f4-121">Erstellen eines Ordners</span><span class="sxs-lookup"><span data-stu-id="490f4-121">Creating a Folder</span></span>  
 <span data-ttu-id="490f4-122">Rufen Sie zum programmgesteuerten Erstellen eines Speicherordners eine der folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="490f4-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="490f4-123">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-123">Storage Location</span></span>|<span data-ttu-id="490f4-124">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-125">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="490f4-126">Entfernen eines Ordners</span><span class="sxs-lookup"><span data-stu-id="490f4-126">Removing a Folder</span></span>  
 <span data-ttu-id="490f4-127">Rufen Sie zum programmgesteuerten Entfernen eines Speicherordners eine der folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="490f4-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="490f4-128">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-128">Storage Location</span></span>|<span data-ttu-id="490f4-129">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-130">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="490f4-131">Umbenennen eines Ordners</span><span class="sxs-lookup"><span data-stu-id="490f4-131">Renaming a Folder</span></span>  
 <span data-ttu-id="490f4-132">Rufen Sie zum programmgesteuerten Umbenennen eines Speicherordners eine der folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="490f4-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="490f4-133">Speicherort</span><span class="sxs-lookup"><span data-stu-id="490f4-133">Storage Location</span></span>|<span data-ttu-id="490f4-134">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="490f4-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="490f4-135">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="490f4-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="490f4-136">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="490f4-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="490f4-137">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="490f4-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="490f4-138">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="490f4-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="490f4-139">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="490f4-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490f4-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="490f4-140">See Also</span></span>  
 <span data-ttu-id="490f4-141">[Paketverwaltung &#40;SSIS-Dienst&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="490f4-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="490f4-142">Enumerating Available Packages Programmatically</span><span class="sxs-lookup"><span data-stu-id="490f4-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
