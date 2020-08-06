---
title: Aktivieren der Paket Protokollierung in SQL Server Data Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618813"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="9308e-102">Aktivieren der Paketprotokollierung in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="9308e-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="9308e-103">In diesem Verfahren wird beschrieben, wie einem Paket Protokolle hinzugefügt werden, die Protokollierung auf Paketebene konfiguriert wird und die Protokollierungskonfiguration in eine XML-Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9308e-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="9308e-104">Sie können Protokolle nur auf der Paketebene hinzufügen, das Paket muss jedoch keine Protokollierung durchführen, um die Protokollierung in den Containern zu ermöglichen, die im Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9308e-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9308e-105">Wenn Sie das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen, überschreibt der Protokolliergrad, den Sie für die Paketausführung festgelegt haben, die Paketprotokollierung, die Sie mit [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9308e-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9308e-106">Die Container im Paket verwenden standardmäßig dieselbe Protokollierungskonfiguration wie der übergeordnete Container.</span><span class="sxs-lookup"><span data-stu-id="9308e-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="9308e-107">Weitere Informationen zum Festlegen der Protokollierungsoptionen für einzelne Container finden Sie unter [Konfigurieren der Protokollierung mithilfe einer gespeicherten Konfigurationsdatei](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="9308e-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="9308e-108">So aktivieren Sie die Protokollierung in einem Paket</span><span class="sxs-lookup"><span data-stu-id="9308e-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="9308e-109">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="9308e-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9308e-110">Klicken Sie im Menü **SSIS** auf **Protokollierung**.</span><span class="sxs-lookup"><span data-stu-id="9308e-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="9308e-111">Wählen Sie einen Protokollanbieter in der Liste **Anbietertyp** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9308e-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="9308e-112">Wählen Sie in der Spalte **Konfiguration** einen Verbindungs-Manager aus, oder klicken Sie auf **\<New connection>** , um einen neuen Verbindungs-Manager des entsprechenden Typs für den Protokollanbieter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9308e-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="9308e-113">Verwenden Sie je nach ausgewähltem Anbieter einen der folgenden Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9308e-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="9308e-114">Verwenden Sie für Textdateien einen Dateiverbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9308e-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="9308e-115">Weitere Informationen finden Sie unter [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="9308e-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="9308e-116">Verwenden Sie für [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]einen Dateiverbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9308e-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="9308e-117">Verwenden Sie für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]einen OLE DB-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9308e-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="9308e-118">Weitere Informationen finden Sie unter [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9308e-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="9308e-119">Führen Sie für das Windows-Ereignisprotokoll keine Aktion durch.</span><span class="sxs-lookup"><span data-stu-id="9308e-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="9308e-120">erstellt das Protokoll automatisch.</span><span class="sxs-lookup"><span data-stu-id="9308e-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="9308e-121">Verwenden Sie für XML-Dateien einen Dateiverbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9308e-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="9308e-122">Wiederholen Sie die Schritte 3 und 4 für jedes im Paket zu verwendende Protokoll.</span><span class="sxs-lookup"><span data-stu-id="9308e-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9308e-123">Ein Paket kann mehrere Protokolle pro Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="9308e-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="9308e-124">Aktivieren Sie wahlweise das Kontrollkästchen für das Paket, wählen Sie die für die Paketprotokollierung zu verwendenden Protokolle aus, und klicken Sie dann auf die Registerkarte **Details** .</span><span class="sxs-lookup"><span data-stu-id="9308e-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="9308e-125">Wählen Sie auf der Registerkarte **Details** die Option **Ereignisse** , um alle Protokolleinträge zu protokollieren, oder löschen Sie **Ereignisse** , um einzelne Ereignisse auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9308e-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="9308e-126">Klicken Sie wahlweise auf **Erweitert** , um die zu protokollierenden Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9308e-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9308e-127">Standardmäßig werden alle Informationen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9308e-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="9308e-128">Klicken Sie auf der Registerkarte **Details** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9308e-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="9308e-129">Das Dialogfeld **Speichern unter** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9308e-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="9308e-130">Suchen Sie den Ordner, in dem Sie die Protokollierungskonfiguration speichern möchten, geben Sie einen Dateinamen für die neue Protokollkonfiguration ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9308e-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="9308e-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9308e-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="9308e-132">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9308e-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9308e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9308e-133">See Also</span></span>  
 <span data-ttu-id="9308e-134">[Integration Services &#40;SSIS-&#41; Protokollierung](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="9308e-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="9308e-135">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9308e-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
