---
title: Editor für den FTP-Task (Seite Dateiübertragung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615446"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="0f07a-102">Editor für den FTP-Task (Seite Dateiübertragung)</span><span class="sxs-lookup"><span data-stu-id="0f07a-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="0f07a-103">Mithilfe der Seite **Dateiübertragung** des Dialogfelds **Editor für den FTP-Task** können Sie den FTP-Vorgang konfigurieren, der durch den Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0f07a-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="0f07a-104">Informationen zu diesem Task finden Sie unter [FTP-Task](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="0f07a-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0f07a-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0f07a-105">Options</span></span>  
 <span data-ttu-id="0f07a-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="0f07a-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="0f07a-107">Geben Sie an, ob der Remotepfad in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0f07a-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="0f07a-108">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0f07a-109">Wert</span><span class="sxs-lookup"><span data-stu-id="0f07a-109">Value</span></span>|<span data-ttu-id="0f07a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f07a-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f07a-111">**Wahr**</span><span class="sxs-lookup"><span data-stu-id="0f07a-111">**True**</span></span>|<span data-ttu-id="0f07a-112">Der Zielpfad ist in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0f07a-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="0f07a-113">Wenn Sie diesen Wert auswählen, wird die dynamische Option **RemoteVariable**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="0f07a-114">**False**</span><span class="sxs-lookup"><span data-stu-id="0f07a-114">**False**</span></span>|<span data-ttu-id="0f07a-115">Der Zielpfad wird in einem Dateiverbindungs-Manager angegeben.</span><span class="sxs-lookup"><span data-stu-id="0f07a-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="0f07a-116">Wenn Sie diesen Wert auswählen, wird die dynamische Option **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="0f07a-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="0f07a-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="0f07a-118">Geben Sie an, ob eine Datei am Ziel überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f07a-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="0f07a-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="0f07a-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="0f07a-120">Geben Sie an, ob der lokale Pfad in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0f07a-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="0f07a-121">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0f07a-122">Wert</span><span class="sxs-lookup"><span data-stu-id="0f07a-122">Value</span></span>|<span data-ttu-id="0f07a-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f07a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f07a-124">**Wahr**</span><span class="sxs-lookup"><span data-stu-id="0f07a-124">**True**</span></span>|<span data-ttu-id="0f07a-125">Der Zielpfad ist in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0f07a-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="0f07a-126">Wenn Sie diesen Wert auswählen, wird die dynamische Option **LocalVariable**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="0f07a-127">**False**</span><span class="sxs-lookup"><span data-stu-id="0f07a-127">**False**</span></span>|<span data-ttu-id="0f07a-128">Der Zielpfad wird in einem Dateiverbindungs-Manager angegeben.</span><span class="sxs-lookup"><span data-stu-id="0f07a-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="0f07a-129">Wenn Sie diesen Wert auswählen, wird die dynamische Option **LocalPath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="0f07a-130">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="0f07a-130">**Operation**</span></span>  
 <span data-ttu-id="0f07a-131">Wählen Sie den auszuführenden FTP-Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="0f07a-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="0f07a-132">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0f07a-133">Wert</span><span class="sxs-lookup"><span data-stu-id="0f07a-133">Value</span></span>|<span data-ttu-id="0f07a-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f07a-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f07a-135">**Dateien senden**</span><span class="sxs-lookup"><span data-stu-id="0f07a-135">**Send files**</span></span>|<span data-ttu-id="0f07a-136">Senden Sie Dateien.</span><span class="sxs-lookup"><span data-stu-id="0f07a-136">Send files.</span></span> <span data-ttu-id="0f07a-137">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable**, **LocalPathRemoteVariable** und **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="0f07a-138">**Dateien empfangen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-138">**Receive files**</span></span>|<span data-ttu-id="0f07a-139">Empfangen Sie Dateien.</span><span class="sxs-lookup"><span data-stu-id="0f07a-139">Receive files.</span></span> <span data-ttu-id="0f07a-140">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable**, **LocalPathRemoteVariable** und **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="0f07a-141">**Lokales Verzeichnis erstellen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-141">**Create local directory**</span></span>|<span data-ttu-id="0f07a-142">Erstellen Sie ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f07a-142">Create a local directory.</span></span> <span data-ttu-id="0f07a-143">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="0f07a-144">**Remoteverzeichnis erstellen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-144">**Create remote directory**</span></span>|<span data-ttu-id="0f07a-145">Erstellen Sie ein Remoteverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f07a-145">Create a remote directory.</span></span> <span data-ttu-id="0f07a-146">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="0f07a-147">**Lokales Verzeichnis entfernen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-147">**Remove local directory**</span></span>|<span data-ttu-id="0f07a-148">Entfernen Sie ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f07a-148">Removes a local directory.</span></span> <span data-ttu-id="0f07a-149">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="0f07a-150">**Remoteverzeichnis entfernen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-150">**Remove remote directory**</span></span>|<span data-ttu-id="0f07a-151">Entfernen Sie ein Remoteverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f07a-151">Remove a remote directory.</span></span> <span data-ttu-id="0f07a-152">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="0f07a-153">**Lokale Dateien löschen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-153">**Delete local files**</span></span>|<span data-ttu-id="0f07a-154">Löschen Sie lokale Dateien.</span><span class="sxs-lookup"><span data-stu-id="0f07a-154">Delete local files.</span></span> <span data-ttu-id="0f07a-155">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="0f07a-156">**Remotedateien löschen**</span><span class="sxs-lookup"><span data-stu-id="0f07a-156">**Delete remote files**</span></span>|<span data-ttu-id="0f07a-157">Löschen Sie Remotedateien.</span><span class="sxs-lookup"><span data-stu-id="0f07a-157">Delete remote files.</span></span> <span data-ttu-id="0f07a-158">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f07a-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="0f07a-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="0f07a-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="0f07a-160">Geben Sie an, ob die auf und von einem Remote-FTP-Server übertragenen Dateien im ASCII-Modus übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="0f07a-161">IsRemotePathVariable (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="0f07a-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="0f07a-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="0f07a-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="0f07a-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="0f07a-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="0f07a-164">Wählen Sie eine vorhandene benutzerdefinierte Variable aus, oder klicken Sie auf \<**New variable...**>, um eine benutzerdefinierte Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="0f07a-165">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), Hinzufügen von Variablen</span><span class="sxs-lookup"><span data-stu-id="0f07a-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="0f07a-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="0f07a-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="0f07a-167">**RemotePath**</span><span class="sxs-lookup"><span data-stu-id="0f07a-167">**RemotePath**</span></span>  
 <span data-ttu-id="0f07a-168">Wählen Sie einen vorhandenen FTP-Verbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="0f07a-169">**Verwandte Themen:** [FTP-Verbindungs-Manager](connection-manager/ftp-connection-manager.md), [FTP-Verbindungs-Manager-Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="0f07a-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="0f07a-170">IsLocalPathVariable (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="0f07a-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="0f07a-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="0f07a-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="0f07a-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="0f07a-172">**LocalVariable**</span></span>  
 <span data-ttu-id="0f07a-173">Wählen Sie eine vorhandene benutzerdefinierte Variable aus, oder klicken Sie auf \<**New variable...**>, um eine Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="0f07a-174">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), Hinzufügen von Variablen</span><span class="sxs-lookup"><span data-stu-id="0f07a-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="0f07a-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="0f07a-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="0f07a-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="0f07a-176">**LocalPath**</span></span>  
 <span data-ttu-id="0f07a-177">Wählen Sie einen vorhandenen Dateiverbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f07a-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="0f07a-178">**Verwandte Themen:**[Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="0f07a-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f07a-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f07a-179">See Also</span></span>  
 <span data-ttu-id="0f07a-180">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0f07a-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0f07a-181">[Editor für den FTP-Task &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0f07a-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="0f07a-182">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0f07a-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
