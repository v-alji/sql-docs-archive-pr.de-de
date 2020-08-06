---
title: Editor für den Task ' Nachrichten Warteschlange ' (Seite senden) Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727034"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="68673-102">Task 'Nachrichtenwarteschlange' (Seite Senden)</span><span class="sxs-lookup"><span data-stu-id="68673-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="68673-103">Im Dialogfeld **Editor für den Task „Nachrichtenwarteschlange“** können Sie auf der Seite **Senden** den Task „Nachrichtenwarteschlange“ so konfigurieren, dass Nachrichten von einem [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Paket gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="68673-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="68673-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="68673-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="68673-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="68673-105">Options</span></span>  
 <span data-ttu-id="68673-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="68673-106">**UseEncryption**</span></span>  
 <span data-ttu-id="68673-107">Geben Sie an, ob die Nachricht verschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="68673-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="68673-108">Der Standardwert lautet `False`.</span><span class="sxs-lookup"><span data-stu-id="68673-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="68673-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="68673-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="68673-110">Wenn Sie die Verschlüsselung verwenden möchten, müssen Sie den Namen des verwendeten Verschlüsselungsalgorithmus angeben.</span><span class="sxs-lookup"><span data-stu-id="68673-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="68673-111">Für den Task "Nachrichtenwarteschlange" können die Algorithmen RC2 und RC4 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68673-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="68673-112">Die Standardeinstellung lautet **RC2**.</span><span class="sxs-lookup"><span data-stu-id="68673-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68673-113">Der RC4-Algorithmus wird nur aus Gründen der Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68673-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="68673-114">Neues Material kann nur mit RC4 oder RC4_128 verschlüsselt werden, wenn die Datenbank den Kompatibilitätsgrad 90 oder 100 besitzt.</span><span class="sxs-lookup"><span data-stu-id="68673-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="68673-115">(Nicht empfohlen.) Verwenden Sie stattdessen einen neueren Algorithmus, z. B. einen der AES-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="68673-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="68673-116">In der aktuellen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]kann mit RC4 oder RC4_128 verschlüsseltes Material in jedem Kompatibilitätsgrad entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="68673-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="68673-117">Diese Verschlüsselungsalgorithmen werden von der Message Queuing-Technologie (auch bekannt als MSMQ) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68673-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="68673-118">Diese Verschlüsselungsalgorithmen werden inzwischen im Vergleich zu neueren Algorithmen, die von Message Queuing noch nicht unterstützt werden, beide als kryptografisch schwach betrachtet.</span><span class="sxs-lookup"><span data-stu-id="68673-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="68673-119">Daher sollten Sie Ihren Kryptografiebedarf sorgfältig überdenken, wenn Sie Nachrichten mithilfe des Tasks Nachrichtenwarteschlange senden.</span><span class="sxs-lookup"><span data-stu-id="68673-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="68673-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="68673-120">**MessageType**</span></span>  
 <span data-ttu-id="68673-121">Wählen Sie den Nachrichtentyp aus.</span><span class="sxs-lookup"><span data-stu-id="68673-121">Select the message type.</span></span> <span data-ttu-id="68673-122">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="68673-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="68673-123">Wert</span><span class="sxs-lookup"><span data-stu-id="68673-123">Value</span></span>|<span data-ttu-id="68673-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="68673-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68673-125">**Data file message**</span><span class="sxs-lookup"><span data-stu-id="68673-125">**Data file message**</span></span>|<span data-ttu-id="68673-126">Die Nachricht wird in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="68673-126">The message is stored in a file.</span></span> <span data-ttu-id="68673-127">Bei Auswahl dieses Wertes wird die dynamische Option **DataFileMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68673-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="68673-128">**Variable message**</span><span class="sxs-lookup"><span data-stu-id="68673-128">**Variable message**</span></span>|<span data-ttu-id="68673-129">Die Nachricht wird in einer Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="68673-129">The message is stored in a variable.</span></span> <span data-ttu-id="68673-130">Bei Auswahl dieses Wertes wird die dynamische Option **VariableMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68673-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="68673-131">**String message**</span><span class="sxs-lookup"><span data-stu-id="68673-131">**String message**</span></span>|<span data-ttu-id="68673-132">Die Nachricht wird im Task 'Nachrichtenwarteschlange' gespeichert.</span><span class="sxs-lookup"><span data-stu-id="68673-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="68673-133">Bei Auswahl dieses Wertes wird die dynamische Option **StringMessage**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68673-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="68673-134">MessageType (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="68673-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="68673-135">MessageType = Data file message</span><span class="sxs-lookup"><span data-stu-id="68673-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="68673-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="68673-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="68673-137">Geben Sie den Pfad der Datendatei an, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(…)** , um nach der Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="68673-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="68673-138">MessageType = Variable message</span><span class="sxs-lookup"><span data-stu-id="68673-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="68673-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="68673-139">**VariableMessage**</span></span>  
 <span data-ttu-id="68673-140">Geben Sie die Variablennamen ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(…)** , und wählen Sie dann die Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="68673-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="68673-141">Die Variablen werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="68673-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="68673-142">**Verwandte Themen:** Variablen auswählen</span><span class="sxs-lookup"><span data-stu-id="68673-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="68673-143">MessageType = Zeichenfolgennachricht</span><span class="sxs-lookup"><span data-stu-id="68673-143">MessageType = String message</span></span>  
 <span data-ttu-id="68673-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="68673-144">**StringMessage**</span></span>  
 <span data-ttu-id="68673-145">Geben Sie die Zeichenfolgennachricht ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(…)** , und geben Sie dann im Dialogfeld **Zeichenfolgennachricht eingeben** die Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="68673-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68673-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68673-146">See Also</span></span>  
 <span data-ttu-id="68673-147">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="68673-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="68673-148">[Editor für den Task Nachrichten Warteschlange &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="68673-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="68673-149">[Editor für den Task ' Nachrichten Warteschlange ' &#40;&#41;Seite](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="68673-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="68673-150">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68673-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
