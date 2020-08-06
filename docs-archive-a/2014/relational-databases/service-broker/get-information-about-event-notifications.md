---
title: Abrufen von Informationen zu Ereignisbenachrichtigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700911"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="d6822-102">Abrufen von Informationen zu Ereignisbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="d6822-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="d6822-103">Zum Abfragen von Metadaten zu Ereignisbenachrichtigungen stehen die folgenden Katalogsichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d6822-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="d6822-104">**So rufen Sie Informationen zu Ereignisbenachrichtigungen auf der Nichtserverebene ab**</span><span class="sxs-lookup"><span data-stu-id="d6822-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="d6822-105">sys.event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6822-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="d6822-106">Um in **sys.event_notifications** Metadaten zu Ereignisbenachrichtigungen anzeigen zu können, die auf der Datenbankebene erstellt wurden, müssen folgende Voraussetzungen erfüllt sein: Sie müssen über CONTROL-, ALTER-, TAKE OWNERSHIP- oder VIEW DEFINITION-Berechtigungen für die Datenbank verfügen, Sie müssen der Besitzer der Ereignisbenachrichtigung sein oder über die ALTER ANY DATABASE EVENT NOTIFICATION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="d6822-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="d6822-107">Für Ereignisbenachrichtigungen, die für eine bestimmte Warteschlange erstellt wurden, müssen mindestens die folgenden Voraussetzungen erfüllt sein: Sie müssen über CONTROL-, ALTER-, TAKE OWNERSHIP- oder VIEW DEFINITION-Berechtigungen für das Objekt verfügen, Sie müssen der Besitzer der Ereignisbenachrichtigung sein oder über die ALTER ANY DATABASE EVENT NOTIFICATION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="d6822-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="d6822-108">**So rufen Sie Informationen zu Ereignisbenachrichtigungen auf der Serverebene ab**</span><span class="sxs-lookup"><span data-stu-id="d6822-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="d6822-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6822-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="d6822-110">Zum Anzeigen von Metadaten über Ereignisbenachrichtigungen in **sys.server_event_notifications**müssen mindestens die folgenden Voraussetzungen erfüllt sein: Sie müssen über die CONTROL- oder VIEW ANY DEFINITION-Berechtigung für den Server verfügen, Sie müssen der Anmeldename oder Besitzer der Ereignisbenachrichtigung sein, oder Sie müssen über die ALTER ANY EVENT NOTIFICATION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="d6822-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="d6822-111">**So rufen Sie Informationen zu sämtlichen Ereignissen ab, die zur Auslösung von Ereignisbenachrichtigungen führen können**</span><span class="sxs-lookup"><span data-stu-id="d6822-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="d6822-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6822-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="d6822-113">Diese Katalogsicht gibt keine Ereignisgruppen zurück.</span><span class="sxs-lookup"><span data-stu-id="d6822-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6822-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6822-114">See Also</span></span>  
 [<span data-ttu-id="d6822-115">Ereignisbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="d6822-115">Event Notifications</span></span>](event-notifications.md)  
  
  
