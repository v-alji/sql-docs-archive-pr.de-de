---
title: Erstellen eines Ressourcenpools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622528"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="e7d02-102">Erstellen eines Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="e7d02-102">Create a Resource Pool</span></span>
  <span data-ttu-id="e7d02-103">Mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]können Sie einen Ressourcenpool erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7d02-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="e7d02-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="e7d02-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="e7d02-105">**So erstellen Sie einen Ressourcenpool mit:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="e7d02-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7d02-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e7d02-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e7d02-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e7d02-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e7d02-108">Der maximale CPU-Prozentsatz muss gleich oder höher als der minimale CPU-Prozentsatz sein.</span><span class="sxs-lookup"><span data-stu-id="e7d02-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="e7d02-109">Der maximale Arbeitsspeicherprozentsatz muss gleich oder höher als der minimale Arbeitsspeicherprozentsatz sein.</span><span class="sxs-lookup"><span data-stu-id="e7d02-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="e7d02-110">Die Summe der minimalen CPU-Prozentsätze und minimalen Arbeitsspeicherprozentsätze für alle Ressourcenpools darf nicht größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="e7d02-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7d02-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e7d02-111">Permissions</span></span>  
 <span data-ttu-id="e7d02-112">Zum Erstellen eines Ressourcenpools ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7d02-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="e7d02-113">Erstellen eines Ressourcenpools in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7d02-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e7d02-114">**So erstellen Sie einen Ressourcenpool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e7d02-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="e7d02-115">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e7d02-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="e7d02-116">Klicken Sie mit der rechten Maustaste auf **Resource Governor**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e7d02-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e7d02-117">Klicken Sie im Raster **Ressourcenpools** auf die erste Spalte in der leeren Zeile.</span><span class="sxs-lookup"><span data-stu-id="e7d02-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="e7d02-118">Diese Spalte weist ein Sternchen (\*) auf.</span><span class="sxs-lookup"><span data-stu-id="e7d02-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="e7d02-119">Doppelklicken Sie auf die leere Zelle in der Spalte **Name** .</span><span class="sxs-lookup"><span data-stu-id="e7d02-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="e7d02-120">Geben Sie den gewünschten Namen für den Ressourcenpool ein.</span><span class="sxs-lookup"><span data-stu-id="e7d02-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="e7d02-121">Klicken oder doppelklicken Sie auf beliebige Zellen in der Zeile, die Sie sich ändern möchten, und geben Sie die neuen Werte ein.</span><span class="sxs-lookup"><span data-stu-id="e7d02-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="e7d02-122">Klicken Sie auf **OK**, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e7d02-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="e7d02-123">Erstellen eines Ressourcenpools mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7d02-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="e7d02-124">**So erstellen Sie einen Ressourcenpool in [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e7d02-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="e7d02-125">Führen Sie die `CREATE RESOURCE POOL`-Anweisung aus, und geben Sie dabei die festzulegenden Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="e7d02-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="e7d02-126">Führen Sie die **ALTER RESOURCE GOVERNOR RECONFIGURE** -Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="e7d02-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="e7d02-127">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e7d02-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="e7d02-128">Im folgenden Beispiel wird ein Ressourcenpool mit dem Namen `poolAdhoc`erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7d02-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7d02-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7d02-129">See Also</span></span>  
 <span data-ttu-id="e7d02-130">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="e7d02-131">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="e7d02-132">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="e7d02-133">[Ändern der Einstellungen für den Ressourcenpool](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="e7d02-134">[Löschen eines Ressourcenpools](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="e7d02-135">[Konfigurieren der Ressourcenkontrolle mit einer Vorlage](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="e7d02-136">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="e7d02-137">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="e7d02-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="e7d02-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7d02-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="e7d02-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7d02-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
