---
title: Für Ad-hoc-Arbeitsauslastungen optimieren (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697162"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="d254c-102">Für Ad-hoc-Arbeitsauslastungen optimieren (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="d254c-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="d254c-103">Die Option **Optimieren für Ad-hoc-Arbeitsauslastung** wird zum Verbessern der Effizienz des Plancaches für Arbeitsauslastungen verwendet, die viele Ad-hoc-Batches für die einmalige Verwendung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d254c-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="d254c-104">Wenn diese Option auf 1 festgelegt ist, speichert [!INCLUDE[ssDE](../../includes/ssde-md.md)] statt des vollständigen kompilierten Plans einen kleinen Stub des kompilierten Plans in dem Plancache, wenn ein Batch erstmalig ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d254c-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="d254c-105">Dadurch wird die Auslastung des Arbeitsspeichers reduziert, indem verhindert wird, dass der Plancache mit kompilierten Plänen gefüllt wird, die nicht wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d254c-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="d254c-106">Der Stub des kompilierten Plans ermöglicht [!INCLUDE[ssDE](../../includes/ssde-md.md)] zu erkennen, dass dieser Ad-hoc-Batch bereits kompiliert worden ist, jedoch nur ein Stub des kompilierten Plans gespeichert worden ist, sodass [!INCLUDE[ssDE](../../includes/ssde-md.md)] den Batch kompiliert, wenn er erneut aufgerufen (kompiliert oder ausgeführt) wird, dann den Stub des kompilierten Plans aus dem Plancache entfernt und den vollständigen kompilierten Plan zum Plancache hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d254c-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="d254c-107">Wenn **Optimieren für Ad-hoc-Arbeitsauslastungen** auf 1 festgelegt wird, wirkt sich dies ausschließlich auf neue Pläne aus. Pläne, die sich bereits im Plancache befinden, sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="d254c-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="d254c-108">Der Stub des kompilierten Plans ist einer der cacheobjtypes, die von der sys.dm_exec_cached_plans-Katalogsicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d254c-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="d254c-109">Er verfügt über einen eindeutigen SQL-Handle und Planhandle.</span><span class="sxs-lookup"><span data-stu-id="d254c-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="d254c-110">Dem Stub des kompilierten Plans ist kein Ausführungsplan zugeordnet, und die Abfrage des Planhandles gibt keinen XML-Showplan zurück.</span><span class="sxs-lookup"><span data-stu-id="d254c-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="d254c-111">Ablaufverfolgungsflag 8032 setzt die Cachelimitparameter auf die RTM-Einstellung von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] zurück, die im Allgemeinen einen größeren Cache zulässt.</span><span class="sxs-lookup"><span data-stu-id="d254c-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="d254c-112">Verwenden Sie diese Einstellung, wenn häufig wiederverwendete Cacheeinträge nicht in den Cache passen, und wenn das Problem mit dem Plancache durch die *Serverkonfigurations-Option Optimierung für Ad-hoc-Arbeitsauslastung* nicht behoben werden konnte.</span><span class="sxs-lookup"><span data-stu-id="d254c-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d254c-113">Ablaufverfolgungsflag 8032 kann die Leistung mindern, wenn große Caches weniger Arbeitsspeicher für andere Arbeitsspeicherconsumer, z. B. den Pufferpool, verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="d254c-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d254c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d254c-114">See Also</span></span>  
 <span data-ttu-id="d254c-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d254c-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="d254c-116">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d254c-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
