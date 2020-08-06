---
title: SQL Server, Plancache-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696765"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="6201b-102">SQL Server, Plancache-Objekt</span><span class="sxs-lookup"><span data-stu-id="6201b-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="6201b-103">Das **Plancache**-Objekt stellt Indikatoren bereit, mit denen überwacht werden kann, wie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den Arbeitsspeicher zum Speichern von Objekten verwendet, z.B. gespeicherten Prozeduren, Ad-hoc-Anweisungen, vorbereiteten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen sowie Triggern.</span><span class="sxs-lookup"><span data-stu-id="6201b-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="6201b-104">Es können mehrere Instanzen des **Plancache** -Objekts gleichzeitig überwacht werden, wobei jede Instanz einen unterschiedlichen Typ von zu überwachendem Plan darstellt.</span><span class="sxs-lookup"><span data-stu-id="6201b-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="6201b-105">In dieser Tabelle werden die **SQLServer:Plancache**Leistungsindikatoren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6201b-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="6201b-106">SQL Server, Plancache-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="6201b-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="6201b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6201b-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="6201b-108">**Cachetrefferquote**</span><span class="sxs-lookup"><span data-stu-id="6201b-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="6201b-109">Das Verhältnis zwischen Cachetreffern und -suchvorgängen.</span><span class="sxs-lookup"><span data-stu-id="6201b-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="6201b-110">**Cacheobjektzähler**</span><span class="sxs-lookup"><span data-stu-id="6201b-110">**Cache Object Counts**</span></span>|<span data-ttu-id="6201b-111">Anzahl der Cacheobjekte im Cache.</span><span class="sxs-lookup"><span data-stu-id="6201b-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="6201b-112">**Cacheseiten**</span><span class="sxs-lookup"><span data-stu-id="6201b-112">**Cache Pages**</span></span>|<span data-ttu-id="6201b-113">Anzahl der von Cacheobjekten verwendeten 8-KB-Seiten.</span><span class="sxs-lookup"><span data-stu-id="6201b-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="6201b-114">**Verwendete Cacheobjekte**</span><span class="sxs-lookup"><span data-stu-id="6201b-114">**Cache Objects in use**</span></span>|<span data-ttu-id="6201b-115">Anzahl der verwendeten Cacheobjekte.</span><span class="sxs-lookup"><span data-stu-id="6201b-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="6201b-116">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="6201b-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="6201b-117">Plancache-Instanz</span><span class="sxs-lookup"><span data-stu-id="6201b-117">Plan Cache instance</span></span>|<span data-ttu-id="6201b-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6201b-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="6201b-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="6201b-119">**_Total**</span></span>|<span data-ttu-id="6201b-120">Informationen zu allen Typen von Cacheinstanzen.</span><span class="sxs-lookup"><span data-stu-id="6201b-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="6201b-121">**Sql-Pläne**</span><span class="sxs-lookup"><span data-stu-id="6201b-121">**Sql Plans**</span></span>|<span data-ttu-id="6201b-122">Abfragepläne, die von einer Ad-hoc- [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage, einschließlich automatisch parametrisierten Abfragen, oder durch [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen generiert wurden, die mit **sp_prepare** oder **sp_cursorprepare**vorbereitet wurden.</span><span class="sxs-lookup"><span data-stu-id="6201b-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6201b-123">speichert die Pläne für Ad-hoc- [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen für die spätere Wiederverwendung zwischen, wenn die identische [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung später ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6201b-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="6201b-124">Vom Benutzer parametrisierte Abfragen (selbst wenn sie nicht ausdrücklich vorbereitet sind) werden ebenfalls mit Prepared SQL Plans überwacht.</span><span class="sxs-lookup"><span data-stu-id="6201b-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="6201b-125">**Objektpläne**</span><span class="sxs-lookup"><span data-stu-id="6201b-125">**Object Plans**</span></span>|<span data-ttu-id="6201b-126">Abfragepläne, die durch Erstellen von gespeicherten Prozeduren, Funktionen oder Triggern generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6201b-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="6201b-127">**Gebundene Strukturen**</span><span class="sxs-lookup"><span data-stu-id="6201b-127">**Bound Trees**</span></span>|<span data-ttu-id="6201b-128">Normalisierte Strukturen für Sichten, Regeln, berechnete Spalten und CHECK-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="6201b-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="6201b-129">**Erweiterte gespeicherte Prozeduren**</span><span class="sxs-lookup"><span data-stu-id="6201b-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="6201b-130">Kataloginformationen für erweiterte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="6201b-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="6201b-131">**Temporäre Tabellen & Tabellenvariablen**</span><span class="sxs-lookup"><span data-stu-id="6201b-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="6201b-132">Cacheinformationen zu temporären Tabellen und Tabellenvariablen.</span><span class="sxs-lookup"><span data-stu-id="6201b-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6201b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6201b-133">See Also</span></span>  
 <span data-ttu-id="6201b-134">[Serverkonfigurationsoptionen für den Serverarbeitsspeicher](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="6201b-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="6201b-135">[SQL Server, Puffer-Manager-Objekt](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="6201b-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="6201b-136">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="6201b-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
