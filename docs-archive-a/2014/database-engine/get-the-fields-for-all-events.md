---
title: Die Felder für alle Ereignisse erhalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], getting fields
- xe
ms.assetid: 4e4ee03f-5bca-42ed-a37c-db1c82e3aad2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 01d98e827121a0c47111dd601c6e1772f796849d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701577"
---
# <a name="get-the-fields-for-all-events"></a><span data-ttu-id="6c4eb-102">Abrufen der Felder für alle Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6c4eb-102">Get the Fields for All Events</span></span>
  <span data-ttu-id="6c4eb-103">Das Ausführen dieser Aufgabe beinhaltet die Verwendung des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c4eb-103">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6c4eb-104">Nach Abschluss der Anweisungen in dieser Prozedur werden auf der Registerkarte **Ergebnisse** des Abfrage-Editors die folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c4eb-104">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="6c4eb-105">package_name</span><span class="sxs-lookup"><span data-stu-id="6c4eb-105">package_name</span></span>  
  
-   <span data-ttu-id="6c4eb-106">event_name</span><span class="sxs-lookup"><span data-stu-id="6c4eb-106">event_name</span></span>  
  
-   <span data-ttu-id="6c4eb-107">event_field</span><span class="sxs-lookup"><span data-stu-id="6c4eb-107">event_field</span></span>  
  
-   <span data-ttu-id="6c4eb-108">field_type</span><span class="sxs-lookup"><span data-stu-id="6c4eb-108">field_type</span></span>  
  
-   <span data-ttu-id="6c4eb-109">column_type</span><span class="sxs-lookup"><span data-stu-id="6c4eb-109">column_type</span></span>  
  
 <span data-ttu-id="6c4eb-110">Sie können die vorangehenden Informationen verwenden, wenn Sie Ereignissitzungen konfigurieren, die das Bucketzuordnungsziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4eb-110">You can use the preceding information when configuring event sessions that use the bucketing target.</span></span> <span data-ttu-id="6c4eb-111">Weitere Informationen finden Sie unter [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="6c4eb-111">For more information, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6c4eb-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6c4eb-112">Before you Begin</span></span>  
 <span data-ttu-id="6c4eb-113">Bevor Sie eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Sitzung für erweiterte Ereignisse erstellen, sollten Sie Informationen über die mit Ereignissen verbundenen Felder abrufen.</span><span class="sxs-lookup"><span data-stu-id="6c4eb-113">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to get information about the fields associated with events.</span></span>  
  
## <a name="to-get-the-fields-for-all-events-using-query-editor"></a><span data-ttu-id="6c4eb-114">So rufen Sie die Felder für alle Ereignisse mittels Abfrage-Editor ab</span><span class="sxs-lookup"><span data-stu-id="6c4eb-114">To get the fields for all events using Query Editor</span></span>  
  
-   <span data-ttu-id="6c4eb-115">Führen Sie im Abfrage-Editor die folgenden Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="6c4eb-115">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    select p.name package_name, o.name event_name, c.name event_field, c.type_name field_type, c.column_type column_type  
    from sys.dm_xe_objects o  
    join sys.dm_xe_packages p  
          on o.package_guid = p.guid  
    join sys.dm_xe_object_columns c  
          on o.name = c.object_name  
    where o.object_type = 'event'  
    order by package_name, event_name  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6c4eb-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c4eb-116">See Also</span></span>  
 <span data-ttu-id="6c4eb-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c4eb-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="6c4eb-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c4eb-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  