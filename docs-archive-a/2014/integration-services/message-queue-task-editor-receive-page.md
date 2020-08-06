---
title: Editor für den Task ' Nachrichten Warteschlange ' (Seite empfangen) Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727037"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="d0013-102">Editor für den Task 'Nachrichtenwarteschlange' (Seite Empfangen)</span><span class="sxs-lookup"><span data-stu-id="d0013-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="d0013-103">Auf der Seite **Empfangen** des Dialogfelds **Editor für den Task „Nachrichtenwarteschlange“** können Sie den Task „Nachrichtenwarteschlange“ konfigurieren, um MSMQ-Nachrichten ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing) zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="d0013-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="d0013-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="d0013-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0013-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d0013-105">Options</span></span>  
 <span data-ttu-id="d0013-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="d0013-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="d0013-107">Geben Sie an, ob die Nachricht aus der Warteschlange entfernt werden soll, nachdem sie empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0013-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="d0013-108">Standardmäßig ist dieser Wert auf `False` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d0013-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="d0013-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="d0013-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="d0013-110">Geben Sie an, ob der Task fehlschlägt und eine Fehlermeldung angezeigt wird, wenn die Zeit für die Nachricht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="d0013-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="d0013-111">Der Standardwert lautet `False`.</span><span class="sxs-lookup"><span data-stu-id="d0013-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="d0013-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="d0013-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="d0013-113">Wenn eine Fehlermeldung beim Fehlschlagen des Tasks angezeigt werden soll, geben Sie hier die Wartezeit vor dem Anzeigen der Timeoutmeldung in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="d0013-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="d0013-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="d0013-114">**MessageType**</span></span>  
 <span data-ttu-id="d0013-115">Wählen Sie den Nachrichtentyp aus.</span><span class="sxs-lookup"><span data-stu-id="d0013-115">Select the message type.</span></span> <span data-ttu-id="d0013-116">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="d0013-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d0013-117">Wert</span><span class="sxs-lookup"><span data-stu-id="d0013-117">Value</span></span>|<span data-ttu-id="d0013-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0013-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0013-119">**Data file message**</span><span class="sxs-lookup"><span data-stu-id="d0013-119">**Data file message**</span></span>|<span data-ttu-id="d0013-120">Die Nachricht wird in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0013-120">The message is stored in a file.</span></span> <span data-ttu-id="d0013-121">Bei Auswahl dieses Wertes wird die dynamische Option **DataFileMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="d0013-122">**Variable message**</span><span class="sxs-lookup"><span data-stu-id="d0013-122">**Variable message**</span></span>|<span data-ttu-id="d0013-123">Die Nachricht wird in einer Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0013-123">The message is stored in a variable.</span></span> <span data-ttu-id="d0013-124">Bei Auswahl dieses Wertes wird die dynamische Option **VariableMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="d0013-125">**String message**</span><span class="sxs-lookup"><span data-stu-id="d0013-125">**String message**</span></span>|<span data-ttu-id="d0013-126">Die Nachricht wird im Task 'Nachrichtenwarteschlange' gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0013-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="d0013-127">Bei Auswahl dieses Wertes wird die dynamische Option **StringMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="d0013-128">**String message to variable**</span><span class="sxs-lookup"><span data-stu-id="d0013-128">**String message to variable**</span></span>|<span data-ttu-id="d0013-129">Die Nachricht wurde in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0013-129">The message</span></span><br /><br /> <span data-ttu-id="d0013-130">Bei Auswahl dieses Wertes wird die dynamische Option **StringMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="d0013-131">MessageType (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="d0013-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="d0013-132">MessageType = Data file message</span><span class="sxs-lookup"><span data-stu-id="d0013-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="d0013-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="d0013-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="d0013-134">Geben Sie den Pfad der zu verwendenden Datei an, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , um nach der Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d0013-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="d0013-135">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="d0013-135">**Overwrite**</span></span>  
 <span data-ttu-id="d0013-136">Geben Sie an, dass die Daten in einer vorhandenen Datei überschrieben werden sollen, wenn der Inhalt einer Datendateinachricht gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d0013-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="d0013-137">Der Standardwert lautet `False`.</span><span class="sxs-lookup"><span data-stu-id="d0013-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="d0013-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="d0013-138">**Filter**</span></span>  
 <span data-ttu-id="d0013-139">Geben Sie an, ob auf die Nachricht ein Filter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0013-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="d0013-140">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="d0013-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d0013-141">Wert</span><span class="sxs-lookup"><span data-stu-id="d0013-141">Value</span></span>|<span data-ttu-id="d0013-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0013-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0013-143">**Kein Filter**</span><span class="sxs-lookup"><span data-stu-id="d0013-143">**No filter**</span></span>|<span data-ttu-id="d0013-144">Der Task filtert keine Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d0013-144">The task does not filter messages.</span></span> <span data-ttu-id="d0013-145">Wenn Sie diesen Wert auswählen, wird die dynamische Option **IdentifierReadOnly**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="d0013-146">**Vom Paket**</span><span class="sxs-lookup"><span data-stu-id="d0013-146">**From package**</span></span>|<span data-ttu-id="d0013-147">Der Task empfängt nur Nachrichten von dem angegebenen Paket.</span><span class="sxs-lookup"><span data-stu-id="d0013-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="d0013-148">Wenn Sie diesen Wert auswählen, wird die dynamische Option **Identifier**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="d0013-149">Filter (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="d0013-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="d0013-150">Filter = No filter</span><span class="sxs-lookup"><span data-stu-id="d0013-150">Filter = No filter</span></span>  
 <span data-ttu-id="d0013-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d0013-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="d0013-152">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="d0013-152">This option is read-only.</span></span> <span data-ttu-id="d0013-153">Sie kann leer sein oder die GUID eines Pakets enthalten, wenn die Eigenschaft Filter vorher festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0013-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="d0013-154">Filter = From package</span><span class="sxs-lookup"><span data-stu-id="d0013-154">Filter = From package</span></span>  
 <span data-ttu-id="d0013-155">**Bezeichner**</span><span class="sxs-lookup"><span data-stu-id="d0013-155">**Identifier**</span></span>  
 <span data-ttu-id="d0013-156">Wenn Sie einen Filter anwenden möchten, geben Sie den eindeutigen Bezeichner des Pakets ein, aus dem die Nachrichten empfangen werden können, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , und geben Sie das Paket an.</span><span class="sxs-lookup"><span data-stu-id="d0013-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="d0013-157">**Verwandte Themen:** [Paket auswählen](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="d0013-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="d0013-158">MessageType = Variable message</span><span class="sxs-lookup"><span data-stu-id="d0013-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="d0013-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="d0013-159">**Filter**</span></span>  
 <span data-ttu-id="d0013-160">Geben Sie an, ob auf Nachrichten ein Filter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0013-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="d0013-161">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="d0013-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d0013-162">Wert</span><span class="sxs-lookup"><span data-stu-id="d0013-162">Value</span></span>|<span data-ttu-id="d0013-163">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0013-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0013-164">**Kein Filter**</span><span class="sxs-lookup"><span data-stu-id="d0013-164">**No filter**</span></span>|<span data-ttu-id="d0013-165">Der Task filtert keine Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d0013-165">The task does not filter messages.</span></span> <span data-ttu-id="d0013-166">Wenn Sie diesen Wert auswählen, wird die dynamische Option **IdentifierReadOnly**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="d0013-167">**Vom Paket**</span><span class="sxs-lookup"><span data-stu-id="d0013-167">**From package**</span></span>|<span data-ttu-id="d0013-168">Der Task empfängt nur Nachrichten von dem angegebenen Paket.</span><span class="sxs-lookup"><span data-stu-id="d0013-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="d0013-169">Wenn Sie diesen Wert auswählen, wird die dynamische Option **Identifier**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0013-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="d0013-170">**Variable**</span><span class="sxs-lookup"><span data-stu-id="d0013-170">**Variable**</span></span>  
 <span data-ttu-id="d0013-171">Geben Sie den Variablennamen ein, oder klicken Sie auf \<**New variable...**>, und konfigurieren Sie dann eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="d0013-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="d0013-172">**Verwandte Themen:** [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="d0013-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="d0013-173">Filter (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="d0013-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="d0013-174">Filter = No filter</span><span class="sxs-lookup"><span data-stu-id="d0013-174">Filter = No filter</span></span>  
 <span data-ttu-id="d0013-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d0013-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="d0013-176">Diese Option ist leer.</span><span class="sxs-lookup"><span data-stu-id="d0013-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="d0013-177">Filter = From package</span><span class="sxs-lookup"><span data-stu-id="d0013-177">Filter = From package</span></span>  
 <span data-ttu-id="d0013-178">**Bezeichner**</span><span class="sxs-lookup"><span data-stu-id="d0013-178">**Identifier**</span></span>  
 <span data-ttu-id="d0013-179">Wenn Sie einen Filter anwenden möchten, geben Sie den eindeutigen Bezeichner des Pakets ein, aus dem die Nachrichten empfangen werden können, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , und geben Sie das Paket an.</span><span class="sxs-lookup"><span data-stu-id="d0013-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="d0013-180">**Verwandte Themen:** [Paket auswählen](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="d0013-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="d0013-181">MessageType = Zeichenfolgennachricht</span><span class="sxs-lookup"><span data-stu-id="d0013-181">MessageType = String message</span></span>  
 <span data-ttu-id="d0013-182">**Vergleichen**</span><span class="sxs-lookup"><span data-stu-id="d0013-182">**Compare**</span></span>  
 <span data-ttu-id="d0013-183">Geben Sie an, ob auf Nachrichten ein Filter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0013-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="d0013-184">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="d0013-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d0013-185">Wert</span><span class="sxs-lookup"><span data-stu-id="d0013-185">Value</span></span>|<span data-ttu-id="d0013-186">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0013-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0013-187">**None**</span><span class="sxs-lookup"><span data-stu-id="d0013-187">**None**</span></span>|<span data-ttu-id="d0013-188">Die Nachrichten werden nicht verglichen.</span><span class="sxs-lookup"><span data-stu-id="d0013-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="d0013-189">**Genaue Übereinstimmung**</span><span class="sxs-lookup"><span data-stu-id="d0013-189">**Exact match**</span></span>|<span data-ttu-id="d0013-190">Die Nachrichten müssen genau mit der Zeichenfolge in der Option **CompareString** übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d0013-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="d0013-191">**Groß-/Kleinschreibung ignorieren**</span><span class="sxs-lookup"><span data-stu-id="d0013-191">**Ignore case**</span></span>|<span data-ttu-id="d0013-192">Die Nachricht muss mit der Zeichenfolge in der Option **CompareString** übereinstimmen, aber beim Vergleichen wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="d0013-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="d0013-193">**Mit Inhalt**</span><span class="sxs-lookup"><span data-stu-id="d0013-193">**Containing**</span></span>|<span data-ttu-id="d0013-194">Die Nachrichten müssen die Zeichenfolge in der Option **CompareString** enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0013-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="d0013-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="d0013-195">**CompareString**</span></span>  
 <span data-ttu-id="d0013-196">Geben Sie hier die Zeichenfolge an, mit der die Nachricht verglichen wird, wenn die Option **Vergleichen** nicht auf **Keine**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d0013-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="d0013-197">MessageType = String message to variable</span><span class="sxs-lookup"><span data-stu-id="d0013-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="d0013-198">**Vergleichen**</span><span class="sxs-lookup"><span data-stu-id="d0013-198">**Compare**</span></span>  
 <span data-ttu-id="d0013-199">Geben Sie an, ob auf Nachrichten ein Filter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0013-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="d0013-200">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="d0013-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d0013-201">Wert</span><span class="sxs-lookup"><span data-stu-id="d0013-201">Value</span></span>|<span data-ttu-id="d0013-202">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0013-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0013-203">**None**</span><span class="sxs-lookup"><span data-stu-id="d0013-203">**None**</span></span>|<span data-ttu-id="d0013-204">Die Nachrichten werden nicht verglichen.</span><span class="sxs-lookup"><span data-stu-id="d0013-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="d0013-205">**Genaue Übereinstimmung**</span><span class="sxs-lookup"><span data-stu-id="d0013-205">**Exact match**</span></span>|<span data-ttu-id="d0013-206">Die Nachricht muss genau mit der Zeichenfolge in der Option **CompareString** übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d0013-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="d0013-207">**Groß-/Kleinschreibung ignorieren**</span><span class="sxs-lookup"><span data-stu-id="d0013-207">**Ignore case**</span></span>|<span data-ttu-id="d0013-208">Die Nachricht muss mit der Zeichenfolge in der Option **CompareString** übereinstimmen, aber beim Vergleichen wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="d0013-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="d0013-209">**Mit Inhalt**</span><span class="sxs-lookup"><span data-stu-id="d0013-209">**Containing**</span></span>|<span data-ttu-id="d0013-210">Die Nachricht muss die Zeichenfolge in der Option **CompareString** enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0013-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="d0013-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="d0013-211">**CompareString**</span></span>  
 <span data-ttu-id="d0013-212">Geben Sie hier die Zeichenfolge an, mit der die Nachricht verglichen wird, wenn die Option **Vergleichen** nicht auf **Keine**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d0013-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="d0013-213">**Variable**</span><span class="sxs-lookup"><span data-stu-id="d0013-213">**Variable**</span></span>  
 <span data-ttu-id="d0013-214">Geben Sie den Namen der Variablen ein, die die empfangene Nachricht enthalten soll, oder klicken Sie auf \<**New variable...**>, und konfigurieren Sie dann eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="d0013-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="d0013-215">**Verwandte Themen:** [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="d0013-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0013-216">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0013-216">See Also</span></span>  
 <span data-ttu-id="d0013-217">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d0013-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d0013-218">[Editor für den Task Nachrichten Warteschlange &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d0013-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d0013-219">[Editor für den Task Nachrichten Warteschlange &#40;&#41;Seite senden](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0013-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="d0013-220">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0013-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="d0013-221">Nachrichtenwarteschlange (Task)</span><span class="sxs-lookup"><span data-stu-id="d0013-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
