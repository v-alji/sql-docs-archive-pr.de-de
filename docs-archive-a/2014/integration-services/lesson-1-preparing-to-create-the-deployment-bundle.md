---
title: 'Lektion 1: Vorbereiten der Erstellung des Bereitstellungspakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618118"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="00cfe-102">Lektion 1: Vorbereiten der Erstellung des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="00cfe-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="00cfe-103">In dieser Lektion erstellen Sie die Arbeitsordner und Umgebungsvariablen zur Unterstützung des Lernprogramms. Sie erstellen weiterhin ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, fügen diesem mehrere Pakete und die zugehörigen Unterstützungsdateien hinzu und implementieren Konfigurationen in Paketen.</span><span class="sxs-lookup"><span data-stu-id="00cfe-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="00cfe-104">werden Pakete auf Projektbasis bereitgestellt. Deshalb müssen Sie als ersten Schritt beim Erstellen des Bereitstellungspakets alle Pakete und Paketabhängigkeiten in einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt sammeln.</span><span class="sxs-lookup"><span data-stu-id="00cfe-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="00cfe-105">Oft ist es nützlich, weitere Informationen in die bereitgestellten Pakete einzufügen: Sie fügen z. B. dem Projekt auch eine Infodatei hinzu, die eine grundlegende Dokumentation für diese Gruppe von Paketen enthält.</span><span class="sxs-lookup"><span data-stu-id="00cfe-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="00cfe-106">Nachdem Sie die Pakete und Dateien hinzugefügt haben, fügen Sie den Paketen Konfigurationen hinzu, von denen noch keine Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00cfe-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="00cfe-107">Durch die Konfigurationen werden die Eigenschaften von Paketen und Paketobjekten zur Laufzeit aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="00cfe-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="00cfe-108">In einer späteren Lektion ändern Sie die Werte dieser Konfigurationen während der Paketbereitstellung, um die Pakete in der Umgebung zu unterstützen, in der sie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="00cfe-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="00cfe-109">Nachdem Sie die Konfigurationen hinzugefügt haben, sollten Sie die Pakete im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer, dem grafischen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Tool zum Erstellen von ETL-Paketen, öffnen und die Eigenschaften der Pakete und Paketelemente sowie die Paketkonfigurationen untersuchen, um die Probleme besser zu verstehen, die bei der Bereitstellung berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="00cfe-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="00cfe-110">Zum Beispiel werden durch eines der Pakete Daten aus Textdateien extrahiert, sodass der Speicherort der Datendateien aktualisiert werden muss, damit die bereitgestellten Pakete erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00cfe-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="00cfe-111">**Geschätzte Zeit zum Bearbeiten dieser Lektion:** 1 Stunde</span><span class="sxs-lookup"><span data-stu-id="00cfe-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="00cfe-112">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="00cfe-112">Lesson Tasks</span></span>  
 <span data-ttu-id="00cfe-113">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="00cfe-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="00cfe-114">Schritt 1: Erstellen von Arbeitsordnern und Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="00cfe-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="00cfe-115">Schritt 2: Erstellen des Bereitstellungsprojekts</span><span class="sxs-lookup"><span data-stu-id="00cfe-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="00cfe-116">Schritt 3: Hinzufügen von Paketen und weiteren Dateien</span><span class="sxs-lookup"><span data-stu-id="00cfe-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="00cfe-117">Schritt 4: Hinzufügen von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="00cfe-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="00cfe-118">Schritt 5: Testen der aktualisierten Pakete</span><span class="sxs-lookup"><span data-stu-id="00cfe-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="00cfe-119">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="00cfe-119">Start the Lesson</span></span>  
 [<span data-ttu-id="00cfe-120">Schritt 1: Erstellen von Arbeitsordnern und Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="00cfe-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="00cfe-121">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="00cfe-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="00cfe-122">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="00cfe-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="00cfe-123">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="00cfe-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="00cfe-124">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="00cfe-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
