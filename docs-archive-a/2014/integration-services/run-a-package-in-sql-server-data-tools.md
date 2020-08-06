---
title: Ausführen eines Pakets in SQL Server Data Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696921"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="ec6c0-102">Ausführen eines Pakets in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="ec6c0-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="ec6c0-103">Das Ausführen von Paketen in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erfolgt zumeist beim Entwickeln, Debuggen und Testen von Paketen.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="ec6c0-104">Wenn Sie ein Paket im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer ausführen, wird das Paket immer sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="ec6c0-105">Während ein Paket ausgeführt wird, zeigt der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer den Fortschritt der Paketausführung auf der **Status** -Registerkarte an. Sie können den Start- und Endzeitpunkt des Pakets sowie seine Tasks und Container sehen. Außerdem werden Informationen über Tasks und Container im Paket angezeigt, deren Ausführung fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="ec6c0-106">Wenn die Ausführung des Pakets beendet wurde, sind die Laufzeitinformationen weiterhin auf der Registerkarte **Ausführungsergebnisse** verfügbar. Weitere Informationen finden Sie im Abschnitt "Fortschrittsberichte" im Thema [Debugging Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="ec6c0-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="ec6c0-107">**Entwurfszeitbereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-107">**Design-time deployment**.</span></span> <span data-ttu-id="ec6c0-108">Wenn Sie ein Paket in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]ausführen, wird das Paket erstellt und dann in einem Ordner bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="ec6c0-109">Vor dem Ausführen des Pakets können Sie den Ordner angeben, in dem das Paket bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="ec6c0-110">Wenn Sie keinen Ordner angeben, wird standardmäßig der Ordner **bin** verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="ec6c0-111">Dieser Bereitstellungstyp wird als Entwurfszeitbereitstellung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="ec6c0-112">So führen Sie ein Paket in SQL Server-Datentools aus</span><span class="sxs-lookup"><span data-stu-id="ec6c0-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="ec6c0-113">Wenn die Projektmappe mehrere Projekte enthält, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, und klicken Sie anschließend auf **Als Startobjekt festlegen** , um das Startprojekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="ec6c0-114">Wenn das Projekt mehrere Pakete enthält, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, und klicken Sie anschließend auf **Als Startobjekt** festlegen, um das Startpaket festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="ec6c0-115">Sie können ein Paket mit einem der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ec6c0-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="ec6c0-116">Öffnen Sie das Paket, das Sie ausführen möchten, und klicken Sie auf der Menüleiste auf **Debuggen starten** , oder drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="ec6c0-117">Nachdem das Paket ausgeführt wurde, drücken Sie UMSCHALT+F5, um zum Entwurfsmodus zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="ec6c0-118">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, und klicken Sie anschließend auf **Paket ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="ec6c0-119">So geben Sie einen anderen Ordner für die Entwurfszeitbereitstellung an</span><span class="sxs-lookup"><span data-stu-id="ec6c0-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="ec6c0-120">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projektordner, der das auszuführende Paket enthält. Klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ec6c0-121">Klicken Sie im Dialogfeld **\<project name>-Eigenschaftenseiten** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="ec6c0-122">Aktualisieren Sie den Wert der OutputPath-Eigenschaft, und geben Sie den Ordner an, den Sie für die Entwurfszeitbereitstellung verwenden möchten. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec6c0-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6c0-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec6c0-123">See Also</span></span>  
 <span data-ttu-id="ec6c0-124">[Ausführung von Projekten und Paketen](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="ec6c0-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="ec6c0-125">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) (Integration Services-Pakete [SSIS])</span><span class="sxs-lookup"><span data-stu-id="ec6c0-125">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md)</span></span>  
  
  
