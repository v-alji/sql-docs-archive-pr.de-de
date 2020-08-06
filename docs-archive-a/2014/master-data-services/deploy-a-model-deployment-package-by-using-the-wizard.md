---
title: Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721533"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="b585b-102">Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="b585b-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="b585b-103">Verwenden Sie den Modellbereitstellungs-Assistenten von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , um Pakete bereitzustellen, die nur Modellobjekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="b585b-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="b585b-104">Wenn Sie ein Paket mit Daten bereitstellen müssen, finden Sie weitere Informationen unter [Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="b585b-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b585b-105">Pakete können nur in der Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bereitgestellt werden, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b585b-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="b585b-106">Dies bedeutet, dass in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] erstellte Pakete nicht in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="b585b-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b585b-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b585b-107">Prerequisites</span></span>  
 <span data-ttu-id="b585b-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="b585b-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b585b-109">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Zielumgebung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b585b-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="b585b-110">Ein Modellbereitstellungspaket muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b585b-110">A model deployment package must exist.</span></span> <span data-ttu-id="b585b-111">Weitere Informationen finden Sie unter [Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b585b-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="b585b-112">Sie müssen Administrator in der Umgebung sein, in der Sie das Modell bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b585b-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="b585b-113">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b585b-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="b585b-114">So stellen Sie ein Modellbereitstellungspaket bereit, das ausschließlich Modellobjekte enthält</span><span class="sxs-lookup"><span data-stu-id="b585b-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="b585b-115">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="b585b-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b585b-116">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **System** , und klicken Sie auf **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="b585b-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="b585b-117">Klicken Sie auf **Bereitstellen**im **Modellbereitstellungs-Assistenten**.</span><span class="sxs-lookup"><span data-stu-id="b585b-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="b585b-118">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="b585b-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="b585b-119">Suchen Sie das Bereitstellungspaket (PKG-Datei), und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b585b-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="b585b-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b585b-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b585b-121">Nachdem das Paket geladen wurde, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b585b-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b585b-122">Wenn bereits ein Modell vorhanden ist, können Sie es aktualisieren, indem Sie **Vorhandenes Modell aktualisieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="b585b-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="b585b-123">Wählen Sie **Neues Modell erstellen** aus, um ein neues Modell zu erstellen. Nachdem Sie auf **Weiter** geklickt haben, können Sie einen Namen für das neue Modell eingeben.</span><span class="sxs-lookup"><span data-stu-id="b585b-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="b585b-124">Klicken Sie auf **Fertig stellen**, um den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b585b-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="b585b-125">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="b585b-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="b585b-126">Wenn eine Abonnement Sicht im Paket denselben Namen wie eine Abonnement Sicht in einem vorhandenen Modell aufweist, wird die Sicht als *modelname. abonnementviewname*erstellt.</span><span class="sxs-lookup"><span data-stu-id="b585b-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="b585b-127">Wenn dieser Name bereits verwendet wird, wird die Abonnementsicht nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="b585b-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="b585b-128">Der Bereitstellungsprozess umfasst vier Schritte:</span><span class="sxs-lookup"><span data-stu-id="b585b-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="b585b-129">Die Modellobjekte werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="b585b-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="b585b-130">Abonnementsichten werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="b585b-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="b585b-131">Geschäftsregeln werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="b585b-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="b585b-132">Masterdaten werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b585b-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="b585b-133">Beim Erstellen eines neuen oder geklonten Modells wird das Modell gelöscht, falls der Prozess während eines beliebigen Schritts fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b585b-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="b585b-134">Falls bei der Aktualisierung eines Modells der Prozess während eines der ersten drei Schritte fehlschlägt, wird sie nicht über diesen Schritt hinaus fortgesetzt. Für bereits vorgenommene Änderungen wird jedoch kein Rollback durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b585b-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="b585b-135">Wenn der Prozess in Schritt 4 fehlschlägt, werden Elemente, die aktualisiert werden können, aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b585b-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b585b-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b585b-136">Next Steps</span></span>  
 <span data-ttu-id="b585b-137">Benutzerdefinierte Metadaten, Dateiattribute sowie Benutzer- und Gruppenberechtigungen sind nicht in den Modellbereitstellungspaketen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b585b-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="b585b-138">Nachdem Sie ein Modell bereitgestellt haben, müssen diese manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b585b-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="b585b-139">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="b585b-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="b585b-140">Metadaten &#40;Master Data Services hinzufügen&#41;</span><span class="sxs-lookup"><span data-stu-id="b585b-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="b585b-141">Zuweisen von Berechtigungen für Modellobjekte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b585b-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b585b-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b585b-142">See Also</span></span>  
 [<span data-ttu-id="b585b-143">Bereitstellen von Modellen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b585b-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
