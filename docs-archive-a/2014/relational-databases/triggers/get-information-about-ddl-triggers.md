---
title: Abrufen von Informationen zu DDL-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621930"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="f0159-102">Abrufen von Informationen zu DDL-Triggern</span><span class="sxs-lookup"><span data-stu-id="f0159-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="f0159-103">Die in diesem Abschnitt aufgeführten Katalogsichten können zum Abrufen von Informationen zu DLL-Triggern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0159-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="f0159-104">**So rufen Sie Informationen zu Ereignissen oder Ereignisgruppen ab, bei denen ein DDL-Trigger ausgelöst werden kann**</span><span class="sxs-lookup"><span data-stu-id="f0159-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="f0159-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="f0159-106">**So zeigen Sie die Abhängigkeiten eines Triggers an**</span><span class="sxs-lookup"><span data-stu-id="f0159-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="f0159-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="f0159-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="f0159-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="f0159-110">Datenbankbezogene DLL-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0159-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="f0159-111">**So rufen Sie Informationen zu datenbankbezogenen Triggern ab**</span><span class="sxs-lookup"><span data-stu-id="f0159-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-112">sys.triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="f0159-113">**So rufen Sie Informationen zu Datenbankereignissen ab, die Trigger auslösen**</span><span class="sxs-lookup"><span data-stu-id="f0159-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-114">sys.trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="f0159-115">**So zeigen Sie die Definition eines datenbankbezogenen Triggers an**</span><span class="sxs-lookup"><span data-stu-id="f0159-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="f0159-116">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="f0159-117">**So rufen Sie Informationen zu auf CRL-Datenbanken bezogenen Trigger ab**</span><span class="sxs-lookup"><span data-stu-id="f0159-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-118">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="f0159-119">Serverbezogene DLL-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0159-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="f0159-120">**So rufen Sie Informationen zu serverbezogenen Triggern ab**</span><span class="sxs-lookup"><span data-stu-id="f0159-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-121">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="f0159-122">**So rufen Sie Informationen zu Serverereignissen ab, die Trigger auslösen**</span><span class="sxs-lookup"><span data-stu-id="f0159-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="f0159-124">**So zeigen Sie die Definition eines serverbezogenen Triggers an**</span><span class="sxs-lookup"><span data-stu-id="f0159-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="f0159-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="f0159-126">**So rufen Sie Informationen zu auf CRL-Server bezogenen Triggern ab**</span><span class="sxs-lookup"><span data-stu-id="f0159-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="f0159-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0159-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f0159-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0159-128">See Also</span></span>  
 [<span data-ttu-id="f0159-129">DDL-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0159-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
