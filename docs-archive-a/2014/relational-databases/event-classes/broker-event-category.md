---
title: Broker (Ereigniskategorie) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609268"
---
# <a name="broker-event-category"></a><span data-ttu-id="1d3fb-102">Broker (Ereigniskategorie)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-102">Broker Event Category</span></span>
  <span data-ttu-id="1d3fb-103">Die **Broker** -Ereigniskategorie enthält allgemeine Service Broker-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d3fb-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1d3fb-104">In This Section</span></span>  
  
|<span data-ttu-id="1d3fb-105">Thema</span><span class="sxs-lookup"><span data-stu-id="1d3fb-105">Topic</span></span>|<span data-ttu-id="1d3fb-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1d3fb-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1d3fb-107">Broker:Activation (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="1d3fb-108">Ein Ereignis, das generiert wird, wenn durch eine Warteschlangenüberwachung eine gespeicherte Aktivierungsprozedur gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="1d3fb-109">Broker:Connection-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1d3fb-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="1d3fb-110">Ein Ereignis, das generiert wird, um den Status einer von Service Broker verwalteten Transportverbindung zu melden.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="1d3fb-111">Broker:Conversation-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1d3fb-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="1d3fb-112">Ein Ereignis, das generiert wird, um den Fortschritt einer Konversation zu melden.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="1d3fb-113">Broker:Conversation Group-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1d3fb-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="1d3fb-114">Ein Ereignis, das generiert wird, wenn die Datenbank eine Konversationsgruppe erstellt oder löscht.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="1d3fb-115">Broker:Corrupted Message (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="1d3fb-116">Ein Ereignis, das zum Angeben einer fehlerhaften, von der Datenbank erhaltenen Nachricht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="1d3fb-117">Broker:Forwarded Message Dropped-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1d3fb-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="1d3fb-118">Ein Ereignis, das generiert wird, wenn SQL Server eine Service Broker-Nachricht löscht, die hätte weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="1d3fb-119">Broker:Forwarded Message Sent-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1d3fb-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="1d3fb-120">Ein Ereignis, das generiert wird, wenn SQL Server eine Service Broker-Nachricht weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="1d3fb-121">Broker:Message Classify (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="1d3fb-122">Ein Ereignis, das generiert wird, wenn Service Broker das Routing für eine Nachricht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="1d3fb-123">Broker:Message Drop (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="1d3fb-124">Ein Ereignis, das generiert wird, wenn Service Broker eine empfangene Nachricht nicht beibehalten kann, die in dieser Instanz an einen Dienst weitergeleitet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="1d3fb-125">Broker:Remote Message Ack (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1d3fb-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="1d3fb-126">Ein Ereignis, das generiert wird, wenn Service Broker eine Nachrichtenbestätigung sendet oder empfängt.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="1d3fb-127">Service Broker bietet auch zwei Sicherheitsüberwachungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="1d3fb-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="1d3fb-128">Weitere Informationen zu diesen Ereignissen finden Sie unter [Audit Broker Login (Ereignisklasse)](audit-broker-login-event-class.md) und [Audit Broker Conversation (Ereignisklasse)](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="1d3fb-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3fb-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d3fb-129">See Also</span></span>  
 [<span data-ttu-id="1d3fb-130">Sicherheitsüberwachung-Ereigniskategorie</span><span class="sxs-lookup"><span data-stu-id="1d3fb-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
