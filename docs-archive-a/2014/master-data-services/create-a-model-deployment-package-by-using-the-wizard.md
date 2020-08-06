---
title: Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622189"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="90af7-102">Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="90af7-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="90af7-103">Verwenden Sie den [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Modellbereitstellungs-Assistenten, um nur ein Paket der Modellobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="90af7-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="90af7-104">Informationen zum Aufnehmen von Daten in ein Paket finden Sie unter [Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="90af7-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="90af7-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="90af7-105">Prerequisites</span></span>  
 <span data-ttu-id="90af7-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="90af7-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="90af7-107">Sie müssen in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="90af7-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="90af7-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="90af7-108">You must be a model administrator.</span></span> <span data-ttu-id="90af7-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="90af7-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="90af7-110">Es muss ein Modell vorhanden sein, aus dem Sie ein Paket erstellen können.</span><span class="sxs-lookup"><span data-stu-id="90af7-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="90af7-111">Weitere Informationen finden Sie unter [Erstellen eines Modells &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="90af7-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="90af7-112">So erstellen Sie ein Modellbereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="90af7-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="90af7-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="90af7-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="90af7-114">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **System** , und klicken Sie auf **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="90af7-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="90af7-115">Klicken Sie auf **Erstellen**im **Modellbereitstellungs-Assistenten**.</span><span class="sxs-lookup"><span data-stu-id="90af7-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="90af7-116">Wählen Sie auf der Seite **Paket erstellen** ein Modell aus der Liste **Modell** aus.</span><span class="sxs-lookup"><span data-stu-id="90af7-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="90af7-117">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="90af7-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="90af7-118">Klicken Sie auf **Download**.</span><span class="sxs-lookup"><span data-stu-id="90af7-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="90af7-119">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="90af7-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="90af7-120">Klicken Sie auf **Schließen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="90af7-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="90af7-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="90af7-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="90af7-122">Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="90af7-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="90af7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90af7-123">See Also</span></span>  
 [<span data-ttu-id="90af7-124">Bereitstellen von Modellen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="90af7-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
