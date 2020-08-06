---
title: Integration Services projektkonvertierungs-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618172"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="675e1-102">Assistent für die Konvertierung von Integration Services-Projekten</span><span class="sxs-lookup"><span data-stu-id="675e1-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="675e1-103">Der Assistent für die Konvertierung von **Integration Services-Projekten** konvertiert ein Projekt ins Projektbereitstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="675e1-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="675e1-104">Wenn das Projekt mindestens eine Datenquelle enthält, werden die Datenquellen entfernt, wenn die Projektkonvertierung abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="675e1-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="675e1-105">Fügen Sie einen Verbindungs-Manager auf Projektebene hinzu, um eine Verbindung mit einer Datenquelle herzustellen, die von den Paketen im Projekt gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="675e1-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="675e1-106">Weitere Informationen finden Sie unter [Hinzufügen, Löschen oder Freigeben eines Verbindungs-Managers in einem Paket](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="675e1-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="675e1-107">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="675e1-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="675e1-108">Öffnen des Assistenten für die Konvertierung von Integration Services-Projekten</span><span class="sxs-lookup"><span data-stu-id="675e1-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="675e1-109">Festlegen von Optionen auf der Seite "Pakete suchen"</span><span class="sxs-lookup"><span data-stu-id="675e1-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="675e1-110">Festlegen von Optionen auf der Seite "Pakete auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="675e1-111">Festlegen von Optionen auf der Seite "Ziel auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="675e1-112">Festlegen von Optionen auf der Seite "Projekteigenschaften angeben"</span><span class="sxs-lookup"><span data-stu-id="675e1-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="675e1-113">Festlegen von Optionen auf der Seite "Task 'Paket ausführen' aktualisieren"</span><span class="sxs-lookup"><span data-stu-id="675e1-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="675e1-114">Festlegen von Optionen auf der Seite "Konfigurationen auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="675e1-115">Festlegen von Optionen auf der Seite "Parameter erstellen"</span><span class="sxs-lookup"><span data-stu-id="675e1-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="675e1-116">Festlegen von Optionen auf der Seite "Parameter konfigurieren"</span><span class="sxs-lookup"><span data-stu-id="675e1-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="675e1-117">Festlegen der Optionen auf der Seite zum Überprüfen</span><span class="sxs-lookup"><span data-stu-id="675e1-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="675e1-118">Festlegen der Optionen unter "Konvertierung ausführen"</span><span class="sxs-lookup"><span data-stu-id="675e1-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="675e1-119">Assistent zum Konvertieren von Integration Services Projekten öffnen</span><span class="sxs-lookup"><span data-stu-id="675e1-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="675e1-120">Führen Sie einen der folgenden Schritte aus, um den Assistenten zum Konvertieren von **Integration Services-Projekten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="675e1-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="675e1-121">Öffnen Sie das Projekt in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], und klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt. Klicken Sie anschließend auf **In Projektbereitstellungsmodell konvertieren**.</span><span class="sxs-lookup"><span data-stu-id="675e1-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="675e1-122">Klicken Sie im Objekt-Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf den Knoten **Projekte** , und wählen Sie anschließend die Option **Pakete importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="675e1-123">Abhängig davon, ob Sie den Assistenten zum Konvertieren von **Integration Services-Projekten** von [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oder von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]ausführen, führt der Assistent unterschiedliche Konvertierungstasks aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="675e1-124">Weitere Informationen finden Sie unter [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="675e1-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="675e1-125">Festlegen von Optionen auf der Seite "Pakete suchen"</span><span class="sxs-lookup"><span data-stu-id="675e1-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="675e1-126"> Die Seite **Pakete suchen** ist nur verfügbar, wenn Sie den Assistenten über [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="675e1-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="675e1-127">Die folgende Option wird auf der Seite angezeigt, wenn Sie **Dateisystem** in der Dropdownliste **Quelle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="675e1-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="675e1-128">Wählen Sie diese Option, wenn das Paket im Dateisystem gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="675e1-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="675e1-129">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="675e1-129">**Folder**</span></span>  
 <span data-ttu-id="675e1-130">Geben Sie den Paketpfad ein, oder navigieren Sie zum Paket, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="675e1-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="675e1-131">Die folgenden Optionen werden auf der Seite angezeigt, wenn Sie **SSIS-Paketspeicher** in der Dropdownliste **Quelle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="675e1-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="675e1-132">Weitere Informationen zum Paketspeicher finden Sie unter [Paketverwaltung &#40;SSIS-Dienst&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="675e1-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="675e1-133">**Server**</span><span class="sxs-lookup"><span data-stu-id="675e1-133">**Server**</span></span>  
 <span data-ttu-id="675e1-134">Geben Sie einen Servernamen ein, oder wählen Sie den Server aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="675e1-135">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="675e1-135">**Folder**</span></span>  
 <span data-ttu-id="675e1-136">Geben Sie den Paketpfad ein, oder navigieren Sie zum Paket, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="675e1-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="675e1-137">Die folgenden Optionen werden auf der Seite angezeigt, wenn Sie **Microsoft SQL Server** in der Dropdownliste **Quelle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="675e1-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="675e1-138">Wählen Sie diese Option aus, wenn das Paket in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="675e1-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="675e1-139">**Server**</span><span class="sxs-lookup"><span data-stu-id="675e1-139">**Server**</span></span>  
 <span data-ttu-id="675e1-140">Geben Sie einen Servernamen ein, oder wählen Sie den Server aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="675e1-141">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="675e1-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="675e1-142">Der Microsoft Windows-Authentifizierungsmodus ermöglicht Benutzern das Herstellen einer Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="675e1-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="675e1-143">Wenn Sie die Windows-Authentifizierung verwenden, müssen Sie keinen Benutzernamen und kein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="675e1-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="675e1-144">**SQL Server Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="675e1-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="675e1-145">Wenn ein Benutzer eine Verbindung mit einem angegebenen Benutzernamen und einem Kennwort von einer nicht vertrauenswürdigen Verbindung herstellt, authentifiziert [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Verbindung, indem überprüft wird, ob ein [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldekonto eingerichtet wurde und ob das angegebene Kennwort mit dem zuvor aufgezeichneten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="675e1-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="675e1-146">Wenn kein Anmeldekonto in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eingerichtet wurde, schlägt die Authentifizierung fehl, und der Benutzer erhält eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="675e1-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="675e1-147">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="675e1-147">**User name**</span></span>  
 <span data-ttu-id="675e1-148">Geben Sie einen Benutzernamen an, wenn Sie die SQL Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="675e1-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="675e1-149">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="675e1-149">**Password**</span></span>  
 <span data-ttu-id="675e1-150">Geben Sie das Kennwort ein, wenn Sie die SQL Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="675e1-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="675e1-151">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="675e1-151">**Folder**</span></span>  
 <span data-ttu-id="675e1-152">Geben Sie den Paketpfad ein, oder navigieren Sie zum Paket, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="675e1-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="675e1-153">Festlegen von Optionen auf der Seite "Pakete auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="675e1-154">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="675e1-154">**Package Name**</span></span>  
 <span data-ttu-id="675e1-155">Listet die Paketdatei auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="675e1-156">**Status**</span><span class="sxs-lookup"><span data-stu-id="675e1-156">**Status**</span></span>  
 <span data-ttu-id="675e1-157">Gibt an, ob ein Paket bereit ist, in das Projektbereitstellungsmodell konvertiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="675e1-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="675e1-158">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="675e1-158">**Message**</span></span>  
 <span data-ttu-id="675e1-159">Zeigt eine Meldung an, die dem Paket zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="675e1-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="675e1-160">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="675e1-160">**Password**</span></span>  
 <span data-ttu-id="675e1-161">Zeigt ein Kennwort an, das dem Paket zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="675e1-161">Displays a password associated with the package.</span></span> <span data-ttu-id="675e1-162">Der Kennworttext ist ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="675e1-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="675e1-163">**Auf Auswahl anwenden**</span><span class="sxs-lookup"><span data-stu-id="675e1-163">**Apply to selection**</span></span>  
 <span data-ttu-id="675e1-164">Klicken Sie, um das Kennwort im Textfeld **Kennwort** auf das bzw. die ausgewählten Pakete anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="675e1-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="675e1-165">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="675e1-165">**Refresh**</span></span>  
 <span data-ttu-id="675e1-166">Aktualisiert die Liste der Pakete.</span><span class="sxs-lookup"><span data-stu-id="675e1-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="675e1-167">Festlegen von Optionen auf der Seite "Ziel auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="675e1-168">Geben Sie auf dieser Seite den Namen und den Pfad für eine neue Projektbereitstellungsdatei (.ispac) an, oder wählen Sie eine vorhandene Datei aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="675e1-169"> Die Seite **Ziel auswählen** ist nur verfügbar, wenn Sie den Assistenten über [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="675e1-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="675e1-170">**Ausgabepfad**</span><span class="sxs-lookup"><span data-stu-id="675e1-170">**Output path**</span></span>  
 <span data-ttu-id="675e1-171">Geben Sie den Pfad für die Bereitstellungsdatei ein, oder navigieren Sie zur Datei, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="675e1-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="675e1-172">**Projektname**</span><span class="sxs-lookup"><span data-stu-id="675e1-172">**Project name**</span></span>  
 <span data-ttu-id="675e1-173">Geben Sie den Projektnamen ein.</span><span class="sxs-lookup"><span data-stu-id="675e1-173">Type the project name.</span></span>  
  
 <span data-ttu-id="675e1-174">**Schutzebene**</span><span class="sxs-lookup"><span data-stu-id="675e1-174">**Protection level**</span></span>  
 <span data-ttu-id="675e1-175">Wählen Sie die Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-175">Select the protection level.</span></span> <span data-ttu-id="675e1-176">Weitere Informationen finden Sie unter [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="675e1-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="675e1-177">**Projektbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="675e1-177">**Project description**</span></span>  
 <span data-ttu-id="675e1-178">Geben Sie eine optionale Beschreibung für das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="675e1-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a> <span data-ttu-id="675e1-179">Festlegen von Optionen auf der Seite "Projekteigenschaften angeben"</span><span class="sxs-lookup"><span data-stu-id="675e1-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="675e1-180"> Die Seite **Projekteigenschaften angeben** ist nur verfügbar, wenn Sie den Assistenten über [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="675e1-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="675e1-181">**Projektname**</span><span class="sxs-lookup"><span data-stu-id="675e1-181">**Project name**</span></span>  
 <span data-ttu-id="675e1-182">Listet den Projektnamen auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="675e1-183">**Schutzebene**</span><span class="sxs-lookup"><span data-stu-id="675e1-183">**Protection level**</span></span>  
 <span data-ttu-id="675e1-184">Wählen Sie eine Schutzebene für die im Projekt enthaltenen Pakete aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="675e1-185">Weitere Informationen zu Schutzebenen finden Sie unter [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="675e1-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="675e1-186">**Projektbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="675e1-186">**Project description**</span></span>  
 <span data-ttu-id="675e1-187">Geben Sie eine optionale Beschreibung für das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="675e1-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="675e1-188">Festlegen von Optionen auf der Seite "Task ' Paket ausführen ' aktualisieren"</span><span class="sxs-lookup"><span data-stu-id="675e1-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="675e1-189">Aktualisieren Sie die in den Paketen enthaltenen Tasks "Paket ausführen", um einen projektbasierten Verweis zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="675e1-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="675e1-190">Weitere Informationen finden Sie unter [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="675e1-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="675e1-191">**Übergeordnetes Paket**</span><span class="sxs-lookup"><span data-stu-id="675e1-191">**Parent Package**</span></span>  
 <span data-ttu-id="675e1-192">Listet den Namen eines Pakets auf, das ein untergeordnetes Paket mithilfe des Tasks "Paket ausführen" ausführt.</span><span class="sxs-lookup"><span data-stu-id="675e1-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="675e1-193">**Taskname**</span><span class="sxs-lookup"><span data-stu-id="675e1-193">**Task name**</span></span>  
 <span data-ttu-id="675e1-194">Listet den Namen des Tasks "Paket ausführen" auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="675e1-195">**Ursprünglicher Verweis**</span><span class="sxs-lookup"><span data-stu-id="675e1-195">**Original reference**</span></span>  
 <span data-ttu-id="675e1-196">Listet den aktuellen Pfad des untergeordneten Pakets auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="675e1-197">**Verweis zuweisen**</span><span class="sxs-lookup"><span data-stu-id="675e1-197">**Assign reference**</span></span>  
 <span data-ttu-id="675e1-198">Wählen Sie ein untergeordnetes im Projekt gespeichertes Paket aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a> <span data-ttu-id="675e1-199">Festlegen von Optionen auf der Seite "Konfigurationen auswählen"</span><span class="sxs-lookup"><span data-stu-id="675e1-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="675e1-200">Wählen Sie die Paketkonfigurationen aus, die Sie durch Parameter ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="675e1-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="675e1-201">**Paket**</span><span class="sxs-lookup"><span data-stu-id="675e1-201">**Package**</span></span>  
 <span data-ttu-id="675e1-202">Listet die Paketdatei auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="675e1-203">**Type**</span><span class="sxs-lookup"><span data-stu-id="675e1-203">**Type**</span></span>  
 <span data-ttu-id="675e1-204">Listet den Typ der Konfiguration auf, z. B. eine XML-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="675e1-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="675e1-205">**Konfigurationszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="675e1-205">**Configuration String**</span></span>  
 <span data-ttu-id="675e1-206">Listet den Pfad der Konfigurationsdatei auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="675e1-207">**Status**</span><span class="sxs-lookup"><span data-stu-id="675e1-207">**Status**</span></span>  
 <span data-ttu-id="675e1-208">Zeigt eine Statusmeldung für die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="675e1-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="675e1-209">Klicken Sie auf die Meldung, um den gesamten Meldungstext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="675e1-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="675e1-210">**Hinzufügen von Konfigurationen**</span><span class="sxs-lookup"><span data-stu-id="675e1-210">**Add Configurations**</span></span>  
 <span data-ttu-id="675e1-211">Fügen Sie in anderen Projekten enthaltene Paketkonfigurationen der Liste mit verfügbaren Konfigurationen hinzu, die Sie durch Parameter ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="675e1-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="675e1-212">Sie können in einem Dateisystem oder in SQL Server gespeicherte Konfigurationen auswählen.</span><span class="sxs-lookup"><span data-stu-id="675e1-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="675e1-213">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="675e1-213">**Refresh**</span></span>  
 <span data-ttu-id="675e1-214">Klicken Sie auf die Option, um die Liste der Konfigurationen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="675e1-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="675e1-215">**Option zum Entfernen der Konfigurationen von allen Paketen nach der Konvertierung**</span><span class="sxs-lookup"><span data-stu-id="675e1-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="675e1-216">Es wird empfohlen, durch Aktivierung dieser Option alle Konfigurationen vom Projekt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="675e1-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="675e1-217">Wenn Sie diese Option nicht auswählen, werden nur die Konfigurationen entfernt, die durch Parameter ersetzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="675e1-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a> <span data-ttu-id="675e1-218">Festlegen von Optionen auf der Seite "Parameter erstellen"</span><span class="sxs-lookup"><span data-stu-id="675e1-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="675e1-219">Wählen Sie den Parameternamen und den Bereich für jede Konfigurationseigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="675e1-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="675e1-220">**Paket**</span><span class="sxs-lookup"><span data-stu-id="675e1-220">**Package**</span></span>  
 <span data-ttu-id="675e1-221">Listet die Paketdatei auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="675e1-222">**Parametername**</span><span class="sxs-lookup"><span data-stu-id="675e1-222">**Parameter Name**</span></span>  
 <span data-ttu-id="675e1-223">Listet den Namen des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="675e1-224">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="675e1-224">**Scope**</span></span>  
 <span data-ttu-id="675e1-225">Wählen Sie den Bereich des Parameters aus, und zwar entweder Paket oder Projekt.</span><span class="sxs-lookup"><span data-stu-id="675e1-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="675e1-226">Festlegen von Optionen auf der Seite "Parameter konfigurieren"</span><span class="sxs-lookup"><span data-stu-id="675e1-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="675e1-227">**Name**</span><span class="sxs-lookup"><span data-stu-id="675e1-227">**Name**</span></span>  
 <span data-ttu-id="675e1-228">Listet den Namen des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="675e1-229">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="675e1-229">**Scope**</span></span>  
 <span data-ttu-id="675e1-230">Listet den Bereich des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="675e1-231">**Wert**</span><span class="sxs-lookup"><span data-stu-id="675e1-231">**Value**</span></span>  
 <span data-ttu-id="675e1-232">Listet den Parameterwert auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="675e1-233">Klicken Sie auf die Auslassungspunkte, die sich neben dem Wertefeld befinden, um die Parametereigenschaften zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="675e1-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="675e1-234">Im Dialogfeld **Parameterdetails festlegen** können Sie den Parameterwert bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="675e1-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="675e1-235">Sie können auch angeben, ob der Parameterwert bereitgestellt werden muss, wenn Sie das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="675e1-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="675e1-236">Sie können den Wert auf der Seite **Parameter** des Dialogfelds **Konfigurieren** in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]ändern, indem Sie neben dem Parameter auf die Schaltfläche zum Durchsuchen klicken.</span><span class="sxs-lookup"><span data-stu-id="675e1-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="675e1-237">Das Dialogfeld **Parameterwert festlegen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="675e1-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="675e1-238">Das Dialogfeld **Parameterdetails festlegen** listet auch den Datentyp des Parameterwerts und den Ursprung des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="675e1-239">Festlegen der Optionen auf der Seite "überprüfen"</span><span class="sxs-lookup"><span data-stu-id="675e1-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="675e1-240">Verwenden Sie die Seite für die **Überprüfung**, um die Optionen zu bestätigen, die Sie für die Konvertierung des Projekts ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="675e1-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="675e1-241">**Zurück**</span><span class="sxs-lookup"><span data-stu-id="675e1-241">**Previous**</span></span>  
 <span data-ttu-id="675e1-242">Klicken Sie, um eine Option zu ändern.</span><span class="sxs-lookup"><span data-stu-id="675e1-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="675e1-243">**Konvertieren**</span><span class="sxs-lookup"><span data-stu-id="675e1-243">**Convert**</span></span>  
 <span data-ttu-id="675e1-244">Klicken Sie, um das Projekt in das Projektbereitstellungsmodell zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="675e1-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="675e1-245">Festlegen der Optionen für die Konvertierung ausführen</span><span class="sxs-lookup"><span data-stu-id="675e1-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="675e1-246">Die Seite "Konvertierung ausführen" zeigt den Status der Projektkonvertierung an.</span><span class="sxs-lookup"><span data-stu-id="675e1-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="675e1-247">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="675e1-247">**Action**</span></span>  
 <span data-ttu-id="675e1-248">Listet einen bestimmten Konvertierungsschritt auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="675e1-249">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="675e1-249">**Result**</span></span>  
 <span data-ttu-id="675e1-250">Listet die Status sämtlicher Konvertierungsschritte auf.</span><span class="sxs-lookup"><span data-stu-id="675e1-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="675e1-251">Klicken Sie auf die Statusmeldung, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="675e1-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="675e1-252">Die Projektkonvertierung wird erst gespeichert, wenn das Projekt in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="675e1-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="675e1-253">**Bericht speichern**</span><span class="sxs-lookup"><span data-stu-id="675e1-253">**Save report**</span></span>  
 <span data-ttu-id="675e1-254">Klicken Sie, um in einer XML-Datei eine Zusammenfassung der Projektkonvertierung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="675e1-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675e1-255">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="675e1-255">See Also</span></span>  
 [<span data-ttu-id="675e1-256">Deploy Projects to Integration Services Server</span><span class="sxs-lookup"><span data-stu-id="675e1-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
