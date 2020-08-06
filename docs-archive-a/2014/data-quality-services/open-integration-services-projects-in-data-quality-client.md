---
title: Öffnen von Integration Services-Projekten im Data Quality-Client | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a8bad2f1-8fb0-4d14-a978-11a5720e62d6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd29bbba274535d6489eb8d188aa4f0150ed7c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616189"
---
# <a name="open-integration-services-projects-in-data-quality-client"></a><span data-ttu-id="01db4-102">Öffnen von Integration Services-Projekten im Data Quality-Client</span><span class="sxs-lookup"><span data-stu-id="01db4-102">Open Integration Services Projects in Data Quality Client</span></span>
  <span data-ttu-id="01db4-103">[!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)] ermöglicht es Ihnen, im Batchmodus ein Bereinigungsprojekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="01db4-103">The [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)] enables you to run a cleansing project in batch mode.</span></span> <span data-ttu-id="01db4-104">Manchmal möchten Sie allerdings die Bereinigungsergebnisse vielleicht in einem Integration Services-Paket überprüfen, wie Sie auch die Bereinigungsergebnisse auf der Registerkarte **Ergebnisse verwalten und anzeigen** einer Bereinigungsaktivität in einem Data Quality-Projekt in DQS überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="01db4-104">However, at times you might want to review the cleansing results in an Integration Services package similar to how you can review the cleansing results in the **Manage and View Results** tab of a cleansing activity in a data quality project in DQS.</span></span> <span data-ttu-id="01db4-105">DQS ermöglicht es Ihnen, Integration Services-Projekte nur in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] wie ein beliebiges anderes Data Quality-Projekt im Bildschirm **Projekt öffnen** zu öffnen und eine interaktive Bereinigung der Bereinigungsergebnisse in einem Integration Services-Projekt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="01db4-105">DQS enables you to open Integration Services projects in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] just like any other data quality project from the **Open project** screen, and have an interactive cleansing experience of the cleansing results in an Integration Services project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="01db4-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="01db4-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="01db4-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="01db4-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="01db4-108">Nur abgeschlossene Integration Services-Projekte sind im Bildschirm **Projekt öffnen** in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01db4-108">Only completed Integration Services projects are available in the **Open project** screen in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="01db4-109">Fehlgeschlagene und aktuell ausgeführte Projekte sind im Bildschirm **Projekt öffnen** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01db4-109">Failed or running projects are not available in the **Open project** screen.</span></span>  
  
-   <span data-ttu-id="01db4-110">Integration Services-Projekte werden in der interaktiven Bereinigungsphase in (Registerkarte**Ergebnisse verwalten und anzeigen** ) in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="01db4-110">Integration Services projects open at the interactive cleansing stage (**Manage View and Results** tab) in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="01db4-111">Sie können nicht auf die Registerkarte **Bereinigen** oder **Struktur** wechseln.</span><span class="sxs-lookup"><span data-stu-id="01db4-111">You cannot go to the **Cleanse** or **Map** tabs.</span></span> <span data-ttu-id="01db4-112">Sie können nur zur Registerkarte **Exportieren** wechseln, indem Sie auf **Weiter**klicken.</span><span class="sxs-lookup"><span data-stu-id="01db4-112">You can only go to the **Export** tab by clicking **Next**.</span></span>  
  
