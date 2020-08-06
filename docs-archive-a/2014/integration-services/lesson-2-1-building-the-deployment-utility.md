---
title: 'Schritt 1: Erstellen des Bereitstellungs-Hilfsprogramms | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618112"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="46dec-102">Schritt 1: Erstellen des Bereitstellungshilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="46dec-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="46dec-103">In dieser Aufgabe konfigurieren und erstellen Sie ein Bereitstellungsprogramm für das Deployment Tutorial-Projekt.</span><span class="sxs-lookup"><span data-stu-id="46dec-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="46dec-104">Vor dem Erstellen des Bereitstellungshilfsprogramms müssen Sie die Eigenschaften des Deployment Tutorial-Projekts ändern.</span><span class="sxs-lookup"><span data-stu-id="46dec-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="46dec-105">Sie können diese Eigenschaften im Dialogfeld **Deployment Tutorial-Eigenschaftenseiten** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46dec-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="46dec-106">In diesem Dialogfeld müssen Sie die Fähigkeit aktivieren, Konfigurationen während der Bereitstellung zu aktualisieren, und angeben, dass beim Erstellungsvorgang ein Bereitstellungshilfsprogramm generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="46dec-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="46dec-107">Nach dem Festlegen der Eigenschaften erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="46dec-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="46dec-108">stellt eine Reihe von Fenstern zum Debuggen von Paketen bereit.</span><span class="sxs-lookup"><span data-stu-id="46dec-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="46dec-109">Sie können Fehler-, Warn- und Informationsmeldungen anzeigen, den Status von Paketen zur Laufzeit nachverfolgen oder den Fortschritt und die Ergebnisse von Erstellungsvorgängen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="46dec-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="46dec-110">In dieser Lektion verwenden Sie das Ausgabefenster, um den Fortschritt und die Ergebnisse beim Erstellen des Bereitstellungshilfsprogramms anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46dec-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="46dec-111">So legen Sie die Eigenschaften des Bereitstellungshilfsprogramms fest</span><span class="sxs-lookup"><span data-stu-id="46dec-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="46dec-112">Wenn [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] noch nicht geöffnet ist, klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft SQL Server 2005**, und klicken Sie dann auf **Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="46dec-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="46dec-113">Klicken Sie im Menü **Datei** auf **Öffnen**&gt; **Projekt/Projektmappe**. Wählen Sie den Ordner **Deployment Tutorial** aus, klicken Sie auf **Öffnen**und anschließend doppelt auf **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="46dec-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="46dec-114">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf „Deployment Tutorial“ und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="46dec-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="46dec-115">Erweitern Sie im Dialogfeld **Deployment Tutorial-Eigenschaftenseiten** den Knoten Konfigurationseigenschaften, und klicken Sie auf Bereitstellungshilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="46dec-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="46dec-116">Überprüfen Sie im rechten Bereich des Dialog Felds **Deployment Tutorial-Eigenschaften Seiten** , ob `AllowConfigurationChanges` auf festgelegt ist `true` , legen `CreateDeploymentUtility` Sie auf fest, `true` und aktualisieren Sie optional den Standardwert von `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="46dec-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="46dec-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46dec-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="46dec-118">So erstellen Sie das Bereitstellungshilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="46dec-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="46dec-119">Klicken Sie im Projektmappen-Explorer auf **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="46dec-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="46dec-120">Klicken Sie im Menü **Ansicht** auf **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="46dec-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="46dec-121">Das Ausgabefenster befindet sich standardmäßig in der unteren linken Ecke von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dec-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="46dec-122">Klicken Sie im Menü **Erstellen** auf **Deployment Tutorial erstellen**.</span><span class="sxs-lookup"><span data-stu-id="46dec-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="46dec-123">Überprüfen Sie im Ausgabefenster die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="46dec-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="46dec-124">Erstellung gestartet: SQL Integration Services-Projekt: Inkrementell ...</span><span class="sxs-lookup"><span data-stu-id="46dec-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="46dec-125">Bereitstellungshilfsprogramm wird erstellt...</span><span class="sxs-lookup"><span data-stu-id="46dec-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="46dec-126">Das Bereitstellungshilfsprogramm wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="46dec-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="46dec-127">Erstellung abgeschlossen -- 0 Fehler, 0 Warnungen</span><span class="sxs-lookup"><span data-stu-id="46dec-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="46dec-128">========== Erstellen: 0 erfolgreich, Fehler bei 0, 1 aktuell, 0 übersprungen ==========</span><span class="sxs-lookup"><span data-stu-id="46dec-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="46dec-129">Klicken Sie im Menü **Datei** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="46dec-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="46dec-130">Wenn Sie zum Speichern der Änderungen an Deployment Tutorial-Elementen aufgefordert werden, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="46dec-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="46dec-131">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="46dec-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="46dec-132">Schritt 2: Überprüfen des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="46dec-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="46dec-133">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="46dec-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="46dec-134">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="46dec-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="46dec-135">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="46dec-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="46dec-136">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="46dec-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dec-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46dec-137">See Also</span></span>  
 [<span data-ttu-id="46dec-138">Erstellen eines Bereitstellungs-Hilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="46dec-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
