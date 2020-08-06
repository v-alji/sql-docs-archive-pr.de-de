---
title: Editor für den Task ' Mail senden ' (Seite e-Mail) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726086"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="6ca12-102">Editor für den Task 'Mail senden' (Seite E-Mail)</span><span class="sxs-lookup"><span data-stu-id="6ca12-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="6ca12-103">Auf der Seite **E-Mail** im Dialogfeld **Editor für den Task „Mail senden“** können Sie die Empfänger, den Nachrichtentyp und die Priorität einer Nachricht angeben.</span><span class="sxs-lookup"><span data-stu-id="6ca12-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="6ca12-104">Sie können der Nachricht auch Dateien anfügen.</span><span class="sxs-lookup"><span data-stu-id="6ca12-104">You can also attach files to the message.</span></span> <span data-ttu-id="6ca12-105">Bei dem Nachrichtentext kann es sich um eine bereitgestellte Zeichenfolge, eine Dateiverbindung mit einer Datei mit Text oder den Namen einer Variablen mit Text handeln.</span><span class="sxs-lookup"><span data-stu-id="6ca12-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="6ca12-106">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="6ca12-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ca12-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6ca12-107">Options</span></span>  
 <span data-ttu-id="6ca12-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="6ca12-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="6ca12-109">Wählen Sie einen SMTP-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **\<New connection...>** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ca12-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ca12-110">Der SMTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="6ca12-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="6ca12-111">Er unterstützt keine Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="6ca12-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="6ca12-112">**Verwandte Themen:** [SMTP-Verbindungs-Manager](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="6ca12-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="6ca12-113">**From**</span><span class="sxs-lookup"><span data-stu-id="6ca12-113">**From**</span></span>  
 <span data-ttu-id="6ca12-114">Geben Sie die E-Mail-Adresse des Absenders an.</span><span class="sxs-lookup"><span data-stu-id="6ca12-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="6ca12-115">**An**</span><span class="sxs-lookup"><span data-stu-id="6ca12-115">**To**</span></span>  
 <span data-ttu-id="6ca12-116">Stellen Sie die E-Mail-Adresse der Empfänger bereit. Verwenden Sie als Trennzeichen ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="6ca12-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="6ca12-117">**Cc**</span><span class="sxs-lookup"><span data-stu-id="6ca12-117">**Cc**</span></span>  
 <span data-ttu-id="6ca12-118">Geben Sie die E-Mail-Adressen der Personen an, die Kopien der Nachricht erhalten sollen. Verwenden Sie als Trennzeichen ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="6ca12-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="6ca12-119">**Bcc**</span><span class="sxs-lookup"><span data-stu-id="6ca12-119">**Bcc**</span></span>  
 <span data-ttu-id="6ca12-120">Geben Sie die E-Mail-Adressen der Personen an, die Blindkopien der Nachricht erhalten sollen. Verwenden Sie als Trennzeichen ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="6ca12-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="6ca12-121">**Subject**</span><span class="sxs-lookup"><span data-stu-id="6ca12-121">**Subject**</span></span>  
 <span data-ttu-id="6ca12-122">Geben Sie einen Betreff für die E-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="6ca12-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="6ca12-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="6ca12-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="6ca12-124">Wählen Sie den Quelltyp der Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="6ca12-124">Select the source type of the message.</span></span> <span data-ttu-id="6ca12-125">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="6ca12-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="6ca12-126">Wert</span><span class="sxs-lookup"><span data-stu-id="6ca12-126">Value</span></span>|<span data-ttu-id="6ca12-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6ca12-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6ca12-128">**Direkteingabe**</span><span class="sxs-lookup"><span data-stu-id="6ca12-128">**Direct input**</span></span>|<span data-ttu-id="6ca12-129">Legen Sie für die Quelle den Nachrichtentext fest.</span><span class="sxs-lookup"><span data-stu-id="6ca12-129">Set the source to the message text.</span></span> <span data-ttu-id="6ca12-130">Bei Auswahl dieses Wertes wird die dynamische Option **MessageSource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ca12-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="6ca12-131">**Dateiverbindung**</span><span class="sxs-lookup"><span data-stu-id="6ca12-131">**File connection**</span></span>|<span data-ttu-id="6ca12-132">Legen Sie für die Quelle die Datei fest, die den Nachrichtentext enthält.</span><span class="sxs-lookup"><span data-stu-id="6ca12-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="6ca12-133">Bei Auswahl dieses Wertes wird die dynamische Option **MessageSource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ca12-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="6ca12-134">**Variable**</span><span class="sxs-lookup"><span data-stu-id="6ca12-134">**Variable**</span></span>|<span data-ttu-id="6ca12-135">Legen Sie für die Quelle eine Variable fest, die den Nachrichtentext enthält.</span><span class="sxs-lookup"><span data-stu-id="6ca12-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="6ca12-136">Bei Auswahl dieses Wertes wird die dynamische Option **MessageSource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ca12-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="6ca12-137">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6ca12-137">**Priority**</span></span>  
 <span data-ttu-id="6ca12-138">Legen Sie die Priorität der Nachricht fest.</span><span class="sxs-lookup"><span data-stu-id="6ca12-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="6ca12-139">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="6ca12-139">**Attachments**</span></span>  
 <span data-ttu-id="6ca12-140">Geben Sie die Dateinamen der Anlagen für die E-Mail-Nachricht an. Verwenden Sie als Trennzeichen das Pipe-Zeichen (|).</span><span class="sxs-lookup"><span data-stu-id="6ca12-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ca12-141">Die Zeilen An, Cc und Bcc sind in Übereinstimmung mit Internetstandards auf 256 Zeichen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="6ca12-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="6ca12-142">MessageSourceType (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="6ca12-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="6ca12-143">MessageSourceType = Direct Input</span><span class="sxs-lookup"><span data-stu-id="6ca12-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="6ca12-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="6ca12-144">**MessageSource**</span></span>  
 <span data-ttu-id="6ca12-145">Geben Sie den Nachrichtentext ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen (…), und geben Sie die Nachricht in das Dialogfeld **Nachrichtenquelle** ein.</span><span class="sxs-lookup"><span data-stu-id="6ca12-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="6ca12-146">MessageSourceType = File connection</span><span class="sxs-lookup"><span data-stu-id="6ca12-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="6ca12-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="6ca12-147">**MessageSource**</span></span>  
 <span data-ttu-id="6ca12-148">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ca12-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="6ca12-149">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="6ca12-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="6ca12-150">MessageSourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="6ca12-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="6ca12-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="6ca12-151">**MessageSource**</span></span>  
 <span data-ttu-id="6ca12-152">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ca12-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="6ca12-153">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="6ca12-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca12-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ca12-154">See Also</span></span>  
 <span data-ttu-id="6ca12-155">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6ca12-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6ca12-156">[Editor für den Task ' Mail senden ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6ca12-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="6ca12-157">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6ca12-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
