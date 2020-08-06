---
title: Ändern einer Sitzung für erweiterte Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607775"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="f68e5-102">Ändern einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f68e5-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="f68e5-103">Nachdem Sie eine Sitzung für erweiterte Ereignisse erstellt haben, können Sie diese je nach Bedarf mithilfe des **SQL Server-Assistenten für erweiterte Ereignisse**ändern.</span><span class="sxs-lookup"><span data-stu-id="f68e5-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f68e5-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f68e5-104">Before you Begin</span></span>  
 <span data-ttu-id="f68e5-105">Sie können kein Ziel für aktive und inaktive Sitzungen ändern, und Sie können zudem für eine aktive Sitzung die Konfigurationen für erweiterte Eigenschaften nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f68e5-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="f68e5-106">Folgende Änderungen sind sowohl für aktive als auch inaktive Ereignissitzungen möglich:</span><span class="sxs-lookup"><span data-stu-id="f68e5-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="f68e5-107">Ereignisse können der Sitzung hinzugefügt oder von dieser entfernt werden. Zudem lassen sich die Ereigniskonfigurationen wie Ereignisfelder, -filter und -aktionen ändern.</span><span class="sxs-lookup"><span data-stu-id="f68e5-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="f68e5-108">Sie können der Ereignissitzung ein Ziel hinzufügen oder von dieser entfernen.</span><span class="sxs-lookup"><span data-stu-id="f68e5-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="f68e5-109">Aktivieren Sie die Option **Ereignissitzung beim Serverstart starten** .</span><span class="sxs-lookup"><span data-stu-id="f68e5-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="f68e5-110">Folgende zusätzliche Änderungen sind für eine inaktive Ereignissitzung möglich:</span><span class="sxs-lookup"><span data-stu-id="f68e5-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="f68e5-111">Aktivieren Sie die Option zum **Nachverfolgen der Beziehung zwischen Ereignissen**.</span><span class="sxs-lookup"><span data-stu-id="f68e5-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="f68e5-112">Ändern Sie die Konfiguration für erweiterte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f68e5-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f68e5-113">Der **SQL Server-Assistent für erweiterte Ereignisse** unterstützt keine Änderung von Ereignissitzungen.</span><span class="sxs-lookup"><span data-stu-id="f68e5-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="f68e5-114">Ändern einer Sitzung für erweiterte Ereignisse mithilfe des SQL Server-Assistenten für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f68e5-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="f68e5-115">Erweitern Sie im Objekt-Explorer **Verwaltung**, erweitern Sie **Erweiterte Ereignisse**, und erweitern Sie dann **Sitzungen**.</span><span class="sxs-lookup"><span data-stu-id="f68e5-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="f68e5-116">Klicken Sie mit der rechten Maustaste auf die zu ändernde Sitzung, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f68e5-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="f68e5-117">Nehmen Sie im Dialogfeld **Eigenschaften** die entsprechenden Änderungen vor, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f68e5-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68e5-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f68e5-118">See Also</span></span>  
 <span data-ttu-id="f68e5-119">[Alter Event Session &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f68e5-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="f68e5-120">Erstellen einer Sitzung für erweiterte Ereignisse mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="f68e5-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
