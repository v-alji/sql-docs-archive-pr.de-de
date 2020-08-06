---
title: 'Schritt 2: Erstellen des Bereitstellungsprojekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618140"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="e0407-102">Schritt 2: Erstellen des Bereitstellungsprojekts</span><span class="sxs-lookup"><span data-stu-id="e0407-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="e0407-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]ist die bereitstellbare Einheit ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="e0407-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="e0407-104">Bevor Sie Pakete bereitstellen können, müssen Sie ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt erstellen und diesem Projekt alle Pakete und Hilfsdateien hinzufügen, die mit den Paketen bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0407-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="e0407-105">So erstellen Sie das Integration Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="e0407-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="e0407-106">Klicken Sie auf **Start**und zeigen sie auf **Alle Programme**. Klicken Sie nun auf **Microsoft SQL Server**und anschließend auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="e0407-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="e0407-107">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie anschließend auf **Projekt** , um ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e0407-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="e0407-108">Wählen Sie im Bereich **Vorlagen** des Dialogfelds **Neues Projekt** die Option **Integration Services-Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="e0407-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="e0407-109">Ändern Sie im Feld **Name** den Standardnamen in **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="e0407-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="e0407-110">Deaktivieren Sie optional das Kontrollkästchen **Projektmappenverzeichnis erstellen** .</span><span class="sxs-lookup"><span data-stu-id="e0407-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="e0407-111">Übernehmen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um nach dem gewünschten Ordner zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e0407-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="e0407-112">Klicken Sie im Dialogfeld **Projektspeicherort** auf den Ordner und anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e0407-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="e0407-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0407-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="e0407-114">Standardmäßig wird ein leeres Paket mit dem Namen Package.dtsx erstellt und dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0407-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="e0407-115">Sie verwenden dieses Paket jedoch nicht, sondern fügen dem Projekt vorhandene Pakete hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0407-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="e0407-116">Da alle Pakete in einem Projekt bei der Bereitstellung berücksichtigt werden, sollten Sie Package.dtsx löschen.</span><span class="sxs-lookup"><span data-stu-id="e0407-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="e0407-117">Klicken Sie dazu mit der rechten Maustaste auf das Paket und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e0407-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e0407-118">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="e0407-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e0407-119">Schritt 3: Hinzufügen von Paketen und weiteren Dateien</span><span class="sxs-lookup"><span data-stu-id="e0407-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="e0407-120">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="e0407-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e0407-121">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="e0407-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e0407-122">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="e0407-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e0407-123">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e0407-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0407-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0407-124">See Also</span></span>  
 [<span data-ttu-id="e0407-125">Integration Services-Projekte &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e0407-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
