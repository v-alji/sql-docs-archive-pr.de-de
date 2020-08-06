---
title: Löschen eines Ressourcenpools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699405"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="ca312-102">Löschen eines Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="ca312-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="ca312-103">Einen Ressourcenpool können Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit Transact-SQL löschen.</span><span class="sxs-lookup"><span data-stu-id="ca312-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="ca312-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ca312-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="ca312-105">**So löschen Sie einen Ressourcenpool mit:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="ca312-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ca312-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ca312-106">Before You Begin</span></span>  
 <span data-ttu-id="ca312-107">Ressourcenpools mit Arbeitsauslastungsgruppen können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ca312-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ca312-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ca312-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ca312-109">Standardpools oder interne Ressourcenpools der Ressourcenkontrolle können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ca312-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="ca312-110">Ressourcenpools mit Arbeitsauslastungsgruppen können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ca312-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="ca312-111">Weitere Informationen finden Sie unter [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="ca312-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ca312-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca312-112">Permissions</span></span>  
 <span data-ttu-id="ca312-113">Zum Löschen eines Ressourcenpools ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca312-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="ca312-114">Löschen eines Ressourcenpools im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="ca312-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="ca312-115">**So löschen Sie einen Ressourcenpool in SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ca312-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="ca312-116">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ca312-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="ca312-117">Klicken Sie mit der rechten Maustaste auf den zu löschenden Ressourcenpool, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ca312-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="ca312-118">Im Fenster **Objekt löschen** wird der Ressourcenpool in der Liste **Zu löschendes Objekt** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ca312-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="ca312-119">Um den Ressourcenpool zu löschen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca312-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca312-120">Falls der zu löschende Ressourcenpool eine Arbeitsauslastungsgruppe enthält, schlägt dieser Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="ca312-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="ca312-121">Löschen eines Ressourcenpools mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ca312-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="ca312-122">**So löschen Sie einen Ressourcenpool mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ca312-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="ca312-123">Führen Sie die `DROP RESOURCE POOL`-Anweisung aus, die den Namen des zu löschenden Ressourcenpools angeben.</span><span class="sxs-lookup"><span data-stu-id="ca312-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="ca312-124">Führen Sie die **ALTER RESOURCE GOVERNOR RECONFIGURE** -Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="ca312-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="ca312-125">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ca312-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ca312-126">Das folgende Beispiel löscht die Arbeitsauslastungsgruppe `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="ca312-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca312-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca312-127">See Also</span></span>  
 <span data-ttu-id="ca312-128">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ca312-129">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="ca312-130">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="ca312-131">[Ändern der Einstellungen für den Ressourcenpool](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="ca312-132">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="ca312-133">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="ca312-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="ca312-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ca312-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="ca312-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ca312-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="ca312-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ca312-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
