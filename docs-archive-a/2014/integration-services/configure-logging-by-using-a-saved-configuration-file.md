---
title: Konfigurieren der Protokollierung mithilfe einer gespeicherten Konfigurationsdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619273"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="76d9a-102">Konfigurieren der Protokollierung mithilfe einer gespeicherten Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="76d9a-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="76d9a-103">In diesem Verfahren wird beschrieben, wie die Protokollierung für neue Container in einem Paket konfiguriert wird, indem eine zuvor gespeicherte Protokollierungskonfigurationsdatei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="76d9a-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="76d9a-104">Alle Container in einem Paket verwenden standardmäßig dieselbe Protokollierungskonfiguration wie der übergeordnete Container.</span><span class="sxs-lookup"><span data-stu-id="76d9a-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="76d9a-105">Die Tasks in einer Foreach-Schleife verwenden z. B. dieselbe Protokollierungskonfiguration wie die Foreach-Schleife.</span><span class="sxs-lookup"><span data-stu-id="76d9a-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="76d9a-106">So konfigurieren Sie die Protokollierung für einen Container</span><span class="sxs-lookup"><span data-stu-id="76d9a-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="76d9a-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="76d9a-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="76d9a-108">Klicken Sie im Menü **SSIS** auf **Protokollierung**.</span><span class="sxs-lookup"><span data-stu-id="76d9a-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="76d9a-109">Erweitern Sie die Paketbaumansicht, und wählen Sie den zu konfigurierenden Container aus.</span><span class="sxs-lookup"><span data-stu-id="76d9a-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="76d9a-110">Wählen Sie auf der Registerkarte **Anbieter und Protokolle** die Protokolle aus, die Sie für den Container verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="76d9a-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76d9a-111">Sie können Protokolle nur auf Paketebene erstellen.</span><span class="sxs-lookup"><span data-stu-id="76d9a-111">You can create logs only at the package level.</span></span> <span data-ttu-id="76d9a-112">Weitere Informationen finden Sie unter [Aktivieren der Paketprotokollierung in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="76d9a-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="76d9a-113">Klicken Sie auf die Registerkarte **Details** und dann auf **Laden**.</span><span class="sxs-lookup"><span data-stu-id="76d9a-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="76d9a-114">Suchen Sie die zu verwendende Protokollierungskonfigurationsdatei, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="76d9a-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="76d9a-115">Wählen Sie optional einen anderen zu protokollierenden Protokolleintrag aus, indem Sie das entsprechende Kontrollkästchen in der Spalte **Ereignisse** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76d9a-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="76d9a-116">Klicken Sie auf **Erweitert** , um den für diesen Eintrag zu protokollierenden Informationstyp auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="76d9a-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76d9a-117">Der neue Container enthält u. U. weitere Protokolleinträge, die für den Container nicht verfügbar sind, der ursprünglich zum Erstellen der Protokollierungskonfiguration verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="76d9a-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="76d9a-118">Diese zusätzlichen Protokolleinträge müssen manuell ausgewählt werden, falls diese protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76d9a-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="76d9a-119">Um die aktualisierte Version der Protokollierungskonfiguration zu speichern, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="76d9a-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="76d9a-120">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="76d9a-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d9a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76d9a-121">See Also</span></span>  
 [<span data-ttu-id="76d9a-122">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76d9a-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
