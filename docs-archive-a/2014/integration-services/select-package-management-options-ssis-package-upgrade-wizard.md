---
title: Wählen Sie Paketverwaltung Optionen aus (SSIS-Paket Upgrade-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622769"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="3f2f0-102">Paketverwaltungsoptionen auswählen (SSIS Paketupgrade-Assistent)</span><span class="sxs-lookup"><span data-stu-id="3f2f0-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="3f2f0-103">Verwenden Sie die Seite **Paketverwaltungsoptionen auswählen** , um Optionen für Paketupgrades anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="3f2f0-104">**So führen Sie den SSIS Paketupgrade-Assistenten aus**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="3f2f0-105">Aktualisieren von Integration Services-Paketen mit dem SSIS-Paketupgrade-Assistenten</span><span class="sxs-lookup"><span data-stu-id="3f2f0-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="3f2f0-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3f2f0-106">Options</span></span>  
 <span data-ttu-id="3f2f0-107">**Verbindungszeichenfolgen zum Verwenden neuer Anbieternamen aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="3f2f0-108">Aktualisieren Sie die Verbindungszeichenfolgen, um für die aktuelle Version von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]die Namen für die folgenden Anbieter zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="3f2f0-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="3f2f0-109">OLE DB-Anbieter für [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f2f0-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="3f2f0-110">Native Client</span><span class="sxs-lookup"><span data-stu-id="3f2f0-110">Native Client</span></span>  
  
 <span data-ttu-id="3f2f0-111">Der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketupgrade-Assistent aktualisiert nur Verbindungszeichenfolgen, die in Verbindungs-Managern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="3f2f0-112">Der Assistent aktualisiert keine Verbindungszeichenfolgen, die dynamisch mithilfe der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Ausdruckssprache oder mithilfe von Code in einem Skripttask erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="3f2f0-113">**Überprüfen von Upgradepaketen**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="3f2f0-114">Überprüfen Sie die Upgradepakete, und speichern Sie nur die Upgradepakete, die die Überprüfung bestehen.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="3f2f0-115">Wenn Sie diese Option nicht aktivieren, überprüft der Assistent keine Upgradepakete.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="3f2f0-116">Deshalb speichert der Assistent alle Upgradepakete, unabhängig davon, ob die Pakete gültig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="3f2f0-117">Der Assistent speichert Upgradepakete unter dem Ziel, das auf der Seite **Zielspeicherort auswählen** des Assistenten angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="3f2f0-118">Die Überprüfung verlängert die Dauer des Upgradevorgangs.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="3f2f0-119">Es wird empfohlen, diese Option für große Pakete, die voraussichtlich erfolgreich aktualisiert werden, nicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="3f2f0-120">**Neue Paket-IDs erstellen**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="3f2f0-121">Erstellen Sie neue Paket-IDs für die Upgradepakete.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="3f2f0-122">**Upgradeprozess bei fehlerhaftem Paketupgrade fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="3f2f0-123">Legen Sie fest, dass der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketupgrade-Assistent mit dem Upgrade der restlichen Pakete fortfährt, wenn ein Paket nicht aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="3f2f0-124">**Paketnamenskonflikte**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="3f2f0-125">Geben Sie an, wie der Assistent Pakete behandeln soll, die denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="3f2f0-126">Für diese Option sind die in der folgenden Tabelle aufgeführten Werte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="3f2f0-127">**Vorhandene Paketdateien überschreiben**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="3f2f0-128">Ersetzt das vorhandene Paket durch das Upgradepaket desselben Namens.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="3f2f0-129">**Zum Aktualisieren von Paketnamen numerische Suffixe hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="3f2f0-130">Fügt dem Namen des Upgradepakets ein numerisches Suffix hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="3f2f0-131">**Pakete nicht aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="3f2f0-132">Unterbricht das Upgrade der Pakete und zeigt einen Fehler an, wenn Sie den Assistenten abschließen.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="3f2f0-133">Diese Optionen sind nicht verfügbar, wenn Sie die Option **An Quellspeicherort speichern** auf der Seite **Zielspeicherort auswählen** des Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="3f2f0-134">**Konfigurationen ignorieren**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="3f2f0-135">Lädt keine Paketkonfigurationen während des Paketupgrades.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="3f2f0-136">Durch Auswahl dieser Option wird weniger Zeit für das Paketupgrade benötigt.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="3f2f0-137">**Originalpakete sichern**</span><span class="sxs-lookup"><span data-stu-id="3f2f0-137">**Backup original packages**</span></span>  
 <span data-ttu-id="3f2f0-138">Lassen Sie den Assistenten die Originalpakete in einem **SSISBackupFolder** -Ordner sichern.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="3f2f0-139">Der Assistent erstellt den **SSISBackupFolder** -Ordner als Unterordner des Ordners, der die Originalpakete und die Upgradepakete enthält.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f2f0-140">Diese Option ist nur verfügbar, wenn Sie festlegen, dass die Originalpakete und die Upgradepakete im Dateisystem und im selben Ordner gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3f2f0-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="3f2f0-141">Weitere Informationen finden Sie unter [Aktualisieren von Integration Services-Paketen mit dem SSIS Paketupgrade-Assistenten](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3f2f0-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2f0-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f2f0-142">See Also</span></span>  
 [<span data-ttu-id="3f2f0-143">Aktualisieren von Integration Services-Paketen</span><span class="sxs-lookup"><span data-stu-id="3f2f0-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
