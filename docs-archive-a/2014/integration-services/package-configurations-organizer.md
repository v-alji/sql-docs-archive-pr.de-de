---
title: Paket Konfigurations Planer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721578"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="1a45c-102">Paketkonfigurationsplaner</span><span class="sxs-lookup"><span data-stu-id="1a45c-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="1a45c-103">Mithilfe des Dialogfelds **Paketkonfigurationsplaner** können Sie Paketkonfigurationen aktivieren, eine Liste der Konfigurationen für das aktuelle Paket anzeigen und die bevorzugte Reihenfolge angeben, in der die Konfigurationen geladen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="1a45c-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a45c-104">Konfigurationen sind für das Paketbereitstellungsmodell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a45c-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="1a45c-105">Parameter werden für das Projektbereitstellungsmodell anstelle von Konfigurationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a45c-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="1a45c-106">Mithilfe des Projektbereitstellungsmodells können Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekte auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a45c-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="1a45c-107">Weitere Informationen zu Bereitstellungsmodellen finden Sie unter [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1a45c-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="1a45c-108">Wenn mehrere Konfigurationen dieselbe Eigenschaft aktualisieren, ersetzen Werte aus Konfigurationen weiter unten in der Konfigurationsliste die Werte aus Konfigurationen weiter oben in der Liste.</span><span class="sxs-lookup"><span data-stu-id="1a45c-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="1a45c-109">Der letzte in die Eigenschaft geladene Wert ist der Wert, der verwendet wird, wenn das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a45c-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="1a45c-110">Auch muss die indirekte Konfiguration, die auf den Speicherort der direkten Konfiguration verweist, weiter oben in der Liste stehen, wenn das Paket eine Kombination aus direkter Konfiguration, z. B. XML-Konfigurationsdatei, und indirekter Konfiguration, z. B. Umgebungsvariable, verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a45c-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a45c-111">Wenn Paketkonfigurationen in der bevorzugten Reihenfolge geladen werden, werden die Konfigurationen in der Reihenfolge geladen, in der sie im Dialogfeld **Paketkonfigurationsplaner** angezeigt werden, wobei mit der Konfiguration am Anfang der Liste begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="1a45c-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="1a45c-112">Zur Laufzeit werden Paketkonfigurationen möglicherweise aber nicht in der bevorzugten Reihenfolge geladen.</span><span class="sxs-lookup"><span data-stu-id="1a45c-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="1a45c-113">Beispielsweise werden übergeordnete Paketkonfigurationen nach Konfigurationen anderer Typen geladen.</span><span class="sxs-lookup"><span data-stu-id="1a45c-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="1a45c-114">Paketkonfigurationen aktualisieren die Werte der Eigenschaften von Paketobjekten zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1a45c-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="1a45c-115">Beim Laden eines Pakets werden die beim Entwickeln des Pakets festgelegten Werte durch die Werte der Konfigurationen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1a45c-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="1a45c-116">unterstützt unterschiedliche Konfigurationstypen.</span><span class="sxs-lookup"><span data-stu-id="1a45c-116">supports different configuration types.</span></span> <span data-ttu-id="1a45c-117">Beispielsweise können Sie eine XML-Datei mit mehreren möglichen Konfigurationen oder eine Umgebungsvariable mit einer einzigen enthaltenen Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a45c-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="1a45c-118">Weitere Informationen finden Sie unter [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="1a45c-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a45c-119">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1a45c-119">Options</span></span>  
 <span data-ttu-id="1a45c-120">**Paketkonfigurationen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="1a45c-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="1a45c-121">Wählen Sie diese Option aus, um mit dem Paket Konfigurationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a45c-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="1a45c-122">**Konfigurationsname**</span><span class="sxs-lookup"><span data-stu-id="1a45c-122">**Configuration Name**</span></span>  
 <span data-ttu-id="1a45c-123">Zeigt den Namen der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="1a45c-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="1a45c-124">**Konfigurationstyp**</span><span class="sxs-lookup"><span data-stu-id="1a45c-124">**Configuration Type**</span></span>  
 <span data-ttu-id="1a45c-125">Zeigt den Typ des Speicherorts von Konfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="1a45c-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="1a45c-126">**Konfigurationszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="1a45c-126">**Configuration String**</span></span>  
 <span data-ttu-id="1a45c-127">Zeigt den Speicherort der Konfigurationswerte an.</span><span class="sxs-lookup"><span data-stu-id="1a45c-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="1a45c-128">Der Speicherort kann der Pfad einer Datei, der Name einer Umgebungsvariablen, der Name einer Variablen für das übergeordnete Paket, ein Registrierungsschlüssel oder der Name einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="1a45c-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="1a45c-129">**Zielobjekt**</span><span class="sxs-lookup"><span data-stu-id="1a45c-129">**Target Object**</span></span>  
 <span data-ttu-id="1a45c-130">Zeigt den Namen des Objekts an, das von der Konfiguration aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1a45c-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="1a45c-131">Wenn es sich bei der Konfiguration um eine XML-Konfigurationsdatei oder eine SQL Server-Tabelle handelt, ist die Spalte leer, da die Konfiguration mehrere Objekte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1a45c-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="1a45c-132">**Zieleigenschaft**</span><span class="sxs-lookup"><span data-stu-id="1a45c-132">**Target Property**</span></span>  
 <span data-ttu-id="1a45c-133">Zeigt den Namen der durch die Konfiguration geänderten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1a45c-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="1a45c-134">Diese Spalte ist leer, wenn der Konfigurationstyp mehrere Konfigurationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a45c-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="1a45c-135">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="1a45c-135">**Add**</span></span>  
 <span data-ttu-id="1a45c-136">Fügt mithilfe des Paketkonfigurationsassistenten eine Konfiguration hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a45c-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="1a45c-137">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="1a45c-137">**Edit**</span></span>  
 <span data-ttu-id="1a45c-138">Bearbeitet eine vorhandene Konfiguration, indem der Paketkonfigurationsassistent erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a45c-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="1a45c-139">**Remove**</span><span class="sxs-lookup"><span data-stu-id="1a45c-139">**Remove**</span></span>  
 <span data-ttu-id="1a45c-140">Wählen Sie eine Konfiguration aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1a45c-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="1a45c-141">**Pfeile**</span><span class="sxs-lookup"><span data-stu-id="1a45c-141">**Arrows**</span></span>  
 <span data-ttu-id="1a45c-142">Wählen Sie eine Konfiguration aus, und verschieben Sie sie mithilfe der Pfeile in der Liste nach oben oder nach unten.</span><span class="sxs-lookup"><span data-stu-id="1a45c-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="1a45c-143">Konfigurationen werden in der Reihenfolge geladen, in der sie in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a45c-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a45c-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a45c-144">See Also</span></span>  
 [<span data-ttu-id="1a45c-145">Erstellen von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="1a45c-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
