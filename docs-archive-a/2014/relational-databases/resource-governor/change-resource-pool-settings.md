---
title: Ändern der Einstellungen für den Ressourcenpool | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697880"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="54624-102">Ändern der Einstellungen für den Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="54624-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="54624-103">Sie können die Einstellungen für Ressourcenpools in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="54624-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="54624-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="54624-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="54624-105">**So ändern Sie die Einstellungen eines Ressourcenpools mit:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="54624-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54624-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="54624-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="54624-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="54624-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="54624-108">Der maximale CPU-Prozentsatz muss gleich oder höher als der minimale CPU-Prozentsatz sein.</span><span class="sxs-lookup"><span data-stu-id="54624-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="54624-109">Der maximale Arbeitsspeicherprozentsatz muss gleich oder höher als der minimale Arbeitsspeicherprozentsatz sein.</span><span class="sxs-lookup"><span data-stu-id="54624-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="54624-110">Die Summe der minimalen CPU-Prozentsätze und minimalen Arbeitsspeicherprozentsätze für alle Ressourcenpools darf nicht größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="54624-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54624-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="54624-111">Permissions</span></span>  
 <span data-ttu-id="54624-112">Zum Ändern der Einstellungen für Ressourcenpools ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="54624-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="54624-113">Ändern der Einstellungen für Ressourcenpools in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54624-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="54624-114">**So ändern Sie Ressourcenpooleinstellungen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="54624-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="54624-115">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer und erweitern Sie rekursiv den Knoten **Verwaltung** bis einschließlich zum Eintrag **Ressourcenpools**.</span><span class="sxs-lookup"><span data-stu-id="54624-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="54624-116">Klicken Sie mit der rechten Maustaste auf den zu ändernden Ressourcenpool, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="54624-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="54624-117">Wählen Sie auf der Seite **Eigenschaften der Ressourcenkontrolle** die Zeile für den Ressourcenpool im Raster **Ressourcenpools** aus, sofern diese nicht automatisch ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="54624-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="54624-118">Klicken oder doppelklicken Sie auf die Zellen in der zu ändernden Zeile, und geben Sie die neuen Werte ein.</span><span class="sxs-lookup"><span data-stu-id="54624-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="54624-119">Klicken Sie auf **OK**, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="54624-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="54624-120">Ändern der Ressourcenpooleinstellungen mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54624-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="54624-121">**So ändern Sie Ressourcenpooleinstellungen in [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="54624-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="54624-122">Führen Sie die `ALTER RESOURCE POOL`-Anweisung aus, die die zu ändernden Eigenschaftswerte angibt.</span><span class="sxs-lookup"><span data-stu-id="54624-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="54624-123">Führen Sie die **ALTER RESOURCE GOVERNOR RECONFIGURE** -Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="54624-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="54624-124">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="54624-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="54624-125">Im folgenden Beispiel wird die maximale CPU-Prozenteinstellung für den Ressourcenpool `poolAdhoc`geändert.</span><span class="sxs-lookup"><span data-stu-id="54624-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="54624-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54624-126">See Also</span></span>  
 <span data-ttu-id="54624-127">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="54624-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="54624-128">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="54624-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="54624-129">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="54624-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="54624-130">[Löschen eines Ressourcenpools](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="54624-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="54624-131">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="54624-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="54624-132">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="54624-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="54624-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54624-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="54624-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54624-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
