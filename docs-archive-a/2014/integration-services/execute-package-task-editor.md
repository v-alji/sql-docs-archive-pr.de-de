---
title: Editor für den Task Paket ausführen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618793"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="1f26f-102">Editor für den Task 'Paket ausführen'</span><span class="sxs-lookup"><span data-stu-id="1f26f-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="1f26f-103">Mit dem Editor für den Task "Paket ausführen" können Sie Task "Paket ausführen" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f26f-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="1f26f-104">Der Task Paket ausführen erweitert die Unternehmensfunktionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , indem Paketen das Ausführen anderer Pakete als Teil eines Workflows ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="1f26f-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="1f26f-105">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="1f26f-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="1f26f-106">Öffnen des Editors für den Task "Paket ausführen"</span><span class="sxs-lookup"><span data-stu-id="1f26f-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="1f26f-107">Festlegen der Optionen auf der Seite „Allgemein“</span><span class="sxs-lookup"><span data-stu-id="1f26f-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="1f26f-108">Festlegen der Optionen auf der Seite "Paket"</span><span class="sxs-lookup"><span data-stu-id="1f26f-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="1f26f-109">Festlegen der Optionen auf der Seite "Parameterbindungen"</span><span class="sxs-lookup"><span data-stu-id="1f26f-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="1f26f-110">Öffnen des Editors für den Task "Paket ausführen"</span><span class="sxs-lookup"><span data-stu-id="1f26f-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="1f26f-111">Öffnen Sie in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ein [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] -Projekt, das einen Task „Paket ausführen“ enthält.</span><span class="sxs-lookup"><span data-stu-id="1f26f-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="1f26f-112">Klicken Sie im SSIS-Designer mit der rechten Maustaste auf den Task, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1f26f-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="1f26f-113">Festlegen der Optionen auf der Seite „Allgemein“</span><span class="sxs-lookup"><span data-stu-id="1f26f-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="1f26f-114">**Name**</span><span class="sxs-lookup"><span data-stu-id="1f26f-114">**Name**</span></span>  
 <span data-ttu-id="1f26f-115">Geben Sie einen eindeutigen Namen für den Task "Paket ausführen" an.</span><span class="sxs-lookup"><span data-stu-id="1f26f-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="1f26f-116">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f26f-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f26f-117">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="1f26f-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="1f26f-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f26f-118">**Description**</span></span>  
 <span data-ttu-id="1f26f-119">Geben Sie eine Beschreibung des Tasks "Paket ausführen" ein.</span><span class="sxs-lookup"><span data-stu-id="1f26f-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="1f26f-120">Festlegen der Optionen auf der Seite "Paket"</span><span class="sxs-lookup"><span data-stu-id="1f26f-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="1f26f-121">**ReferenceType**</span><span class="sxs-lookup"><span data-stu-id="1f26f-121">**ReferenceType**</span></span>  
 <span data-ttu-id="1f26f-122">Wählen Sie **Projektverweis** für untergeordnete Pakete im Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="1f26f-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="1f26f-123">Wählen Sie **Externer Verweis** für untergeordnete Pakete aus, die sich außerhalb des Pakets befinden.</span><span class="sxs-lookup"><span data-stu-id="1f26f-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f26f-124">Die Option **ReferenceType** ist schreibgeschützt und auf **Externer Verweis** festgelegt, wenn das Projekt, das das Paket enthält, nicht in das Projektbereitstellungsmodell konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1f26f-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="1f26f-125">Weitere Informationen zur Konvertierung finden Sie unter [Bereitstellen von Projekten auf dem Integration Services-Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f26f-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="1f26f-126">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="1f26f-126">**Password**</span></span>  
 <span data-ttu-id="1f26f-127">Wenn das untergeordnete Paket kennwortgeschützt ist, stellen Sie das Kennwort für das untergeordnete Paket bereit, oder klicken Sie auf die Schaltfläche mit den drei Auslassungspunkten (...), und erstellen Sie ein neues Kennwort für das untergeordnete Paket.</span><span class="sxs-lookup"><span data-stu-id="1f26f-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="1f26f-128">Geben Sie an, ob das untergeordnete Paket im Prozess des übergeordneten Pakets oder in einem separaten Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f26f-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="1f26f-129">Standardmäßig ist die executeouesfprocess-Eigenschaft des Tasks "Paket ausführen" auf festgelegt `False` , und das untergeordnete Paket wird im selben Prozess wie das übergeordnete Paket ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f26f-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="1f26f-130">Wenn Sie diese Eigenschaft auf `true` festlegen, wird das untergeordnete Paket in einem separaten Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f26f-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="1f26f-131">Dadurch kann sich der Start des untergeordneten Pakets verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="1f26f-132">Wenn die Eigenschaft auf `true` festgelegt wurde, ist außerdem das Debuggen des Pakets in einer Installation, die nur die Tools enthält, nicht möglich; das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Produkt muss von Ihnen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f26f-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="1f26f-133">Weitere Informationen finden Sie unter [Installieren von Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="1f26f-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="1f26f-134">Dynamische Optionen für ReferenceType</span><span class="sxs-lookup"><span data-stu-id="1f26f-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="1f26f-135">ReferenceType = Externer Verweis</span><span class="sxs-lookup"><span data-stu-id="1f26f-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="1f26f-136">**Location**</span><span class="sxs-lookup"><span data-stu-id="1f26f-136">**Location**</span></span>  
 <span data-ttu-id="1f26f-137">Wählen Sie den Speicherort des untergeordneten Pakets aus.</span><span class="sxs-lookup"><span data-stu-id="1f26f-137">Select the location of the child package.</span></span> <span data-ttu-id="1f26f-138">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1f26f-139">Wert</span><span class="sxs-lookup"><span data-stu-id="1f26f-139">Value</span></span>|<span data-ttu-id="1f26f-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f26f-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1f26f-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1f26f-141">**SQL Server**</span></span>|<span data-ttu-id="1f26f-142">Legt den Speicherort als Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]fest.</span><span class="sxs-lookup"><span data-stu-id="1f26f-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="1f26f-143">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="1f26f-143">**File system**</span></span>|<span data-ttu-id="1f26f-144">Legen Sie als Speicherort das Dateisystem fest.</span><span class="sxs-lookup"><span data-stu-id="1f26f-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="1f26f-145">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1f26f-145">**Connection**</span></span>  
 <span data-ttu-id="1f26f-146">Wählen Sie den Typ des Speicherorts für das untergeordnete Paket aus.</span><span class="sxs-lookup"><span data-stu-id="1f26f-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="1f26f-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1f26f-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="1f26f-148">Zeigt den Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="1f26f-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="1f26f-149">ReferenceType = Projektverweis</span><span class="sxs-lookup"><span data-stu-id="1f26f-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="1f26f-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="1f26f-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="1f26f-151">Wählen Sie ein im Projekt enthaltenes Paket als untergeordnetes Paket aus.</span><span class="sxs-lookup"><span data-stu-id="1f26f-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="1f26f-152">Dynamische Optionen für Location</span><span class="sxs-lookup"><span data-stu-id="1f26f-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="1f26f-153">Location = SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f26f-153">Location = SQL Server</span></span>  
 <span data-ttu-id="1f26f-154">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1f26f-154">**Connection**</span></span>  
 <span data-ttu-id="1f26f-155">Wählen Sie einen OLE DB-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="1f26f-156">**Verwandte Themen:** [OLE DB-Verbindungs-Manager](connection-manager/ole-db-connection-manager.md), [OLE DB-Verbindungs-Manager konfigurieren](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="1f26f-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="1f26f-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="1f26f-157">**PackageName**</span></span>  
 <span data-ttu-id="1f26f-158">Geben Sie den Namen des untergeordneten Pakets an, oder klicken Sie auf die Schaltfläche mit den drei Auslassungspunkten (...), um nach dem Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="1f26f-159">Location = File system</span><span class="sxs-lookup"><span data-stu-id="1f26f-159">Location = File system</span></span>  
 <span data-ttu-id="1f26f-160">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1f26f-160">**Connection**</span></span>  
 <span data-ttu-id="1f26f-161">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="1f26f-162">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="1f26f-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="1f26f-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1f26f-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="1f26f-164">Zeigt den Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="1f26f-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="1f26f-165">Festlegen der Optionen auf der Seite "Parameterbindungen"</span><span class="sxs-lookup"><span data-stu-id="1f26f-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="1f26f-166">Sie können Werte aus dem übergeordneten Paket oder dem Projekt an das untergeordnete Paket übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f26f-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="1f26f-167">Das Projekt muss das Projektbereitstellungsmodell verwenden, und das untergeordnete Paket muss im gleichen Projekt enthalten sein wie das übergeordnete Paket.</span><span class="sxs-lookup"><span data-stu-id="1f26f-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="1f26f-168">Weitere Informationen zum Konvertieren eines Projekts in das Projektbereitstellungsmodell finden Sie unter [Bereitstellen von Projekten auf dem Integration Services-Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f26f-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="1f26f-169">**Untergeordneter Paketparameter**</span><span class="sxs-lookup"><span data-stu-id="1f26f-169">**Child package parameter**</span></span>  
 <span data-ttu-id="1f26f-170">Geben Sie einen Namen für den untergeordneten Paketparameter ein, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="1f26f-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="1f26f-171">**Bindungsparameter oder Variable**</span><span class="sxs-lookup"><span data-stu-id="1f26f-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="1f26f-172">Wählen Sie den Parameter oder die Variable mit dem Wert aus, den Sie an das untergeordnete Paket übergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="1f26f-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="1f26f-173">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="1f26f-173">**Add**</span></span>  
 <span data-ttu-id="1f26f-174">Klicken Sie, um einen Parameter oder eine Variable einem untergeordneten Paketparameter zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="1f26f-175">**Remove**</span><span class="sxs-lookup"><span data-stu-id="1f26f-175">**Remove**</span></span>  
 <span data-ttu-id="1f26f-176">Klicken Sie, um eine Zuordnung zwischen einem Parameter oder einer Variable und einem untergeordneten Paketparameter zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1f26f-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
