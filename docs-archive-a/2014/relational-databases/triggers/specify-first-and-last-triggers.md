---
title: Angeben des ersten und des letzten Triggers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621914"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="7dfa7-102">Angeben des ersten und des letzten Triggers</span><span class="sxs-lookup"><span data-stu-id="7dfa7-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="7dfa7-103">Sie können angeben, dass einer der AFTER-Trigger, der einer Tabelle zugeordnet ist, der erste oder der letzte AFTER-Trigger ist, der für jede der auslösenden INSERT-, DELETE- und UPDATE-Aktionen ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="7dfa7-104">Die AFTER-Trigger, die zwischen dem ersten und letzten Trigger ausgelöst werden, werden in einer nicht definierten Reihenfolge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="7dfa7-105">Um die Ausführungsreihenfolge für einen AFTER-Trigger anzugeben, verwenden Sie die gespeicherte Prozedur **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="7dfa7-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="7dfa7-106">**sp_settriggerorder** besitzt die folgenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="7dfa7-107">Option</span><span class="sxs-lookup"><span data-stu-id="7dfa7-107">Option</span></span>|<span data-ttu-id="7dfa7-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7dfa7-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7dfa7-109">**First**</span><span class="sxs-lookup"><span data-stu-id="7dfa7-109">**First**</span></span>|<span data-ttu-id="7dfa7-110">Gibt an, dass der DML-Trigger der erste AFTER-Trigger ist, der für eine Triggeraktion ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="7dfa7-111">**Last**</span><span class="sxs-lookup"><span data-stu-id="7dfa7-111">**Last**</span></span>|<span data-ttu-id="7dfa7-112">Gibt an, dass der DML-Trigger der letzte AFTER-Trigger ist, der für eine Triggeraktion ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="7dfa7-113">**None**</span><span class="sxs-lookup"><span data-stu-id="7dfa7-113">**None**</span></span>|<span data-ttu-id="7dfa7-114">Gibt an, dass keine besondere Reihenfolge vorhanden ist, in der der DML-Trigger ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="7dfa7-115">Diese Option wird hauptsächlich verwendet, um einen ersten oder letzten Trigger zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="7dfa7-116">Das folgende Beispiel zeigt die Verwendung von **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="7dfa7-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7dfa7-117">Der erste und der letzte Trigger müssen zwei unterschiedliche Trigger sein.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="7dfa7-118">Für eine Tabelle können gleichzeitig INSERT-, UPDATE- und DELETE-Trigger definiert sein.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="7dfa7-119">Jeder Anweisungstyp kann über eigene erste und letzte Trigger verfügen; es darf sich dabei jedoch nicht um dieselben Trigger handeln.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="7dfa7-120">Wenn der für eine Tabelle definierte erste oder letzte Trigger keine Triggeraktion abdeckt, wie beispielsweise FOR UPDATE, FOR DELETE oder FOR INSERT, gibt es keinen ersten oder letzten Trigger für die fehlenden Aktionen.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="7dfa7-121">INSTEAD OF-Trigger können nicht als erste oder letzte Trigger angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="7dfa7-122">INSTEAD OF-Trigger werden ausgelöst, bevor Updates an den zugrunde liegenden Tabellen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="7dfa7-123">Wenn die Updates an zugrunde liegenden Tabellen durch einen INSTEAD OF-Trigger vorgenommen werden, erfolgen die Updates, bevor einer der für die Tabelle definierten AFTER-Trigger ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="7dfa7-124">Wenn z. B. ein INSTEAD OF INSERT-Trigger für eine Sicht Daten in eine Basistabelle einfügt und die Basistabelle selbst einen INSTEAD OF INSERT-Trigger und drei AFTER INSERT-Trigger enthält, wird der INSTEAD OF INSERT-Trigger für die Basistabelle statt der Einfügeaktion ausgelöst, und die AFTER-Trigger für die Basistabelle werden nach einer Einfügeaktion für die Basistabelle ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="7dfa7-125">Weitere Informationen finden Sie unter [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="7dfa7-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="7dfa7-126">Wenn eine ALTER TRIGGER-Anweisung den ersten oder letzten Trigger ändert, wird das **First** - oder **Last** -Attribut gelöscht, und der Reihenfolgewert wird auf **None**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="7dfa7-127">Die Reihenfolge muss mit **sp_settriggerorder**zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="7dfa7-128">Die OBJECTPROPERTY-Funktion gibt mithilfe der **ExecIsFirstTrigger** - und **ExecIsLastTrigger**-Eigenschaften an, ob es sich um einen ersten oder letzten Trigger handelt.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="7dfa7-129">Die Replikation generiert automatisch einen ersten Trigger für alle Tabellen, die in einem Abonnement mit sofortigem Update oder verzögertem Update über eine Warteschlange enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="7dfa7-130">Für die Replikation gilt, dass ihr Trigger der erste Trigger sein muss.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="7dfa7-131">Die Replikation meldet einen Fehler, wenn Sie versuchen, eine Tabelle, die einen ersten Trigger aufweist, in ein Abonnement mit sofortigem Update bzw. verzögertem Update über eine Warteschlange einzufügen.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="7dfa7-132">Wenn Sie versuchen, einen Trigger zum ersten Trigger zu erklären, nachdem eine Tabelle in ein Abonnement aufgenommen wurde, gibt **sp_settriggerorder** einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="7dfa7-133">Wenn Sie ALTER für den Replikationstrigger verwenden oder **sp_settriggerorder** verwenden, um den Replikationstrigger auf einen Trigger vom Typ LAST oder NONE festzulegen, funktioniert das Abonnement nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="7dfa7-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfa7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7dfa7-134">See Also</span></span>  
 <span data-ttu-id="7dfa7-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dfa7-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="7dfa7-136">sp_settriggerorder &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7dfa7-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
