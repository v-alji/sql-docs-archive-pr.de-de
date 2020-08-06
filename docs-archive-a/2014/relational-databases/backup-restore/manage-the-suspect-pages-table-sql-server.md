---
title: Verwalten der suspect_pages-Tabelle (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622709"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="a6f8b-102">Verwalten der suspect_pages-Tabelle (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a6f8b-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="a6f8b-103">In diesem Thema wird beschrieben, wie Sie die **suspect_pages** -Tabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verwalten.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a6f8b-104">Die **suspect_pages** -Tabelle, die zum Verwalten von Informationen über fehlerverdächtige Seiten verwendet wird, ist hilfreich für die Entscheidung, ob eine Wiederherstellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="a6f8b-105">Die [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) -Tabelle befindet sich in der [msdb](../databases/msdb-database.md)-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="a6f8b-106">Eine Seite wird als "fehlerverdächtig" betrachtet , wenn das [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] bei dem Versuch, eine Datenseite zu lesen, einen der folgenden Fehler findet:</span><span class="sxs-lookup"><span data-stu-id="a6f8b-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="a6f8b-107">Ein [823-Fehler](../errors-events/mssqlserver-823-database-engine-error.md) , der durch eine vom Betriebssystem ausgegebene zyklische Redundanz Prüfung (CRC) verursacht wurde, z. b. ein Datenträger Fehler (bestimmte Hardwarefehler).</span><span class="sxs-lookup"><span data-stu-id="a6f8b-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="a6f8b-108">[824-Fehler](../errors-events/mssqlserver-824-database-engine-error.md), z. b. eine zerrissene Seite (logischer Fehler)</span><span class="sxs-lookup"><span data-stu-id="a6f8b-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="a6f8b-109">Die Seiten-ID jeder fehlerverdächtigen Seite wird in der **suspect_pages** -Tabelle aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="a6f8b-110">Das [!INCLUDE[ssDE](../../includes/ssde-md.md)] zeichnet alle fehlerverdächtigen Seiten auf, die während der regulären Verarbeitung auftreten, z. B. bei folgenden Vorgängen:</span><span class="sxs-lookup"><span data-stu-id="a6f8b-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="a6f8b-111">Eine Abfrage muss eine Seite lesen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="a6f8b-112">Während eines DBCC CHECKDB-Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="a6f8b-113">Während eines Sicherungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="a6f8b-114">Die **suspect_pages** -Tabelle wird ggf. auch während eines Wiederherstellungsvorgangs, eines DBCC-Reparaturvorgangs oder eines Datenbanklöschvorgangs aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="a6f8b-115">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a6f8b-116">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a6f8b-117">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a6f8b-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a6f8b-118">Security</span><span class="sxs-lookup"><span data-stu-id="a6f8b-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a6f8b-119">**So verwalten Sie die "suspect_pages"-Tabelle mit**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="a6f8b-120">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6f8b-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a6f8b-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6f8b-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a6f8b-122">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a6f8b-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a6f8b-123">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a6f8b-123">Recommendations</span></span>  
  
-   <span data-ttu-id="a6f8b-124">**In der suspect_pages-Tabelle aufgezeichnete Fehler**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="a6f8b-125">Die **suspect_pages** -Tabelle enthält eine Zeile für jede Seite mit einem Fehler vom Typ 824 (maximal 1.000 Zeilen).</span><span class="sxs-lookup"><span data-stu-id="a6f8b-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="a6f8b-126">Die folgenden Tabellen enthalten Fehler, die in der **event_type** -Spalte der **suspect_pages** -Tabelle protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="a6f8b-127">Fehlerbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a6f8b-127">Error description</span></span>|<span data-ttu-id="a6f8b-128">**event_type** -Wert</span><span class="sxs-lookup"><span data-stu-id="a6f8b-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="a6f8b-129">Ein Fehler vom Typ 823, der durch einen vom Betriebssystem ausgegebenen CRC-Fehler verursacht wird, oder ein Fehler vom Typ 824, der außer einer fehlerhaften Prüfsumme oder einer zerrissenen Seite z. B. eine fehlerhafte Seiten-ID anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="a6f8b-130">1</span><span class="sxs-lookup"><span data-stu-id="a6f8b-130">1</span></span>|  
    |<span data-ttu-id="a6f8b-131">Fehlerhafte Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="a6f8b-131">Bad checksum</span></span>|<span data-ttu-id="a6f8b-132">2</span><span class="sxs-lookup"><span data-stu-id="a6f8b-132">2</span></span>|  
    |<span data-ttu-id="a6f8b-133">Zerrissene Seite</span><span class="sxs-lookup"><span data-stu-id="a6f8b-133">Torn page</span></span>|<span data-ttu-id="a6f8b-134">3</span><span class="sxs-lookup"><span data-stu-id="a6f8b-134">3</span></span>|  
    |<span data-ttu-id="a6f8b-135">Wiederhergestellt (die Seite wurde wiederhergestellt, nachdem sie als beschädigt markiert wurde)</span><span class="sxs-lookup"><span data-stu-id="a6f8b-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="a6f8b-136">4</span><span class="sxs-lookup"><span data-stu-id="a6f8b-136">4</span></span>|  
    |<span data-ttu-id="a6f8b-137">Repariert (DBCC, AlwaysOn oder Datenbankspiegelung hat die Seite repariert)</span><span class="sxs-lookup"><span data-stu-id="a6f8b-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="a6f8b-138">5</span><span class="sxs-lookup"><span data-stu-id="a6f8b-138">5</span></span>|  
    |<span data-ttu-id="a6f8b-139">Zuordnung durch DBCC aufgehoben</span><span class="sxs-lookup"><span data-stu-id="a6f8b-139">Deallocated by DBCC</span></span>|<span data-ttu-id="a6f8b-140">7</span><span class="sxs-lookup"><span data-stu-id="a6f8b-140">7</span></span>|  
  
     <span data-ttu-id="a6f8b-141">In der **suspect_pages** -Tabelle werden auch vorübergehende Fehler aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="a6f8b-142">Ursachen für vorübergehende Fehler sind beispielsweise E/A-Fehler (z. B. eine fehlende Kabelverbindung) oder eine Seite, die einen wiederholten Prüfsummentest vorübergehend nicht besteht.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="a6f8b-143">**Vorgehensweise der Datenbank-Engine beim Aktualisieren der "suspect_pages"-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="a6f8b-144">[!INCLUDE[ssDE](../../includes/ssde-md.md)] führt folgende Aktionen in der **suspect_pages** -Tabelle aus:</span><span class="sxs-lookup"><span data-stu-id="a6f8b-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="a6f8b-145">Wenn die Tabelle nicht voll ist, wird sie für jeden Fehler vom Typ 824 aktualisiert, um anzuzeigen, dass ein Fehler aufgetreten ist, und die Fehleranzahl wird erhöht.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="a6f8b-146">Wenn eine Seite einen Fehler aufweist, nachdem sie durch eine Reparatur, eine Wiederherstellung oder das Aufheben einer Zuordnung repariert wurde, wird die zugehörige **number_of_errors** -Fehleranzahl erhöht, und die zugehörige **last_update** -Spalte wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="a6f8b-147">Nachdem eine aufgelistete Seite durch einen Wiederherstellungs- oder Reparaturvorgang repariert wurde, aktualisiert der Vorgang die **suspect_pages** -Zeile, um anzuzeigen, dass die Seite repariert (**event_type** = 5) oder wiederhergestellt (**event_type** = 4) wurde.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="a6f8b-148">Wenn eine DBCC-Überprüfung ausgeführt wird, markiert die Überprüfung alle fehlerfreien Seiten als repariert (**event_type** = 5) oder als Seiten, deren Zuordnung aufgehoben wurde (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="a6f8b-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="a6f8b-149">**Automatische Updates der "suspect_pages"-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="a6f8b-150">Die **suspect_pages** -Tabelle wird von einem Datenbank-Spiegelungspartner oder AlwaysOn-Verfügbarkeitsreplikat aktualisiert, nachdem bei einem Versuch, eine Seite aus einer Datendatei zu lesen, aus einem der folgenden Gründe ein Fehler aufgetreten ist:</span><span class="sxs-lookup"><span data-stu-id="a6f8b-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="a6f8b-151">Fehler vom Typ 823, der von einem durch das Betriebssystem ausgegebenen CRC-Fehler verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="a6f8b-152">Fehler vom Typ 824 (logische Beschädigung, z. B. eine zerrissene Seite).</span><span class="sxs-lookup"><span data-stu-id="a6f8b-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="a6f8b-153">Die folgenden Aktionen aktualisieren auch automatisch Zeilen in der **suspect_pages** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="a6f8b-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS aktualisiert die **suspect_pages** -Tabelle, um jede Seite anzugeben, deren Zuordnung aufgehoben wurde oder die repariert wurde.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="a6f8b-155">Eine vollständige, Datei- oder Seitenwiederherstellung markiert die Seiteneinträge als wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="a6f8b-156">Die folgenden Aktionen löschen automatisch Zeilen aus der **suspect_pages** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="a6f8b-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="a6f8b-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="a6f8b-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="a6f8b-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="a6f8b-159">**Verwaltungsrolle des Datenbankadministrators**</span><span class="sxs-lookup"><span data-stu-id="a6f8b-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="a6f8b-160">Datenbankadministratoren sind zuständig für das Verwalten der Tabelle, insbesondere indem sie alte Zeilen löschen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="a6f8b-161">Die Größe der **suspect_pages** -Tabelle ist beschränkt, und wenn sie voll ist, werden keine neuen Fehler mehr protokolliert.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="a6f8b-162">Um zu verhindern, dass sich diese Tabelle füllt, muss der Datenbankadministrator oder Systemadministrator durch das Löschen von Zeilen die alten Einträge manuell aus der Tabelle löschen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="a6f8b-163">Aus diesem Grund wird empfohlen, Zeilen mit einem wiederhergestellten oder reparierten **event_type** -Objekt oder Zeilen mit einem alten **last_update** -Wert regelmäßig zu löschen bzw. zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="a6f8b-164">Sie können die [Database Suspect Data Page-Ereignsklasse](../event-classes/database-suspect-data-page-event-class.md)verwenden, um die Aktivität in der suspect_pages-Tabelle zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="a6f8b-165">Der **suspect_pages** -Tabelle werden aufgrund vorübergehender Fehler manchmal Zeilen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="a6f8b-166">Wenn der Tabelle viele Zeilen hinzugefügt werden, liegt möglicherweise bereits ein Fehler in Bezug auf das E/A-Subsystem vor.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="a6f8b-167">Wenn Sie feststellen, dass die Anzahl der Tabelle hinzugefügter Zeilen plötzlich ansteigt, sollten Sie die möglichen Ursachen hierfür in Ihrem E/A-Subsystem untersuchen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="a6f8b-168">Ein Datenbankadministrator kann auch Datensätze einfügen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="a6f8b-169">Das Aktualisieren einer Zeile ist z. B. sinnvoll, wenn der Datenbankadministrator weiß, dass eine bestimmte fehlerverdächtige Seite tatsächlich intakt ist, den Datensatz jedoch für eine Weile erhalten möchte.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a6f8b-170">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a6f8b-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a6f8b-171">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a6f8b-171">Permissions</span></span>  
 <span data-ttu-id="a6f8b-172">Jeder mit Zugriff auf **msdb** kann die Daten in der Tabelle **suspect_pages** lesen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="a6f8b-173">Jeder mit UPDATE-Berechtigung für die suspect_pages-Tabelle kann ihre Datensätze aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="a6f8b-174">Mitglieder der festen Datenbankrolle **db_owner** auf **msdb** oder der festen Serverrolle **sysadmin** können Datensätze einfügen, aktualisieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a6f8b-175">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6f8b-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="a6f8b-176">So verwalten Sie die "suspect_pages"-Tabelle</span><span class="sxs-lookup"><span data-stu-id="a6f8b-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="a6f8b-177">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]her, erweitern Sie diese Instanz und dann **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="a6f8b-178">Erweitern Sie **Systemdatenbanken**, **msdb**, **Tabellen**und anschließend **Systemtabellen**.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="a6f8b-179">Erweitern Sie **dbo.suspect_pages** , und klicken Sie mit der rechten Maustaste auf **Die ersten 200 Zeilen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="a6f8b-180">Bearbeiten, aktualisieren oder löschen Sie im Abfragefenster die gewünschten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a6f8b-181">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6f8b-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="a6f8b-182">So verwalten Sie die "suspect_pages"-Tabelle</span><span class="sxs-lookup"><span data-stu-id="a6f8b-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="a6f8b-183">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6f8b-184">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a6f8b-185">Kopieren Sie die folgenden Beispiele, fügen Sie sie in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="a6f8b-186">Im folgenden Beispiel werden einige Zeilen aus der `suspect_pages` -Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="a6f8b-187">In diesem Beispiel werden die ungültigen Seiten in der Tabelle `suspect_pages` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a6f8b-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6f8b-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6f8b-188">See Also</span></span>  
 <span data-ttu-id="a6f8b-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="a6f8b-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="a6f8b-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a6f8b-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="a6f8b-193">[Wiederherstellung von Seiten &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="a6f8b-194">[suspect_pages &#40;Transact-SQL-&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="a6f8b-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="a6f8b-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="a6f8b-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="a6f8b-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
