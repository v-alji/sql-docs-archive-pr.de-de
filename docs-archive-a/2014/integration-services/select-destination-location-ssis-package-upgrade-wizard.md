---
title: Ziel Speicherort auswählen (SSIS-Paket Upgrade-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622771"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="ebacd-102">Zielspeicherort auswählen (SSIS Paketupgrade-Assistent)</span><span class="sxs-lookup"><span data-stu-id="ebacd-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="ebacd-103">Auf der Seite **Zielspeicherort auswählen** können Sie das Ziel angeben, an dem die aktualisierten Pakete gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebacd-104">Diese Seite ist nur verfügbar, wenn Sie den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketupgrade-Assistenten in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oder an der Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="ebacd-105">**So führen Sie den SSIS Paketupgrade-Assistenten aus**</span><span class="sxs-lookup"><span data-stu-id="ebacd-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="ebacd-106">Aktualisieren von Integration Services-Paketen mit dem SSIS-Paketupgrade-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ebacd-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="ebacd-107">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="ebacd-107">Static Options</span></span>  
 <span data-ttu-id="ebacd-108">**An Quellspeicherort speichern**</span><span class="sxs-lookup"><span data-stu-id="ebacd-108">**Save to source location**</span></span>  
 <span data-ttu-id="ebacd-109">Speichert die aktualisierten Pakete an demselben Speicherort, der auf der Seite **Quellspeicherort auswählen** des Assistenten festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ebacd-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="ebacd-110">Wenn die ursprünglichen Pakete im Dateisystem gespeichert sind und der Assistent diese Pakete sichern soll, wählen Sie die Option **An Quellspeicherort speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ebacd-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="ebacd-111">Weitere Informationen finden Sie unter [Aktualisieren von Integration Services-Paketen mit dem SSIS Paketupgrade-Assistenten](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ebacd-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="ebacd-112">**Neuen Zielspeicherort auswählen**</span><span class="sxs-lookup"><span data-stu-id="ebacd-112">**Select new destination location**</span></span>  
 <span data-ttu-id="ebacd-113">Speichert die aktualisierten Pakete an dem Zielspeicherort, der auf dieser Seite angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ebacd-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="ebacd-114">**Paketquelle**</span><span class="sxs-lookup"><span data-stu-id="ebacd-114">**Package source**</span></span>  
 <span data-ttu-id="ebacd-115">Gibt an, wo die Upgradepakete gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="ebacd-116">Für diese Option sind die in der folgenden Tabelle aufgeführten Werte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ebacd-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="ebacd-117">Wert</span><span class="sxs-lookup"><span data-stu-id="ebacd-117">Value</span></span>|<span data-ttu-id="ebacd-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ebacd-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ebacd-119">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="ebacd-119">**File System**</span></span>|<span data-ttu-id="ebacd-120">Gibt an, dass die aktualisierten Pakete in einem Ordner auf dem lokalen Computer gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="ebacd-121">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="ebacd-121">**SSIS Package Store**</span></span>|<span data-ttu-id="ebacd-122">Gibt an, dass die aktualisierten Pakete im Integration Services-Paketspeicher gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="ebacd-123">Der Paketspeicher besteht aus dem Satz von Dateisystemordnern, die vom Integration Services-Dienst verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ebacd-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="ebacd-124">Weitere Informationen finden Sie unter [Paketverwaltung &#40;SSIS-Dienst&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="ebacd-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="ebacd-125">Bei Auswahl dieses Werts werden die entsprechenden dynamischen Optionen **Paketquelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebacd-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="ebacd-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ebacd-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="ebacd-127">Gibt an, dass die aktualisierten Pakete in einer vorhandenen Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ebacd-128">Bei Auswahl dieses Werts werden die entsprechenden dynamischen Optionen **Paketquelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebacd-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="ebacd-129">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="ebacd-129">**Folder**</span></span>  
 <span data-ttu-id="ebacd-130">Geben Sie den Namen eines Ordners ein, in dem die aktualisierten Pakete gespeichert werden, oder klicken Sie auf **Durchsuchen** , und suchen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="ebacd-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="ebacd-131">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="ebacd-131">**Browse**</span></span>  
 <span data-ttu-id="ebacd-132">Suchen Sie nach dem Ordner, in dem die aktualisierten Pakete gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="ebacd-133">Dynamische Paketquellenoptionen</span><span class="sxs-lookup"><span data-stu-id="ebacd-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="ebacd-134">Paketquelle = SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="ebacd-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="ebacd-135">**Server**</span><span class="sxs-lookup"><span data-stu-id="ebacd-135">**Server**</span></span>  
 <span data-ttu-id="ebacd-136">Geben Sie den Namen des Servers ein, auf dem die Upgradepakete gespeichert werden sollen, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ebacd-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="ebacd-137">Paketquelle = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebacd-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="ebacd-138">**Server**</span><span class="sxs-lookup"><span data-stu-id="ebacd-138">**Server**</span></span>  
 <span data-ttu-id="ebacd-139">Geben Sie den Namen des Servers ein, auf dem die Upgradepakete gespeichert werden sollen, oder wählen Sie diesen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ebacd-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="ebacd-140">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="ebacd-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="ebacd-141">Wählen Sie diese Option aus, um für die Herstellung einer Verbindung mit dem Server die Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebacd-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="ebacd-142">**SQL Server Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="ebacd-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="ebacd-143">Wählen Sie diese Option aus, um für die Herstellung einer Verbindung mit dem Server die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebacd-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="ebacd-144">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie einen Benutzernamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="ebacd-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="ebacd-145">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="ebacd-145">**User name**</span></span>  
 <span data-ttu-id="ebacd-146">Geben Sie den Benutzernamen ein, der bei der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwendet werden soll, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="ebacd-147">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="ebacd-147">**Password**</span></span>  
 <span data-ttu-id="ebacd-148">Geben Sie das Kennwort ein, das bei der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwendet werden soll, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ebacd-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebacd-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebacd-149">See Also</span></span>  
 [<span data-ttu-id="ebacd-150">Aktualisieren von Integration Services-Paketen</span><span class="sxs-lookup"><span data-stu-id="ebacd-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
