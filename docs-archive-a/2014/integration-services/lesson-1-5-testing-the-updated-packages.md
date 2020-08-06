---
title: 'Schritt 5: Testen der aktualisierten Pakete | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618127"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="6c398-102">Schritt 5: Testen der aktualisierten Pakete</span><span class="sxs-lookup"><span data-stu-id="6c398-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="6c398-103">Bevor Sie mit der nächsten Lektion fortfahren, in der Sie das Bereitstellungspaket erstellen, das bei der Installation der Lernprogrammpakete auf dem Zielcomputer verwendet werden soll, sollten Sie die Pakete testen.</span><span class="sxs-lookup"><span data-stu-id="6c398-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="6c398-104">In dieser Aufgabe führen Sie die Pakete DataTransfer.dtsx und LoadXMLData aus, die Sie dem Deployment Tutorial-Projekt hinzugefügt und dann mit Konfigurationen erweitert haben.</span><span class="sxs-lookup"><span data-stu-id="6c398-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="6c398-105">Bei der Ausführung der Pakete wird jede ausführbare Datei im Paket, die erfolgreich abgeschlossen wurde, in Grün angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c398-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="6c398-106">Werden alle ausführbaren Dateien in Grün angezeigt, wurde das Paket erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6c398-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="6c398-107">Sie können den Status der Paketausführung auch auf der Registerkarte **Status** verfolgen.</span><span class="sxs-lookup"><span data-stu-id="6c398-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="6c398-108">Werden die Pakete nicht erfolgreich ausgeführt, müssen Sie das Problem beheben, bevor Sie mit der nächsten Lektion fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6c398-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="6c398-109">So führen Sie das DataTransfer-Paket aus</span><span class="sxs-lookup"><span data-stu-id="6c398-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="6c398-110">Klicken Sie im Projektmappen-Explorer auf DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6c398-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="6c398-111">Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="6c398-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="6c398-112">Klicken Sie nach Ausführen des Pakets im Menü **Debuggen** auf **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="6c398-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="6c398-113">So führen Sie das LoadXMLData-Paket aus</span><span class="sxs-lookup"><span data-stu-id="6c398-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="6c398-114">Klicken Sie im Projektmappen-Explorer auf LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6c398-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="6c398-115">Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="6c398-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="6c398-116">Klicken Sie nach Ausführen des Pakets im Menü **Debuggen** auf **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="6c398-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6c398-117">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="6c398-117">Next Lesson</span></span>  
 [<span data-ttu-id="6c398-118">Lektion 2: Erstellen des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="6c398-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="6c398-119">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="6c398-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6c398-120">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="6c398-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6c398-121">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="6c398-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6c398-122">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6c398-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
