---
title: Bereitstellen von Paketen mithilfe des Bereitstellungs Hilfsprogramms | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718622"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="3fc63-102">Bereitstellen von Paketen mithilfe des Bereitstellungshilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="3fc63-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="3fc63-103">Wenn Sie ein Bereitstellungshilfsprogramm erstellt haben, um Pakete aus einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt auf einem anderen Computer zu installieren als dem Computer, auf dem das Bereitstellungshilfsprogramm erstellt wurde, müssen Sie zuerst den Bereitstellungsordner auf den Zielcomputer kopieren.</span><span class="sxs-lookup"><span data-stu-id="3fc63-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="3fc63-104">Der Pfad des Bereitstellungsordners wird in der DeploymentOutputPath-Eigenschaft des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekts angegeben, für das Sie das Bereitstellungshilfsprogramm erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3fc63-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="3fc63-105">Der Standardpfad ist bin\Deployment, relativ zum [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="3fc63-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="3fc63-106">Weitere Informationen finden Sie unter [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3fc63-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="3fc63-107">Sie können zum Installieren der Pakete den Paketinstallations-Assistenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fc63-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="3fc63-108">Doppelklicken Sie zum Starten des Assistenten auf die Datei des Bereitstellungshilfsprogramms, nachdem Sie den Bereitstellungsordner auf den Server kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="3fc63-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="3fc63-109">Die Datei hat den Namen „\<project name>.SSISDeploymentManifest“ und befindet sich im Bereitstellungsordner des Zielcomputers.</span><span class="sxs-lookup"><span data-stu-id="3fc63-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fc63-110">Abhängig von der Version des Pakets, das Sie bereitstellen, könnte ein Fehler auftreten, wenn Sie verschiedene Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] parallel installiert haben.</span><span class="sxs-lookup"><span data-stu-id="3fc63-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="3fc63-111">Dieser Fehler kann auftreten, da die Dateinamenerweiterung ".SSISDeploymentManifest" für alle Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]identisch ist.</span><span class="sxs-lookup"><span data-stu-id="3fc63-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="3fc63-112">Durch Doppelklicken auf die Datei wird das Installationsprogramm („dtsinstall.exe“) für die zuletzt installierte Version von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]aufgerufen, die möglicherweise nicht der Version der Datei des Bereitstellungs-Hilfsprogramms entspricht.</span><span class="sxs-lookup"><span data-stu-id="3fc63-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="3fc63-113">Um dieses Problem zu umgehen, führen Sie die richtige Version von "dtsinstall.exe" in der Befehlszeile aus, und stellen Sie den Pfad der Datei des BereitstellungsHilfsprogramms bereit.</span><span class="sxs-lookup"><span data-stu-id="3fc63-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="3fc63-114">Der Paketinstallations-Assistent führt Sie schrittweise durch das Installieren der Pakete im Dateisystem oder in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fc63-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3fc63-115">Es gibt folgende Möglichkeiten, um die Installation zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3fc63-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="3fc63-116">Auswählen des Speichertyps und des Speicherorts zum Installieren der Pakete.</span><span class="sxs-lookup"><span data-stu-id="3fc63-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="3fc63-117">Auswählen des Speicherorts zum Installieren von Paketabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="3fc63-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="3fc63-118">Überprüfen der Pakete nach dem Installieren der Pakete auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="3fc63-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="3fc63-119">Die dateibasierten Abhängigkeiten für Pakete werden immer im Dateisystem installiert.</span><span class="sxs-lookup"><span data-stu-id="3fc63-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="3fc63-120">Wenn Sie ein Paket im Dateisystem installieren, werden die Abhängigkeiten im selben Ordner installiert, den Sie für das Paket angeben.</span><span class="sxs-lookup"><span data-stu-id="3fc63-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="3fc63-121">Wenn Sie ein Paket in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]installieren, können Sie den Ordner angeben, in dem die dateibasierten Abhängigkeiten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3fc63-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="3fc63-122">Wenn das Paket Konfigurationen enthält, die zum Verwenden auf dem Zielcomputer geändert werden sollen, können Sie die Werte der Eigenschaften mit diesem Assistenten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3fc63-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="3fc63-123">Außer der Installation von Paketen mit dem Paketinstallations-Assistenten können Sie Pakete mit dem Eingabeaufforderungs-Hilfsprogramm **dtutil** kopieren und verschieben.</span><span class="sxs-lookup"><span data-stu-id="3fc63-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="3fc63-124">Weitere Informationen finden Sie unter [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3fc63-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="3fc63-125">So stellen Sie Pakete in einer Instanz von SQL Server bereit</span><span class="sxs-lookup"><span data-stu-id="3fc63-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="3fc63-126">Öffnen Sie den Bereitstellungsordner auf dem Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="3fc63-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="3fc63-127">Doppelklicken Sie auf die Manifestdatei „\<project name>.SSISDeploymentManifest“, um den Paketinstallations-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="3fc63-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="3fc63-128">Wählen Sie auf der Seite **SSIS-Pakete bereitstellen** die Option **Bereitstellung in SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="3fc63-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="3fc63-129">Wählen Sie optional **Pakete nach der Installation überprüfen** , wenn Sie die Pakete nach der Installation auf dem Zielserver überprüfen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="3fc63-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="3fc63-130">Geben Sie auf der Seite **Zielserver mit SQL Server angeben** die Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an, in der die Pakete installiert werden sollen, und wählen Sie einen Authentifizierungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="3fc63-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="3fc63-131">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung auswählen, müssen Sie einen Benutzernamen und ein Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3fc63-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="3fc63-132">Geben Sie auf der Seite **Installationsordner auswählen** den Dateisystemordner für die zu installierenden Paketabhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="3fc63-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="3fc63-133">Wenn das Paket Konfigurationen enthält, können Sie diese bearbeiten, indem Sie die Werte der **Wert** -Liste auf der Seite Pakete konfigurieren aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3fc63-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="3fc63-134">Wenn Sie ausgewählt haben, dass Pakete nach der Installation überprüft werden sollen, zeigen Sie nun die Überprüfungsergebnisse der bereitgestellten Pakete an.</span><span class="sxs-lookup"><span data-stu-id="3fc63-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc63-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fc63-135">See Also</span></span>  
 [<span data-ttu-id="3fc63-136">Paket Bereitstellung &#40;SSIS-&#41;</span><span class="sxs-lookup"><span data-stu-id="3fc63-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  