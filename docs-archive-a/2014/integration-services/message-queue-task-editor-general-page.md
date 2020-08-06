---
title: Editor für den Task Nachrichten Warteschlange (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622777"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="936bd-102">Editor für den Task 'Nachrichtenwarteschlange' (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="936bd-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="936bd-103">Auf der Seite **Allgemein** des Dialogfelds **Editor für den Task „Nachrichtenwarteschlange“** können Sie den Task „Nachrichtenwarteschlange“ benennen und beschreiben, das Nachrichtenformat angeben und kennzeichnen, ob vom Task Nachrichten gesendet oder empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="936bd-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="936bd-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="936bd-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="936bd-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="936bd-105">Options</span></span>  
 <span data-ttu-id="936bd-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="936bd-106">**Name**</span></span>  
 <span data-ttu-id="936bd-107">Geben Sie einen eindeutigen Namen für den Task Nachrichtenwarteschlange an.</span><span class="sxs-lookup"><span data-stu-id="936bd-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="936bd-108">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="936bd-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="936bd-109">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="936bd-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="936bd-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="936bd-110">**Description**</span></span>  
 <span data-ttu-id="936bd-111">Geben Sie eine Beschreibung des Tasks Nachrichtenwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="936bd-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="936bd-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="936bd-112">**Use2000Format**</span></span>  
 <span data-ttu-id="936bd-113">Geben Sie an, ob das 2000-Format von Message Queuing (auch bekannt als MSMQ) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="936bd-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="936bd-114">Der Standardwert lautet `False`.</span><span class="sxs-lookup"><span data-stu-id="936bd-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="936bd-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="936bd-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="936bd-116">Wählen Sie einen vorhandenen MSMQ-Verbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="936bd-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="936bd-117">**Verwandte Themen:** [MSMQ-Verbindungs-Manager ](connection-manager/msmq-connection-manager.md), [MSMQ-Verbindungs-Manager-Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="936bd-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="936bd-118">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="936bd-118">**Message**</span></span>  
 <span data-ttu-id="936bd-119">Geben Sie an, ob Nachrichten vom Task Nachrichtenwarteschlange gesendet oder empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="936bd-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="936bd-120">Wenn Sie **Nachricht senden**auswählen, wird im linken Bereich des Dialogfelds die Seite Senden angezeigt; wenn Sie **Nachricht empfangen**auswählen, wird die Seite Empfangen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="936bd-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="936bd-121">Standardmäßig ist dieser Wert auf **Nachricht senden**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="936bd-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936bd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="936bd-122">See Also</span></span>  
 <span data-ttu-id="936bd-123">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="936bd-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="936bd-124">[Editor für den Task ' Nachrichten Warteschlange ' &#40;&#41;Seite](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="936bd-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="936bd-125">[Editor für den Task Nachrichten Warteschlange &#40;&#41;Seite senden](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="936bd-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="936bd-126">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="936bd-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
