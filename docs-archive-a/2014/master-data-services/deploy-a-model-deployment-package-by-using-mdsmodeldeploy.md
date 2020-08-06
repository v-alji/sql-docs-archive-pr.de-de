---
title: Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619881"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="0ac0d-102">Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="0ac0d-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="0ac0d-103">Sie verwenden in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]das Tool MDSModelDeploy, um ein Paket mit dem folgenden Inhalt bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="0ac0d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="0ac0d-104">Nur Modellobjekte.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="0ac0d-105">Modellobjekte und Daten.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="0ac0d-106">Wenn Sie ein Paket bereitstellen möchten, das nur Modellobjekte enthält, können Sie stattdessen den Modellbereitstellungs-Assistenten in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="0ac0d-107">Weitere Informationen finden Sie unter [Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0ac0d-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ac0d-108">Pakete können nur in der Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bereitgestellt werden, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="0ac0d-109">Dies bedeutet, dass in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] erstellte Pakete nicht in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] oder höher bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ac0d-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0ac0d-110">Prerequisites</span></span>  
 <span data-ttu-id="0ac0d-111">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="0ac0d-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0ac0d-112">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Zielumgebung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="0ac0d-113">Ein Modellbereitstellungspaket muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-113">A model deployment package must exist.</span></span> <span data-ttu-id="0ac0d-114">Weitere Informationen finden Sie unter  [Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="0ac0d-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="0ac0d-115">Sie müssen Administrator in der Umgebung sein, in der Sie das Modell bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="0ac0d-116">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ac0d-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="0ac0d-117">Wenn Sie ein Modell mit Daten aktualisieren, kann die Version, für die Sie **bereit**stellen, nicht **gesperrt** oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="0ac0d-118">So stellen Sie ein Modellbereitstellungspaket bereit</span><span class="sxs-lookup"><span data-stu-id="0ac0d-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="0ac0d-119">Legen Sie fest, ob Sie ein neues Modell erstellen, ein Modell klonen oder ein zuvor geklontes Modell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="0ac0d-120">Weitere Informationen finden Sie unter [Optionen für Modellbereitstellung &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ac0d-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="0ac0d-121">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zu "MDSModelDeploy.exe".</span><span class="sxs-lookup"><span data-stu-id="0ac0d-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="0ac0d-122">Wenn MDS am Standard Speicherort installiert ist, ist das Tool unter *Laufwerk*: \Programme\Microsoft SQL server\120\master Data Services\Configuration\MDSModelDeploy.exe verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="0ac0d-123">Wenn MDS nicht am Standardspeicherort installiert wurde, suchen Sie auf dem lokalen Computer nach der Datei "MDSModelDeploy.exe".</span><span class="sxs-lookup"><span data-stu-id="0ac0d-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="0ac0d-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-124">Optional.</span></span> <span data-ttu-id="0ac0d-125">Dient zum Anzeigen der Optionen und der Hilfe.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="0ac0d-126">Geben Sie `MDSModelDeploy` ein, und drücken Sie EINGABETASTE, um alle verfügbaren Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="0ac0d-127">Geben Sie Folgendes ein, um Hilfe für eine Option anzuzeigen, wobei *OptionName* der Name der Option ist: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="0ac0d-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-128">Optional.</span></span> <span data-ttu-id="0ac0d-129">Wenn Sie über mehrere Webanwendungen verfügen, bestimmen Sie den Namen des Diensts, für den Sie die Bereitstellung durchführen, indem Sie diesen Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="0ac0d-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="0ac0d-130">Eine Liste von Werten wird zurückgegeben, z. B. `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="0ac0d-131">Der erste Wert in dieser Liste (in diesem Fall `MDS1`) wird benötigt, um das Modell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="0ac0d-132">Geben Sie an der Eingabeaufforderung Folgendes ein, und drücken Sie die EINGABETASTE. Der Befehl unterscheidet sich je nachdem, ob Sie ein Modell erstellen, ein Modell klonen oder ein Modell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="0ac0d-133">So erstellen Sie ein neues Modell:</span><span class="sxs-lookup"><span data-stu-id="0ac0d-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="0ac0d-134">So erstellen Sie einen Klon eines Modells</span><span class="sxs-lookup"><span data-stu-id="0ac0d-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="0ac0d-135">So aktualisieren Sie ein vorhandenes Modell samt Daten</span><span class="sxs-lookup"><span data-stu-id="0ac0d-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0ac0d-136">Wenn Sie das MDSModelDeploy-Tool verwenden, um ein vorhandenes Modell inklusive Daten zu aktualisieren, und das Paket keine Entität, kein Attribut oder kein Element enthält, die bzw. das im Zielmodell enthalten ist, wird diese Entität bzw. dieses Attribut oder Element von MDSModelDeploy nicht aus dem Modell gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="0ac0d-137">Dabei gilt: *PackageName* ist der Name der Paketdatei (PKG-Datei), *ModelName* ist der Name des neuen Modells, *VersionName* ist der Name der Version, und *ServiceName* ist der Name des Diensts, der im vorherigen Schritt zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="0ac0d-138">Stellen Sie sicher, dass die Modell- und Versionsnamen nach Groß-/Kleinschreibung genau mit den Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="0ac0d-139">Nach der erfolgreichen Bereitstellung des Pakets wird eine Meldung angezeigt, die angibt, dass der MDSModelDeploy-Vorgang erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="0ac0d-140">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="0ac0d-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="0ac0d-141">Wenn eine Abonnement Sicht im Paket denselben Namen wie eine Abonnement Sicht in einem vorhandenen Modell aufweist, wird die Sicht als *modelname. abonnementviewname*erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="0ac0d-142">Wenn dieser Name bereits verwendet wird, wird die Abonnementsicht nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="0ac0d-143">Der Bereitstellungsprozess umfasst vier Schritte:</span><span class="sxs-lookup"><span data-stu-id="0ac0d-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="0ac0d-144">Die Modellobjekte werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="0ac0d-145">Geschäftsregeln werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="0ac0d-146">Abonnementsichten werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="0ac0d-147">Masterdaten werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="0ac0d-148">Beim Erstellen eines neuen oder geklonten Modells wird das Modell gelöscht, falls der Prozess während eines beliebigen Schritts fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="0ac0d-149">Falls bei der Aktualisierung eines Modells der Prozess während der ersten drei Schritte fehlschlägt, wird sie nicht fortgesetzt. Für bereits vorgenommene Änderungen wird jedoch kein Rollback durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="0ac0d-150">Wenn der Prozess in Schritt 4 fehlschlägt, werden Elemente, die aktualisiert werden können, aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0ac0d-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0ac0d-151">Next Steps</span></span>  
 <span data-ttu-id="0ac0d-152">Benutzerdefinierte Metadaten, Dateiattribute sowie Benutzer- und Gruppenberechtigungen sind nicht in den Modellbereitstellungspaketen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="0ac0d-153">Nachdem Sie ein Modell bereitgestellt haben, müssen diese manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ac0d-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="0ac0d-154">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="0ac0d-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="0ac0d-155">Metadaten &#40;Master Data Services hinzufügen&#41;</span><span class="sxs-lookup"><span data-stu-id="0ac0d-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="0ac0d-156">Zuweisen von Berechtigungen für Modellobjekte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0ac0d-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ac0d-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ac0d-157">See Also</span></span>  
 [<span data-ttu-id="0ac0d-158">Bereitstellen von Modellen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0ac0d-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
