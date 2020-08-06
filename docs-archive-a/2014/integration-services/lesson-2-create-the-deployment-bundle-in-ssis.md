---
title: 'Lektion 2: Erstellen des Bereitstellungs Pakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619904"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="bfc68-102">Lektion 2: Erstellen des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="bfc68-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="bfc68-103">In [Lektion 1: Vorbereiten der Erstellung des Bereitstellungspakets](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md)haben Sie das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit Namen „Deployment Tutorial“ erstellt, diesem die Pakete und Unterstützungsdateien hinzugefügt und Konfigurationen in Paketen implementiert.</span><span class="sxs-lookup"><span data-stu-id="bfc68-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="bfc68-104">In dieser Lektion erstellen Sie das Bereitstellungspaket. Dabei handelt es sich um einen Ordner, der die Elemente enthält, die Sie benötigen, um Pakete auf einem anderen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bfc68-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="bfc68-105">Das Bereitstellungspaket enthält ein Bereitstellungsmanifest, Kopien der Pakete und Kopien der Unterstützungsdateien aus dem Deployment Tutorial-Projekt.</span><span class="sxs-lookup"><span data-stu-id="bfc68-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="bfc68-106">Im Bereitstellungsmanifest werden die Pakete, verschiedene Dateien und Konfigurationen im Bereitstellungspaket aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bfc68-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="bfc68-107">Sie überprüfen auch die Dateiliste im Bereitstellungspaket und untersuchen den Inhalt des Manifests.</span><span class="sxs-lookup"><span data-stu-id="bfc68-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="bfc68-108">**Geschätzte Zeit zum Bearbeiten dieser Lektion:** 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="bfc68-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="bfc68-109">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="bfc68-109">Lesson Tasks</span></span>  
 <span data-ttu-id="bfc68-110">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="bfc68-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="bfc68-111">Schritt 1: Erstellen des Bereitstellungshilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="bfc68-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="bfc68-112">Schritt 2: Überprüfen des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="bfc68-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="bfc68-113">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="bfc68-113">Start the Lesson</span></span>  
 [<span data-ttu-id="bfc68-114">Schritt 1: Erstellen des Bereitstellungshilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="bfc68-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="bfc68-115">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="bfc68-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bfc68-116">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="bfc68-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bfc68-117">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="bfc68-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bfc68-118">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bfc68-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
