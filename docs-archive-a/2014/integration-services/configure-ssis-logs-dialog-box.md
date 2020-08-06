---
title: Dialog Feld ' SSIS-Protokolle konfigurieren ' | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616632"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="5a67d-102">SSIS-Protokolle konfigurieren (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="5a67d-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="5a67d-103">Verwenden Sie das Dialogfeld **SSIS-Protokolle konfigurieren** , um Protokollierungsoptionen für ein Paket zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="5a67d-104">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="5a67d-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="5a67d-105">Öffnen Sie das Dialogfeld "SSIS-Protokolle konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="5a67d-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="5a67d-106">Konfigurieren Sie die Optionen im Bereich "Container".</span><span class="sxs-lookup"><span data-stu-id="5a67d-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="5a67d-107">Konfigurieren Sie die Optionen auf der Registerkarte "Anbieter und Protokolle".</span><span class="sxs-lookup"><span data-stu-id="5a67d-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="5a67d-108">Konfigurieren Sie die Optionen auf der Registerkarte "Details".</span><span class="sxs-lookup"><span data-stu-id="5a67d-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="5a67d-109">Öffnen Sie das Dialogfeld "SSIS-Protokolle konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="5a67d-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="5a67d-110">**So öffnen Sie das Dialogfeld "SSIS-Protokolle konfigurieren"**</span><span class="sxs-lookup"><span data-stu-id="5a67d-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="5a67d-111">Klicken Sie in [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf **Protokollierung** im **SSIS** -Menü.</span><span class="sxs-lookup"><span data-stu-id="5a67d-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="5a67d-112">Konfigurieren Sie die Optionen im Bereich "Container".</span><span class="sxs-lookup"><span data-stu-id="5a67d-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="5a67d-113">Mithilfe des **Container** -Bereichs des Dialogfelds **SSIS-Protokolle konfigurieren** können Sie das Paket und seine Container für das Protokollieren aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5a67d-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5a67d-114">Options</span></span>  
 <span data-ttu-id="5a67d-115">**Container**</span><span class="sxs-lookup"><span data-stu-id="5a67d-115">**Containers**</span></span>  
 <span data-ttu-id="5a67d-116">Aktivieren Sie die Kontrollkästchen in der hierarchischen Sicht, um das Paket und seine Container für die Protokollierung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="5a67d-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="5a67d-117">Falls diese Option deaktiviert ist, ist der Container nicht für die Protokollierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5a67d-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="5a67d-118">Wählen Sie diese Option aus, um die Protokollierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="5a67d-119">Falls die Option abgeblendet ist, verwendet der Container die Protokollierungsoptionen des ihm übergeordneten Containers.</span><span class="sxs-lookup"><span data-stu-id="5a67d-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="5a67d-120">Diese Option steht für das Paket nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5a67d-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="5a67d-121">Wenn diese Option aktiviert ist, definiert der Container seine eigenen Protokollierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="5a67d-122">Falls ein Container abgeblendet ist und Sie Protokollierungsoptionen für den Container festlegen möchten, klicken Sie zweimal auf das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="5a67d-123">Durch das erste Klicken wird das Kontrollkästchen deaktiviert, durch das zweite Klicken wird es ausgewählt, und Sie können somit die zu verwendenden Protokollanbieter und die zu protokollierenden Informationen auswählen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="5a67d-124">Konfigurieren Sie die Optionen auf der Registerkarte "Anbieter und Protokolle".</span><span class="sxs-lookup"><span data-stu-id="5a67d-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="5a67d-125">Verwenden Sie die Registerkarte **Anbieter und Protokolle** des Dialogfelds **SSIS-Protokolle konfigurieren** , um Protokolle für das Aufzeichnen von Laufzeitereignissen zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5a67d-126">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5a67d-126">Options</span></span>  
 <span data-ttu-id="5a67d-127">**Anbietertyp**</span><span class="sxs-lookup"><span data-stu-id="5a67d-127">**Provider type**</span></span>  
 <span data-ttu-id="5a67d-128">Wählen Sie einen Protokollanbietertyp aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5a67d-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="5a67d-129">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="5a67d-129">**Add**</span></span>  
 <span data-ttu-id="5a67d-130">Fügen Sie der Auflistung der Protokollanbieter des Pakets ein Protokoll des angegebenen Typs hinzu.</span><span class="sxs-lookup"><span data-stu-id="5a67d-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="5a67d-131">**Name**</span><span class="sxs-lookup"><span data-stu-id="5a67d-131">**Name**</span></span>  
 <span data-ttu-id="5a67d-132">Aktivieren oder deaktivieren Sie Protokolle für Container und Tasks, die Sie im Bereich **Container** des Dialogfelds **SSIS-Protokolle konfigurieren** auswählen, indem Sie die Kontrollkästchen aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="5a67d-133">Das Feld Name kann bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a67d-133">The name field is editable.</span></span> <span data-ttu-id="5a67d-134">Verwenden Sie den Standardnamen für den Anbieter, oder geben Sie einen eindeutigen, beschreibenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="5a67d-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="5a67d-135">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5a67d-135">**Description**</span></span>  
 <span data-ttu-id="5a67d-136">Das Feld Beschreibung kann bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a67d-136">The description field is editable.</span></span> <span data-ttu-id="5a67d-137">Klicken Sie in das Feld und ändern Sie die Standardbeschreibung des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="5a67d-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="5a67d-138">**Konfiguration**</span><span class="sxs-lookup"><span data-stu-id="5a67d-138">**Configuration**</span></span>  
 <span data-ttu-id="5a67d-139">Wählen Sie einen vorhandenen Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="5a67d-140">Abhängig vom Typ des Protokollanbieters können Sie einen OLE DB-Verbindungs-Manager oder einen Dateiverbindungs-Manager konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="5a67d-141">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Ereignisprotokollanbieter erfordert keine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="5a67d-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="5a67d-142">Verwandte Themen: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) , [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="5a67d-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="5a67d-143">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="5a67d-143">**Delete**</span></span>  
 <span data-ttu-id="5a67d-144">Wählen Sie einen Protokollanbieter aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5a67d-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="5a67d-145">Konfigurieren Sie die Optionen auf der Registerkarte "Details".</span><span class="sxs-lookup"><span data-stu-id="5a67d-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="5a67d-146">Auf der Registerkarte **Details** des Dialogfelds **SSIS-Protokolle konfigurieren** können Sie die Ereignisse für das Protokollieren sowie die zu protokollierenden Informationsdetails aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a67d-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="5a67d-147">Die Informationen, die Sie auswählen, gelten für alle Protokollanbieter im Paket.</span><span class="sxs-lookup"><span data-stu-id="5a67d-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="5a67d-148">Sie können z. B. nicht einige Informationen in die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz und andere Informationen in eine Textdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="5a67d-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5a67d-149">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5a67d-149">Options</span></span>  
 <span data-ttu-id="5a67d-150">**Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="5a67d-150">**Events**</span></span>  
 <span data-ttu-id="5a67d-151">Aktivieren oder Deaktivieren von Ereignissen für die Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="5a67d-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="5a67d-152">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5a67d-152">**Description**</span></span>  
 <span data-ttu-id="5a67d-153">Anzeigen einer Beschreibung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5a67d-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="5a67d-154">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="5a67d-154">**Advanced**</span></span>  
 <span data-ttu-id="5a67d-155">Auswählen oder Löschen zu protokollierender Ereignisse und Auswählen oder Löschen von Informationen, die für jedes Ereignis protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="5a67d-156">Klicken Sie auf **Standard** , um alle Protokollierungsdetails mit Ausnahme der Liste der Ereignisse auszublenden.</span><span class="sxs-lookup"><span data-stu-id="5a67d-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="5a67d-157">Die folgenden Informationen sind für die Protokollierung verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5a67d-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="5a67d-158">value</span><span class="sxs-lookup"><span data-stu-id="5a67d-158">Value</span></span>|<span data-ttu-id="5a67d-159">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a67d-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a67d-160">**Computer**</span><span class="sxs-lookup"><span data-stu-id="5a67d-160">**Computer**</span></span>|<span data-ttu-id="5a67d-161">Der Name des Computers, auf dem das protokollierte Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5a67d-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="5a67d-162">**Operator**</span><span class="sxs-lookup"><span data-stu-id="5a67d-162">**Operator**</span></span>|<span data-ttu-id="5a67d-163">Der Benutzername der Person, die das Paket gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="5a67d-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="5a67d-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="5a67d-164">**SourceName**</span></span>|<span data-ttu-id="5a67d-165">Der Name des Pakets, Containers oder Tasks, in dem das protokollierte Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5a67d-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="5a67d-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="5a67d-166">**SourceID**</span></span>|<span data-ttu-id="5a67d-167">GUID (Global Unique Identifier) des Pakets, Containers oder Tasks, in dem das protokollierte Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5a67d-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="5a67d-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="5a67d-168">**ExecutionID**</span></span>|<span data-ttu-id="5a67d-169">Der global eindeutige Bezeichner der Paketausführungsinstanz.</span><span class="sxs-lookup"><span data-stu-id="5a67d-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="5a67d-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="5a67d-170">**MessageText**</span></span>|<span data-ttu-id="5a67d-171">Eine dem Protokolleintrag zugeordnete Meldung.</span><span class="sxs-lookup"><span data-stu-id="5a67d-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="5a67d-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="5a67d-172">**DataBytes**</span></span>|<span data-ttu-id="5a67d-173">Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="5a67d-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="5a67d-174">**Grundlegend**</span><span class="sxs-lookup"><span data-stu-id="5a67d-174">**Basic**</span></span>  
 <span data-ttu-id="5a67d-175">Wählen Sie zu protokollierende Ereignisse aus, oder löschen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="5a67d-175">Select or clear events to log.</span></span> <span data-ttu-id="5a67d-176">Diese Option blendet alle Protokollierungsdetails mit Ausnahme der Liste der Ereignisse aus.</span><span class="sxs-lookup"><span data-stu-id="5a67d-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="5a67d-177">Wenn Sie ein Ereignis auswählen, werden standardmäßig alle Protokollierungsdetails für das Ereignis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5a67d-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="5a67d-178">Klicken Sie auf **Erweitert** , um alle Protokollierungsdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a67d-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="5a67d-179">**Load**</span><span class="sxs-lookup"><span data-stu-id="5a67d-179">**Load**</span></span>  
 <span data-ttu-id="5a67d-180">Geben Sie eine vorhandene XML-Datei an, die als Vorlage zum Festlegen der Protokollierungsoptionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a67d-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="5a67d-181">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="5a67d-181">**Save**</span></span>  
 <span data-ttu-id="5a67d-182">Speichern Sie Konfigurationsdetails als Vorlage in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="5a67d-182">Save configuration details as a template to an XML file.</span></span>  
  
  
