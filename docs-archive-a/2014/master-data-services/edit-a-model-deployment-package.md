---
title: Bearbeiten eines Modellbereitstellungspakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630673"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="44151-102">Bearbeiten eines Modellbereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="44151-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="44151-103">In diesem Thema wird beschrieben, wie ausgewählte Teile eines Modells statt eines ganzen Modells in MDS bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="44151-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="44151-104">Hierzu bearbeiten Sie mit dem Modellpaketeditor ein MDS-Modellpaket.</span><span class="sxs-lookup"><span data-stu-id="44151-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="44151-105">Der Modellpaketeditor-Assistent ermöglicht es Ihnen, bestimmte Entitäten, abgeleitete Hierarchien, Abonnementsichten und Geschäftsregeln in einem Modell auszuwählen, die Sie in ein MDS-Paket einschließen und dann später bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="44151-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="44151-106">Sie können die Teile des Modells auslassen, die Sie nicht bereitstellen wollen.</span><span class="sxs-lookup"><span data-stu-id="44151-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="44151-107">Wenn Sie eine Entität auswählen, werden alle abhängigen Objekte in dieser Entität automatisch auch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="44151-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="44151-108">Sie wählen mithilfe des Modellpaketeditors Teile eines Modells in einer Paketdatei, die entweder vom Tool MDSModelDeploy (welches eine Paketdatei erstellt, die Objekte und Daten umfasst) oder dem Modellbereitstellungs-Assistenten (welcher eine Datei erstellt, die nur die Modellstruktur enthält) erstellt wurde, aus.</span><span class="sxs-lookup"><span data-stu-id="44151-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="44151-109">Nachdem Sie das Modell im Paket bearbeitet haben, verwenden Sie das Tool MDSModelDeploy, um Objekte und Daten bereitzustellen, oder den Modellbereitstellungs-Assistent, um nur die Modellstruktur bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="44151-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44151-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="44151-110">Prerequisites</span></span>  
 <span data-ttu-id="44151-111">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="44151-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="44151-112">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="44151-112">You must be a model administrator.</span></span> <span data-ttu-id="44151-113">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="44151-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="44151-114">Es muss ein Modellpaket vorhanden sein, das Sie bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="44151-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="44151-115">Weitere Informationen finden Sie unter [Bereitstellen von Modellen &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) und [Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) oder [Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="44151-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="44151-116">So bearbeiten Sie ein Modellbereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="44151-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="44151-117">Wechseln Sie in Windows-Explorer auf dem MDS-Server zu *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\configuration.</span><span class="sxs-lookup"><span data-stu-id="44151-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="44151-118">Führen Sie ModelPackageEditor.exe aus.</span><span class="sxs-lookup"><span data-stu-id="44151-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="44151-119">Klicken Sie im Modellpaketeditor-Assistenten auf **Durchsuchen**, wechseln Sie zu dem Ordner, der die Pakete enthält, wählen Sie ein Paket aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="44151-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="44151-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="44151-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="44151-121">Wählen Sie die Entitäten, abgeleiteten Hierarchien, Abonnementsichten oder Geschäftsregeln, die Sie bereitstellen möchten, aus.</span><span class="sxs-lookup"><span data-stu-id="44151-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="44151-122">Heben Sie die Auswahl für die auf, die Sie nicht bereitstellen wollen.</span><span class="sxs-lookup"><span data-stu-id="44151-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="44151-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="44151-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="44151-124">Überprüfen Sie die bereitzustellende Auswahlliste.</span><span class="sxs-lookup"><span data-stu-id="44151-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="44151-125">Um Änderungen vorzunehmen, klicken Sie auf **Zurück** und wiederholen Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="44151-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="44151-126">Klicken Sie auf **Durchsuchen**, wechseln Sie in den Ordner, in dem Sie das Teilpaket speichern möchten, und geben Sie anschließend den Dateinamen des Teilpakets ein (mit der Erweiterung „.pkg“).</span><span class="sxs-lookup"><span data-stu-id="44151-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="44151-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="44151-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="44151-128">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="44151-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="44151-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="44151-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="44151-130">Bereitstellen eines Modellbereitstellungspakets mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="44151-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="44151-131">Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="44151-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
