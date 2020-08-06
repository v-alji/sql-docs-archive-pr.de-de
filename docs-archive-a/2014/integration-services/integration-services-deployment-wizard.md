---
title: Bereitstellungs-Assistent für Integration Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721609"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="ccb2a-102">Bereitstellungs-Assistent für Integration Services</span><span class="sxs-lookup"><span data-stu-id="ccb2a-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="ccb2a-103">Der Bereitstellungs-Assistent für [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] stellt Projekte im SSISDB-Katalog auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz bereit, die das Projektbereitstellungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="ccb2a-104">Um den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Bereitstellungs-Assistenten in einem geöffneten Projekt in zu starten [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , wählen Sie im Menü **Projekt** die Option bereitstellen aus. **Deploy**</span><span class="sxs-lookup"><span data-stu-id="ccb2a-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="ccb2a-105">Um den Assistenten in zu starten [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , erweitern Sie den Knoten **Integration Services Kataloge**  >  **ssisdb** in Objekt-Explorer, klicken Sie mit der rechten Maustaste auf den Ordner **Projekte** , und klicken Sie dann auf **Projekt**bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="ccb2a-106">Der Assistent führt Sie die folgenden vier Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="ccb2a-107">Klicken Sie auf **weiter** , um zum nächsten Schritt zu wechseln **, oder zurück, um zum** vorherigen Schritt zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="ccb2a-108">**Quelle auswählen** : Wählen Sie das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Projekt aus, das Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="ccb2a-109">**Ziel auswählen** : Wählen Sie das Projektziel aus.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="ccb2a-110">**Review** : zeigt Ihre Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="ccb2a-111">Bereitstellen **/Ergebnisse** : stellt das Projekt bereit und zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="ccb2a-112">Auswählen der Quelle</span><span class="sxs-lookup"><span data-stu-id="ccb2a-112">Select Source</span></span>  
 <span data-ttu-id="ccb2a-113">Um eine von Ihnen erstellte Projekt Bereitstellungs Datei bereitzustellen, wählen Sie **Projekt Bereitstellungs Datei** aus, und geben Sie den Pfad zur ispac-Datei ein, oder klicken Sie auf **Durchsuchen** , um Sie im [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Projektordner zu suchen</span><span class="sxs-lookup"><span data-stu-id="ccb2a-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="ccb2a-114">Um ein Projekt bereitzustellen, das sich im [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Katalog befindet, wählen Sie **Integration Services-Katalog**aus und geben dann den Servernamen und den Pfad zum Projekt im Katalog ein.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="ccb2a-115">Wenn Sie den Assistenten in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] starten, dann wählt der Assistent standardmäßig das geöffnete Projekt als Quelle aus und überspringt diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="ccb2a-116">Wenn Sie zu diesem Schritt zurückkehren und eine andere Quelle auswählen möchten, klicken Sie auf zurück **, oder klicken** Sie im linken Bereich auf **Quelle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="ccb2a-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="ccb2a-117">Ziel auswählen</span><span class="sxs-lookup"><span data-stu-id="ccb2a-117">Select Destination</span></span>  
 <span data-ttu-id="ccb2a-118">Um den Zielordner für das Projekt im [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Katalog auszuwählen, geben Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz ein, oder klicken Sie auf **Durchsuchen** , um aus einer Liste von Servern auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="ccb2a-119">Geben Sie den Projektpfad in SSISDB ein, oder klicken Sie auf **Durchsuchen** , um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="ccb2a-120">Wenn Sie den Assistenten in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starten, dann wählt der Assistent standardmäßig die verbundene Serverinstanz aus und gibt den Pfad für das ausgewählte Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="ccb2a-121">Sie können diese Werte ändern, um das Projekt an einem anderen Speicherort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="ccb2a-122">Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ccb2a-122">Review</span></span>  
 <span data-ttu-id="ccb2a-123">Mit dem Assistenten können Sie die von Ihnen ausgewählten Einstellungen überprüfen, bevor Sie das Projekt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="ccb2a-124">Sie können Ihre Auswahl ändern, indem Sie auf **Zurück**klicken oder indem Sie auf einen der Schritte im linken Bereich klicken.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="ccb2a-125">Bereitstellen/Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="ccb2a-125">Deploy/Results</span></span>  
 <span data-ttu-id="ccb2a-126">Wenn Sie auf der Seite **überprüfen** auf Bereitstellen klicken, wird das Projekt bereitgestellt, **und auf der** Seite **Ergebnisse** wird der Erfolg oder Misserfolg der einzelnen Aktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="ccb2a-127">Ist die Aktion fehlerhaft, klicken Sie auf **Fehler** in der Spalte **Ergebnis** , um eine Erklärung über den Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="ccb2a-128">Klicken Sie auf **Bericht speichern...** , um die Ergebnisse in einer XML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="ccb2a-129">Klicken Sie auf **Schließen**, um den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb2a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb2a-130">See Also</span></span>  
 <span data-ttu-id="ccb2a-131">[Bereitstellen von Projekten auf Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="ccb2a-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="ccb2a-132">Bereitstellung von Projekten und Paketen</span><span class="sxs-lookup"><span data-stu-id="ccb2a-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
