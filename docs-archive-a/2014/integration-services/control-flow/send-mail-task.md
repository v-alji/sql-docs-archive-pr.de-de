---
title: Mail senden (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610001"
---
# <a name="send-mail-task"></a><span data-ttu-id="cac10-102">Mail senden (Task)</span><span class="sxs-lookup"><span data-stu-id="cac10-102">Send Mail Task</span></span>
  <span data-ttu-id="cac10-103">Der Task 'Mail senden' sendet eine E-Mail.</span><span class="sxs-lookup"><span data-stu-id="cac10-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="cac10-104">Mithilfe des Tasks 'Mail senden' kann ein Paket Nachrichten senden, wenn Tasks im Paket-Workflow erfolgreich ausgeführt werden oder einen Fehler erzeugen, oder Nachrichten als Antwort auf ein Ereignis senden, das vom Paket zur Laufzeit ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cac10-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="cac10-105">Beispielsweise kann mit diesem Task ein Datenbankadministrator über das erfolgreiche Ausführen des Tasks Datenbank sichern benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="cac10-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="cac10-106">Es gibt folgende Möglichkeiten, um den Task Mail senden zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="cac10-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="cac10-107">Geben Sie den Nachrichtentext für die E-Mail-Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="cac10-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="cac10-108">Geben Sie ein Betreffzeile für die E-Mail-Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="cac10-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="cac10-109">Legen Sie die Prioritätsstufe der Nachricht fest.</span><span class="sxs-lookup"><span data-stu-id="cac10-109">Set the priority level of the message.</span></span> <span data-ttu-id="cac10-110">Dieser Task unterstützt drei Prioritätsebenen: normal, niedrig und hoch.</span><span class="sxs-lookup"><span data-stu-id="cac10-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="cac10-111">Geben Sie in den Zeilen An, Cc und Bcc die Empfänger an.</span><span class="sxs-lookup"><span data-stu-id="cac10-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="cac10-112">Falls für den Task mehrere Empfänger angegeben sind, werden sie durch Semikolons getrennt.</span><span class="sxs-lookup"><span data-stu-id="cac10-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cac10-113">Die Zeilen An, Cc und Bcc sind auf 256 Zeichen in Übereinstimmung mit den Internetstandards begrenzt.</span><span class="sxs-lookup"><span data-stu-id="cac10-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="cac10-114">Fügen Sie Anlagen hinzu.</span><span class="sxs-lookup"><span data-stu-id="cac10-114">Include attachments.</span></span> <span data-ttu-id="cac10-115">Falls für den Task mehrere Anlagen angegeben sind, werden sie durch einen senkrechten Strich (|) getrennt.</span><span class="sxs-lookup"><span data-stu-id="cac10-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cac10-116">Falls beim Ausführen des Pakets eine Anlagedatei nicht vorhanden ist, wird ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="cac10-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="cac10-117">Geben Sie den zu verwendenden SMTP-Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="cac10-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cac10-118">Der SMTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cac10-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="cac10-119">Er unterstützt keine Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cac10-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="cac10-120">Der Nachrichtentext kann eine von Ihnen eingegebene Zeichenfolge sein, eine Verbindung mit einer Datei, die den Text enthält, oder der Name einer Variablen, die den Text enthält.</span><span class="sxs-lookup"><span data-stu-id="cac10-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="cac10-121">Dieser Task verwendet einen Dateiverbindungs-Manager, um eine Verbindung mit einer Datei herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cac10-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="cac10-122">Weitere Informationen finden Sie unter [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cac10-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="cac10-123">Dieser Task verwendet einen SMTP-Verbindungs-Manager, um eine Verbindung mit einem Mailserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cac10-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="cac10-124">Weitere Informationen finden Sie unter [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cac10-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="cac10-125">Verfügbare benutzerdefinierte Meldungen für die Protokollierung für den Task 'Mail senden'</span><span class="sxs-lookup"><span data-stu-id="cac10-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="cac10-126">In der folgenden Tabelle werden die benutzerdefinierten Protokolleinträge für den Task 'Mail senden' aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cac10-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="cac10-127">Weitere Informationen finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) und [Benutzerdefinierte Meldungen für die Protokollierung](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="cac10-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="cac10-128">Protokolleintrag</span><span class="sxs-lookup"><span data-stu-id="cac10-128">Log entry</span></span>|<span data-ttu-id="cac10-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cac10-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="cac10-130">Zeigt an, dass das Senden einer E-Mail-Nachricht begonnen wurde.</span><span class="sxs-lookup"><span data-stu-id="cac10-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="cac10-131">Zeigt an, dass das Senden einer E-Mail-Nachricht beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cac10-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="cac10-132">Enthält beschreibende Informationen zum Task.</span><span class="sxs-lookup"><span data-stu-id="cac10-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="cac10-133">Konfigurieren des Tasks Mail senden</span><span class="sxs-lookup"><span data-stu-id="cac10-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="cac10-134">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="cac10-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cac10-135">Klicken Sie auf eines der folgenden Themen, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="cac10-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cac10-136">Editor für den Task „Mail senden“ &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="cac10-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="cac10-137">Editor für den Task „Mail senden“ &#40;Seite „E-Mail“&#41;</span><span class="sxs-lookup"><span data-stu-id="cac10-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="cac10-138">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="cac10-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="cac10-139">Klicken Sie auf das folgende Thema, um Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="cac10-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="cac10-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="cac10-140">Related Tasks</span></span>  
 <span data-ttu-id="cac10-141">Klicken Sie auf [!INCLUDE[ssIS](../../includes/ssis-md.md)] Festlegen der Eigenschaften eines Tasks oder Containers [, um Informationen zum Festlegen dieser Eigenschaften im](../set-the-properties-of-a-task-or-container.md)-Designer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cac10-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="cac10-142">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="cac10-142">Related Content</span></span>  
  
-   <span data-ttu-id="cac10-143">Technischer Artikel [Vorgehensweise: Senden von E-Mails mit Zustellungsbenachrichtigung in C#](https://go.microsoft.com/fwlink/?LinkId=237625)(Gewusst wie: Senden von E-Mails mit Zustellungsbenachrichtigung in C#) auf shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="cac10-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac10-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cac10-144">See Also</span></span>  
 <span data-ttu-id="cac10-145">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="cac10-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="cac10-146">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="cac10-146">Control Flow</span></span>](control-flow.md)  
  
  
