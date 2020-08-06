---
title: Implementieren von DDL-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621921"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="063db-102">Implementieren von DDL-Triggern</span><span class="sxs-lookup"><span data-stu-id="063db-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="063db-103">Dieses Thema enthält Informationen, die Ihnen beim Erstellen von DDL-Triggern, Ändern von DDL-Triggern sowie Deaktivieren oder Löschen von DDL-Triggern helfen sollen.</span><span class="sxs-lookup"><span data-stu-id="063db-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="063db-104">Erstellen von DDL-Triggern</span><span class="sxs-lookup"><span data-stu-id="063db-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="063db-105">DDL-Trigger werden mithilfe der CREATE TRIGGER-Anweisung von [!INCLUDE[tsql](../../includes/tsql-md.md)] für DDL-Trigger erstellt.</span><span class="sxs-lookup"><span data-stu-id="063db-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="063db-106">**So erstellen Sie einen DDL-Trigger**</span><span class="sxs-lookup"><span data-stu-id="063db-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="063db-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="063db-108">Die Fähigkeit, Resultsets aus Triggern zurückzugeben, wird in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="063db-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="063db-109">Durch Trigger, die Resultsets zurückgeben, kann es in Anwendungen, die hierfür nicht konzipiert wurden, zu unerwartetem Verhalten kommen.</span><span class="sxs-lookup"><span data-stu-id="063db-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="063db-110">Vermeiden Sie deshalb bei Neuentwicklungen, Resultsets aus Triggern zurückzugeben, und planen Sie die Änderung von Anwendungen, in denen dies derzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="063db-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="063db-111">Legen Sie die Option [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Ergebnisse von Triggern nicht zulassen [auf 1 fest, um zu verhindern, dass Trigger in](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) Resultsets zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="063db-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="063db-112">In einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]wird die Standardeinstellung für die Option 1 sein.</span><span class="sxs-lookup"><span data-stu-id="063db-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="063db-113">Ändern von DDL-Triggern</span><span class="sxs-lookup"><span data-stu-id="063db-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="063db-114">Wenn Sie die Definition eines DDL-Triggers ändern müssen, können Sie den Trigger entweder löschen und neu erstellen oder den vorhandenen Trigger in einem einzigen Schritt neu definieren.</span><span class="sxs-lookup"><span data-stu-id="063db-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="063db-115">Wenn Sie den Namen eines Objekts ändern, auf das ein DDL-Trigger verweist, müssen Sie den Trigger so ändern, dass sein Text den neuen Namen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="063db-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="063db-116">Bevor Sie ein Objekt umbenennen, sollten Sie daher erst die Abhängigkeiten des Objekts anzeigen, um feststellen zu können, ob Trigger von der beabsichtigten Änderung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="063db-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="063db-117">Sie können einen Trigger auch ändern, um seine Definition zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="063db-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="063db-118">**So ändern Sie einen Trigger**</span><span class="sxs-lookup"><span data-stu-id="063db-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="063db-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="063db-120">**So zeigen Sie die Abhängigkeiten eines Triggers an**</span><span class="sxs-lookup"><span data-stu-id="063db-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="063db-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="063db-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="063db-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="063db-124">Deaktivieren und Löschen von DDL-Triggern</span><span class="sxs-lookup"><span data-stu-id="063db-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="063db-125">Wenn ein DDL-Trigger nicht mehr benötigt wird, kann er deaktiviert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="063db-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="063db-126">Durch das Deaktivieren eines DDL-Triggers wird er nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="063db-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="063db-127">Der Trigger ist weiterhin als Objekt in der aktuellen Datenbank vorhanden.</span><span class="sxs-lookup"><span data-stu-id="063db-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="063db-128">Der Trigger wird jedoch bei der Ausführung von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen, für die er programmiert wurde, nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="063db-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="063db-129">Deaktivierte DDL-Trigger können erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="063db-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="063db-130">Wenn ein DDL-Trigger aktiviert wird, wird er so ausgelöst wie nach seiner ursprünglichen Erstellung.</span><span class="sxs-lookup"><span data-stu-id="063db-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="063db-131">DDL-Trigger werden beim Erstellen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="063db-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="063db-132">Wenn ein DDL-Trigger gelöscht wird, wird er aus der aktuellen Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="063db-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="063db-133">Objekte oder Daten, für die der DDL-Trigger den Bereich besitzt, sind hiervon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="063db-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="063db-134">**So deaktivieren Sie einen DDL-Trigger**</span><span class="sxs-lookup"><span data-stu-id="063db-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="063db-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="063db-136">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="063db-137">**So aktivieren Sie einen DDL-Trigger**</span><span class="sxs-lookup"><span data-stu-id="063db-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="063db-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="063db-139">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="063db-140">**So löschen Sie einen DDL-Trigger**</span><span class="sxs-lookup"><span data-stu-id="063db-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="063db-141">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="063db-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
