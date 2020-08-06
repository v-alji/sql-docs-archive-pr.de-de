---
title: Angeben von Verarbeitungsoptionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696242"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="f4fe2-102">Angeben von Verarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="f4fe2-102">Specifying Processing Options</span></span>
  <span data-ttu-id="f4fe2-103">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Bereitstellungs-Assistent liest die Verarbeitungsoptionen aus der \<*project name*> Datei ". deploymentoptions".</span><span class="sxs-lookup"><span data-stu-id="f4fe2-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f4fe2-104">erstellt diese Datei, wenn Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f4fe2-105">verwendet die Verarbeitungsoptionen, die auf der Seite **Bereitstellung** des Dialog Felds *\<project name>* **Eigenschaften Seiten** angegeben werden, um die \<*project name*> Datei. deploymentoptions zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="f4fe2-106">Überprüfen der Verarbeitungsoptionen für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f4fe2-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="f4fe2-107">Die in der \<*project name*> Datei. deploymentoptions gespeicherten Konfigurationseinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f4fe2-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="f4fe2-108">**Verarbeitungsmethode** Diese Einstellung steuert, ob die bereitgestellten Objekte nach der Bereitstellung verarbeitet werden und welche Art von Verarbeitung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="f4fe2-109">Es stehen drei Verarbeitungsoptionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f4fe2-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="f4fe2-110">Standardverarbeitung (Standardeinstellung)</span><span class="sxs-lookup"><span data-stu-id="f4fe2-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="f4fe2-111">Vollständige Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="f4fe2-111">Full processing</span></span>  
  
    -   <span data-ttu-id="f4fe2-112">Keine</span><span class="sxs-lookup"><span data-stu-id="f4fe2-112">None</span></span>  
  
-   <span data-ttu-id="f4fe2-113">**Optionen für die Rückschreibetabelle** Wenn im [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt Rückschreiben aktiviert ist, wird mit dieser Einstellung die Ausführung dieses Vorgangs definiert.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="f4fe2-114">Es sind drei Rückschreibetabellenoptionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f4fe2-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="f4fe2-115">Wenn eine Rückschreibetabelle vorhanden ist, wird diese standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="f4fe2-116">Ist keine Rückschreibetabelle vorhanden, wird eine neue Rückschreibetabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="f4fe2-117">Wenn bereits eine Rückschreibetabelle vorhanden ist, kann die Bereitstellung nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="f4fe2-118">Ist keine Rückschreibetabelle vorhanden, wird eine neue Rückschreibetabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="f4fe2-119">Unabhängig davon, ob bereits eine Rückschreibetabelle vorhanden ist, wird eine neue Rückschreibetabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="f4fe2-120">In diesem Fall löscht der Bereitstellungs-Assistent für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die vorhandene Tabelle und ersetzt sie durch eine neue Rückschreibetabelle.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="f4fe2-121">**Transaktionsbereitstellung** Diese Einstellung steuert, ob die Bereitstellung von Metadatenänderungen und Verarbeitungsbefehlen in einer einzelnen Transaktion oder in getrennten Transaktionen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="f4fe2-122">Wenn diese Option auf `True` (Standard) festgelegt ist, stellt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] alle Metadatenänderungen und alle Verarbeitungsbefehle in einer einzelnen Transaktion bereit.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="f4fe2-123">Ist diese Option `False`, stellt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die Metadatenänderungen in einer einzelnen Transaktion und jeden Verarbeitungsbefehl jeweils in einer eigenen Transaktion bereit.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="f4fe2-124">Ändern der Verarbeitungsoptionen für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f4fe2-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="f4fe2-125">Allerdings müssen Sie das Projekt möglicherweise [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mit anderen Verarbeitungsoptionen bereitstellen, als in der \<*project name*> Datei. deploymentoptions gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="f4fe2-126">Vielleicht sollen alle Objekte vollständig oder mithilfe der Standardverarbeitungsoption oder überhaupt nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="f4fe2-127">Wenn die Cubes oder Dimensionen für den Schreibzugriff aktiviert sind, können Sie angeben, ob eine neue oder eine vorhandene Rückschreibetabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="f4fe2-128">Wenn Sie die bei der Bereitstellung zu verwendenden Verarbeitungsoptionen ändern möchten, können Sie entweder das Projekt bearbeiten und neu erstellen, oder Sie ändern mithilfe einer der im Folgenden beschriebenen Prozedur die Verarbeitungsoptionen in der Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="f4fe2-129">So ändern Sie Verarbeitungsoptionen, nachdem die Eingabedateien generiert wurden</span><span class="sxs-lookup"><span data-stu-id="f4fe2-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="f4fe2-130">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interaktiv aus.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="f4fe2-131">Geben Sie auf der Seite **Verarbeitungsoptionen** die Verarbeitungsoptionen für das bereitzustellende Projekt an.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="f4fe2-132">Oder</span><span class="sxs-lookup"><span data-stu-id="f4fe2-132">-or-</span></span>  
  
-   <span data-ttu-id="f4fe2-133">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] an der Eingabeaufforderung aus, und legen Sie fest, dass der Assistent im Antwortdateimodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="f4fe2-134">Weitere Informationen zum Antwortdateimodus finden Sie unter [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f4fe2-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="f4fe2-135">Oder</span><span class="sxs-lookup"><span data-stu-id="f4fe2-135">-or-</span></span>  
  
-   <span data-ttu-id="f4fe2-136">Ändern \<*project name*> Sie die Datei ". deploymentoptions" mit einem beliebigen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="f4fe2-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fe2-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4fe2-137">See Also</span></span>  
 <span data-ttu-id="f4fe2-138">[Angeben des Installations Ziels](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="f4fe2-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="f4fe2-139">[Angeben von Bereitstellungs Optionen für Partitionen und Rollen](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="f4fe2-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="f4fe2-140">Angeben der Konfigurationseinstellungen für die Lösungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="f4fe2-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
