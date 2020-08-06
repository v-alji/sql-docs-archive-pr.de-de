---
title: Aktualisieren von Analysis Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616164"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="7b95e-102">Aktualisieren von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7b95e-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="7b95e-103">Verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Setup zum Ausführen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Upgrades.</span><span class="sxs-lookup"><span data-stu-id="7b95e-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b95e-104">Ausführliche Informationen zum Upgrade von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im SharePoint-Modus finden Sie unter [Upgrade PowerPivot für SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="7b95e-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="7b95e-105">Weitere Informationen zum Aktualisieren einer vorhandenen SQL Server Instanz finden Sie unter [Upgrade auf SQL Server 2014 mit dem Installations-Assistenten &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7b95e-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="7b95e-106">Bekannte Upgradeprobleme</span><span class="sxs-lookup"><span data-stu-id="7b95e-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="7b95e-107">Überprüfen Sie vor dem Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7b95e-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="7b95e-108">[Anmerkungen zu dieser Version von SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="7b95e-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="7b95e-109">Informationen zu den [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Features und Funktionen, die eingestellt, veraltet oder geändert wurden, finden Sie unter [Analysis Services Abwärtskompatibilität](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="7b95e-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="7b95e-110">Prüfliste vor dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="7b95e-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="7b95e-111">Lesen Sie vor dem Upgrade die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7b95e-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="7b95e-112">Unterstützte Versions- und Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="7b95e-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="7b95e-113">Hardware- und Softwareanforderungen für die Installation von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7b95e-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="7b95e-114">Überprüfen der Parameter für die Systemkonfigurationsprüfung</span><span class="sxs-lookup"><span data-stu-id="7b95e-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="7b95e-115">Überlegungen zur Sicherheit bei SQL Server-Installationen</span><span class="sxs-lookup"><span data-stu-id="7b95e-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="7b95e-116">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7b95e-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="7b95e-117">Verwenden von Upgrade Advisor zur Vorbereitung auf Upgrades</span><span class="sxs-lookup"><span data-stu-id="7b95e-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="7b95e-118">Aktualisieren von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7b95e-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="7b95e-119">Sie können Server und Daten auf verschiedene Art und Weise aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="7b95e-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="7b95e-120">Ein direktes **Upgrade** ersetzt die vorhandenen Programmdateien durch [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Programmdateien.</span><span class="sxs-lookup"><span data-stu-id="7b95e-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="7b95e-121">Datenbanken verbleiben am gleichen Ort.</span><span class="sxs-lookup"><span data-stu-id="7b95e-121">Databases remain in the same location.</span></span> <span data-ttu-id="7b95e-122">Programmordner werden aktualisiert, um den neuen Namen widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="7b95e-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="7b95e-123">Bei einem parallelen **Upgrade** handelt es sich um eine Neuinstallation von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] auf dem gleichen Computer, auf dem bereits eine Analysis Services Instanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7b95e-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="7b95e-124">Sie können Datenbanken zur neuen Instanz auf dem gleichen Computer verschoben und dann die alte Version deinstallieren, wenn Sie sie nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b95e-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="7b95e-125">Sie können auch Analysis Services auf neuer Hardware installieren und dann vorhandene Datenbanken zu diesem Server migrieren.</span><span class="sxs-lookup"><span data-stu-id="7b95e-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="7b95e-126">Direktes Upgrade</span><span class="sxs-lookup"><span data-stu-id="7b95e-126">In-place Upgrade</span></span>  
 <span data-ttu-id="7b95e-127">Sie können eine vorhandene Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auf aktualisieren [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] und im Rahmen des Upgradevorgangs vorhandene Datenbanken automatisch von der alten Instanz zur neuen Instanz migrieren.</span><span class="sxs-lookup"><span data-stu-id="7b95e-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="7b95e-128">Da die Metadaten und die binären Daten zwischen den beiden Versionen kompatibel sind, behalten Sie die Daten nach dem Upgrade bei, und es ist nicht nötig, eine manuelle Datenmigration durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="7b95e-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="7b95e-129">Um eine vorhandene Instanz zu aktualisieren, führen Sie das Setup aus, und geben Sie den Namen der vorhandenen Instanz als Namen für die neue Instanz an.</span><span class="sxs-lookup"><span data-stu-id="7b95e-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="7b95e-130">Datenbankupgrades</span><span class="sxs-lookup"><span data-stu-id="7b95e-130">Upgrading Databases</span></span>  
 <span data-ttu-id="7b95e-131">Datenbanken, die in früheren Versionen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] erstellt wurden, werden auf dem aktualisierten Server unter einer älteren Einstellung für den Datenbank-Kompatibilitätsgrad ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b95e-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="7b95e-132">Datenbanken, die in den folgenden Versionen erstellt wurden, verfügen über den Datenbank-Kompatibilitätsgrad 105.</span><span class="sxs-lookup"><span data-stu-id="7b95e-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="7b95e-133">Sie können den Kompatibilitätsgrad ändern, wenn Sie Funktionen verwenden möchten, die einen neueren Datenbank-Kompatibilitätsgrad erfordern.</span><span class="sxs-lookup"><span data-stu-id="7b95e-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="7b95e-134">Andernfalls können Sie die Datenbanken auf dem aktualisierten Server mithilfe der ursprünglichen Einstellungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b95e-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="7b95e-135">Weitere Informationen finden Sie unter [Festlegen des Kompatibilitäts Grad einer mehrdimensionalen Datenbank &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="7b95e-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b95e-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b95e-136">See Also</span></span>  
 <span data-ttu-id="7b95e-137">[Von den-Editionen unterstützte Funktionen SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="7b95e-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="7b95e-138">[Planen einer SQL Server-Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="7b95e-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="7b95e-139">[Grundlegendes zur Microsoft OLAP-Architektur](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="7b95e-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="7b95e-140">[UpgradePowerPivot für SharePoint](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="7b95e-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="7b95e-141">[Installieren von Analysis Services im mehrdimensionalen und Data Mining-Modus](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="7b95e-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="7b95e-142">PowerPivot für SharePoint 2010-Installation</span><span class="sxs-lookup"><span data-stu-id="7b95e-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
