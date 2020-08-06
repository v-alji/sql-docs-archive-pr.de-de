---
title: Grundlegendes zu den zum Erstellen des Bereitstellungs Skripts verwendeten Eingabedateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618378"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="9efc8-102">Grundlegendes zu den zum Erstellen des Bereitstellungsskripts verwendeten Eingabedateien</span><span class="sxs-lookup"><span data-stu-id="9efc8-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="9efc8-103">Wenn Sie ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt erstellen, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generiert XML-Dateien für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9efc8-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="9efc8-104">legt diese XML-Dateien im Ausgabeordner des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Projekts ab.</span><span class="sxs-lookup"><span data-stu-id="9efc8-104">puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="9efc8-105">Standardmäßig erfolgt die Ausgabe in den Ordner \Bin.</span><span class="sxs-lookup"><span data-stu-id="9efc8-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="9efc8-106">In der folgenden Tabelle werden die von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] erstellten Dateien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9efc8-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="9efc8-107">XMLA-Datei</span><span class="sxs-lookup"><span data-stu-id="9efc8-107">XMLA file</span></span>|<span data-ttu-id="9efc8-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9efc8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9efc8-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="9efc8-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="9efc8-110">Enthält die deklarativen Definitionen für alle [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte im Projekt.</span><span class="sxs-lookup"><span data-stu-id="9efc8-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="9efc8-111">\<*project name*>deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="9efc8-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="9efc8-112">Enthält den Namen der Instanz und der Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in der die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9efc8-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="9efc8-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="9efc8-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="9efc8-114">Enthält umgebungsspezifische Einstellungen wie Verbindungsinformationen für die Datenquelle und Speicherorte für die Objektspeicherung.</span><span class="sxs-lookup"><span data-stu-id="9efc8-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="9efc8-115">Einstellungen in dieser Datei überschreiben die Einstellungen in der \<*project name*> . asdatabase-Datei.</span><span class="sxs-lookup"><span data-stu-id="9efc8-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="9efc8-116">\<*project name*>. deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="9efc8-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="9efc8-117">Enthält Bereitstellungsoptionen, z. B. ob es sich um eine Transaktionsbereitstellung handelt und ob die bereitgestellten Objekte nach der Bereitstellung verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9efc8-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="9efc8-118">speichert Kennwörter nie in den Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="9efc8-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="9efc8-119">Ändern der Eingabedateien</span><span class="sxs-lookup"><span data-stu-id="9efc8-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="9efc8-120">Durch Ändern der Werte in den Eingabedateien oder der aus den Eingabedateien abgerufenen Werte können das Bereitstellungs Ziel, die Konfigurationseinstellungen und die Bereitstellungs Optionen geändert werden, ohne die gesamte \<*project name*> ASDATABASE-Datei zu bearbeiten (oder eine gesamte XMLA-Skriptdatei, wenn Sie ein Skript aus einer vorhandenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank generieren).</span><span class="sxs-lookup"><span data-stu-id="9efc8-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="9efc8-121">Durch die Möglichkeit, einzelne Dateien zu ändern, können Sie auf einfache Weise verschiedene Bereitstellungsskripts für unterschiedliche Zwecke erstellen.</span><span class="sxs-lookup"><span data-stu-id="9efc8-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="9efc8-122">In den folgenden Themen wird erläutert, wie Sie Werte in den verschiedenen Eingabedateien ändern:</span><span class="sxs-lookup"><span data-stu-id="9efc8-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="9efc8-123">Angeben des Installationszieles</span><span class="sxs-lookup"><span data-stu-id="9efc8-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="9efc8-124">Angeben von Bereitstellungsoptionen für Partitionen und Rollen</span><span class="sxs-lookup"><span data-stu-id="9efc8-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="9efc8-125">Angeben der Konfigurationseinstellungen für die Lösungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="9efc8-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="9efc8-126">Angeben von Verarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="9efc8-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="9efc8-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9efc8-127">See Also</span></span>  
 <span data-ttu-id="9efc8-128">[Ausführen des Bereitstellungs-Assistenten für Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="9efc8-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="9efc8-129">Grundlegendes zum Analysis Services-Bereitstellungsskript</span><span class="sxs-lookup"><span data-stu-id="9efc8-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
