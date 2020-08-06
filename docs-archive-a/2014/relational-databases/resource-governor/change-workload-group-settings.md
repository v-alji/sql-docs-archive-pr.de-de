---
title: Ändern der Einstellungen von Arbeitsauslastungsgruppen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607629"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="44491-102">Ändern der Einstellungen von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="44491-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="44491-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]können Sie die Einstellungen von Arbeitsauslastungsgruppen ändern.</span><span class="sxs-lookup"><span data-stu-id="44491-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="44491-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="44491-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="44491-105">**So ändern Sie die Einstellungen einer Workloadgruppe mit:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="44491-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="44491-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="44491-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="44491-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="44491-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="44491-108">Sie können die Einstellungen der Standardarbeitsauslastungsgruppe und von benutzerdefinierten Arbeitsauslastungsgruppen ändern.</span><span class="sxs-lookup"><span data-stu-id="44491-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="44491-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="44491-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="44491-110">Der durch die Indexerstellung für eine nicht ausgerichtete partitionierte Tabelle belegte Arbeitsspeicher ist proportional zur Anzahl der beteiligten Partitionen.</span><span class="sxs-lookup"><span data-stu-id="44491-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="44491-111">Wenn der insgesamt erforderliche Arbeitsspeicher die Grenze übersteigt, die pro Abfrage von der Arbeitsauslastungsgruppe festgelegt wurde (REQUEST_MAX_MEMORY_GRANT_PERCENT), kann bei dieser Indexerstellung ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="44491-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="44491-112">Da die Standardarbeitsauslastungsgruppe Abfragen zulässt, die die pro Abfrage festgelegte Grenze mit dem mindestens für eine Kompatibilität mit SQL Server 2005 erforderlichen Arbeitsspeicher übersteigen, können Benutzer dieselbe Indexerstellung in der Standardarbeitsauslastungsgruppe ausführen. Voraussetzung ist, dass der Standardressourcenpool über ausreichend Gesamtarbeitsspeicher verfügt, um eine solche Abfrage ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="44491-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="44491-113">Bei der Indexerstellung darf mehr Arbeitsbereichsspeicher verwendet werden, als ursprünglich zugewiesen, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="44491-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="44491-114">Die Ressourcenkontrolle unterstützt diese besondere Behandlung, die ursprüngliche und alle weiteren Speicherzuweisungen werden jedoch durch die Einstellungen für Arbeitsauslastungsgruppe und Ressourcenpool begrenzt.</span><span class="sxs-lookup"><span data-stu-id="44491-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44491-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="44491-115">Permissions</span></span>  
 <span data-ttu-id="44491-116">Zum Ändern der Einstellungen von Arbeitsauslastungsgruppen ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="44491-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="44491-117">Ändern der Einstellungen von Arbeitsauslastungsgruppen in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44491-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="44491-118">**So ändern Sie die Einstellungen von Arbeitsauslastungsgruppen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="44491-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="44491-119">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** rekursiv nach unten, bis einschließlich des Ordners **Arbeitsauslastungsgruppen** , der die zu ändernde Arbeitsauslastungsgruppe enthält.</span><span class="sxs-lookup"><span data-stu-id="44491-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="44491-120">Klicken Sie mit der rechten Maustaste auf die zu ändernde Arbeitsauslastungsgruppe, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="44491-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="44491-121">Wählen Sie auf der Seite **Eigenschaften der Ressourcenkontrolle** die Zeile für die Arbeitsauslastungsgruppe im Raster **Arbeitsauslastungsgruppen für Ressourcenpool** aus, sofern diese nicht automatisch ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="44491-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="44491-122">Klicken oder doppelklicken Sie auf die Zellen in der zu ändernden Zeile, und geben Sie die neuen Werte ein.</span><span class="sxs-lookup"><span data-stu-id="44491-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="44491-123">Klicken Sie auf **OK**, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="44491-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="44491-124">Ändern der Einstellungen von Arbeitsauslastungsgruppen mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44491-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="44491-125">**So ändern Sie die Einstellungen von Arbeitsauslastungsgruppen mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="44491-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="44491-126">Führen Sie die ALTER WORKLOAD GROUP-Anweisung aus, und geben Sie dabei die zu ändernden Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="44491-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="44491-127">Führen Sie die ALTER RESOURCE GOVERNOR RECONFIGURE-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="44491-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="44491-128">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44491-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="44491-129">Im folgenden Beispiel wird die Einstellung für die maximale prozentuale Arbeitsspeicherzuweisung für die Arbeitsauslastungsgruppe `groupAdhoc`geändert.</span><span class="sxs-lookup"><span data-stu-id="44491-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="44491-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44491-130">See Also</span></span>  
 <span data-ttu-id="44491-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="44491-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="44491-132">[Erstellen einer Arbeitsauslastungsgruppe](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="44491-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="44491-133">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="44491-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="44491-134">[Ändern der Einstellungen für den Ressourcenpool](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="44491-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="44491-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44491-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="44491-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44491-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="44491-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44491-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
