---
title: Aktivieren und Deaktivieren der Änderungsnachverfolgung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616953"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="112ea-102">Aktivieren und Deaktivieren der Änderungsnachverfolgung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="112ea-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="112ea-103">In diesem Thema wird beschrieben, wie Sie die Änderungsnachverfolgung für Datenbanken und Tabellen aktivieren und deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="112ea-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="112ea-104">Aktivieren der Änderungsnachverfolgung für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="112ea-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="112ea-105">Bevor Sie die Änderungsnachverfolgung verwenden können, müssen Sie die Änderungsnachverfolgung auf Datenbankebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="112ea-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="112ea-106">Im folgenden Beispiel wird gezeigt, wie die Änderungsnachverfolgung mit [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="112ea-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="112ea-107">Sie können die Änderungsnachverfolgung auch in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aktivieren. Verwenden Sie hierzu das Dialogfeld [Datenbankeigenschaften &#40;Seite Änderungsnachverfolgung&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="112ea-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="112ea-108">Bei der Aktivierung der Änderungsnachverfolgung können Sie die CHANGE_RETENTION-Option und die AUTO_CLEANUP-Option angeben. Die Werte können Sie nach der Aktivierung der Änderungsnachverfolgung jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="112ea-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="112ea-109">Der Änderungsbeibehaltungswert gibt den Zeitraum an, für den Änderungsnachverfolgungsinformationen geführt werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="112ea-110">Änderungsnachverfolgungsinformationen, die älter sind als der angegebene Zeitraum, werden in regelmäßigen Abständen entfernt.</span><span class="sxs-lookup"><span data-stu-id="112ea-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="112ea-111">Bei der Festlegung dieses Werts ist zu berücksichtigen, wie häufig Anwendungen mit den Tabellen in der Datenbank synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="112ea-112">Die angegebene Beibehaltungsdauer muss wenigstens so lange sein wie der maximale Zeitraum zwischen Synchronisierungen.</span><span class="sxs-lookup"><span data-stu-id="112ea-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="112ea-113">Ruft eine Anwendung Änderungen in längeren Intervallen ab, werden möglicherweise falsche Ergebnisse zurückgegeben, da einige Änderungsinformationen wahrscheinlich entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="112ea-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="112ea-114">Zur Vermeidung falscher Ergebnisse kann eine Anwendung die CHANGE_TRACKING_MIN_VALID_VERSION-Systemfunktion verwenden, um zu ermitteln, ob das Intervall zwischen den Synchronisierungen zu lang war.</span><span class="sxs-lookup"><span data-stu-id="112ea-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="112ea-115">Mit der AUTO_CLEANUP-Option können Sie den Cleanup-Task aktivieren oder deaktivieren, mit dem alte Nachverfolgungsinformationen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="112ea-116">Dies kann hilfreich sein, wenn ein temporäres Problem vorliegt, das eine Synchronisierung von Anwendungen verhindert, und der Prozess zum Entfernen von Änderungsnachverfolgungsinformationen, die älter sind als die Beibehaltungsdauer, angehalten werden muss, bis das Problem behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="112ea-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="112ea-117">Beachten Sie generell für Datenbanken, für die die Änderungsnachverfolgung verwendet wird, Folgendes:</span><span class="sxs-lookup"><span data-stu-id="112ea-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="112ea-118">Zur Verwendung der Änderungsnachverfolgung muss für den Datenbankkompatibilitätsgrad 90 oder höher festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="112ea-119">Wenn eine Datenbank einen Kompatibilitätsgrad von weniger als 90 aufweist, können Sie die Änderungsnachverfolgung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="112ea-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="112ea-120">Allerdings gibt dann die CHANGETABLE-Funktion, die verwendet wird, um Änderungsnachverfolgungsinformationen abzurufen, einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="112ea-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="112ea-121">Die Momentaufnahmeisolation ist die einfachste Möglichkeit, die Konsistenz aller Änderungsnachverfolgungsinformationen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="112ea-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="112ea-122">Aus diesem Grund sollte für die Momentaufnahmeisolation für die Datenbank auf jeden Fall ON festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="112ea-123">Weitere Informationen finden Sie unter [Verwenden der Änderungsnachverfolgung &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="112ea-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="112ea-124">Aktivieren der Änderungsnachverfolgung für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="112ea-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="112ea-125">Die Änderungsnachverfolgung muss für jede nachzuverfolgende Tabelle aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="112ea-126">Nach der Aktivierung der Änderungsnachverfolgung werden für alle Zeilen in der Tabelle, die von einem DML-Vorgang betroffen sind, Änderungsnachverfolgungsinformationen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="112ea-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="112ea-127">Im folgenden Beispiel wird gezeigt, wie die Änderungsnachverfolgung für eine Tabelle mit [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql)aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="112ea-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="112ea-128">Sie können die Änderungsnachverfolgung für eine Tabelle auch in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aktivieren. Verwenden Sie hierzu das Dialogfeld [Datenbankeigenschaften &#40;Seite Änderungsnachverfolgung&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="112ea-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="112ea-129">Ist für die TRACK_COLUMNS_UPDATED-Option ON festgelegt, speichert [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in der internen Änderungsnachverfolgungstabelle zusätzliche Informationen dazu, welche Spalten aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="112ea-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="112ea-130">Mit Spaltennachverfolgung kann eine Anwendung aktiviert werden, um nur die aktualisierten Spalten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="112ea-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="112ea-131">Hiermit können Effizienz und Leistung gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="112ea-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="112ea-132">Da die Verwaltung der Spaltennachverfolgungsinformationen jedoch zusätzlichen Speicherplatz beansprucht, ist diese Option standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="112ea-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="112ea-133">Deaktivieren der Änderungsnachverfolgung für Datenbanken oder Tabellen</span><span class="sxs-lookup"><span data-stu-id="112ea-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="112ea-134">Die Änderungsnachverfolgung muss zunächst für alle Tabellen mit Änderungsnachverfolgung deaktiviert werden, bevor die Änderungsnachverfolgung auch für die Datenbank deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="112ea-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="112ea-135">Ermitteln Sie für eine Datenbank die Tabellen mit aktivierter Änderungsnachverfolgung mit der [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) -Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="112ea-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="112ea-136">Wenn für keine Tabelle einer Datenbank Änderungen nachverfolgt werden, können Sie die Änderungsnachverfolgung für die Datenbank deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="112ea-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="112ea-137">Im folgenden Beispiel wird gezeigt, wie die Änderungsnachverfolgung für eine Datenbank mit [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="112ea-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="112ea-138">Im folgenden Beispiel wird gezeigt, wie die Änderungsnachverfolgung für eine Tabelle mit [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql)deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="112ea-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="112ea-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="112ea-139">See Also</span></span>  
 <span data-ttu-id="112ea-140">[Datenbankeigenschaften &#40;Seite Änderungsnachverfolgung&#41;](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="112ea-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="112ea-141">[ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="112ea-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="112ea-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="112ea-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="112ea-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="112ea-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="112ea-144">[Nachverfolgen von Datenänderungen &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="112ea-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="112ea-145">[Informationen zur Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="112ea-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="112ea-146">[Arbeiten mit Änderungsdaten &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="112ea-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="112ea-147">Verwalten der Änderungsnachverfolgung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="112ea-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
