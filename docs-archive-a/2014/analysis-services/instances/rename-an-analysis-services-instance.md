---
title: Umbenennen einer Analysis Services Instanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702063"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="84bc0-102">Umbenennen einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="84bc0-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="84bc0-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Mit dem Dialogfeld **Instanz umbenennen** können Sie eine vorhandene Instanz von umbenennen.</span><span class="sxs-lookup"><span data-stu-id="84bc0-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84bc0-104">Das Tool zum Umbenennen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanzen wird beim Umbenennen der Instanz mit erhöhten Rechten ausgeführt und aktualisiert den Windows-Dienstnamen, Sicherheitskonten und Registrierungseinträge, die dieser Instanz zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="84bc0-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="84bc0-105">Um sicherzustellen, dass diese Aktionen stattfinden, muss das Tool als lokaler Systemadministrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="84bc0-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="84bc0-106">Das Tool zum Umbenennen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanzen ändert nicht den Programmordner, der für die ursprüngliche Instanz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="84bc0-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="84bc0-107">Ändern Sie den Namen des Programmordners nicht entsprechend der umbenannten Instanz.</span><span class="sxs-lookup"><span data-stu-id="84bc0-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="84bc0-108">Wenn Sie den Namen eines Programmordners ändern, kann dies dazu führen, dass Setup die Installation nicht reparieren oder deinstallieren kann.</span><span class="sxs-lookup"><span data-stu-id="84bc0-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84bc0-109">Das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Tool zur Instanzumbenennung wird in einer Clusterumgebung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84bc0-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="84bc0-110">So benennen Sie eine Instanz von Analysis Services um</span><span class="sxs-lookup"><span data-stu-id="84bc0-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="84bc0-111">Starten Sie das Tool zum **Umbenennen von Instanzen** ( **asinstancerename.exe**) aus c:\Programme\Microsoft SQL server\110\tools\binn\managementstudio.</span><span class="sxs-lookup"><span data-stu-id="84bc0-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="84bc0-112">Wählen Sie im Dialogfeld **Instanz umbenennen** aus der Liste **Umzubenennende Instanz** die Instanz aus, die Sie umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="84bc0-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="84bc0-113">Geben Sie in das Feld **Neuer Instanzname** den neuen Namen für die Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="84bc0-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="84bc0-114">Überprüfen Sie den Benutzernamen und das Kennwort, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="84bc0-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="84bc0-115">Die Analysis Services-Instanz wird im Rahmen der Namensänderung beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="84bc0-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="84bc0-116">Prüfliste nach dem Umbenennen</span><span class="sxs-lookup"><span data-stu-id="84bc0-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="84bc0-117">Um wieder auf die Datenbanken auf der umbenannten Instanz zugreifen zu können, müssen Sie die Datenverbindungen in Excel oder anderen Clientanwendungen manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84bc0-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="84bc0-118">Überprüfen Sie auch alle vordefinierten Verbindungen, z. B. freigegebene Reporting Services-Datenquellen, Excel-ODC-Dateien oder BI Semantikmodell-Verbindungsdateien, die möglicherweise auf die umbenannte Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="84bc0-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="84bc0-119">Weitere Informationen finden Sie unter [Verbinden mit Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="84bc0-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="84bc0-120">Aktualisieren Sie PowerShell-Skripts oder AMO-Skripts, mit denen Sie routinemäßig Datenbanken sichern, synchronisieren oder verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="84bc0-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="84bc0-121">Aktualisieren Sie die Projekteigenschaften für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekte, mit denen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]arbeiten.</span><span class="sxs-lookup"><span data-stu-id="84bc0-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="84bc0-122">Für Serverinstanzen im tabellarischen Modus müssen die Eigenschaft Arbeitsbereichsserver für die Datei model.bim und die Eigenschaft Server für das Projekt aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="84bc0-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="84bc0-123">Je nachdem, wie Sie das Dienstkonto angegeben haben, müssen Sie ggf. Datenbank-Anmeldenamen oder Dateiberechtigungen aktualisieren, die dem Dienst Datenzugriffsrechte gewähren (z. B., wenn Sie das Dienstkonto verwenden, um Daten zu verarbeiten oder auf verknüpfte Objekte auf einem anderen Server zuzugreifen).</span><span class="sxs-lookup"><span data-stu-id="84bc0-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="84bc0-124">Das Aktualisieren eines Datenbank-Anmeldenamens oder von Dateiberechtigungen ist erforderlich, wenn Sie ein virtuelles Konto zum Bereitstellen des Diensts verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="84bc0-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="84bc0-125">Virtuelle Konten basieren auf dem Instanznamen. Wenn Sie die Instanz umbenennen, wird daher gleichzeitig auch das virtuelle Konto aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="84bc0-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="84bc0-126">Dies bedeutet, dass alle vorherigen Anmeldenamen oder Berechtigungen, die Sie für die vorherige Instanz erstellt haben, nicht mehr gültig sind.</span><span class="sxs-lookup"><span data-stu-id="84bc0-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="84bc0-127">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="84bc0-127">The following example provides an illustration.</span></span> <span data-ttu-id="84bc0-128">Angenommen, Sie haben einen Server im tabellarischen Modus als Instanz mit dem Namen "tabellarisch" unter Verwendung des virtuellen Standard Kontos installiert. Dies führt zu folgender Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="84bc0-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="84bc0-129">Instanzname = \<server> \tabellarisch</span><span class="sxs-lookup"><span data-stu-id="84bc0-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="84bc0-130">Dienstname = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="84bc0-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="84bc0-131">Virtuelles Konto = NT-Dienst\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="84bc0-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="84bc0-132">Nehmen Sie nun an, Sie benennen die Instanz in "Tab2" um.</span><span class="sxs-lookup"><span data-stu-id="84bc0-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="84bc0-133">Nach der Namensänderung würde die Konfiguration wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="84bc0-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="84bc0-134">Instanzname = \<server> \tab2</span><span class="sxs-lookup"><span data-stu-id="84bc0-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="84bc0-135">Dienstname = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="84bc0-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="84bc0-136">Virtuelles Konto = NT-Dienst\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="84bc0-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="84bc0-137">Wie Sie sehen können, sind Datenbank-und Dateiberechtigungen, die zuvor "NT-Dienst \ MSOLAP $ tabellarisch" erteilt wurden, nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="84bc0-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="84bc0-138">Um sicherzustellen, dass die vom Dienst ausgeführten Tasks und Vorgänge wie zuvor ausgeführt werden, müssen Sie jetzt der "NT-Dienst \ MSOLAP $ Tab2" neue Datenbank-und Dateiberechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="84bc0-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
