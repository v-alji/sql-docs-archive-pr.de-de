---
title: Erstellen einer Arbeitsauslastungsgruppe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group create
- workload groups [SQL Server], create
ms.assetid: 072868ec-ceff-4db6-941b-281af731a067
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 144bcef57b3d6e191b03b1539e9e7382a9085c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616472"
---
# <a name="create-a-workload-group"></a><span data-ttu-id="e3ac0-102">Erstellen einer Arbeitsauslastungsgruppe</span><span class="sxs-lookup"><span data-stu-id="e3ac0-102">Create a Workload Group</span></span>
  <span data-ttu-id="e3ac0-103">Sie können Arbeitsauslastungsgruppen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-103">You can create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="e3ac0-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="e3ac0-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="e3ac0-105">**Erstellen einer Arbeitsauslastungsgruppe mit:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="e3ac0-105">**To create a workload group, using:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3ac0-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e3ac0-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e3ac0-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e3ac0-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e3ac0-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="e3ac0-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="e3ac0-109">Der durch die Indexerstellung für eine nicht ausgerichtete partitionierte Tabelle belegte Arbeitsspeicher ist proportional zur Anzahl der beteiligten Partitionen.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-109">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="e3ac0-110">Wenn der insgesamt erforderliche Arbeitsspeicher die Grenze übersteigt, die pro Abfrage von der Arbeitsauslastungsgruppe festgelegt wurde (REQUEST_MAX_MEMORY_GRANT_PERCENT), kann bei dieser Indexerstellung ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-110">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="e3ac0-111">Da die Standardarbeitsauslastungsgruppe Abfragen zulässt, die die pro Abfrage festgelegte Grenze mit dem mindestens für eine Kompatibilität mit SQL Server 2005 erforderlichen Arbeitsspeicher übersteigen, können Benutzer dieselbe Indexerstellung in der Standardarbeitsauslastungsgruppe ausführen. Voraussetzung ist, dass der Standardressourcenpool über ausreichend Gesamtarbeitsspeicher verfügt, um eine solche Abfrage ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-111">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="e3ac0-112">Bei der Indexerstellung darf mehr Arbeitsbereichsspeicher verwendet werden, als ursprünglich zugewiesen, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-112">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="e3ac0-113">Die Ressourcenkontrolle unterstützt diese besondere Behandlung, die ursprüngliche und alle weiteren Speicherzuweisungen werden jedoch durch die Einstellungen für Arbeitsauslastungsgruppe und Ressourcenpool begrenzt.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-113">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3ac0-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e3ac0-114">Permissions</span></span>  
 <span data-ttu-id="e3ac0-115">Zum Erstellen einer Arbeitsauslastungsgruppe ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-115">Creating a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-workload-group-using-sql-server-management-studio"></a><a name="CreWGProp"></a> <span data-ttu-id="e3ac0-116">Erstellen einer Arbeitsauslastungsgruppe in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3ac0-116">Create a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e3ac0-117">**So erstellen Sie Arbeitsauslastungsgruppen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e3ac0-117">**To create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="e3ac0-118">Erweitern Sie im Objekt-Explorer rekursiv den Knoten **Verwaltung** , bis einschließlich zum Ressourcenpool mit der zu ändernden Arbeitsauslastungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-118">In Object Explorer, recursively expand the **Management** node down to and including the resource pool that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="e3ac0-119">Klicken Sie mit der rechten Maustaste auf den Ordner **Arbeitsauslastungsgruppen** , und klicken Sie dann auf **Neue Arbeitsauslastungsgruppe**.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-119">Right-click the **Workload Groups** folder, and then click **New Workload Group**.</span></span>  
  
3.  <span data-ttu-id="e3ac0-120">Stellen Sie im Raster **Ressourcenpools** sicher, dass der Ressourcenpool, dem Sie die Arbeitsauslastungsgruppe hinzufügen möchten, markiert ist.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-120">In the **Resource pools** grid, ensure the resource pool where you want to add the workload group is highlighted.</span></span>  
  
4.  <span data-ttu-id="e3ac0-121">Das Raster **Arbeitsauslastungsgruppen für Ressourcenpool** weist eine neue Zeile mit einem leeren Namen und Standardwerten in den anderen Spalten auf.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-121">The **Workload groups for resource pool** grid will have a new line with a blank name and default values in the other columns.</span></span>  
  
5.  <span data-ttu-id="e3ac0-122">Klicken Sie auf die Zelle **Name** , und geben Sie einen Namen für die Arbeitsauslastungsgruppe ein.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-122">Click the **Name** cell and enter a name for the workload group.</span></span>  
  
6.  <span data-ttu-id="e3ac0-123">Klicken oder doppelklicken Sie auf beliebige andere Zellen in der Zeile, deren Standardeinstellungen Sie aufheben möchten, und geben Sie jeweils die neuen Werte ein.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-123">Click or double-click any other cells in the row you want to change from their default settings, and enter the new values.</span></span>  
  
7.  <span data-ttu-id="e3ac0-124">Klicken Sie auf **OK**, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-124">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-workload-group-using-transact-sql"></a><a name="CreWGTSQL"></a> <span data-ttu-id="e3ac0-125">Erstellen einer Arbeitsauslastungsgruppe mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ac0-125">Create a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="e3ac0-126">**So erstellen Sie Arbeitsauslastungsgruppen in [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e3ac0-126">**To create a workload group by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="e3ac0-127">Führen Sie die CREATE WORKLOAD GROUP-Anweisung aus, und geben Sie dabei die festzulegenden Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-127">Run the CREATE WORKLOAD GROUP statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="e3ac0-128">Führen Sie die ALTER RESOURCE GOVERNOR RECONFIGURE-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-128">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="e3ac0-129">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3ac0-129">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="e3ac0-130">Im folgenden Beispiel wird im Ressourcenpool `groupAdhoc` die Arbeitsauslastungsgruppe `poolAdhoc`erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-130">The following example creates a workload group named `groupAdhoc` in the resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE WORKLOAD GROUP groupAdhoc  
USING poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3ac0-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3ac0-131">See Also</span></span>  
 <span data-ttu-id="e3ac0-132">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-132">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="e3ac0-133">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-133">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="e3ac0-134">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-134">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="e3ac0-135">[Ändern der Einstellungen von Arbeitsauslastungsgruppen](change-workload-group-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-135">[Change Workload Group Settings](change-workload-group-settings.md) </span></span>  
 <span data-ttu-id="e3ac0-136">[Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion](create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-136">[Create and Test a Classifier User-Defined Function](create-and-test-a-classifier-user-defined-function.md) </span></span>  
 <span data-ttu-id="e3ac0-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3ac0-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="e3ac0-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3ac0-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
