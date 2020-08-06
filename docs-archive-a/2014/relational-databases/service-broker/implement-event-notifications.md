---
title: Implementieren von Ereignisbenachrichtigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618606"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="43fd1-102">Implementieren von Ereignisbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="43fd1-102">Implement Event Notifications</span></span>
  <span data-ttu-id="43fd1-103">Zum Implementieren einer Ereignisbenachrichtigung müssen Sie zuerst einen Zieldienst erstellen, der Ereignisbenachrichtigungen empfängt, und dann die Ereignisbenachrichtigung erstellen.</span><span class="sxs-lookup"><span data-stu-id="43fd1-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="43fd1-104">-Dialogsicherheit sollte für Ereignisbenachrichtigungen konfiguriert werden, die Meldungen an einen Service Broker auf einem Remoteserver senden.</span><span class="sxs-lookup"><span data-stu-id="43fd1-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="43fd1-105">Die Dialogsicherheit muss manuell entsprechend dem Modell der vollständigen Sicherheit konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="43fd1-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="43fd1-106">Erstellen des Zieldiensts</span><span class="sxs-lookup"><span data-stu-id="43fd1-106">Creating the Target Service</span></span>  
 <span data-ttu-id="43fd1-107">Sie müssen keinen Dienst zum Initiieren von [!INCLUDE[ssSB](../../includes/sssb-md.md)]erstellen, da [!INCLUDE[ssSB](../../includes/sssb-md.md)] den folgenden speziellen Meldungstyp und Vertrag für Ereignisbenachrichtigungen enthält:</span><span class="sxs-lookup"><span data-stu-id="43fd1-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="43fd1-108">Der Zieldienst, der Ereignisbenachrichtigungen empfängt, muss diesen bereits vorhandenen Vertrag berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="43fd1-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="43fd1-109">**So erstellen Sie einen Zieldienst**:</span><span class="sxs-lookup"><span data-stu-id="43fd1-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="43fd1-110">Erstellen Sie eine Warteschlange, in der Meldungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="43fd1-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43fd1-111">Die Warteschlange empfängt den folgenden Meldungstyp: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="43fd1-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="43fd1-112">Erstellen Sie einen Dienst für die Warteschlange, der auf den Ereignisbenachrichtigungsvertrag verweist.</span><span class="sxs-lookup"><span data-stu-id="43fd1-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="43fd1-113">Erstellen Sie eine Route für den Dienst, um die Adresse zu definieren, an die [!INCLUDE[ssSB](../../includes/sssb-md.md)] Meldungen für den Dienst sendet.</span><span class="sxs-lookup"><span data-stu-id="43fd1-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="43fd1-114">Für Ereignisbenachrichtigungen, die an einen Dienst in der gleichen Datenbank gerichtet sind, geben Sie `ADDRESS = 'LOCAL'`an.</span><span class="sxs-lookup"><span data-stu-id="43fd1-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="43fd1-115">-Routing bestimmt den Dienst, der die Benachrichtigungsmeldungen empfängt.</span><span class="sxs-lookup"><span data-stu-id="43fd1-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="43fd1-116">Wenn die Ereignisbenachrichtigung an einen Dienst auf einem Remoteserver gerichtet ist, müssen für den Quellserver und den Zielserver Routen definiert sein, damit sichergestellt ist, dass eine bidirektionale Kommunikation stattfindet.</span><span class="sxs-lookup"><span data-stu-id="43fd1-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="43fd1-117">Das folgende Beispiel erstellt eine Warteschlange, einen Dienst für die Warteschlange und eine Route für den Dienst, um Meldungen aus dem Ereignisbenachrichtigungsvertrag zu verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="43fd1-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="43fd1-118">Erstellen der Ereignisbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="43fd1-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="43fd1-119">Ereignisbenachrichtigungen werden mithilfe der [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION-Anweisung erstellt und mithilfe von DROP EVENT NOTIFICATION gelöscht.</span><span class="sxs-lookup"><span data-stu-id="43fd1-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="43fd1-120">Wenn Sie eine Ereignisbenachrichtigung ändern möchten, müssen Sie sie löschen und dann neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43fd1-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="43fd1-121">Im folgenden Beispiel wird die Ereignisbenachrichtigung mit dem Namen `CreateDatabaseNotification`erstellt.</span><span class="sxs-lookup"><span data-stu-id="43fd1-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="43fd1-122">Diese Ereignisbenachrichtigung sendet eine Meldung zu jedem `CREATE_DATABASE`-Ereignis, das auf dem Server auftritt, an den `NotifyService`-Dienst, der zuvor erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="43fd1-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="43fd1-123">Ereignisbenachrichtigungen erkennen CREATE_SCHEMA-Ereignisse und die <schema_element>-Definitionen von CREATE SCHEMA-Anweisungen als separate Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="43fd1-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="43fd1-124">Angenommen, eine Ereignisbenachrichtigung wird für die Ereignisse CREATE_SCHEMA und CREATE_TABLE erstellt, und Sie führen den folgenden Batch aus.</span><span class="sxs-lookup"><span data-stu-id="43fd1-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="43fd1-125">In diesem Fall wird die Ereignisbenachrichtigung zweimal ausgegeben: Einmal beim Auftreten des CREATE_SCHEMA-Ereignisses, und ein zweites Mal beim Auftreten des CREATE_TABLE-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="43fd1-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="43fd1-126">Es wird empfohlen, entweder keine Ereignisbenachrichtigungen für die CREATE_SCHEMA-Ereignisse und gleichzeitig für die <schema_element>-Texte von entsprechenden CREATE SCHEMA-Definitionen zu erstellen, oder Ihre Anwendung so zu programmieren, dass keine nicht erwünschten Ereignisdaten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="43fd1-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="43fd1-127">**So erstellen Sie eine Ereignisbenachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="43fd1-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="43fd1-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43fd1-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="43fd1-129">**So löschen Sie eine Ereignisbenachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="43fd1-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="43fd1-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43fd1-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="43fd1-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43fd1-131">See Also</span></span>  
 <span data-ttu-id="43fd1-132">[Abrufen von Informationen zu Ereignisbenachrichtigungen](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="43fd1-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="43fd1-133">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43fd1-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
