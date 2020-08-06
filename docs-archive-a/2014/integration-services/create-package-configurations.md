---
title: Erstellen von Paket Konfigurationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, configurations
- Package Configurations Organizer dialog box
- SSIS packages, configurations
- Integration Services packages, configurations
- configurations [Integration Services]
- packages [Integration Services], configurations
- deploying packages [Integration Services], configurations
ms.assetid: 91ac0347-f908-44f5-bd3d-115790223af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58c93242c9ef51a5e00076bd367e46b43187098e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616609"
---
# <a name="create-package-configurations"></a><span data-ttu-id="34f7c-102">Erstellen von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="34f7c-102">Create Package Configurations</span></span>
  <span data-ttu-id="34f7c-103">Im Dialogfeld **Paketkonfigurationsplaner** und im Paketkonfigurationsassistenten erstellen Sie Paketkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-103">You create package configurations by using the **Package Configuration Organizer** dialog box and the Package Configuration Wizard.</span></span> <span data-ttu-id="34f7c-104">Um auf diese Tools zuzugreifen, klicken Sie in **im Menü** SSIS **auf** Paketkonfigurationen [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f7c-104">To access these tools, click **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f7c-105">Sie können auch auf den **Paket Konfigurations Planer**zugreifen, indem Sie auf die Schaltfläche mit den Auslassungs Punkten neben der- **Konfigurations** Eigenschaft klicken.</span><span class="sxs-lookup"><span data-stu-id="34f7c-105">You can also access the **Package Configuration Organizer**, by clicking the ellipsis button next to the **Configuration** property.</span></span> <span data-ttu-id="34f7c-106">Die Eigenschaft Konfiguration wird im Eigenschaftenfenster für das Paket angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34f7c-106">The Configuration property appears in the properties window for the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f7c-107">Konfigurationen sind für das Paketbereitstellungsmodell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34f7c-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="34f7c-108">Parameter werden für das Projektbereitstellungsmodell anstelle von Konfigurationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="34f7c-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="34f7c-109">Mithilfe des Projektbereitstellungsmodells können Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekte auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="34f7c-110">Weitere Informationen zu Bereitstellungsmodellen finden Sie unter [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="34f7c-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="34f7c-111">Im Dialogfeld **Paketkonfigurationsplaner** können Sie Pakete zum Verwenden von Konfigurationen aktivieren, Konfigurationen hinzufügen und löschen sowie die bevorzugte Reihenfolge festlegen, in der die Konfigurationen geladen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="34f7c-111">In the **Package Configuration Organizer** dialog box, you can enable packages to use configurations, add and delete configurations, and set the preferred order in which configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f7c-112">Wenn Paketkonfigurationen in der bevorzugten Reihenfolge geladen werden, werden die Konfigurationen in der Reihenfolge geladen, in der sie im Dialogfeld **Paketkonfigurationsplaner** angezeigt werden, wobei mit der Konfiguration am Anfang der Liste begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="34f7c-112">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="34f7c-113">Zur Laufzeit werden Paketkonfigurationen möglicherweise aber nicht in der bevorzugten Reihenfolge geladen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-113">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="34f7c-114">Beispielsweise werden übergeordnete Paketkonfigurationen nach Konfigurierungen anderer Typen geladen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-114">In particular, parent package configurations load after configurations of other types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f7c-115">Wenn mehrere Konfigurationen dieselbe Objekteigenschaft festlegen, wird der zuletzt geladene Wert zur Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="34f7c-115">If multiple configurations set the same object property, the value loaded last is used at run time.</span></span>  
  
 <span data-ttu-id="34f7c-116">Im Dialogfeld **Paketkonfigurationsplaner** führen Sie den Paketkonfigurations-Assistenten aus, der Sie durch die Schritte zum Erstellen einer Konfiguration führt.</span><span class="sxs-lookup"><span data-stu-id="34f7c-116">From the **Package Configuration Organizer** dialog box, you run the Package Configuration Wizard, which guides you through the steps to create a configuration.</span></span> <span data-ttu-id="34f7c-117">Um den Paketkonfigurations-Assistenten auszuführen, fügen Sie im Dialogfeld **Paketkonfigurationsplaner** eine neue Konfiguration hinzu, oder bearbeiten Sie eine vorhandene Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="34f7c-117">To run the Package Configuration Wizard, add a new configuration in the **Package Configurations Organizer** dialog box or edit an existing one.</span></span> <span data-ttu-id="34f7c-118">Auf den Seiten des Assistenten wählen Sie den Konfigurationstyp aus. Sie legen fest, ob Sie direkt auf die Konfiguration zugreifen oder Umgebungsvariablen verwenden möchten, und Sie wählen die in der Konfiguration zu speichernden Eigenschaften aus.</span><span class="sxs-lookup"><span data-stu-id="34f7c-118">On the wizard pages, you choose the configuration type, select whether you want to access the configuration directly or use environment variables, and select the properties to save in the configuration.</span></span>  
  
 <span data-ttu-id="34f7c-119">Im folgenden Beispiel werden die Zieleigenschaften einer Variablen und eines Pakets gezeigt, so wie sie auf der Seite Assistenten abschließen des Paketkonfigurations-Assistenten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="34f7c-119">The following example shows the target properties of a variable and a package as they appear on the Completing the Wizard page of the Package Configuration Wizard.:</span></span>  
  
 <span data-ttu-id="34f7c-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span><span class="sxs-lookup"><span data-stu-id="34f7c-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span></span>  
  
 <span data-ttu-id="34f7c-121">\Package.Properties[MaximumErrorCount]</span><span class="sxs-lookup"><span data-stu-id="34f7c-121">\Package.Properties[MaximumErrorCount]</span></span>  
  
 <span data-ttu-id="34f7c-122">\Package.Properties[LoggingMode]</span><span class="sxs-lookup"><span data-stu-id="34f7c-122">\Package.Properties[LoggingMode]</span></span>  
  
 <span data-ttu-id="34f7c-123">\Package.Properties[LocaleID]</span><span class="sxs-lookup"><span data-stu-id="34f7c-123">\Package.Properties[LocaleID]</span></span>  
  
 <span data-ttu-id="34f7c-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span><span class="sxs-lookup"><span data-stu-id="34f7c-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span></span>  
  
 <span data-ttu-id="34f7c-125">In diesem Beispiel werden diese Eigenschaften von der Konfiguration aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="34f7c-125">In this example, the configuration updates these properties:</span></span>  
  
-   <span data-ttu-id="34f7c-126">Die RaiseChangedEvent-Eigenschaft der benutzerdefinierten Variablen `TodaysDate`.</span><span class="sxs-lookup"><span data-stu-id="34f7c-126">The RaiseChangedEvent property of user-defined variable, `TodaysDate`.</span></span>  
  
-   <span data-ttu-id="34f7c-127">Die Eigenschaften MaximumErrorCount, LoggingMode und LocaleID des Pakets.</span><span class="sxs-lookup"><span data-stu-id="34f7c-127">The MaximumErrorCount, LoggingMode, and LocaleID properties of the package.</span></span>  
  
-   <span data-ttu-id="34f7c-128">Die Value-Eigenschaft der benutzerdefinierten Variablen `varTableName`im Bereich des Tasks My SQL Task.</span><span class="sxs-lookup"><span data-stu-id="34f7c-128">The Value property of user-defined variable, `varTableName`, within scope of the task, My SQL Task.</span></span>  
  
 <span data-ttu-id="34f7c-129">"\Package" stellt den Stamm dar, und Punkte (.) trennen die Objekte, die den Pfad für die von der Konfiguration aktualisierten Eigenschaft definieren.</span><span class="sxs-lookup"><span data-stu-id="34f7c-129">The "\Package" represents the root, and periods (.) separate the objects that define the path to the property that the configuration updates.</span></span> <span data-ttu-id="34f7c-130">Die Namen von Variablen und Eigenschaften werden in eckigen Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-130">The names of variables and properties are enclosed in brackets.</span></span> <span data-ttu-id="34f7c-131">Der Begriff Package wird immer in der Konfiguration verwendet, unabhängig vom Paketnamen. Für alle anderen Objekte im Pfad werden jedoch die benutzerdefinierten Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="34f7c-131">The term Package is always used in configuration, regardless of the package name; however, all other objects in the path use their user-defined names.</span></span>  
  
 <span data-ttu-id="34f7c-132">Nachdem der Assistent beendet ist, wird die neue Konfiguration der Konfigurationsliste im Dialogfeld **Paketkonfigurationsplaner** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="34f7c-132">After the wizard finishes, the new configuration is added to the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f7c-133">Auf der letzten Seite des Paketkonfigurations-Assistenten, der Seite Assistenten abschließen, werden die Zieleigenschaften der Konfiguration aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="34f7c-133">The last page in the Package Configuration Wizard, Completing the Wizard, lists the target properties in the configuration.</span></span> <span data-ttu-id="34f7c-134">Wenn Sie beim Ausführen von Paketen mithilfe des Eingabeaufforderungs-Hilfsprogramms **dtexec** die Eigenschaften aktualisieren möchten, können Sie die Zeichenfolgen, die die Eigenschaftspfade darstellen, generieren. Führen Sie hierzu den Paketkonfigurations-Assistenten aus, kopieren Sie dann die Zeichenfolgen, und fügen Sie diese im Eingabeaufforderungsfenster für die Verwendung mit der festgelegten Option von **dtexec**ein.</span><span class="sxs-lookup"><span data-stu-id="34f7c-134">If you want to update properties when you run packages by using the **dtexec** command prompt utility, you can generate the strings that represent the property paths by running the Package Configuration Wizard and then copy and paste them into the command prompt window for use with the set option of **dtexec.**</span></span>  
  
 <span data-ttu-id="34f7c-135">In der folgenden Tabelle werden die Spalten der Konfigurationsliste im Dialogfeld **Paketkonfigurationsplaner** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34f7c-135">The following table describes the columns in the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
|<span data-ttu-id="34f7c-136">Column</span><span class="sxs-lookup"><span data-stu-id="34f7c-136">Column</span></span>|<span data-ttu-id="34f7c-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="34f7c-137">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="34f7c-138">**Konfigurationsname**</span><span class="sxs-lookup"><span data-stu-id="34f7c-138">**Configuration Name**</span></span>|<span data-ttu-id="34f7c-139">De Name der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="34f7c-139">The name of the configuration.</span></span>|  
|<span data-ttu-id="34f7c-140">**Konfigurationstyp**</span><span class="sxs-lookup"><span data-stu-id="34f7c-140">**Configuration Type**</span></span>|<span data-ttu-id="34f7c-141">Der Konfigurationstyp.</span><span class="sxs-lookup"><span data-stu-id="34f7c-141">The configuration type.</span></span>|  
|<span data-ttu-id="34f7c-142">**Konfigurationszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="34f7c-142">**Configuration String**</span></span>|<span data-ttu-id="34f7c-143">Der Speicherort der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="34f7c-143">The location of the configuration.</span></span> <span data-ttu-id="34f7c-144">Beim Speicherort kann es sich um einen Pfad, eine Umgebungsvariable, einen Registrierungsschlüssel, den Namen einer Variablen eines übergeordneten Pakets oder eine Tabelle in einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank handeln.</span><span class="sxs-lookup"><span data-stu-id="34f7c-144">The location can be a path, an environment variable, a Registry key, a parent package variable name, or a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="34f7c-145">**Zielobjekt**</span><span class="sxs-lookup"><span data-stu-id="34f7c-145">**Target Object**</span></span>|<span data-ttu-id="34f7c-146">Der Name des Objekts mit einer Eigenschaft, die eine Konfiguration besitzt.</span><span class="sxs-lookup"><span data-stu-id="34f7c-146">The name of the object with a property that has a configuration.</span></span> <span data-ttu-id="34f7c-147">Wenn es sich bei der Konfiguration um eine XML-Konfigurationsdatei handelt, ist die Spalte leer, da die Konfiguration mehrere Objekte aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="34f7c-147">If the configuration is an XML configuration file, the column is blank, because the configuration can update multiple objects.</span></span>|  
|<span data-ttu-id="34f7c-148">**Zieleigenschaft**</span><span class="sxs-lookup"><span data-stu-id="34f7c-148">**Target Property**</span></span>|<span data-ttu-id="34f7c-149">Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="34f7c-149">The name of the property.</span></span> <span data-ttu-id="34f7c-150">Wenn die Konfiguration in eine XML-Konfigurationsdatei oder in eine SQL Server-Tabelle schreibt, ist die Spalte leer, da die Konfiguration mehrere Objekte aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="34f7c-150">If the configuration writes to an XML configuration file or a SQL Server table, the column is blank, because the configuration can update multiple objects.</span></span>|  
  
### <a name="to-create-a-package-configuration"></a><span data-ttu-id="34f7c-151">So erstellen Sie eine Paketkonfiguration</span><span class="sxs-lookup"><span data-stu-id="34f7c-151">To create a package configuration</span></span>  
  
1.  <span data-ttu-id="34f7c-152">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="34f7c-152">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="34f7c-153">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-153">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="34f7c-154">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**, **Ereignishandler**oder **Paket-Explorer** .</span><span class="sxs-lookup"><span data-stu-id="34f7c-154">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, **Event Handler**, or **Package Explorer** tab.</span></span>  
  
4.  <span data-ttu-id="34f7c-155">Klicken Sie im Menü **SSIS** auf **Paketkonfigurationen**.</span><span class="sxs-lookup"><span data-stu-id="34f7c-155">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="34f7c-156">Wählen Sie im Dialogfeld **Paketkonfigurationsplaner** die Option **Paketkonfigurationen aktivieren**aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34f7c-156">In the **Package Configuration Organizer** dialog box, select **Enable package configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="34f7c-157">Klicken Sie auf der Willkommensseite des Paketkonfigurationsassistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34f7c-157">On the welcome page of the Package Configuration Wizard page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="34f7c-158">Geben Sie auf der Seite "Konfigurationstyp auswählen" den Konfigurationstyp an, und legen Sie dann die für den Konfigurationstyp relevanten Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="34f7c-158">On the Select Configuration Type page, specify the configuration type, and then set the properties that are relevant to the configuration type.</span></span> <span data-ttu-id="34f7c-159">Weitere Informationen finden Sie unter [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34f7c-159">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
8.  <span data-ttu-id="34f7c-160">Wählen Sie auf der Seite zum Auswählen der zu exportierenden Eigenschaften die Eigenschaften von Paketobjekten aus, die in der Konfiguration enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-160">On the Select Properties to Export page, select the properties of package objects to include in the configuration.</span></span> <span data-ttu-id="34f7c-161">Wenn der Konfigurationstyp nur eine Eigenschaft unterstützt, lautet die Überschrift dieser Assistentenseite Zieleigenschaft auswählen.</span><span class="sxs-lookup"><span data-stu-id="34f7c-161">If the configuration type supports only one property, the title of this wizard page is Select Target Property.</span></span> <span data-ttu-id="34f7c-162">Weitere Informationen finden Sie unter [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34f7c-162">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34f7c-163">Nur die Konfigurationstypen **XML-Konfigurationsdatei** und **SQL Server** unterstützen die Berücksichtigung von mehreren Eigenschaften in einer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="34f7c-163">Only the **XML Configuration File** and **SQL Server** configuration types support including multiple properties in a configuration.</span></span>  
  
9. <span data-ttu-id="34f7c-164">Geben Sie auf der Seite "Assistenten abschließen" den Namen der Konfiguration ein, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="34f7c-164">On the Completing the Wizard page, type the name of the configuration, and then click **Finish**.</span></span>  
  
10. <span data-ttu-id="34f7c-165">Zeigen Sie die Konfiguration im Dialogfeld **Paketkonfigurationsplaner** an.</span><span class="sxs-lookup"><span data-stu-id="34f7c-165">View the configuration in the **Package Configuration Organizer** dialog box.</span></span>  
  
11. <span data-ttu-id="34f7c-166">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="34f7c-166">Click **Close**.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="34f7c-167">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="34f7c-167">External Resources</span></span>  
  
-   <span data-ttu-id="34f7c-168">Technischer Artikel [Grundlegendes zu Integration Services-Paketkonfigurationen](https://go.microsoft.com/fwlink/?LinkId=165643)auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="34f7c-168">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="34f7c-169">Blog Eintrag [Erstellen von Paketen in Code Paket Konfigurationen](https://go.microsoft.com/fwlink/?LinkId=217663)auf www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="34f7c-169">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="34f7c-170">Blog Eintrag [API-Beispiel: Programm gesteuertes Hinzufügen einer Konfigurationsdatei zu einem Paket](https://go.microsoft.com/fwlink/?LinkId=217664)auf Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="34f7c-170">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f7c-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34f7c-171">See Also</span></span>  
 <span data-ttu-id="34f7c-172">[Paket Konfigurationen](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="34f7c-172">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="34f7c-173">[Paket Bereitstellung &#40;SSIS-&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="34f7c-173">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="34f7c-174">Programmgesteuertes Arbeiten mit Variablen</span><span class="sxs-lookup"><span data-stu-id="34f7c-174">Working with Variables Programmatically</span></span>](building-packages-programmatically/working-with-variables-programmatically.md)  
  
  