-   <span data-ttu-id="01db4-113">Sie können ein gesperrtes Integration Services-Projekt nicht aus [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="01db4-113">You cannot delete a locked Integration Services project from [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="01db4-114">Zum Löschen müssen Sie es zunächst entsperren.</span><span class="sxs-lookup"><span data-stu-id="01db4-114">You must first unlock it to delete.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="01db4-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="01db4-115">Prerequisites</span></span>  
 <span data-ttu-id="01db4-116">Sie müssen das Ausführen eines Integration Services-Projekts, das ein Paket mit einer DQS-Bereinigungskomponente enthält, erfolgreich abgeschlossen haben, um es in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]anzuzeigen und zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="01db4-116">You must have successfully completed running an Integration Services project containing a package with a DQS Cleansing component to see and open it in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="01db4-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="01db4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="01db4-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="01db4-118">Permissions</span></span>  
 <span data-ttu-id="01db4-119">Sie müssen die Rolle „dqs_kb_editor“ oder „dqs_kb_operator“ in der Datenbank DQS_MAIN haben, um ein Integration Services-Projekt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="01db4-119">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to open an Integration Services project.</span></span>  
  
##  <a name="open-an-integration-services-project"></a><a name="Open"></a> <span data-ttu-id="01db4-120">Öffnen eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="01db4-120">Open an Integration Services Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="01db4-121">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="01db4-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="01db4-122">[!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]Klicken Sie im-Startbildschirm **auf Data Quality-Projekt öffnen**.</span><span class="sxs-lookup"><span data-stu-id="01db4-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open Data Quality Project**.</span></span> <span data-ttu-id="01db4-123">Der Bildschirm **Projekt öffnen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01db4-123">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="01db4-124">Im Bildschirm **Projekt öffnen** können Sie ein Integration Services-Projekt auf eine der folgenden Weisen identifizieren:</span><span class="sxs-lookup"><span data-stu-id="01db4-124">In the **Open project** screen, you can identify an Integration Services project in either of the following ways:</span></span>  
  
    1.  <span data-ttu-id="01db4-125">**Projekt Name**: Integration Services Projekte werden mit der folgenden Benennungs Terminologie aufgelistet: "Package. DQS Cleansing_ *\<DATE>\*\*\<TIME>* _ {GUID}".</span><span class="sxs-lookup"><span data-stu-id="01db4-125">**Project Name**: Integration Services projects are listed using the following naming terminology: "Package.DQS Cleansing_*\<DATE>\*\*\<TIME>*_{GUID}."</span></span> <span data-ttu-id="01db4-126">Bei jeder erfolgreichen Ausführung des gleichen Pakets in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]wird ein neues Projekt auf dem Bildschirm **Projekt öffnen** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="01db4-126">Every time you successfully run the same package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], a new project is listed in the **Open project** screen.</span></span>  
  
    2.  <span data-ttu-id="01db4-127">**Projekttyp**: Integration Services-Projekte haben **SSIS** als Projekttyp im Bildschirm **Projekt öffnen** .</span><span class="sxs-lookup"><span data-stu-id="01db4-127">**Project Type**: Integration Services projects have **SSIS** as the project type in the **Open project** screen.</span></span>  
  
     <span data-ttu-id="01db4-128">Wählen Sie ein Projekt aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01db4-128">Select a project, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="01db4-129">Das Integration Services-Projekt wird in der interaktiven Bereinigungsphase (Registerkarte**Ergebnisse verwalten und anzeigen** ) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="01db4-129">The Integration Services project opens at the interactive cleansing stage (**Manage View and Results** tab).</span></span> <span data-ttu-id="01db4-130">Sie können eine interaktive Bereinigung für die Daten im Integration Services-Projekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="01db4-130">You can perform an interactive cleansing on the data in the Integration Services project.</span></span> <span data-ttu-id="01db4-131">Ausführliche Informationen zur Registerkarte **Ergebnisse verwalten und anzeigen** finden Sie unter [Interaktive Bereinigungsphase](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md#Interactive) in [Bereinigen von Daten mit &#40;internem&#41; DQS-Wissen](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md).</span><span class="sxs-lookup"><span data-stu-id="01db4-131">For detailed information about the **Manage and View Results** tab, see [Interactive Cleansing Stage](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md#Interactive) in [Cleanse Data Using DQS &#40;Internal&#41; Knowledge](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md).</span></span>  
  
5.  <span data-ttu-id="01db4-132">Klicken Sie auf **Weiter** , um zur Registerkarte **Exportieren** zu wechseln, wo Sie die verarbeiteten Daten in eine neue Tabelle in der SQL Server-Datenbank, eine CSV-Datei oder eine Excel-Datei exportieren können.</span><span class="sxs-lookup"><span data-stu-id="01db4-132">Click **Next** to go to the **Export** tab where you can export the processed data to any of the following: a new table in the SQL Server database, a .csv file, or an Excel file.</span></span> <span data-ttu-id="01db4-133">Ausführliche Informationen zur Registerkarte **Exportieren** finden Sie unter [Exportphase](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md#Export) in [Bereinigen von Daten mit &#40;internem&#41; DQS-Wissen](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md).</span><span class="sxs-lookup"><span data-stu-id="01db4-133">For detailed information about the **Export** tab, see [Export Stage](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md#Export) in [Cleanse Data Using DQS &#40;Internal&#41; Knowledge](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)</span></span>  
  
6.  <span data-ttu-id="01db4-134">Klicken Sie nach dem Exportieren der Daten auf **Fertig stellen** , um das Integration Services-Projekt zu schließen.</span><span class="sxs-lookup"><span data-stu-id="01db4-134">After exporting the data, click **Finish** to close the Integration Services project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01db4-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01db4-135">See Also</span></span>  
 <span data-ttu-id="01db4-136">[Transformation für DQS-Bereinigung](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="01db4-136">[DQS Cleansing Transformation](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) </span></span>  
 [<span data-ttu-id="01db4-137">Integration Services-Projekte &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="01db4-137">Integration Services &#40;SSIS&#41; Projects</span></span>](../integration-services/integration-services-ssis-projects-and-solutions.md)  