---
title: Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622751"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="d8283-102">Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="d8283-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="d8283-103">Sie verwenden in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]das Tool MDSModelDeploy, um ein Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8283-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="d8283-104">Abhängig von den angegebenen Befehlen kann das Paket folgenden Inhalt haben:</span><span class="sxs-lookup"><span data-stu-id="d8283-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="d8283-105">Nur Modellobjekte.</span><span class="sxs-lookup"><span data-stu-id="d8283-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="d8283-106">Modellobjekte und Daten.</span><span class="sxs-lookup"><span data-stu-id="d8283-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="d8283-107">Wenn Sie ein Paket bereitstellen möchten, das nur Modellobjekte enthält, können Sie stattdessen den Modellbereitstellungs-Assistenten in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8283-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="d8283-108">Weitere Informationen finden Sie unter [Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d8283-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="d8283-109">Diese Version des mdsmodelbereitstellungs-Tools kann nicht mehr als Gigabyte (GB) Arbeitsspeicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8283-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="d8283-110">Wenn Sie große Modelle mithilfe der Option **Modell Objekte und Daten** erstellen oder bereitstellen, tritt möglicherweise der Fehler "nicht genügend Arbeitsspeicher" oder "der Stream war zu lang" auf.</span><span class="sxs-lookup"><span data-stu-id="d8283-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="d8283-111">Um dieses Problem zu beheben, verwenden Sie das MDS-Staging zum Bereitstellen der Daten. oder führen Sie ein Upgrade auf MDS 2016 oder eine höhere Version durch, einschließlich der aktualisierten Version des mdsmodelbereitstellungs-Tools.</span><span class="sxs-lookup"><span data-stu-id="d8283-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="d8283-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8283-112">Prerequisites</span></span>  
 <span data-ttu-id="d8283-113">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d8283-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="d8283-114">Die grundlegenden Berechtigungen zum Ausführen des MDSModelDeploy-Tools lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d8283-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="d8283-115">Die gleiche Windows-Berechtigung wie der MDS-Konfigurations-Manager (Windows-Administrator)</span><span class="sxs-lookup"><span data-stu-id="d8283-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="d8283-116">DBA-Berechtigung für die MDS-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d8283-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="d8283-117">Die grundlegenden Berechtigungen zum Erstellen des Pakets mit dem MDSModelDeploy-Tool lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d8283-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="d8283-118">MDS-Modelladministratorberechtigung für das Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="d8283-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="d8283-119">Funktionsberechtigung für das MDS-Integrationsmanagement</span><span class="sxs-lookup"><span data-stu-id="d8283-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="d8283-120">Die grundlegenden Berechtigungen zum Bereitstellen eines Modells mit dem MDSModelDeploy-Tool lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d8283-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="d8283-121">Funktionsberechtigung für den MDS-Explorer</span><span class="sxs-lookup"><span data-stu-id="d8283-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="d8283-122">Funktions Berechtigung für die MDS-Integrations Verwaltung</span><span class="sxs-lookup"><span data-stu-id="d8283-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="d8283-123">Funktionsberechtigung für die MDS-Systemverwaltung</span><span class="sxs-lookup"><span data-stu-id="d8283-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="d8283-124">Die grundlegenden Berechtigungen zum Auflisten von Modellen mit dem MDSModelDeploy-Tool lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d8283-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="d8283-125">Funktionsberechtigung für den MDS-Explorer</span><span class="sxs-lookup"><span data-stu-id="d8283-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="d8283-126">MDS-Modelladministratorberechtigung für das Datenmodell zum Anzeigen des Modells in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d8283-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="d8283-127">Es muss ein Modell vorhanden sein, aus dem Sie ein Paket erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d8283-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="d8283-128">Weitere Informationen finden Sie unter [Erstellen eines Modells &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8283-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="d8283-129">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8283-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="d8283-130">So erstellen Sie ein Modellbereitstellungspaket mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="d8283-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="d8283-131">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="d8283-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="d8283-132">Navigieren Sie zum Speicherort von "MDSModelDeploy.exe".</span><span class="sxs-lookup"><span data-stu-id="d8283-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="d8283-133">Wenn MDS am Standard Speicherort installiert wurde, befindet sich die Datei unter *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\configuration.</span><span class="sxs-lookup"><span data-stu-id="d8283-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="d8283-134">Wenn MDS nicht am Standardspeicherort installiert wurde, suchen Sie auf dem lokalen Computer nach der Datei "MDSModelDeploy.exe".</span><span class="sxs-lookup"><span data-stu-id="d8283-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="d8283-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="d8283-135">Optional.</span></span> <span data-ttu-id="d8283-136">Dient zum Anzeigen der Optionen und der Hilfe.</span><span class="sxs-lookup"><span data-stu-id="d8283-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="d8283-137">Geben Sie `MDSModelDeploy` ein, und drücken Sie EINGABETASTE, um alle verfügbaren Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8283-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="d8283-138">Geben Sie Folgendes ein, um Hilfe für eine Option anzuzeigen, wobei *OptionName* der Name der Option ist: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="d8283-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="d8283-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="d8283-139">Optional.</span></span> <span data-ttu-id="d8283-140">Wenn Sie über mehrere Webanwendungen verfügen, bestimmen Sie den Namen des Diensts, für den Sie die Bereitstellung durchführen, indem Sie diesen Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="d8283-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="d8283-141">Eine Liste von Werten wird zurückgegeben, z. B. `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="d8283-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="d8283-142">Der erste Wert in dieser Liste (in diesem Fall `MDS1`) wird benötigt, um das Modell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8283-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="d8283-143">Geben Sie Folgendes ein, um ein Paket zu erstellen, das Modellobjekte und Daten enthält. Dabei gilt: *ModelName*, *VersionName*, *ServiceName*und *PackageName* sind die Namen des Modells, der Version, des Diensts bzw. der PKG-Ausgabedatei:</span><span class="sxs-lookup"><span data-stu-id="d8283-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="d8283-144">Wenn Sie keine Daten einschließen möchten, verwenden Sie nicht die Schalter `-version` und `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="d8283-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="d8283-145">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="d8283-145">Press Enter.</span></span> <span data-ttu-id="d8283-146">Nach der erfolgreichen Erstellung des Pakets wird eine Meldung angezeigt, die besagt, dass der MDSModelDeploy-Vorgang erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d8283-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d8283-147">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d8283-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="d8283-148">Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="d8283-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8283-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8283-149">See Also</span></span>  
 <span data-ttu-id="d8283-150">[Modell Bereitstellungs Optionen &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d8283-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="d8283-151">Bereitstellen von Modellen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d8283-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
