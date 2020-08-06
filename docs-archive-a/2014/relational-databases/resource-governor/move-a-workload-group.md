---
title: Verschieben einer Arbeitsauslastungsgruppe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699392"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="201e4-102">Verschieben von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="201e4-102">Move a Workload Group</span></span>
  <span data-ttu-id="201e4-103">Arbeitsauslastungsgruppen der Ressourcenkontrolle können Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit Transact-SQL in einen anderen Ressourcenpool verschieben.</span><span class="sxs-lookup"><span data-stu-id="201e4-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="201e4-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="201e4-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="201e4-105">**So verschieben Sie eine Arbeitsauslastungsgruppe mit:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="201e4-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="201e4-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="201e4-106">Before You Begin</span></span>  
 <span data-ttu-id="201e4-107">Sie können keine Arbeitsauslastungsgruppen verschieben, wenn für die Ressourcenkontrolle ein Konfigurationsvorgang aussteht.</span><span class="sxs-lookup"><span data-stu-id="201e4-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="201e4-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="201e4-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="201e4-109">Sie können keine Arbeitsauslastungsgruppen verschieben, wenn für die Ressourcenkontrolle ein Konfigurationsvorgang aussteht.</span><span class="sxs-lookup"><span data-stu-id="201e4-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="201e4-110">Sie können feststellen, ob eine ausstehende Konfiguration vorliegt, indem Sie die dynamische Verwaltungssicht [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) abfragen, um den aktuellen Status von „is_configuration_pending“ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="201e4-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="201e4-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="201e4-111">Permissions</span></span>  
 <span data-ttu-id="201e4-112">Zum Verschieben einer Arbeitsauslastungsgruppe ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="201e4-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="201e4-113">Verschieben einer Arbeitsauslastungsgruppe in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="201e4-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="201e4-114">**So verschieben Sie eine Arbeitsauslastungsgruppe in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="201e4-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="201e4-115">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , bis der erweiterte Eintrag **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="201e4-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="201e4-116">Klicken Sie mit der rechten Maustaste auf **Resource Governor** , und klicken Sie dann auf **Eigenschaften**. Damit öffnen Sie die Seite **Eigenschaften des Resource Governors** .</span><span class="sxs-lookup"><span data-stu-id="201e4-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="201e4-117">Klicken Sie im Fenster **Ressourcenpools** auf den Ressourcenpool mit der zu verschiebenden Arbeitsauslastungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="201e4-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="201e4-118">Im Fenster **Arbeitsauslastungsgruppen** werden nun die Arbeitsauslastungsgruppen in diesem Ressourcenpool aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="201e4-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="201e4-119">Klicken Sie im Fenster **Arbeitsauslastungsgruppen** mit der rechten Maustaste links neben der zu verschiebenden Arbeitsauslastungsgruppe auf den Pfeil nach rechts, und klicken Sie auf **Verschieben nach**.</span><span class="sxs-lookup"><span data-stu-id="201e4-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="201e4-120">Daraufhin wird das Fenster **Arbeitsauslastungsgruppe verschieben** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="201e4-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="201e4-121">Verfügbare Ressourcenpools werden im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="201e4-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="201e4-122">Klicken Sie auf den Namen des Ressourcenpools, in den Sie die Arbeitsauslastungsgruppe verschieben möchten, und klicken Sie dann auf **OK** , um diese Aktion durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="201e4-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="201e4-123">Diese Aktion wird erst abgeschlossen, wenn Sie auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="201e4-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="201e4-124">Wenn Sie auf **OK**klicken, wird die Anweisung ALTER RESOURCE GOVERNOR RECONFIGURE ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="201e4-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="201e4-125">Schlägt der Erstellungs- oder Neukonfigurierungsvorgang für den Ressourcenpool oder die Arbeitsauslastungsgruppe fehl, wird unter dem Titel der Eigenschaftenseite eine zusammenfassende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="201e4-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="201e4-126">Klicken Sie auf den Abwärtspfeil an der Fehlermeldung, um eine ausführliche Fehlermeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="201e4-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="201e4-127">Verschieben einer Arbeitsauslastungsgruppe mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="201e4-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="201e4-128">**So verschieben Sie eine Arbeitsauslastungsgruppe mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="201e4-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="201e4-129">Führen Sie die `ALTER WORKLOAD GROUP`-Anweisung aus, und geben Sie dabei den Namen der zu verschiebenden Arbeitsauslastungsgruppe sowie die Ressource an, in die diese verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="201e4-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="201e4-130">Führen Sie die **ALTER RESOURCE GOVERNOR RECONFIGURE** -Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="201e4-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="201e4-131">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="201e4-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="201e4-132">Im folgenden Beispiel wird die Arbeitsauslastungsgruppe `groupAdhoc` in den Standardressourcenpool verschoben.</span><span class="sxs-lookup"><span data-stu-id="201e4-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="201e4-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="201e4-133">See Also</span></span>  
 <span data-ttu-id="201e4-134">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="201e4-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="201e4-135">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="201e4-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="201e4-136">[Erstellen eines Ressourcenpools](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="201e4-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="201e4-137">[Erstellen einer Arbeitsauslastungsgruppe](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="201e4-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="201e4-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="201e4-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="201e4-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="201e4-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
