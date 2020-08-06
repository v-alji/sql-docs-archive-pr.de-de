---
title: Quell Speicherort auswählen (SSIS-Paket Upgrade-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695817"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="9b193-102">Quellspeicherort auswählen (SSIS Paketupgrade-Assistent)</span><span class="sxs-lookup"><span data-stu-id="9b193-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="9b193-103">Mithilfe der Seite **Quellspeicherort auswählen** geben Sie die Quelle an, aus der Pakete aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9b193-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b193-104">Diese Seite ist nur verfügbar, wenn Sie den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketupgrade-Assistenten in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oder an der Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b193-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="9b193-105">**So führen Sie den SSIS Paketupgrade-Assistenten aus**</span><span class="sxs-lookup"><span data-stu-id="9b193-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="9b193-106">Aktualisieren von Integration Services-Paketen mit dem SSIS-Paketupgrade-Assistenten</span><span class="sxs-lookup"><span data-stu-id="9b193-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="9b193-107">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="9b193-107">Static Options</span></span>  
 <span data-ttu-id="9b193-108">**Paketquelle**</span><span class="sxs-lookup"><span data-stu-id="9b193-108">**Package source**</span></span>  
 <span data-ttu-id="9b193-109">Wählen Sie den Speicherort aus, der die zu aktualisierenden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="9b193-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="9b193-110">Für diese Option sind die in der folgenden Tabelle aufgeführten Werte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9b193-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="9b193-111">Wert</span><span class="sxs-lookup"><span data-stu-id="9b193-111">Value</span></span>|<span data-ttu-id="9b193-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b193-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b193-113">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="9b193-113">**File System**</span></span>|<span data-ttu-id="9b193-114">Gibt an, dass sich die zu aktualisierenden Pakete in einem Ordner auf dem lokalen Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="9b193-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="9b193-115">Die ursprünglichen Pakete müssen im Dateisystem gespeichert sein, damit der Assistent die ursprünglichen Pakete vor deren Upgrade sichern kann.</span><span class="sxs-lookup"><span data-stu-id="9b193-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="9b193-116">Weitere Informationen finden Sie in den Vorgehensweisen zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="9b193-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="9b193-117">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="9b193-117">**SSIS Package Store**</span></span>|<span data-ttu-id="9b193-118">Gibt an, dass sich die zu aktualisierenden Pakete im Paketspeicher befinden.</span><span class="sxs-lookup"><span data-stu-id="9b193-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="9b193-119">Der Paketspeicher besteht aus dem Satz von Dateisystemordnern, die vom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9b193-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="9b193-120">Weitere Informationen finden Sie unter [Paketverwaltung &#40;SSIS-Dienst&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="9b193-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="9b193-121">Bei Auswahl dieses Werts werden die entsprechenden dynamischen Optionen **Paketquelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b193-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="9b193-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9b193-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="9b193-123">Gibt an, dass die zu aktualisierenden Pakete aus einer vorhandenen Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]stammen.</span><span class="sxs-lookup"><span data-stu-id="9b193-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="9b193-124">Bei Auswahl dieses Werts werden die entsprechenden dynamischen Optionen **Paketquelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b193-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="9b193-125">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="9b193-125">**Folder**</span></span>  
 <span data-ttu-id="9b193-126">Geben Sie den Namen eines Ordners ein, in dem die zu aktualisierenden Pakete enthalten sind, oder klicken Sie auf **Durchsuchen** , und suchen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="9b193-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="9b193-127">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="9b193-127">**Browse**</span></span>  
 <span data-ttu-id="9b193-128">Suchen Sie nach dem Ordner, der die zu aktualisierenden Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="9b193-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="9b193-129">Dynamische Paketquellenoptionen</span><span class="sxs-lookup"><span data-stu-id="9b193-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="9b193-130">Paketquelle = SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="9b193-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="9b193-131">**Server**</span><span class="sxs-lookup"><span data-stu-id="9b193-131">**Server**</span></span>  
 <span data-ttu-id="9b193-132">Geben Sie den Namen des Servers ein, auf dem die zu aktualisierenden Pakete gespeichert sind, oder wählen Sie diesen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="9b193-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="9b193-133">Paketquelle = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b193-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="9b193-134">**Server**</span><span class="sxs-lookup"><span data-stu-id="9b193-134">**Server**</span></span>  
 <span data-ttu-id="9b193-135">Geben Sie den Namen des Servers ein, auf dem die zu aktualisierenden Pakete gespeichert sind, oder wählen Sie diesen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="9b193-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="9b193-136">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="9b193-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="9b193-137">Wählen Sie diese Option aus, um für die Herstellung einer Verbindung mit dem Server die Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b193-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="9b193-138">**SQL Server Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="9b193-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="9b193-139">Wählen Sie diese Option aus, um für die Herstellung einer Verbindung mit dem Server die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b193-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="9b193-140">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie einen Benutzernamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="9b193-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="9b193-141">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="9b193-141">**User name**</span></span>  
 <span data-ttu-id="9b193-142">Geben Sie den Benutzernamen ein, den die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwendet, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9b193-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="9b193-143">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="9b193-143">**Password**</span></span>  
 <span data-ttu-id="9b193-144">Geben Sie das Kennwort ein, das die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwendet, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9b193-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b193-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b193-145">See Also</span></span>  
 [<span data-ttu-id="9b193-146">Aktualisieren von Integration Services-Paketen</span><span class="sxs-lookup"><span data-stu-id="9b193-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
