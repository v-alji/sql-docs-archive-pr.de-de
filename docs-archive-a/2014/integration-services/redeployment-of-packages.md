---
title: Erneute Bereitstellung von Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- redeploying packages [Integration Services]
- deploying packages [Integration Services], redeploying
ms.assetid: 86806efb-8cf4-4f9d-9824-1152cb4c495c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c5286d406d96f62fc74eb619f7e7a6064fde2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696950"
---
# <a name="redeployment-of-packages"></a><span data-ttu-id="163bf-102">Erneutes Bereitstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="163bf-102">Redeployment of Packages</span></span>
  <span data-ttu-id="163bf-103">Nachdem ein Projekt bereitgestellt wurde, kann es erforderlich werden, die Paketfunktionalität zu aktualisieren oder zu erweitern und anschließend das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, das die aktualisierten Pakete enthält, erneut bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="163bf-103">After a project is deployed, you may need to update or extend package functionality and then redeploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the updated packages.</span></span> <span data-ttu-id="163bf-104">Im Zusammenhang mit dem erneuten Bereitstellen von Paketen sollten Sie die zum Bereitstellungshilfsprogramm gehörenden Konfigurationseigenschaften überprüfen.</span><span class="sxs-lookup"><span data-stu-id="163bf-104">As part of the process of redeploying packages, you should review the configuration properties that are included in the deployment utility.</span></span> <span data-ttu-id="163bf-105">Beispielsweise können Sie festlegen, dass nach dem erneuten Bereitstellen des Pakets keine Konfigurationsänderungen zulässig sein sollen.</span><span class="sxs-lookup"><span data-stu-id="163bf-105">For example, you may not want to allow configuration changes after the package is redeployed.</span></span>  
  
## <a name="process-for-redeployment"></a><span data-ttu-id="163bf-106">Prozess für die erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="163bf-106">Process for Redeployment</span></span>  
 <span data-ttu-id="163bf-107">Nachdem Sie die Pakete aktualisiert haben, erstellen Sie das Projekt neu. Kopieren Sie dann den Bereitstellungsordner zum Zielcomputer, und führen Sie dann den Paketinstallations-Assistenten erneut aus.</span><span class="sxs-lookup"><span data-stu-id="163bf-107">After you finish updating the packages, you rebuild the project, copy the deployment folder to the target computer, and then rerun the Package Installation Wizard.</span></span>  
  
 <span data-ttu-id="163bf-108">Wenn Sie nur wenige Pakete aus dem Projekt aktualisieren, muss eventuell nicht das gesamte Projekt erneut bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="163bf-108">If you update only a few packages in the project, you may not want to redeploy the entire project.</span></span> <span data-ttu-id="163bf-109">Um nur wenige Pakete bereitzustellen, können Sie ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt erstellen, diesem neuen Projekt die aktualisierten Pakete hinzufügen und dann das Projekt erstellen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="163bf-109">To deploy only a few packages, you can create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add the updated packages to the new project, and then build and deploy the project.</span></span> <span data-ttu-id="163bf-110">Die Paketkonfigurationen werden automatisch zusammen mit dem Paket kopiert, wenn Sie das Paket einem anderen Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="163bf-110">Package configurations are automatically copied with the package when you add the package to a different project.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="163bf-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="163bf-111">Related Tasks</span></span>  
 [<span data-ttu-id="163bf-112">Bereitstellen von Paketen mithilfe des Bereitstellungshilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="163bf-112">Deploy Packages by Using the Deployment Utility</span></span>](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)  
  
  
