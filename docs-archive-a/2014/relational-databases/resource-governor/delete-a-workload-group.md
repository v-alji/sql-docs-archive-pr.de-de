---
title: Löschen von Arbeitsauslastungsgruppen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699417"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="fb353-102">Löschen von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="fb353-102">Delete a Workload Group</span></span>
  <span data-ttu-id="fb353-103">Eine Arbeitsauslastungsgruppe oder einen Ressourcenpool können Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit Transact-SQL löschen.</span><span class="sxs-lookup"><span data-stu-id="fb353-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="fb353-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="fb353-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="fb353-105">**So löschen Sie eine Arbeitsauslastungsgruppe mit:**  [dem Objekt-Explorer](#DelWGObjEx), [Resource Governor-Eigenschaften](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="fb353-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fb353-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="fb353-106">Before You Begin</span></span>  
 <span data-ttu-id="fb353-107">Sie können keine Arbeitsauslastungsgruppe löschen, die aktive Sitzungen enthält.</span><span class="sxs-lookup"><span data-stu-id="fb353-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="fb353-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fb353-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="fb353-109">Falls eine Arbeitsauslastungsgruppe aktive Sitzungen enthält, tritt beim Löschen bzw. Verschieben der Arbeitsauslastungsgruppe in einen anderen Ressourcenpool ein Fehler auf, wenn Sie die ALTER RESOURCE GOVERNOR RECONFIGURE-Anweisung aufrufen, um die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="fb353-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="fb353-110">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="fb353-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="fb353-111">Warten Sie, bis die Verbindungen für alle Sitzungen der entsprechenden Gruppe geschlossen wurden, und führen Sie dann die ALTER RESOURCE GOVERNOR RECONFIGURE-Anweisung noch einmal aus.</span><span class="sxs-lookup"><span data-stu-id="fb353-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="fb353-112">Stoppen Sie die Sitzungen in der betreffenden Gruppe explizit mit dem KILL-Befehl, und führen Sie die ALTER RESOURCE GOVERNOR RECONFIGURE-Anweisung noch einmal aus.</span><span class="sxs-lookup"><span data-stu-id="fb353-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="fb353-113">Falls Sie beschließen, die aktiven Sitzungen nicht explizit zu beenden, nachdem Sie **Löschen** verwendet, die Sitzungen jedoch noch nicht gestoppt haben, erstellen Sie die Gruppe noch einmal mit dem ursprünglichen Namen und verschieben sie in den ursprünglichen Ressourcenpool.</span><span class="sxs-lookup"><span data-stu-id="fb353-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="fb353-114">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="fb353-114">Restart the server.</span></span> <span data-ttu-id="fb353-115">Nach Abschluss des Neustarts wird die gelöschte Gruppe nicht erstellt und die neue Ressourcenpoolzuordnung wird von einer verschobenen Gruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb353-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fb353-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fb353-116">Permissions</span></span>  
 <span data-ttu-id="fb353-117">Zum Löschen einer Arbeitsauslastungsgruppe ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb353-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="fb353-118">Löschen einer Arbeitsauslastungsgruppe im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="fb353-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="fb353-119">**So löschen Sie eine Arbeitsauslastungsgruppe im Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="fb353-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="fb353-120">Öffnen Sie in[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer und erweitern Sie rekursiv den Knoten **Verwaltung** bis einschließlich zum Eintrag **Ressourcenpools**.</span><span class="sxs-lookup"><span data-stu-id="fb353-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="fb353-121">Erweitern Sie im Ressourcenpool rekursiv den Knoten **Ressourcenpools** bis einschließlich zum Knoten **Arbeitsauslastungsgruppen** , der die zu löschende Arbeitsauslastungsgruppe enthält.</span><span class="sxs-lookup"><span data-stu-id="fb353-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="fb353-122">Klicken Sie mit der rechten Maustaste auf die Arbeitsauslastungsgruppe, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="fb353-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="fb353-123">Im Fenster **Objekt löschen** wird die Arbeitsauslastungsgruppe in der Liste **Zu löschendes Objekt** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb353-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="fb353-124">Um die Arbeitsauslastungsgruppe zu löschen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb353-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="fb353-125">Löschen einer Arbeitsauslastungsgruppe über die Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="fb353-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="fb353-126">**So löschen Sie eine Arbeitsauslastungsgruppe auf der Seite "Eigenschaften der Ressourcenkontrolle"**</span><span class="sxs-lookup"><span data-stu-id="fb353-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="fb353-127">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** so lange, bis der Eintrag **Ressourcenpools**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb353-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="fb353-128">Klicken Sie mit der rechten Maustaste auf den Ressourcenpool, der die zu löschende Arbeitsauslastungsgruppe enthält, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fb353-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="fb353-129">Die Seite **Eigenschaften der Ressourcenkontrolle** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb353-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="fb353-130">Klicken Sie im Fenster **Arbeitsauslastungsgruppen für Ressourcenpool** auf die Zeile für die zu löschende Arbeitsauslastungsgruppe, klicken Sie dann links neben der Zeile mit der rechten Maustaste auf den Pfeil nach rechts, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="fb353-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="fb353-131">Um die Arbeitsauslastungsgruppe zu löschen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb353-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="fb353-132">Löschen einer Arbeitsauslastungsgruppe mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb353-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="fb353-133">**So löschen Sie eine Arbeitsauslastungsgruppe mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="fb353-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="fb353-134">Führen Sie die `DROP WORKLOAD GROUP`-Anweisung aus, die den Namen der zu löschenden Arbeitsauslastungsgruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="fb353-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="fb353-135">Stellen Sie sicher, dass in der zu löschenden Arbeitsauslastungsgruppe keine Anforderungen mehr aktiv sind, bevor Sie die `ALTER RESOURCE GOVERNOR RECONFIGURE`-Anweisung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="fb353-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="fb353-136">Wenn aktive Anforderungen vorhanden sind, tritt bei `ALTER RESOURCE GOVERNOR` ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="fb353-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="fb353-137">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="fb353-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="fb353-138">Warten Sie, bis alle Sitzungen der Arbeitsauslastungsgruppe die Verbindung geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="fb353-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="fb353-139">Beenden Sie Sitzungen in der Arbeitsauslastungsgruppe explizit mit dem `KILL`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb353-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="fb353-140">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="fb353-140">Restart the server.</span></span> <span data-ttu-id="fb353-141">Die Arbeitsauslastungsgruppe wird nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="fb353-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="fb353-142">Falls Sie nach Ausgabe der `DROP WORKLOAD GROUP`-Anweisung beschließen, dass Sie keine Sitzungen explizit stoppen möchten, um die Änderung zu übernehmen, können Sie die Gruppe mit dem gleichen Namen, den sie vor Ausgabe der DROP-Anweisung hatte, neu erstellen und dann in den ursprünglichen Ressourcenpool verschieben.</span><span class="sxs-lookup"><span data-stu-id="fb353-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="fb353-143">Führen Sie die- `ALTER RESOURCE GOVERNOR RECONFIGURE` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="fb353-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="fb353-144">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb353-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="fb353-145">Das folgende Beispiel löscht die Arbeitsauslastungsgruppe `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="fb353-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb353-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb353-146">See Also</span></span>  
 <span data-ttu-id="fb353-147">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="fb353-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="fb353-148">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="fb353-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="fb353-149">[Erstellen einer Arbeitsauslastungsgruppe](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="fb353-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="fb353-150">[Löschen eines Ressourcenpools](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="fb353-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="fb353-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb353-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="fb353-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb353-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="fb353-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb353-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
