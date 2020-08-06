---
title: Angeben von Bereitstellungs Optionen für Partitionen und Rollen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621695"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="f875a-102">Angeben von Bereitstellungsoptionen für Partitionen und Rollen</span><span class="sxs-lookup"><span data-stu-id="f875a-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="f875a-103">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Bereitstellungs-Assistent liest die Bereitstellungs Optionen für Partitionen und Rollen aus der \<*project name*> Datei ". deploymentoptions".</span><span class="sxs-lookup"><span data-stu-id="f875a-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f875a-104">erstellt diese Datei, wenn Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="f875a-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f875a-105">verwendet die Bereitstellungs Optionen für Partitionen und Rollen des aktuellen Projekts, wenn die \<*project name*> Datei. deploymentoptions erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f875a-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="f875a-106">Weitere Informationen zu den Konfigurationseinstellungen finden Sie unter [Grundlegendes zu den zum Erstellen des Bereitstellungsskripts verwendeten Eingabedateien](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="f875a-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="f875a-107">Überprüfen der Bereitstellungsoptionen für Partitionen und Rollen</span><span class="sxs-lookup"><span data-stu-id="f875a-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="f875a-108">Die Bereitstellungs Optionen in der \<*project name*> Datei. deploymentoptions umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f875a-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="f875a-109">**Bereitstellungsoptionen für Partitionen**</span><span class="sxs-lookup"><span data-stu-id="f875a-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="f875a-110">Die \<*project name*> Datei. deploymentoptions gibt an, ob vorhandene Partitionen in der Zieldatenbank beibehalten oder überschrieben (Standard) werden.</span><span class="sxs-lookup"><span data-stu-id="f875a-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="f875a-111">Wenn vorhandene Partitionen beibehalten werden, werden nur neue Partitionen bereitgestellt, und der Partitions- bzw. Aggregationsentwurf in allen vorhandenen Measuregruppen wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f875a-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f875a-112">Wird die Measuregruppe, in der die Partition vorhanden ist, gelöscht, wird die Partition automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f875a-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="f875a-113">**Bereitstellungsoptionen für Rollen**</span><span class="sxs-lookup"><span data-stu-id="f875a-113">**Role deployment options**</span></span>  
 <span data-ttu-id="f875a-114">Die \<*project name*> Datei. deploymentoptions gibt eine der folgenden Optionen für die Rollen Bereitstellung an:</span><span class="sxs-lookup"><span data-stu-id="f875a-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="f875a-115">Vorhandene Rollen und Rollenelemente in der Zieldatenbank werden beibehalten, und nur neue Rollen und Rollenelemente werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f875a-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="f875a-116">Alle in der Zieldatenbank vorhandenen Rollen und Elemente werden durch die bereitgestellten Rollen und Elemente ersetzt.</span><span class="sxs-lookup"><span data-stu-id="f875a-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="f875a-117">Vorhandene Rollen und Rollenelemente in der Zieldatenbank werden beibehalten, neue Rollen werden nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f875a-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="f875a-118">**Hinweis:** Wenn vorhandene Rollen und Elemente beibehalten werden, werden die Berechtigungen, die diesen Rollen zugeordnet sind, zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f875a-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="f875a-119">Sicherheitsberechtigungen sind in den Objekten enthalten, die sie sichern, und nicht in den Sicherheitsrollen, denen sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f875a-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="f875a-120">Weitere Informationen zum Arbeiten mit diesem Verhalten mithilfe des Bereitstellungs-Assistenten für Analysis Services finden Sie unter "beibehalten von Rollen und Mitgliedern" in der Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="f875a-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="f875a-121">Ändern der Bereitstellungsoptionen für Partitionen und Rollen</span><span class="sxs-lookup"><span data-stu-id="f875a-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="f875a-122">Möglicherweise müssen Sie das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt mit anderen Partitions-und Rollen Optionen bereitstellen, als in der \<*project name*> Datei. deploymentoptions gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f875a-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="f875a-123">Beispielsweise möchten Sie möglicherweise vorhandene Partitionen, Rollen und Rollen Mitglieder beibehalten, anstatt alle vorhandenen Partitionen, Rollen und Member wie in der \<*project name*> Datei. deploymentoptions angegeben zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f875a-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="f875a-124">Wenn Sie die Bereitstellung von Partitionen und Rollen in einem-Projekt ändern möchten [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , können Sie die Partitions-und Rollen Einstellungen innerhalb des Projekts nicht ändern, da *\<project name>* Diese Optionen im Dialogfeld **Eigenschaften Seiten** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f875a-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="f875a-125">Wenn Sie die Bereitstellungs Optionen für Rollen und Partitionen ändern möchten, müssen Sie diese Informationen in der \<*project name*> Datei. deploymentoptions selbst ändern.</span><span class="sxs-lookup"><span data-stu-id="f875a-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="f875a-126">Im folgenden Verfahren wird beschrieben, wie die Bereitstellungs Optionen für Partitionen und Rollen in der \<*project name*> Datei ". deploymentoptions" geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f875a-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="f875a-127">So ändern Sie die Bereitstellung von Partitionen und Rollen, nachdem die Eingabedateien generiert wurden</span><span class="sxs-lookup"><span data-stu-id="f875a-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="f875a-128">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interaktiv aus, und geben Sie auf der Seite **Bereitstellungsoptionen für Partitionen und Rollen** neue Bereitstellungsoptionen für die Partitionen und Rollen an.</span><span class="sxs-lookup"><span data-stu-id="f875a-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="f875a-129">Oder</span><span class="sxs-lookup"><span data-stu-id="f875a-129">-or-</span></span>  
  
-   <span data-ttu-id="f875a-130">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] an der Eingabeaufforderung aus, und legen Sie fest, dass der Assistent im Antwortdateimodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f875a-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="f875a-131">(Weitere Informationen zum Antwortdatei Modus finden Sie unter [Ausführen des Bereitstellungs-Assistenten für Analysis Services](running-the-analysis-services-deployment-wizard.md).)</span><span class="sxs-lookup"><span data-stu-id="f875a-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="f875a-132">Oder</span><span class="sxs-lookup"><span data-stu-id="f875a-132">-or-</span></span>  
  
-   <span data-ttu-id="f875a-133">Öffnen Sie die \<*project name*> deploymentoptions in einem beliebigen Text-Editor, und ändern Sie die Optionen manuell.</span><span class="sxs-lookup"><span data-stu-id="f875a-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f875a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f875a-134">See Also</span></span>  
 <span data-ttu-id="f875a-135">[Angeben des Installations Ziels](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="f875a-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="f875a-136">[Angeben von Konfigurationseinstellungen für die Lösungs Bereitstellung](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f875a-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="f875a-137">Angeben von Verarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="f875a-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
