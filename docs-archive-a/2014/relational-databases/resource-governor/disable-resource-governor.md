---
title: Deaktivieren der Ressourcenkontrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699404"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="3fba8-102">Deaktivieren der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="3fba8-102">Disable Resource Governor</span></span>
  <span data-ttu-id="3fba8-103">Sie können die Ressourcenkontrolle in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit Transact-SQL deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3fba8-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="3fba8-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="3fba8-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="3fba8-105">**So deaktivieren Sie den Resource Governor mit:**  [dem Objekt-Explorer](#RGOffObjEx), [Resource Governor-Eigenschaften](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="3fba8-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3fba8-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3fba8-106">Before You Begin</span></span>  
 <span data-ttu-id="3fba8-107">Wenn Sie die Ressourcenkontrolle deaktivieren, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3fba8-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="3fba8-108">Die Klassifizierungsfunktion wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3fba8-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="3fba8-109">Alle neuen Verbindungen werden automatisch der Standardarbeitsauslastungsgruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3fba8-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="3fba8-110">Vom System initiierte Anforderungen werden der internen Arbeitsauslastungsgruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3fba8-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="3fba8-111">Alle Einstellungen für bestehende Arbeitsauslastungsgruppen und Ressourcenpools werden auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3fba8-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="3fba8-112">In diesem Fall werden keine Ereignisse ausgelöst, wenn Grenzwerte erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="3fba8-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="3fba8-113">Die reguläre Systemüberwachung bleibt unbeeinflusst.</span><span class="sxs-lookup"><span data-stu-id="3fba8-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="3fba8-114">Sie können die Konfiguration ändern, die Änderungen treten jedoch erst in Kraft, wenn die Ressourcenkontrolle wieder aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="3fba8-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="3fba8-115">Beim Neustart von SQL Server lädt die Ressourcenkontrolle nicht ihre Konfiguration, sondern enthält lediglich die Standardarbeitsauslastungsgruppen und -pools sowie die internen Gruppen und Ressourcenpools.</span><span class="sxs-lookup"><span data-stu-id="3fba8-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="3fba8-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3fba8-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3fba8-117">Mithilfe der `ALTER RESOURCE GOVERNOR`-Anweisung können Sie die Ressourcenkontrolle während einer Benutzertransaktion nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3fba8-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3fba8-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3fba8-118">Permissions</span></span>  
 <span data-ttu-id="3fba8-119">Zum Deaktivieren der Ressourcenkontrolle ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3fba8-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="3fba8-120">Deaktivieren der Ressourcenkontrolle im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="3fba8-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="3fba8-121">**So deaktivieren Sie die Ressourcenkontrolle im Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="3fba8-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="3fba8-122">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fba8-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="3fba8-123">Klicken Sie mit der rechten Maustaste auf **Resource Governor**, und klicken Sie dann auf **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="3fba8-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="3fba8-124">Deaktivieren der Ressourcenkontrolle über die Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="3fba8-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="3fba8-125">**So deaktivieren Sie die Ressourcenkontrolle auf der Eigenschaftenseite der Ressourcenkontrolle**</span><span class="sxs-lookup"><span data-stu-id="3fba8-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="3fba8-126">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fba8-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="3fba8-127">Klicken Sie mit der rechten Maustaste auf **Resource Governor** , und klicken Sie dann auf **Eigenschaften**. Damit öffnen Sie die Seite **Eigenschaften des Resource Governors** .</span><span class="sxs-lookup"><span data-stu-id="3fba8-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="3fba8-128">Aktivieren Sie das Kontrollkästchen **Ressourcenkontrolle aktivieren** , stellen Sie sicher, dass Kontrollkästchen nicht aktiviert ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fba8-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="3fba8-129">Deaktivieren der Ressourcenkontrolle mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fba8-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="3fba8-130">**So deaktivieren Sie die Ressourcenkontrolle mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3fba8-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="3fba8-131">Führen Sie die Anweisung **ALTER RESOURCE GOVERNOR DISABLE** aus.</span><span class="sxs-lookup"><span data-stu-id="3fba8-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="3fba8-132">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3fba8-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3fba8-133">Im folgenden Beispiel wird die Ressourcenkontrolle aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3fba8-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fba8-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fba8-134">See Also</span></span>  
 <span data-ttu-id="3fba8-135">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="3fba8-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="3fba8-136">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="3fba8-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="3fba8-137">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="3fba8-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="3fba8-138">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="3fba8-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="3fba8-139">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="3fba8-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="3fba8-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fba8-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
