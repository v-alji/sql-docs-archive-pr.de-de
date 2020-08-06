---
title: Bereitstellen von Modellen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630690"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="56e69-102">Bereitstellen von Modellen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="56e69-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="56e69-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ist ein Paket eine XML-Datei, die eine zur Bereitstellung geeignete Modellstruktur enthält und optional Daten vom Modell.</span><span class="sxs-lookup"><span data-stu-id="56e69-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="56e69-104">Verschieben Sie Kopien von Modellen mithilfe von Modellpaketen von einer MDS-Umgebung in eine andere oder erstellen Sie damit neue Modelle in der vorhandenen MDS-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="56e69-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56e69-105">Pakete können nur in der Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bereitgestellt werden, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="56e69-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="56e69-106">Dies bedeutet, dass in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] erstellte Pakete nicht in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] oder höher bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="56e69-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="56e69-107">Tools zum Bereitstellen von Modellen</span><span class="sxs-lookup"><span data-stu-id="56e69-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="56e69-108">Sie können je nach Anforderungen mithilfe eines der drei Tools mit Modellpaketen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="56e69-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="56e69-109">**MDSModelDeploy-Tool**: Zum Erstellen und Bereitstellen von Modellobjekten und -daten verwenden Sie das Tool MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="56e69-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="56e69-110">Wenn Sie bei der Installation von MDS den Standardpfad ausgewählt haben, befindet sich dieses Tool unter *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\configuration.</span><span class="sxs-lookup"><span data-stu-id="56e69-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="56e69-111">**Modellbereitstellungs-Assistent**: Zum Erstellen und Bereitstellen von Paketen, die nur die Modellstruktur enthalten, verwenden Sie den Assistenten in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="56e69-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="56e69-112">Sie können diesen Assistenten nicht zur Bereitstellung von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="56e69-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="56e69-113">**Modellpaket-Editor**: Um ein Modellpaket zu bearbeiten, verwenden Sie „ModelPackageEditor.exe“, womit der Assistent für den Modellpaket-Editor gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="56e69-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="56e69-114">Sie verwenden diesen Assistenten, um ein Paket zu bearbeiten, das vom MDSModelDeploy-Tool oder dem Modellbereitstellungs-Assistenten erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="56e69-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="56e69-115">Wenn Sie bei der Installation von MDS den Standardpfad ausgewählt haben, befindet sich dieses Tool unter *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\configuration.</span><span class="sxs-lookup"><span data-stu-id="56e69-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56e69-116">Sie können das MDSDeployModel verwenden, um ein neues Modell oder einen Modellklon zu erstellen oder um ein vorhandenes Modell einschließlich Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="56e69-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="56e69-117">Wenn Sie das MDSModelDeploy-Tool verwenden, um ein vorhandenes Modell inklusive Daten zu aktualisieren, und das Paket keine Entität, kein Attribut oder kein Element enthält, die bzw. das im Zielmodell enthalten ist, wird diese Entität bzw. dieses Attribut oder Element von MDSModelDeploy nicht aus dem Modell gelöscht.</span><span class="sxs-lookup"><span data-stu-id="56e69-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="56e69-118">Inhalte von Paketen</span><span class="sxs-lookup"><span data-stu-id="56e69-118">What Packages Contain</span></span>  
 <span data-ttu-id="56e69-119">Ein Modellpaket ist eine XML-Datei, die mit der Erweiterung .pkg gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="56e69-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="56e69-120">Wenn Sie ein Bereitstellungspaket erstellen, können Sie entscheiden, ob Daten eingeschlossen werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="56e69-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="56e69-121">Wenn Sie entscheiden, Daten einzuschließen, müssen Sie eine Version der einzuschließenden Daten auswählen.</span><span class="sxs-lookup"><span data-stu-id="56e69-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="56e69-122">Alle Modellobjekte sind in einem Paket enthalten.</span><span class="sxs-lookup"><span data-stu-id="56e69-122">All model objects are included in a package.</span></span> <span data-ttu-id="56e69-123">Diese Objekte sind:</span><span class="sxs-lookup"><span data-stu-id="56e69-123">These objects are:</span></span>  
  
-   <span data-ttu-id="56e69-124">Entitäten</span><span class="sxs-lookup"><span data-stu-id="56e69-124">Entities</span></span>  
  
-   <span data-ttu-id="56e69-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="56e69-125">Attributes</span></span>  
  
-   <span data-ttu-id="56e69-126">Attributgruppen</span><span class="sxs-lookup"><span data-stu-id="56e69-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="56e69-127">Hierarchien</span><span class="sxs-lookup"><span data-stu-id="56e69-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="56e69-128">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="56e69-128">Collections</span></span>  
  
-   <span data-ttu-id="56e69-129">Geschäftsregeln</span><span class="sxs-lookup"><span data-stu-id="56e69-129">Business rules</span></span>  
  
-   <span data-ttu-id="56e69-130">Versionsflags</span><span class="sxs-lookup"><span data-stu-id="56e69-130">Version flags</span></span>  
  
-   <span data-ttu-id="56e69-131">Abonnementsichten</span><span class="sxs-lookup"><span data-stu-id="56e69-131">Subscription views</span></span>  
  
 <span data-ttu-id="56e69-132">Benutzerdefinierte Metadaten, Dateiattribute sowie Benutzer- und Gruppenberechtigungen sind nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="56e69-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="56e69-133">Nachdem Sie ein Modell bereitgestellt haben, müssen diese manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="56e69-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="56e69-134">Beispielpakete</span><span class="sxs-lookup"><span data-stu-id="56e69-134">Sample Packages</span></span>  
 <span data-ttu-id="56e69-135">In der Installation von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]sind Beispielpaketdateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="56e69-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="56e69-136">Diese Paketdateien sind Installationsverzeichnis von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]im Unterverzeichnis Master Data Services\Samples\Packages gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56e69-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="56e69-137">Wenn Sie diese Beispielspakete mithilfe des Tools MDSModelDeploy bereitstellen, werden Beispielmodelle erstellt und mit Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="56e69-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="56e69-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="56e69-138">Related Tasks</span></span>  
  
|<span data-ttu-id="56e69-139">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="56e69-139">Task Description</span></span>|<span data-ttu-id="56e69-140">Thema</span><span class="sxs-lookup"><span data-stu-id="56e69-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="56e69-141">Erstellen Sie mit dem Tool MDSModelDeploy ein neues Bereitstellungspaket mit Modellobjekten und/oder Daten.</span><span class="sxs-lookup"><span data-stu-id="56e69-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="56e69-142">Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="56e69-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="56e69-143">Erstellen Sie nur mit dem Assistenten ein neues Bereitstellungspaket mit Modellobjekten.</span><span class="sxs-lookup"><span data-stu-id="56e69-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="56e69-144">Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="56e69-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="56e69-145">Stellen Sie mit dem Tool MDSModelDeploy ein Paket mit Modellobjekten und Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="56e69-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="56e69-146">Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="56e69-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="56e69-147">Stellen Sie nur mit dem Assistenten ein Paket Modellobjekte bereit.</span><span class="sxs-lookup"><span data-stu-id="56e69-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="56e69-148">Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="56e69-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="56e69-149">Bearbeiten Sie ein Modellbereitstellungspaket, um ausgewählte Teile eines Modells und nicht das ganze Modell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="56e69-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="56e69-150">Bearbeiten eines Modellbereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="56e69-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="56e69-151">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="56e69-151">Related Content</span></span>  
  
-   [<span data-ttu-id="56e69-152">Optionen für Modellbereitstellung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="56e69-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
