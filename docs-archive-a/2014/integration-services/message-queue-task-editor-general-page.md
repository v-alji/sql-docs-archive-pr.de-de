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
# <a name="message-queue-task-editor-general-page"></a>Editor für den Task 'Nachrichtenwarteschlange' (Seite Allgemein)
  Auf der Seite **Allgemein** des Dialogfelds **Editor für den Task „Nachrichtenwarteschlange“** können Sie den Task „Nachrichtenwarteschlange“ benennen und beschreiben, das Nachrichtenformat angeben und kennzeichnen, ob vom Task Nachrichten gesendet oder empfangen werden.  
  
 Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Message Queue Task](control-flow/message-queue-task.md).  
  
## <a name="options"></a>Tastatur  
 **Name**  
 Geben Sie einen eindeutigen Namen für den Task Nachrichtenwarteschlange an. Dieser Name wird im Tasksymbol als Bezeichnung verwendet.  
  
> [!NOTE]  
>  Tasknamen müssen innerhalb eines Pakets eindeutig sein.  
  
 **Beschreibung**  
 Geben Sie eine Beschreibung des Tasks Nachrichtenwarteschlange ein.  
  
 **Use2000Format**  
 Geben Sie an, ob das 2000-Format von Message Queuing (auch bekannt als MSMQ) verwendet werden soll. Der Standardwert lautet `False`.  
  
 **MSMQConnection**  
 Wählen Sie einen vorhandenen MSMQ-Verbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.  
  
 **Verwandte Themen:** [MSMQ-Verbindungs-Manager ](connection-manager/msmq-connection-manager.md), [MSMQ-Verbindungs-Manager-Editor](../../2014/integration-services/msmq-connection-manager-editor.md)  
  
 **Meldung**  
 Geben Sie an, ob Nachrichten vom Task Nachrichtenwarteschlange gesendet oder empfangen werden. Wenn Sie **Nachricht senden**auswählen, wird im linken Bereich des Dialogfelds die Seite Senden angezeigt; wenn Sie **Nachricht empfangen**auswählen, wird die Seite Empfangen aufgelistet. Standardmäßig ist dieser Wert auf **Nachricht senden**festgelegt.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor für den Task ' Nachrichten Warteschlange ' &#40;&#41;Seite](../../2014/integration-services/message-queue-task-editor-receive-page.md)   
 [Editor für den Task Nachrichten Warteschlange &#40;&#41;Seite senden](../../2014/integration-services/message-queue-task-editor-send-page.md)   
 [Seite Ausdrücke](expressions/expressions-page.md)  
  
  
