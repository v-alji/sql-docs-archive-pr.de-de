---
title: Durchführen eines Upgrades für Integration Services-Pakete mit dem SSIS-Paketupgrade-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, upgrading
- upgrading Integration Services packages
ms.assetid: 9359275a-48f5-4d1e-8ae7-e797759e3ccf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bcafd1c9750d8333639ca2d315512a2c2b8759c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618187"
---
# <a name="upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="0f3de-102">Aktualisieren von Integration Services-Paketen mit dem SSIS-Paketupgrade-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0f3de-102">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>
  <span data-ttu-id="0f3de-103">Sie können Pakete, die in früheren Versionen von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt wurden, auf das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Format aktualisieren, das [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f3de-103">You can upgrade packages that were created in earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] format that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f3de-104">stellt zu diesem Zweck den [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketupgrade-Assistenten bereit.</span><span class="sxs-lookup"><span data-stu-id="0f3de-104">provides the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard to help in this process.</span></span> <span data-ttu-id="0f3de-105">Da Sie den Assistenten so konfigurieren können, dass er die ursprünglichen Pakete sichert, können Sie die ursprünglichen Pakete weiter verwenden, falls Probleme beim Upgrade auftreten.</span><span class="sxs-lookup"><span data-stu-id="0f3de-105">Because you can configure the wizard to backup up your original packages, you can continue to use the original packages if you experience upgrade difficulties.</span></span>  
  
 <span data-ttu-id="0f3de-106">Der [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketupgrade-Assistent ist installiert, wenn [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f3de-106">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is installed when [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f3de-107">Der [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketaktualisierungs-Assistent ist in den Editionen Standard, Enterprise und Developer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0f3de-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is available in the Standard, Enterprise, and Developer Editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0f3de-108">Weitere Informationen zum Aktualisieren von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen finden Sie unter [Aktualisieren von Integration Services-Paketen](upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="0f3de-108">For more information about how to upgrade [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, see [Upgrade Integration Services Packages](upgrade-integration-services-packages.md).</span></span>  
  
 <span data-ttu-id="0f3de-109">Im weiteren Verlauf dieses Themas wird beschrieben, wie Sie den Assistenten ausführen und die ursprünglichen Pakete sichern.</span><span class="sxs-lookup"><span data-stu-id="0f3de-109">The remainder of this topic describes how to run the wizard and back up the original packages.</span></span>  
  
## <a name="running-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="0f3de-110">Ausführen des SSIS Paketupgrade-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0f3de-110">Running the SSIS Package Upgrade Wizard</span></span>  
 <span data-ttu-id="0f3de-111">Sie können den [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketupgrade-Assistenten in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]oder an der Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f3de-111">You can run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or at the command prompt.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-data-tools"></a><span data-ttu-id="0f3de-112">So führen Sie den Assistenten in SQL Server-Datentools aus</span><span class="sxs-lookup"><span data-stu-id="0f3de-112">To run the wizard from SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="0f3de-113">Erstellen oder öffnen Sie ein [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]-Projekt in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f3de-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="0f3de-114">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **SSIS-Pakete** , und klicken Sie dann auf **Alle Pakete aktualisieren** , um alle Pakete unter diesem Knoten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0f3de-114">In Solution Explorer, right-click the **SSIS Packages** node, and then click **Upgrade All Packages** to upgrade all the packages under this node.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f3de-115">Wenn Sie ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket öffnen, das [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]- oder [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)]-Pakete enthält, öffnet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatisch den [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Paketaktualisierungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="0f3de-115">When you open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] packages, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatically opens the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-management-studio"></a><span data-ttu-id="0f3de-116">So führen Sie den Assistenten in SQL Server Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="0f3de-116">To run the wizard from SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="0f3de-117">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]her, erweitern Sie den Knoten **Gespeicherte Pakete** , klicken Sie mit der rechten Maustaste auf den Knoten **Dateisystem** oder **MSDB** , und klicken Sie dann auf **Pakete aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="0f3de-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expand the **Stored Packages** node, and right-click the **File System** or **MSDB** node, and then click **Upgrade Packages**.</span></span>  
  
#### <a name="to-run-the-wizard-at-the-command-prompt"></a><span data-ttu-id="0f3de-118">So führen Sie den Assistenten an der Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="0f3de-118">To run the wizard at the command prompt</span></span>  
  
-   <span data-ttu-id="0f3de-119">Führen Sie an der Eingabeaufforderung die SSISUpgrade.exe Datei im Ordner " **c:\Programme\Microsoft SQL server\120\dz\binn** " aus.</span><span class="sxs-lookup"><span data-stu-id="0f3de-119">At the command prompt, run the SSISUpgrade.exe file from the **C:\Program Files\Microsoft SQL Server\120\DTS\Binn** folder.</span></span>  
  
## <a name="backing-up-the-original-packages"></a><span data-ttu-id="0f3de-120">Sichern der ursprünglichen Pakete</span><span class="sxs-lookup"><span data-stu-id="0f3de-120">Backing Up the Original Packages</span></span>  
 <span data-ttu-id="0f3de-121">Um die ursprünglichen Pakete zu sichern, müssen sowohl die ursprünglichen Pakete als auch die aktualisierten Pakete in demselben Ordner im Dateisystem gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="0f3de-121">To back up the original packages, both the original packages and the upgraded packages must be stored in the same folder in the file system.</span></span> <span data-ttu-id="0f3de-122">Abhängig davon, wie Sie den Assistenten ausführen, kann dieser Speicherort automatisch ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="0f3de-122">Depending on how you run the wizard, this storage location might be automatically selected.</span></span>  
  
-   <span data-ttu-id="0f3de-123">Wenn Sie den [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketaktualisierungs-Assistenten in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]ausführen, speichert der Assistent automatisch sowohl die ursprünglichen Pakete als auch die aktualisierten Pakete in demselben Ordner im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="0f3de-123">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the wizard automatically stores both the original packages and upgraded packages in the same folder in the file system.</span></span>  
  
-   <span data-ttu-id="0f3de-124">Wenn Sie den [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketaktualisierungs-Assistenten in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder an der Eingabeaufforderung ausführen, können Sie unterschiedliche Speicherorte für die ursprünglichen und die aktualisierten Pakete angeben.</span><span class="sxs-lookup"><span data-stu-id="0f3de-124">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, you can specify different storage locations for the original and upgraded packages.</span></span> <span data-ttu-id="0f3de-125">Um die ursprünglichen Pakete zu sichern, geben Sie unbedingt an, dass sowohl die ursprünglichen als auch die aktualisierten Pakete in demselben Ordner im Dateisystem gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0f3de-125">To back up the original packages, make sure to specify that both the original and upgraded packages are stored in the same folder in the file system.</span></span> <span data-ttu-id="0f3de-126">Wenn Sie andere Speicheroptionen angeben, ist der Assistent nicht in der Lage, die ursprünglichen Pakete zu sichern.</span><span class="sxs-lookup"><span data-stu-id="0f3de-126">If you specify any other storage options, the wizard will not be able to back up the original packages.</span></span>  
  
 <span data-ttu-id="0f3de-127">Wenn der Assistent die ursprünglichen Pakete sichert, speichert er eine Kopie der ursprünglichen Pakete in einem **SSISBackupFolder** -Ordner.</span><span class="sxs-lookup"><span data-stu-id="0f3de-127">When the wizard backs up the original packages, the wizard stores a copy of the original packages in an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="0f3de-128">Der Assistent erstellt diesen **SSISBackupFolder** -Ordner als Unterordner des Ordners, der die ursprünglichen Pakete und die aktualisierten Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="0f3de-128">The wizard creates this **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-management-studio-or-at-the-command-prompt"></a><span data-ttu-id="0f3de-129">So sichern Sie die ursprünglichen Pakete in SQL Server Management Studio oder an der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="0f3de-129">To back up the original packages in SQL Server Management Studio or at the command prompt</span></span>  
  
1.  <span data-ttu-id="0f3de-130">Speichern Sie die ursprünglichen Pakete an einem Speicherort im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="0f3de-130">Save the original packages to a location on the file system.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f3de-131">Die Sicherungsoption im Assistenten funktioniert nur mit Paketen, die im Dateisystem gespeichert worden sind.</span><span class="sxs-lookup"><span data-stu-id="0f3de-131">The backup option in the wizard only works with packages that have been stored to the file system.</span></span>  
  
2.  <span data-ttu-id="0f3de-132">Führen Sie den [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Paketupgrade-Assistenten in [!INCLUDE[ssIS](../../includes/ssis-md.md)] oder an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="0f3de-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
3.  <span data-ttu-id="0f3de-133">Legen Sie auf der Seite **Quellspeicherort auswählen** des Assistenten die Eigenschaft **Paketquelle** auf **Dateisystem**fest.</span><span class="sxs-lookup"><span data-stu-id="0f3de-133">On the **Select Source Location** page of the wizard, set the **Package source** property to **File System**.</span></span>  
  
4.  <span data-ttu-id="0f3de-134">Wählen Sie auf der Seite **Zielspeicherort auswählen** die Option **An Quellspeicherort speichern** aus, um die aktualisierten Pakete an demselben Speicherort wie die ursprünglichen Pakete zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0f3de-134">On the **Select Destination Location** page of the wizard, select **Save to source location** tosave the upgraded packages to the same location as the original packages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f3de-135">Die Sicherungsoption im Assistenten ist nur verfügbar, wenn die aktualisierten Pakete in demselben Ordner gespeichert werden wie die ursprünglichen Pakete.</span><span class="sxs-lookup"><span data-stu-id="0f3de-135">The backup option in the wizard is available only when the upgraded packages are stored in the same folder as the original packages.</span></span>  
  
5.  <span data-ttu-id="0f3de-136">Wählen Sie auf der Seite **Paketverwaltungsoptionen auswählen** des Assistenten die Option **Originalpakete sichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0f3de-136">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-data-tools"></a><span data-ttu-id="0f3de-137">So sichern Sie die Originalpakete in SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="0f3de-137">To back up the original packages in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="0f3de-138">Speichern Sie die ursprünglichen Pakete an einem Speicherort im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="0f3de-138">Save the original packages to a location on the file system.</span></span>  
  
2.  <span data-ttu-id="0f3de-139">Wählen Sie auf der Seite **Paketverwaltungsoptionen auswählen** des Assistenten die Option **Originalpakete sichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0f3de-139">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0f3de-140">Die Option **Original Pakete sichern** wird nicht angezeigt, wenn Sie ein- [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] oder- [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] Projekt in öffnen [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , wodurch der Assistent automatisch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0f3de-140">The **Backup original packages** option is not displayed when you open a [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which automatically launches the wizard.</span></span>  
  
3.  <span data-ttu-id="0f3de-141">Führen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]den [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketaktualisierungs-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="0f3de-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
  
