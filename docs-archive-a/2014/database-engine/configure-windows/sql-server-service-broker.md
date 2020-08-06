---
title: SQL Server Service Broker | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724153"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="7c982-102">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c982-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7c982-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] bietet native Unterstützung für Messaging- und Warteschlangenanwendungen in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c982-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="7c982-104">Dies erleichtert Entwicklern das Erstellen anspruchsvoller Anwendungen, die die [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Komponenten für die Kommunikation zwischen verschiedenartigen Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c982-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="7c982-105">Entwickler können [!INCLUDE[ssSB](../../includes/sssb-md.md)] verwenden, um verteilte und zuverlässige Anwendungen auf einfache Weise zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c982-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="7c982-106">Anwendungsentwickler, die [!INCLUDE[ssSB](../../includes/sssb-md.md)] verwenden, können Datenarbeitsauslastungen zwischen mehreren Datenbanken verteilen, ohne komplizierte Besonderheiten von Kommunikation und Messaging programmieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7c982-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="7c982-107">Dadurch werden die Entwicklungs- und die Testarbeit reduziert, da [!INCLUDE[ssSB](../../includes/sssb-md.md)] die Kommunikationspfade im Kontext einer Konversation behandelt.</span><span class="sxs-lookup"><span data-stu-id="7c982-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="7c982-108">Außerdem wird die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="7c982-108">It also improves performance.</span></span> <span data-ttu-id="7c982-109">Front-End-Datenbanken, die Websites unterstützen, können z. B. Informationen aufzeichnen und prozessintensive Tasks an die Warteschlange von Back-End-Datenbanken senden.</span><span class="sxs-lookup"><span data-stu-id="7c982-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="7c982-110">stellt sicher, dass alle Tasks im Kontext von Transaktionen verwaltet werden, um die Zuverlässigkeit und technische Konsistenz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="7c982-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="7c982-111">Wo finde ich die Dokumentation für Service Broker?</span><span class="sxs-lookup"><span data-stu-id="7c982-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="7c982-112">Die Referenzdokumentation für [!INCLUDE[ssSB](../../includes/sssb-md.md)] ist in der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Dokumentation enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c982-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="7c982-113">Diese Referenzdokumentation enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="7c982-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="7c982-114">[Anweisungen &#40;Transact-SQL&#41; für Datendefinitionssprache &#40;DDL&#41;](/sql/odbc/reference/develop-app/ddl-statements) für CREATE-, ALTER- und DROP-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7c982-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="7c982-115">Service Broker-Katalogsichten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7c982-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="7c982-116">Dynamische Verwaltungssichten in Verbindung mit Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7c982-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="7c982-117">ssbdiagnose-Hilfsprogramm &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="7c982-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="7c982-118">Informationen zu [-Konzepten sowie Entwicklungs- und Verwaltungsaufgaben finden Sie in der](https://go.microsoft.com/fwlink/?LinkId=231312) zuvor veröffentlichten Dokumentation [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c982-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="7c982-119">Diese Dokumentation ist aufgrund der geringen Anzahl von Änderungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssSB](../../includes/sssb-md.md)] nicht in der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Dokumentation enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c982-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="7c982-120">Neues in Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c982-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="7c982-121">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]wurden keine wesentlichen Änderungen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c982-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="7c982-122">Für [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]wurden die folgenden Änderungen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c982-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="7c982-123">Nachrichten können an mehrere Zieldienste gesendet werden (Multicast)</span><span class="sxs-lookup"><span data-stu-id="7c982-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="7c982-124">Die Syntax der [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql)-Anweisung wurde erweitert, um mehrere Konversationshandles zu unterstützen und so die Multicastübermittlung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7c982-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="7c982-125">Warteschlangen machen die Nachrichtenwartezeit verfügbar</span><span class="sxs-lookup"><span data-stu-id="7c982-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="7c982-126">Warteschlangen verfügen über eine neue **message_enqueue_time**-Spalte, in der angezeigt wird, wie lange eine Nachricht in der Warteschlange war.</span><span class="sxs-lookup"><span data-stu-id="7c982-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="7c982-127">Behandlung nicht verarbeitbarer Nachrichten kann deaktiviert werden</span><span class="sxs-lookup"><span data-stu-id="7c982-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="7c982-128">Die Anweisungen [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) und [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) bieten nun die Möglichkeit, die Behandlung von nicht verarbeitbaren Nachrichten zu aktivieren oder deaktivieren, indem die Klausel `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)` hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7c982-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="7c982-129">Die **sys.service_queues** -Katalogsicht enthält jetzt eine **is_poison_message_handling_enabled** -Spalte, in der angezeigt wird, ob die Behandlung nicht verarbeitbarer Nachrichten aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7c982-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="7c982-130">AlwaysOn-Unterstützung in Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c982-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="7c982-131">Weitere Informationen finden Sie unter [Service Broker mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7c982-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
