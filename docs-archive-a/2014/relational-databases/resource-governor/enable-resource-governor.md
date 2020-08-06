---
title: Aktivieren der Ressourcenkontrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699398"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="f5a94-102">Aktivieren der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="f5a94-102">Enable Resource Governor</span></span>
  <span data-ttu-id="f5a94-103">Die Ressourcenkontrolle ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5a94-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="f5a94-104">Sie können die Ressourcenkontrolle in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit Transact-SQL aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5a94-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="f5a94-105">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="f5a94-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="f5a94-106">**So aktivieren Sie den Resource Governor mit:**  [dem Objekt-Explorer](#RGOnObjEx), [Resource Governor-Eigenschaften](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="f5a94-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f5a94-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f5a94-107">Before You Begin</span></span>  
 <span data-ttu-id="f5a94-108">Wenn Sie die Ressourcenkontrolle aktivieren, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f5a94-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="f5a94-109">Die Klassifizierungsfunktion wird für neue Verbindungen ausgeführt, damit deren Arbeitsauslastungen Arbeitsauslastungsgruppen zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="f5a94-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="f5a94-110">Die in der Konfiguration der Ressourcenkontrolle angegebenen Ressourcengrenzwerte werden überprüft und durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f5a94-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="f5a94-111">Alle Konfigurationsänderungen, die bei deaktivierter Ressourcenkontrolle vorgenommen wurden, wirken sich auf Anforderungen aus, die bereits bestanden, bevor die Ressourcenkontrolle aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="f5a94-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="f5a94-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f5a94-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f5a94-113">Mithilfe der `ALTER RESOURCE GOVERNOR`-Anweisung können Sie die Ressourcenkontrolle während einer Benutzertransaktion nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5a94-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f5a94-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f5a94-114">Permissions</span></span>  
 <span data-ttu-id="f5a94-115">Zum Aktivieren der Ressourcenkontrolle ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f5a94-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="f5a94-116">Aktivieren der Ressourcenkontrolle im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="f5a94-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="f5a94-117">**So aktivieren Sie die Ressourcenkontrolle im Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="f5a94-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="f5a94-118">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f5a94-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="f5a94-119">Klicken Sie mit der rechten Maustaste auf den **Resource Governor**, und klicken Sie anschließend auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="f5a94-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="f5a94-120">Aktivieren der Ressourcenkontrolle über die Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="f5a94-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="f5a94-121">**So aktivieren Sie die Ressourcenkontrolle auf der Eigenschaftenseite der Ressourcenkontrolle**</span><span class="sxs-lookup"><span data-stu-id="f5a94-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="f5a94-122">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f5a94-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="f5a94-123">Klicken Sie mit der rechten Maustaste auf **Resource Governor** , und klicken Sie dann auf **Eigenschaften**. Damit öffnen Sie die Seite **Eigenschaften des Resource Governors** .</span><span class="sxs-lookup"><span data-stu-id="f5a94-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="f5a94-124">Aktivieren Sie das Kontrollkästchen **Ressourcenkontrolle aktivieren** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5a94-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="f5a94-125">Aktivieren der Ressourcenkontrolle mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5a94-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="f5a94-126">**So aktivieren Sie die Ressourcenkontrolle mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="f5a94-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="f5a94-127">Führen Sie die **ALTER RESOURCE GOVERNOR RECONFIGURE** -Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="f5a94-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="f5a94-128">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f5a94-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="f5a94-129">Im folgenden Beispiel wird die Ressourcenkontrolle aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5a94-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a94-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5a94-130">See Also</span></span>  
 <span data-ttu-id="f5a94-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="f5a94-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="f5a94-132">[Deaktivieren der Ressourcenkontrolle](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="f5a94-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="f5a94-133">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="f5a94-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="f5a94-134">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="f5a94-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="f5a94-135">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="f5a94-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="f5a94-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f5a94-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
