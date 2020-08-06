---
title: Benutzeroberflächen Referenz für Paketinstallations-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696961"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="4fc29-102">Referenz zur Benutzeroberfläche des Paketinstallations-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4fc29-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="4fc29-103">Mit dem **Paketinstallations-Assistenten** können Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt einschließlich der enthaltenen Pakete, verschiedenen Dateien und Paketabhängigkeiten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="4fc29-104">Bevor Sie Pakete bereitstellen, können Sie Konfigurationen erstellen und diese dann mit den Paketen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="4fc29-105">verwendet Konfigurationen, um Eigenschaften von Paketen und Paketobjekten zur Laufzeit dynamisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4fc29-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="4fc29-106">Beispielsweise kann die Verbindungszeichenfolge einer OLE DB-Verbindung zur Laufzeit dynamisch festgelegt werden, indem Sie eine Konfiguration erstellen, die der Eigenschaft, die die Verbindungszeichenfolge enthält, einen Wert zuordnet.</span><span class="sxs-lookup"><span data-stu-id="4fc29-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="4fc29-107">Der Paketinstallations-Assistent kann erst ausgeführt werden, nachdem Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt und ein Bereitstellungshilfsprogramm erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="4fc29-108">Weitere Informationen finden Sie unter [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4fc29-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="4fc29-109">In den folgenden Abschnitten werden Seiten des Assistenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="4fc29-110">Willkommen auf der Seite des Paketinstallations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4fc29-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="4fc29-111">Mit dem **Paketinstallations-Assistenten** können Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt bereitstellen, für das Sie ein Paketbereitstellungshilfsprogramm erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="4fc29-112">**Diese Anfangsseite nicht mehr anzeigen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="4fc29-113">Wählen Sie diese Option aus, um die Startseite bei der nächsten Ausführung des Assistenten auszulassen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="4fc29-114">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-114">**Next**</span></span>  
 <span data-ttu-id="4fc29-115">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="4fc29-116">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-116">**Finish**</span></span>  
 <span data-ttu-id="4fc29-117">Springen Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-118">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="4fc29-119">Seite "Pakete konfigurieren"</span><span class="sxs-lookup"><span data-stu-id="4fc29-119">Configure Packages Page</span></span>  
 <span data-ttu-id="4fc29-120">Mithilfe der Seite **Pakete konfigurieren** können Sie Paketkonfigurationen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4fc29-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="4fc29-121">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4fc29-121">Options</span></span>  
 <span data-ttu-id="4fc29-122">**Konfigurationsdatei**</span><span class="sxs-lookup"><span data-stu-id="4fc29-122">**Configuration file**</span></span>  
 <span data-ttu-id="4fc29-123">Bearbeiten Sie die Inhalte einer Konfigurationsdatei, indem Sie die Datei aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="4fc29-124">**Verwandte Themen:** [Erstellen von Paketkonfigurationen](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="4fc29-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="4fc29-125">**Pfad**</span><span class="sxs-lookup"><span data-stu-id="4fc29-125">**Path**</span></span>  
 <span data-ttu-id="4fc29-126">Zeigen Sie den Pfad der zu konfigurierenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="4fc29-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4fc29-127">**Type**</span></span>  
 <span data-ttu-id="4fc29-128">Zeigen Sie den Datentyp der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="4fc29-129">**Wert**</span><span class="sxs-lookup"><span data-stu-id="4fc29-129">**Value**</span></span>  
 <span data-ttu-id="4fc29-130">Geben Sie den Wert der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="4fc29-131">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-131">**Next**</span></span>  
 <span data-ttu-id="4fc29-132">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="4fc29-133">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-133">**Finish**</span></span>  
 <span data-ttu-id="4fc29-134">Springen Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-135">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="4fc29-136">Seite "Installation bestätigen"</span><span class="sxs-lookup"><span data-stu-id="4fc29-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="4fc29-137">Mithilfe der Seite **Installation bestätigen** können Sie die Installation von Paketen starten und den Status sowie die Informationen anzeigen, die der Assistent zum Installieren von Dateien aus dem angegebenen Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="4fc29-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="4fc29-138">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-138">**Next**</span></span>  
 <span data-ttu-id="4fc29-139">Installiert die Pakete und die dazugehörigen Abhängigkeiten und wechselt nach Abschluss der Installation zur nächsten Seite des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4fc29-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="4fc29-140">**Status**</span><span class="sxs-lookup"><span data-stu-id="4fc29-140">**Status**</span></span>  
 <span data-ttu-id="4fc29-141">Zeigt den Fortschritt der Paketinstallation an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="4fc29-142">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-142">**Finish**</span></span>  
 <span data-ttu-id="4fc29-143">Wechseln Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-144">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="4fc29-145">Seit "SSIS-Paket bereitstellen"</span><span class="sxs-lookup"><span data-stu-id="4fc29-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="4fc29-146">Mithilfe der Seite **SSIS-Pakete bereitstellen** können Sie angeben, an welcher Stelle [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete und ihre Abhängigkeiten installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="4fc29-147">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4fc29-147">Options</span></span>  
 <span data-ttu-id="4fc29-148">**Bereitstellung im Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="4fc29-148">**File system deployment**</span></span>  
 <span data-ttu-id="4fc29-149">Stellen Sie Pakete und Abhängigkeiten in einem bestimmten Ordner im Dateisystem bereit.</span><span class="sxs-lookup"><span data-stu-id="4fc29-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="4fc29-150">**Bereitstellung in SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4fc29-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="4fc29-151">Stellen Sie Pakete und Abhängigkeiten in einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]bereit.</span><span class="sxs-lookup"><span data-stu-id="4fc29-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4fc29-152">Verwenden Sie diese Option, wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Pakete zwischen Servern freigibt.</span><span class="sxs-lookup"><span data-stu-id="4fc29-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="4fc29-153">Bestehende Paketabhängigkeiten werden im angegebenen Ordner im Dateisystem installiert.</span><span class="sxs-lookup"><span data-stu-id="4fc29-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="4fc29-154">**Pakete nach der Installation überprüfen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="4fc29-155">Geben Sie an, ob Pakete nach der Installation überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="4fc29-156">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-156">**Next**</span></span>  
 <span data-ttu-id="4fc29-157">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="4fc29-158">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-158">**Finish**</span></span>  
 <span data-ttu-id="4fc29-159">Springen Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-160">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="4fc29-161">Seite "Paketüberprüfung"</span><span class="sxs-lookup"><span data-stu-id="4fc29-161">Packages Validation Page</span></span>  
 <span data-ttu-id="4fc29-162">Auf der Seite **Paketüberprüfung** können Sie den Fortschritt und die Ergebnisse der Paketüberprüfung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="4fc29-163">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-163">**Next**</span></span>  
 <span data-ttu-id="4fc29-164">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="4fc29-165">Seite "Installationsordner auswählen"</span><span class="sxs-lookup"><span data-stu-id="4fc29-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="4fc29-166">Mithilfe der Seite **Installationsordner auswählen** können Sie den Dateisystemordner angeben, in dem die Pakete und deren Abhängigkeiten installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="4fc29-167">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4fc29-167">Options</span></span>  
 <span data-ttu-id="4fc29-168">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="4fc29-168">**Folder**</span></span>  
 <span data-ttu-id="4fc29-169">Geben Sie den Pfad und den Ordner an, in den das Paket und seine Abhängigkeiten kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="4fc29-170">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-170">**Browse**</span></span>  
 <span data-ttu-id="4fc29-171">Suchen Sie den Zielordner im Dialogfeld **Ordner suchen** .</span><span class="sxs-lookup"><span data-stu-id="4fc29-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="4fc29-172">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-172">**Next**</span></span>  
 <span data-ttu-id="4fc29-173">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="4fc29-174">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-174">**Finish**</span></span>  
 <span data-ttu-id="4fc29-175">Springen Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-176">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="4fc29-177">Seite "Zielserver mit SQL Server angeben"</span><span class="sxs-lookup"><span data-stu-id="4fc29-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="4fc29-178">Auf der Seite **Zielserver mit SQL Server angeben** können Sie Optionen zur Bereitstellung des Pakets für eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz angeben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="4fc29-179">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4fc29-179">Options</span></span>  
 <span data-ttu-id="4fc29-180">**Servername**</span><span class="sxs-lookup"><span data-stu-id="4fc29-180">**Server name**</span></span>  
 <span data-ttu-id="4fc29-181">Geben Sie den Namen des Servers an, auf dem die Pakete bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="4fc29-182">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="4fc29-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="4fc29-183">Geben Sie an, ob für die Anmeldung beim Server die Windows-Authentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fc29-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="4fc29-184">Im Sinne einer größeren Sicherheit wird die Windows-Authentifizierung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="4fc29-185">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="4fc29-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="4fc29-186">Geben Sie an, ob vom Paket für die Anmeldung beim Server die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fc29-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="4fc29-187">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie einen Benutzernamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="4fc29-188">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="4fc29-188">**User name**</span></span>  
 <span data-ttu-id="4fc29-189">Geben Sie einen Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="4fc29-190">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="4fc29-190">**Password**</span></span>  
 <span data-ttu-id="4fc29-191">Geben Sie ein Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="4fc29-191">Specify a password.</span></span>  
  
 <span data-ttu-id="4fc29-192">**Paketpfad**</span><span class="sxs-lookup"><span data-stu-id="4fc29-192">**Package path**</span></span>  
 <span data-ttu-id="4fc29-193">Geben Sie den Namen des logischen Ordners an, oder geben Sie / für den Standardordner ein.</span><span class="sxs-lookup"><span data-stu-id="4fc29-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="4fc29-194">Klicken Sie zum Auswählen des Ordners im Dialogfeld **SSIS-Paket** auf die Schaltfläche zum Durchsuchen (...). Allerdings bietet das Dialogfeld keine Möglichkeit, den Standardordner auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="4fc29-195">Wenn Sie den Standardordner verwenden möchten, müssen Sie im Textfeld / eingeben.</span><span class="sxs-lookup"><span data-stu-id="4fc29-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fc29-196">Wenn Sie keinen gültigen Paketpfad eingeben, wird die folgende Fehlermeldung angezeigt: „Mindestens ein Argument ist ungültig.“</span><span class="sxs-lookup"><span data-stu-id="4fc29-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="4fc29-197">**Serverspeicher für die Verschlüsselung verwenden**</span><span class="sxs-lookup"><span data-stu-id="4fc29-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="4fc29-198">Wählen Sie diese Option aus, um die Pakete mithilfe von Sicherheitsfunktionen von [!INCLUDE[ssDE](../includes/ssde-md.md)] zu sichern.</span><span class="sxs-lookup"><span data-stu-id="4fc29-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="4fc29-199">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="4fc29-199">**Next**</span></span>  
 <span data-ttu-id="4fc29-200">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fc29-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="4fc29-201">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-201">**Finish**</span></span>  
 <span data-ttu-id="4fc29-202">Springen Sie zur Seite <ui>Fertigstellen des Assistenten</ui>.</span><span class="sxs-lookup"><span data-stu-id="4fc29-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="4fc29-203">Verwenden Sie diese Option, wenn Sie die Assistentenseiten noch einmal mithilfe der Zurück-Option durchgegangen sind, um die ausgewählten Optionen zu überprüfen, und jetzt mit der Auswahl zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4fc29-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="4fc29-204">Seite "Fertigstellen des Assistenten"</span><span class="sxs-lookup"><span data-stu-id="4fc29-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="4fc29-205">Auf der Seite **Fertigstellen des Assistenten** können Sie eine Übersicht über die Ergebnisse der Paketinstallation anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4fc29-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="4fc29-206">Die Seite enthält verschiedene Detailinformationen, z. B. den Namen des bereitgestellten [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekts, die Namen der installierten Pakete, die Konfigurationsdateien und den Installationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="4fc29-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="4fc29-207">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="4fc29-207">**Finish**</span></span>  
 <span data-ttu-id="4fc29-208">Durch Klicken auf **Fertig stellen**beenden Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4fc29-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc29-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fc29-209">See Also</span></span>  
 [<span data-ttu-id="4fc29-210">Paket Bereitstellung &#40;SSIS-&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc29-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
