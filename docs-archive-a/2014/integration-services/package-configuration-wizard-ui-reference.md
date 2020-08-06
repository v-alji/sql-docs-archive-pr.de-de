---
title: Referenz zur Benutzeroberfläche des Paketkonfigurations-Assistenten Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621584"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="02856-102">Referenz zur Benutzeroberfläche des Paketkonfigurations-Assistenten</span><span class="sxs-lookup"><span data-stu-id="02856-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="02856-103">Der **Paketkonfigurations-Assistent** unterstützt Sie dabei, Konfigurationen zu erstellen, durch die die Eigenschaften eines [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakets und seiner Objekte zur Laufzeit aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="02856-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="02856-104">Dieser Assistent wird ausgeführt, wenn Sie im Dialogfeld **Paketkonfigurationsplaner** eine neue Konfiguration hinzufügen oder eine vorhandene Konfiguration ändern.</span><span class="sxs-lookup"><span data-stu-id="02856-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="02856-105">Um das Dialogfeld **Paketkonfigurationsplaner** zu öffnen, wählen Sie in **im Menü** SSIS **die Option** Paketkonfigurationen [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="02856-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="02856-106">Weitere Informationen finden Sie unter [Erstellen von Paketkonfigurationen](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="02856-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02856-107">Konfigurationen sind für das Paketbereitstellungsmodell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02856-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="02856-108">Parameter werden für das Projektbereitstellungsmodell anstelle von Konfigurationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="02856-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="02856-109">Mithilfe des Projektbereitstellungsmodells können Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekte auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02856-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="02856-110">Weitere Informationen zu Bereitstellungsmodellen finden Sie unter [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="02856-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="02856-111">In den folgenden Abschnitten werden Seiten des Assistenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02856-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="02856-112">Willkommensseite des Paketkonfigurationsassistenten</span><span class="sxs-lookup"><span data-stu-id="02856-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="02856-113">Mithilfe des **SSIS-Konfigurations-Assistenten** können Sie Konfigurationen erstellen, durch die die Eigenschaften eines Paketes und seiner Objekte zur Laufzeit aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="02856-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="02856-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="02856-114">Options</span></span>  
 <span data-ttu-id="02856-115">**Diese Seite nicht wieder anzeigen**</span><span class="sxs-lookup"><span data-stu-id="02856-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="02856-116">Die Willkommensseite beim nächsten Öffnen des Assistenten auslassen.</span><span class="sxs-lookup"><span data-stu-id="02856-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="02856-117">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="02856-117">**Next**</span></span>  
 <span data-ttu-id="02856-118">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="02856-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="02856-119">Seite "Konfigurationstyp" auswählen</span><span class="sxs-lookup"><span data-stu-id="02856-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="02856-120">Auf der Seite **Konfigurationstyp auswählen** können Sie die Art der Konfiguration angeben, die erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="02856-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="02856-121">Weitere Informationen dazu, welchen Konfigurationstyp Sie verwenden sollten, finden Sie unter [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="02856-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="02856-122">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="02856-122">Static Options</span></span>  
 <span data-ttu-id="02856-123">**Konfigurationstyp**</span><span class="sxs-lookup"><span data-stu-id="02856-123">**Configuration type**</span></span>  
 <span data-ttu-id="02856-124">Wählen Sie mithilfe folgender Optionen den Typ der Quelle aus, in der die Konfiguration gespeichert werden soll:</span><span class="sxs-lookup"><span data-stu-id="02856-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="02856-125">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-125">Value</span></span>|<span data-ttu-id="02856-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-127">**XML-Konfigurationsdatei**</span><span class="sxs-lookup"><span data-stu-id="02856-127">**XML configuration file**</span></span>|<span data-ttu-id="02856-128">Speichert die Konfiguration als XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="02856-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="02856-129">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen im Abschnitt **Konfigurationstyp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02856-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="02856-130">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-130">**Environment variable**</span></span>|<span data-ttu-id="02856-131">Speichert die Konfiguration in einer der Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="02856-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="02856-132">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen im Abschnitt **Konfigurationstyp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02856-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="02856-133">**Registrierungseintrag**</span><span class="sxs-lookup"><span data-stu-id="02856-133">**Registry entry**</span></span>|<span data-ttu-id="02856-134">Speichert die Konfiguration in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="02856-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="02856-135">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen im Abschnitt **Konfigurationstyp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02856-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="02856-136">**Variable für das übergeordnete Paket**</span><span class="sxs-lookup"><span data-stu-id="02856-136">**Parent package variable**</span></span>|<span data-ttu-id="02856-137">Speichert die Konfiguration als Variable in dem Paket, das den Task enthält.</span><span class="sxs-lookup"><span data-stu-id="02856-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="02856-138">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen im Abschnitt **Konfigurationstyp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02856-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="02856-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="02856-139">**SQL Server**</span></span>|<span data-ttu-id="02856-140">Speichert die Konfiguration in einer Tabelle in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02856-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02856-141">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen im Abschnitt **Konfigurationstyp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02856-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="02856-142">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="02856-142">**Next**</span></span>  
 <span data-ttu-id="02856-143">Zeigt die nächste Seite in der Sequenz des Assistenten an.</span><span class="sxs-lookup"><span data-stu-id="02856-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="02856-144">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="02856-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="02856-145">Konfigurationstypoption = XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="02856-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="02856-146">**Konfigurationseinstellungen direkt angeben**</span><span class="sxs-lookup"><span data-stu-id="02856-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="02856-147">Verwenden Sie diese Option, um die Einstellungen direkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02856-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="02856-148">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-148">Value</span></span>|<span data-ttu-id="02856-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-150">**Konfigurationsdateiname**</span><span class="sxs-lookup"><span data-stu-id="02856-150">**Configuration file name**</span></span>|<span data-ttu-id="02856-151">Geben Sie den Pfad der Konfigurationsdatei ein, die der Assistent generiert.</span><span class="sxs-lookup"><span data-stu-id="02856-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="02856-152">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="02856-152">**Browse**</span></span>|<span data-ttu-id="02856-153">Im Dialogfeld **Speicherort der Konfigurationsdatei auswählen** können Sie den Pfad für die Konfigurationsdatei angeben, die der Assistent generiert.</span><span class="sxs-lookup"><span data-stu-id="02856-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="02856-154">Wenn die Datei nicht vorhanden ist, wird sie durch den Assistenten erstellt.</span><span class="sxs-lookup"><span data-stu-id="02856-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="02856-155">**Konfigurationsspeicherort ist in einer Umgebungsvariablen gespeichert**</span><span class="sxs-lookup"><span data-stu-id="02856-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="02856-156">Verwenden Sie diese Option, um die Umgebungsvariable anzugeben, in der die Konfiguration gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="02856-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="02856-157">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-157">Value</span></span>|<span data-ttu-id="02856-158">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-159">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-159">**Environment variable**</span></span>|<span data-ttu-id="02856-160">Wählen Sie eine Umgebungsvariable aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="02856-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="02856-161">Konfigurationstypoption = Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="02856-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="02856-162">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-162">**Environment variable**</span></span>  
 <span data-ttu-id="02856-163">Wählen Sie die Umgebungsvariable aus, die die Konfigurationsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="02856-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="02856-164">Konfigurationstypoption = Registrierungseintrag</span><span class="sxs-lookup"><span data-stu-id="02856-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="02856-165">**Konfigurationseinstellungen direkt angeben**</span><span class="sxs-lookup"><span data-stu-id="02856-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="02856-166">Verwenden Sie diese Option, um die Einstellungen direkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02856-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="02856-167">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-167">Value</span></span>|<span data-ttu-id="02856-168">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-169">**Registrierungseintrag**</span><span class="sxs-lookup"><span data-stu-id="02856-169">**Registry entry**</span></span>|<span data-ttu-id="02856-170">Geben Sie den Registrierungsschlüssel ein, der die Konfigurationsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="02856-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="02856-171">Das Format ist \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="02856-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="02856-172">Der Registrierungsschlüssel muss bereits in HKEY_CURRENT_USER vorhanden sein und einen Wert mit dem Namen "Value" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="02856-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="02856-173">Bei diesem Wert kann es sich um einen Wert vom Typ DWORD oder um eine Zeichenfolge handeln.</span><span class="sxs-lookup"><span data-stu-id="02856-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="02856-174">Wenn Sie einen Registrierungsschlüssel verwenden möchten, der nicht im Stamm von HKEY_CURRENT_USER gespeichert ist, verwenden Sie das Format \<Registry key\registry key\\...>, um den Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="02856-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="02856-175">**Konfigurationsspeicherort ist in einer Umgebungsvariablen gespeichert**</span><span class="sxs-lookup"><span data-stu-id="02856-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="02856-176">Verwenden Sie diese Option, um die Umgebungsvariable anzugeben, in der die Konfiguration gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="02856-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="02856-177">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-177">Value</span></span>|<span data-ttu-id="02856-178">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-179">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-179">**Environment variable**</span></span>|<span data-ttu-id="02856-180">Wählen Sie eine Umgebungsvariable aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="02856-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="02856-181">Konfigurationstypoption = Variable für das übergeordnete Paket</span><span class="sxs-lookup"><span data-stu-id="02856-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="02856-182">**Konfigurationseinstellungen direkt angeben**</span><span class="sxs-lookup"><span data-stu-id="02856-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="02856-183">Verwenden Sie diese Option, um die Einstellungen direkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02856-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="02856-184">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-184">Value</span></span>|<span data-ttu-id="02856-185">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-186">**Übergeordnete Variable**</span><span class="sxs-lookup"><span data-stu-id="02856-186">**Parent variable**</span></span>|<span data-ttu-id="02856-187">Geben Sie die Variable im übergeordneten Paket an, die die Konfigurationsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="02856-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="02856-188">**Konfigurationsspeicherort ist in einer Umgebungsvariablen gespeichert**</span><span class="sxs-lookup"><span data-stu-id="02856-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="02856-189">Verwenden Sie diese Option, um die Umgebungsvariable anzugeben, in der die Konfiguration gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="02856-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="02856-190">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-190">Value</span></span>|<span data-ttu-id="02856-191">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-192">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-192">**Environment variable**</span></span>|<span data-ttu-id="02856-193">Wählen Sie eine Umgebungsvariable aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="02856-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="02856-194">Konfigurationstypoptionen = SQL Server</span><span class="sxs-lookup"><span data-stu-id="02856-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="02856-195">**Konfigurationseinstellungen direkt angeben**</span><span class="sxs-lookup"><span data-stu-id="02856-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="02856-196">Verwenden Sie diese Option, um die Einstellungen direkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02856-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="02856-197">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-197">Value</span></span>|<span data-ttu-id="02856-198">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-199">**Connection**</span><span class="sxs-lookup"><span data-stu-id="02856-199">**Connection**</span></span>|<span data-ttu-id="02856-200">Wählen Sie eine Verbindung aus der Liste aus, oder klicken Sie auf **Neu** , um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="02856-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="02856-201">**Konfigurationstabelle**</span><span class="sxs-lookup"><span data-stu-id="02856-201">**Configuration table**</span></span>|<span data-ttu-id="02856-202">Wählen Sie eine vorhandene Tabelle aus, oder klicken Sie auf **Neu** , um eine SQL-Anweisung zu schreiben, die eine neue Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="02856-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="02856-203">**Konfigurationsfilter**</span><span class="sxs-lookup"><span data-stu-id="02856-203">**Configuration filter**</span></span>|<span data-ttu-id="02856-204">Wählen Sie einen vorhandenen Konfigurationsnamen aus, oder geben Sie einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="02856-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="02856-205">Viele SQL Server-Konfigurationen können in derselben Tabelle gespeichert werden, und jede Konfiguration kann mehrere Konfigurationselemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="02856-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="02856-206">Dieser benutzerdefinierte Wert wird in der Tabelle gespeichert, um Konfigurationselemente zu identifizieren, die zu einer bestimmten Konfiguration gehören.</span><span class="sxs-lookup"><span data-stu-id="02856-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="02856-207">**Konfigurationsspeicherort ist in einer Umgebungsvariablen gespeichert**</span><span class="sxs-lookup"><span data-stu-id="02856-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="02856-208">Verwenden Sie diese Option, um die Umgebungsvariable anzugeben, in der die Konfiguration gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="02856-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="02856-209">Wert</span><span class="sxs-lookup"><span data-stu-id="02856-209">Value</span></span>|<span data-ttu-id="02856-210">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02856-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02856-211">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="02856-211">**Environment variable**</span></span>|<span data-ttu-id="02856-212">Wählen Sie eine Umgebungsvariable aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="02856-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="02856-213">Seite "Eigenschaften für den Exportvorgang auswählen"</span><span class="sxs-lookup"><span data-stu-id="02856-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="02856-214">Verwenden Sie die Seite **Zieleigenschaft auswählen** oder die Seite Eigenschaften für den Exportvorgang auswählen, um die in der Konfiguration enthaltenen Objekteigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02856-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="02856-215">Mehrere Eigenschaften können nur ausgewählt werden, wenn Sie als Konfigurationstyp XML auswählen.</span><span class="sxs-lookup"><span data-stu-id="02856-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="02856-216">Tastatur</span><span class="sxs-lookup"><span data-stu-id="02856-216">Options</span></span>  
 <span data-ttu-id="02856-217">**Objekte**</span><span class="sxs-lookup"><span data-stu-id="02856-217">**Objects**</span></span>  
 <span data-ttu-id="02856-218">Erweitern Sie die Pakethierarchie, und wählen Sie die zu exportierenden Eigenschaften aus.</span><span class="sxs-lookup"><span data-stu-id="02856-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="02856-219">**Eigenschaftsattribute**</span><span class="sxs-lookup"><span data-stu-id="02856-219">**Property attributes**</span></span>  
 <span data-ttu-id="02856-220">Zeigen Sie die Attribute einer Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="02856-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="02856-221">**Weiter**</span><span class="sxs-lookup"><span data-stu-id="02856-221">**Next**</span></span>  
 <span data-ttu-id="02856-222">Mit dieser Option können Sie zur nächsten Seite des Assistenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="02856-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="02856-223">Seite "Assistenten abschließen"</span><span class="sxs-lookup"><span data-stu-id="02856-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="02856-224">Mithilfe der Seite **Assistenten abschließen** können Sie einen Namen für die Konfiguration und die Einstellungen der Sicht angeben, die der Assistent zum Erstellen der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="02856-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="02856-225">Nach dem Abschließen des Assistenten wird der **Paketkonfigurationsplaner** angezeigt, in dem alle Konfigurationen für das Paket aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="02856-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="02856-226">Tastatur</span><span class="sxs-lookup"><span data-stu-id="02856-226">Options</span></span>  
 <span data-ttu-id="02856-227">**Konfigurationsname**</span><span class="sxs-lookup"><span data-stu-id="02856-227">**Configuration name**</span></span>  
 <span data-ttu-id="02856-228">Geben Sie den Namen der Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="02856-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="02856-229">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="02856-229">**Preview**</span></span>  
 <span data-ttu-id="02856-230">Zeigen Sie die Einstellungen an, die vom Assistenten zum Erstellen der Konfiguration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02856-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="02856-231">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="02856-231">**Finish**</span></span>  
 <span data-ttu-id="02856-232">Erstellen Sie die Konfiguration, und beenden Sie den **Paketkonfigurations-Assistenten**.</span><span class="sxs-lookup"><span data-stu-id="02856-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02856-233">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02856-233">See Also</span></span>  
 [<span data-ttu-id="02856-234">Erstellen von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="02856-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
