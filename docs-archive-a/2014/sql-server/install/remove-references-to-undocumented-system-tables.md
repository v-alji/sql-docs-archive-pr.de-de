---
title: Entfernen von Verweisen auf nicht dokumentierte Systemtabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720848"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="41eaa-102">Entfernen von Verweisen auf nicht dokumentierte Systemtabellen</span><span class="sxs-lookup"><span data-stu-id="41eaa-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="41eaa-103">Viele Systemtabellen, die in früheren Versionen nicht dokumentiert waren, haben sich geändert oder sind nicht mehr vorhanden. Daher kann ihre Verwendung nach einem Upgrade zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="41eaa-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="41eaa-104">Da der Upgrade Advisor nach Verweisen auf Systemtabellennamen sucht, enthält sein Bericht Verweise auf alle Benutzertabellen, die dieselben Namen wie Systemtabellen haben.</span><span class="sxs-lookup"><span data-stu-id="41eaa-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="41eaa-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="41eaa-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="41eaa-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41eaa-106">Description</span></span>  
 <span data-ttu-id="41eaa-107">Die folgenden nicht dokumentierten Systemtabellen wurden entfernt:</span><span class="sxs-lookup"><span data-stu-id="41eaa-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="41eaa-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="41eaa-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="41eaa-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="41eaa-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="41eaa-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="41eaa-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="41eaa-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="41eaa-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="41eaa-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="41eaa-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="41eaa-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="41eaa-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="41eaa-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="41eaa-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="41eaa-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="41eaa-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="41eaa-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="41eaa-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="41eaa-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="41eaa-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="41eaa-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="41eaa-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="41eaa-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="41eaa-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="41eaa-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="41eaa-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="41eaa-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="41eaa-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="41eaa-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="41eaa-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="41eaa-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="41eaa-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="41eaa-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="41eaa-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="41eaa-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="41eaa-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="41eaa-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="41eaa-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="41eaa-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="41eaa-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="41eaa-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="41eaa-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="41eaa-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="41eaa-132">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="41eaa-132">Corrective Action</span></span>  
 <span data-ttu-id="41eaa-133">Ändern Sie die Anwendungen entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="41eaa-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="41eaa-134">Statt</span><span class="sxs-lookup"><span data-stu-id="41eaa-134">Instead of</span></span>|<span data-ttu-id="41eaa-135">Zweck</span><span class="sxs-lookup"><span data-stu-id="41eaa-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="41eaa-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="41eaa-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="41eaa-137">Die **tablefulltextpdingchanges** -Eigenschaft der OBJECTPROPERTYEX-Funktion.</span><span class="sxs-lookup"><span data-stu-id="41eaa-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="41eaa-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="41eaa-138">**syslocks**</span></span>|<span data-ttu-id="41eaa-139">dynamische Verwaltungs Sicht **sys. dm_tran_locks** oder sp_lock oder die **sys.sysLockInfo** -Kompatibilitäts Sicht.</span><span class="sxs-lookup"><span data-stu-id="41eaa-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="41eaa-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="41eaa-140">**sysproperties**</span></span>|<span data-ttu-id="41eaa-141">**sys. extended_properties** -Katalog Sicht oder die **fn_listextendedproperty** -Funktion</span><span class="sxs-lookup"><span data-stu-id="41eaa-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="41eaa-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="41eaa-142">**sysxlogins**</span></span>|<span data-ttu-id="41eaa-143">**sys. server_principals** -Katalog Sicht oder **syslogins** -Kompatibilitäts Sicht.</span><span class="sxs-lookup"><span data-stu-id="41eaa-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="41eaa-144">alle **spt_** Tabellen</span><span class="sxs-lookup"><span data-stu-id="41eaa-144">all **spt_** tables</span></span>|<span data-ttu-id="41eaa-145">Kein Ersatz verfügbar</span><span class="sxs-lookup"><span data-stu-id="41eaa-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41eaa-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41eaa-146">See Also</span></span>  
 <span data-ttu-id="41eaa-147">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="41eaa-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="41eaa-148">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="41eaa-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
