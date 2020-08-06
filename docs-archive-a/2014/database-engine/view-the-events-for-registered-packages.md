---
title: Anzeigen der Ereignisse für registrierte Pakete | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing events
- extended events [SQL Server], viewing events
ms.assetid: 9a90b1a2-aa69-43f6-bdeb-cc5f57a26c6f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5e3665a695bd3f40407a8680872c9b0dc79fbc53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622810"
---
# <a name="view-the-events-for-registered-packages"></a><span data-ttu-id="1c2cf-102">Anzeigen der Ereignisse für registrierte Pakete</span><span class="sxs-lookup"><span data-stu-id="1c2cf-102">View the Events for Registered Packages</span></span>
  <span data-ttu-id="1c2cf-103">Bevor Sie eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events-Sitzung erstellen, sollten Sie zunächst herausfinden, welche Ereignisse in den registrierten Paketen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-103">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to find out what events are available in the registered packages.</span></span> <span data-ttu-id="1c2cf-104">Weitere Informationen finden Sie unter [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1c2cf-104">For more information, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
 <span data-ttu-id="1c2cf-105">Um diese Aufgabe auszuführen, müssen Sie mit dem Abfrage-Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] den folgenden Vorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
 <span data-ttu-id="1c2cf-106">Nach Abschluss der Anweisungen in dieser Prozedur werden auf der Registerkarte **Ergebnisse** des Abfrage-Editors die folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2cf-106">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="1c2cf-107">name.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-107">name.</span></span> <span data-ttu-id="1c2cf-108">Der Paketname.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-108">The package name.</span></span>  
  
-   <span data-ttu-id="1c2cf-109">event.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-109">event.</span></span> <span data-ttu-id="1c2cf-110">Der Ereignisname.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-110">The event name.</span></span>  
  
-   <span data-ttu-id="1c2cf-111">keyword.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-111">keyword.</span></span> <span data-ttu-id="1c2cf-112">Ein Schlüsselwort, das von einer internen numerischen Zuordnungstabelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-112">A keyword derived from an internal numeric mapping table.</span></span>  
  
-   <span data-ttu-id="1c2cf-113">channel.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-113">channel.</span></span> <span data-ttu-id="1c2cf-114">Die Zielgruppe für ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-114">The audience for an event.</span></span>  
  
-   <span data-ttu-id="1c2cf-115">description.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-115">description.</span></span> <span data-ttu-id="1c2cf-116">Die Beschreibung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-116">The event description.</span></span>  
  
## <a name="to-view-the-events-for-registered-packages-using-query-editor"></a><span data-ttu-id="1c2cf-117">So zeigen Sie die Ereignisse für registrierte Pakete mittels Abfrage-Editor an</span><span class="sxs-lookup"><span data-stu-id="1c2cf-117">To view the events for registered packages using Query Editor</span></span>  
  
-   <span data-ttu-id="1c2cf-118">Führen Sie im Abfrage-Editor die folgenden Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="1c2cf-118">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    USE msdb  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
    (  
    SELECT event_package=o.package_guid, o.description,   
    event=c.object_name, channel=v.map_value  
    FROM sys.dm_xe_objects o  
    LEFT JOIN sys.dm_xe_object_columns c ON o.name=c.object_name  
    INNER JOIN sys.dm_xe_map_values v ON c.type_name=v.name   
    AND c.column_value=cast(v.map_key AS nvarchar)  
    WHERE object_type='event' AND (c.name='CHANNEL' or c.name IS NULL)  
  
    ) c LEFT JOIN   
    (  
    SELECT event_package=c.object_package_guid, event=c.object_name,   
    keyword=v.map_value  
    FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
    ON c.type_name=v.name AND c.column_value=v.map_key   
    AND c.type_package_guid=v.object_package_guid  
    INNER JOIN sys.dm_xe_objects o ON o.name=c.object_name   
    AND o.package_guid=c.object_package_guid  
    WHERE object_type='event' AND c.name='KEYWORD'   
    ) k  
    ON  
    k.event_package=c.event_package AND (k.event=c.event or k.event IS NULL)  
    INNER JOIN sys.dm_xe_packages p ON p.guid=c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c2cf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c2cf-119">See Also</span></span>  
 <span data-ttu-id="1c2cf-120">[SQL Server von Paketen für erweiterte Ereignisse](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="1c2cf-120">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="1c2cf-121">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c2cf-121">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="1c2cf-122">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c2cf-122">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
