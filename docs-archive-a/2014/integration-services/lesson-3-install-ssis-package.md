---
title: 'Lektion 3: Installieren von Paketen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617178"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="dbba1-102">Lektion 3: Installieren von Paketen</span><span class="sxs-lookup"><span data-stu-id="dbba1-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="dbba1-103">In [Lektion 2: Erstellen des Bereitstellungs Pakets](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)haben Sie ein Bereitstellungs Hilfsprogramm erstellt und das Bereitstellungs Paket erstellt, das die Elemente enthält, mit denen Sie Pakete auf einem anderen Computer installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="dbba1-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="dbba1-104">Sie haben außerdem die Dateiliste im Bereitstellungspaket überprüft und den Inhalt der Manifestdatei untersucht, die beim Erstellen des Bereitstellungshilfsprogramms erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dbba1-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="dbba1-105">In dieser Lektion kopieren Sie das Bereitstellungspaket auf den Zielcomputer und führen anschließend den Paketinstallations-Assistenten aus, um die Pakete, Paketabhängigkeiten und Hilfsdateien auf diesem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dbba1-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="dbba1-106">Die Pakete werden in der **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank installiert, und die anderen Elemente werden im Dateisystem installiert.</span><span class="sxs-lookup"><span data-stu-id="dbba1-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="dbba1-107">Nach Abschluss der Paketinstallation testen Sie die Bereitstellung, indem Sie die Pakete mithilfe des Paketausführungshilfsprogramms in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="dbba1-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="dbba1-108">**Geschätzte Zeit zum Bearbeiten dieser Lektion:** 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="dbba1-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="dbba1-109">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="dbba1-109">Lesson Tasks</span></span>  
 <span data-ttu-id="dbba1-110">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="dbba1-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="dbba1-111">Schritt 1: Kopieren des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="dbba1-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="dbba1-112">Schritt 2: Ausführen des Paketinstallations-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dbba1-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="dbba1-113">Schritt 3: Testen der bereitgestellten Pakete</span><span class="sxs-lookup"><span data-stu-id="dbba1-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="dbba1-114">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="dbba1-114">Start the Lesson</span></span>  
 [<span data-ttu-id="dbba1-115">Schritt 1: Kopieren des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="dbba1-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="dbba1-116">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="dbba1-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dbba1-117">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="dbba1-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dbba1-118">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="dbba1-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dbba1-119">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dbba1-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
