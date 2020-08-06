---
title: Verwalten von FileTables | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699777"
---
# <a name="manage-filetables"></a><span data-ttu-id="a87da-102">Verwalten von FileTables</span><span class="sxs-lookup"><span data-stu-id="a87da-102">Manage FileTables</span></span>
  <span data-ttu-id="a87da-103">Beschreibt allgemeine administrative Tasks zum Verwalten von FileTables.</span><span class="sxs-lookup"><span data-stu-id="a87da-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="a87da-104">Vorgehensweise: Abrufen einer Liste von FileTable-Objekten und damit in Verbindung stehenden Objekten</span><span class="sxs-lookup"><span data-stu-id="a87da-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="a87da-105">Um eine Liste von FileTables abzurufen, fragen Sie eine der folgenden Katalogsichten ab:</span><span class="sxs-lookup"><span data-stu-id="a87da-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="a87da-106">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a87da-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="a87da-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Überprüfen Sie den Wert der **is_filetable**-Spalte.)</span><span class="sxs-lookup"><span data-stu-id="a87da-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="a87da-108">Um eine Liste der systemdefinierten Objekte abzurufen, die bei der Erstellung der zugeordneten FileTables erstellt wurden, fragen Sie die Katalogsicht [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="a87da-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="a87da-109">Deaktivieren und erneutes Aktivieren von nicht transaktionalem Zugriff auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="a87da-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="a87da-110">Um den exklusiven Zugriff zu erhalten, der für bestimmte administrative Tasks erforderlich ist, müssen Sie möglicherweise nicht transaktionalen Zugriff vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a87da-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="a87da-111">**Verhalten der ALTER DATABASE-Anweisung beim Ändern der Ebene von nicht transaktionalem Zugriff**</span><span class="sxs-lookup"><span data-stu-id="a87da-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="a87da-112">Wenn Sie nicht transaktionalen Zugriff auf READ_ONLY oder OFF festgelegt haben, gibt der ALTER DATABASE-Befehl kein Steuerelement an den Benutzer zurück, solange offene Dateihandles vorhanden sind, die mit dem angeforderten Vorgang in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="a87da-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="a87da-113">Bei folgenden Dateihandles treten Konflikte mit diesem Vorgang auf:</span><span class="sxs-lookup"><span data-stu-id="a87da-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="a87da-114">Bei allen offenen Dateihandles beim Festlegen des Zugriffs auf **NONE**.</span><span class="sxs-lookup"><span data-stu-id="a87da-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="a87da-115">Alle offenen Dateihandles für Schreibzugriff beim Festlegen des Zugriffs auf **READ_ONLY**.</span><span class="sxs-lookup"><span data-stu-id="a87da-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="a87da-116">Informationen zum Abbrechen von offenen Dateihandles finden Sie unter [Abbrechen von einer FileTable zugeordneten offenen Dateihandles](#BasicsKilling) .</span><span class="sxs-lookup"><span data-stu-id="a87da-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="a87da-117">Wenn der ALTER DATABASE-Befehl abgebrochen wird oder mit einem Timeout endet, wird die Ebene des transaktionalen Zugriffs nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a87da-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="a87da-118">Wenn Sie die ALTER DATABASE-Anweisung mit einer WITH-\<termination>-Klausel aufrufen (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), werden alle geöffneten nicht transaktionalen Dateihandles abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a87da-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a87da-119">Durch das Abbrechen geöffneter Dateihandles verlieren Benutzer möglicherweise nicht gespeicherte Daten.</span><span class="sxs-lookup"><span data-stu-id="a87da-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="a87da-120">Dieses Verhalten ist mit dem Verhalten des Dateisystems selbst konsistent.</span><span class="sxs-lookup"><span data-stu-id="a87da-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="a87da-121">**Auswirkungen des Deaktivierens von nicht transaktionalem Zugriff**</span><span class="sxs-lookup"><span data-stu-id="a87da-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="a87da-122">Das Ändern der Ebene von nicht transaktionalem Zugriff auf Datenbankebene hat die folgenden Auswirkungen auf die FileTable-Verzeichnisse unter dem Verzeichnis auf Datenbankebene:</span><span class="sxs-lookup"><span data-stu-id="a87da-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="a87da-123">Wenn der Zugriff auf **NONE**festgelegt ist, kann auf alle FileTable-Verzeichnisse und ihre Inhalte nicht mehr zugegriffen werden. Zudem sind sie nicht mehr sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a87da-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="a87da-124">Wenn der Zugriff auf **READ_ONLY**festgelegt ist, sind alle FileTable-Verzeichnisse und ihre Inhalte ebenfalls schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="a87da-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="a87da-125">Das Deaktivieren von FILESTREAM auf Instanzebene hat die folgenden Auswirkungen auf Verzeichnisse auf Datenbankebene in dieser Instanz und die FileTable-Verzeichnisse darunter:</span><span class="sxs-lookup"><span data-stu-id="a87da-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="a87da-126">Keines der Verzeichnisse auf Datenbankebene auf der Instanz ist sichtbar, wenn FILESTREAM auf Instanzebene deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a87da-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="a87da-127">Vorgehensweise: Deaktivieren und erneutes Aktivieren von nicht transaktionalem Zugriff auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="a87da-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="a87da-128">Weitere Informationen zu dieser Einstellung finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="a87da-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="a87da-129">**So deaktivieren Sie vollständigen nicht transaktionalen Zugriff**</span><span class="sxs-lookup"><span data-stu-id="a87da-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="a87da-130">Rufen Sie die **ALTER DATABASE** -Anweisung auf, und legen Sie den Wert von **NON_TRANSACTED_ACCESS** auf **READ_ONLY** oder **OFF**fest.</span><span class="sxs-lookup"><span data-stu-id="a87da-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="a87da-131">**So aktivieren Sie vollständigen nicht transaktionalen Zugriff erneut**</span><span class="sxs-lookup"><span data-stu-id="a87da-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="a87da-132">Rufen Sie die **ALTER DATABASE** -Anweisung auf, und legen Sie den Wert von **NON_TRANSACTED_ACCESS** auf **FULL**fest.</span><span class="sxs-lookup"><span data-stu-id="a87da-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a><span data-ttu-id="a87da-133">Vorgehensweise: Sicherstellen der Sichtbarkeit der FileTable-Objekte in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a87da-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="a87da-134">Ein Verzeichnis auf Datenbankebene und die FileTable-Verzeichnisse darunter sind sichtbar, wenn alle folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="a87da-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="a87da-135">FILESTREAM ist auf Instanzebene aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a87da-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="a87da-136">Nicht transaktionaler Zugriff ist auf Datenbankebene aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a87da-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="a87da-137">Ein gültiges Verzeichnis wurde auf Datenbankebene angegeben.</span><span class="sxs-lookup"><span data-stu-id="a87da-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="a87da-138">Deaktivieren und erneutes Aktivieren des FileTable-Namespaces auf Tabellenebene</span><span class="sxs-lookup"><span data-stu-id="a87da-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="a87da-139">Durch Deaktivieren des FileTable-Namespaces werden alle systemdefinierten Einschränkungen und Trigger deaktiviert, die mit der FileTable erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a87da-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="a87da-140">Dies ist in Situationen hilfreich, in denen eine FileTable in großem Umfang mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Vorgängen ohne den Aufwand der FileTable-Semantikerzwingung neu organisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a87da-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="a87da-141">Durch diese Vorgänge kann die FileTable jedoch in einem inkonsistenten Status belassen werden, und das erneute Aktivieren des FileTable-Namespaces kann verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="a87da-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="a87da-142">Das Deaktivieren eines FileTable-Namespaces führt zu folgenden Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="a87da-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="a87da-143">FileTable-Spalten und -Daten werden nicht physisch aus der Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a87da-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="a87da-144">Das FileTable-Verzeichnis und die enthaltenen Dateien und Verzeichnisse verschwinden aus dem Dateisystem und sind für Datei-E/A-Zugriff nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a87da-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="a87da-145">Systemdefinierte FileTable-Spalten können nicht gelöscht und neu erstellt werden, sie verhalten sich jedoch bei DML-Vorgängen wie normale Spalten.</span><span class="sxs-lookup"><span data-stu-id="a87da-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="a87da-146">Offene Dateihandles verhindern, dass die FileTable-Einschränkungen deaktiviert werden, da für diesen Vorgang eine Schemasperre für die Tabelle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a87da-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="a87da-147">Die Erzwingung der gesamten FileTable-Semantik, einschließlich systemdefinierter Einschränkungen und Trigger, wird nach dem Deaktivieren des FileTable-Namespaces beendet.</span><span class="sxs-lookup"><span data-stu-id="a87da-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="a87da-148">Das erneute Aktivieren eines FileTable-Namespaces führt zu folgenden Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="a87da-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="a87da-149">Die FileTable wird auf Konsistenz überprüft.</span><span class="sxs-lookup"><span data-stu-id="a87da-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="a87da-150">Werden Inkonsistenzen festgestellt, wird ein Fehler ausgelöst, und die FileTable bleibt deaktiviert. Andernfalls wird die FileTable erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a87da-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="a87da-151">Die Erzwingung der FileTable-Semantik, einschließlich systemdefinierter Einschränkungen und Trigger, wird wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a87da-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="a87da-152">Das FileTable-Verzeichnis und die enthaltenen Dateien und Verzeichnisse werden im Dateisystem sichtbar und stehen zum Datei-E/A-Zugriff zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a87da-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="a87da-153">Vorgehensweise: Deaktivieren und erneutes Aktivieren des FileTable-Namespaces auf Tabellenebene</span><span class="sxs-lookup"><span data-stu-id="a87da-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="a87da-154">Rufen Sie die ALTER TABLE-Anweisung mit der Option **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** auf.</span><span class="sxs-lookup"><span data-stu-id="a87da-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="a87da-155">**So deaktivieren Sie den FileTable-Namespace**</span><span class="sxs-lookup"><span data-stu-id="a87da-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="a87da-156">**So aktivieren Sie den FileTable-Namespace erneut**</span><span class="sxs-lookup"><span data-stu-id="a87da-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="a87da-157">Abbrechen von einer FileTable zugeordneten offenen Dateihandles</span><span class="sxs-lookup"><span data-stu-id="a87da-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="a87da-158">Durch das Öffnen von Handles für Dateien, die in einer FileTable gespeichert sind, kann der exklusive Zugriff verhindert werden, der für bestimmte administrative Tasks erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a87da-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="a87da-159">Um dringende Tasks zu aktivieren, müssen Sie möglicherweise geöffnete Dateihandles, die einer oder mehreren FileTables zugeordnet sind, abbrechen.</span><span class="sxs-lookup"><span data-stu-id="a87da-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a87da-160">Durch das Abbrechen geöffneter Dateihandles verlieren Benutzer möglicherweise nicht gespeicherte Daten.</span><span class="sxs-lookup"><span data-stu-id="a87da-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="a87da-161">Dieses Verhalten ist mit dem Verhalten des Dateisystems selbst konsistent.</span><span class="sxs-lookup"><span data-stu-id="a87da-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="a87da-162">Vorgehensweise: Abrufen einer Liste von einem FileTable-Objekt zugeordneten offenen Dateihandles</span><span class="sxs-lookup"><span data-stu-id="a87da-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="a87da-163">Rufen Sie die Katalogsicht [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="a87da-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="a87da-164">Vorgehensweise: Abbrechen von einem FileTable-Objekt zugeordneten offenen Dateihandles</span><span class="sxs-lookup"><span data-stu-id="a87da-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="a87da-165">Rufen Sie die gespeicherte Prozedur [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) mit den entsprechenden Argumenten auf, um alle offenen Dateihandles in der Datenbank oder FileTable oder ein bestimmtes Handle abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="a87da-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a><span data-ttu-id="a87da-166">Vorgehensweise: Identifizieren der von FileTable-Objekten abgehaltenen Sperren</span><span class="sxs-lookup"><span data-stu-id="a87da-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="a87da-167">Die meisten von FileTables abgehaltenen Sperren entsprechen Dateien, die von Anwendungen geöffnet wurden.</span><span class="sxs-lookup"><span data-stu-id="a87da-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="a87da-168">**So identifizieren Sie geöffnete Dateien und die zugeordneten Sperren**</span><span class="sxs-lookup"><span data-stu-id="a87da-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="a87da-169">Verknüpfen Sie das **request_owner_id**-Feld in der dynamischen Verwaltungssicht [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) mit dem **fcb_id**-Feld in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a87da-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="a87da-170">In einigen Fällen entspricht die Sperre nicht einem einzigen geöffneten Dateihandle.</span><span class="sxs-lookup"><span data-stu-id="a87da-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="a87da-171">FileTable-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a87da-171">FileTable Security</span></span>  
 <span data-ttu-id="a87da-172">Die in FileTables gespeicherten Dateien und Verzeichnisse werden nur von SQL Server-Sicherheit gesichert.</span><span class="sxs-lookup"><span data-stu-id="a87da-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="a87da-173">Tabellen- und spaltenbasierte Sicherheit wird für Dateisystemzugriff sowie [!INCLUDE[tsql](../../includes/tsql-md.md)] -Zugriff erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a87da-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="a87da-174">Windows-Dateisystemsicherheits-APIs und ACL-Einstellungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a87da-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="a87da-175">Die für FILESTREAM-Dateigruppen und -Container geltenden Sicherheits- und Zugriffsberechtigungen gelten auch für FileTables, da die Dateidaten als FILESTREAM-Spalte in der FileTable gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a87da-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="a87da-176">**FileTable-Sicherheit und Transact-SQL-Zugriff**</span><span class="sxs-lookup"><span data-stu-id="a87da-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="a87da-177">Zugriff auf Daten in FileTables wird auf dieselbe Weise wie eine beliebige andere Tabelle gesichert.</span><span class="sxs-lookup"><span data-stu-id="a87da-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="a87da-178">Entsprechende Sicherheitsüberprüfungen auf Tabellen- und Spaltenebene werden für alle Vorgänge ausgeführt, die auf die Daten zugreifen oder sie ändern.</span><span class="sxs-lookup"><span data-stu-id="a87da-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="a87da-179">**FileTable-Sicherheit und Dateisystemzugriff**</span><span class="sxs-lookup"><span data-stu-id="a87da-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="a87da-180">Zum Öffnen eines Handles für eine Datei oder ein Verzeichnis, die bzw. das in der FileTable gespeichert ist, sind für Dateisystem-APIs entsprechende [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Berechtigungen für die gesamte Zeile in der FileTable (Tabellenebenenberechtigung) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a87da-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="a87da-181">Wenn der Benutzer nicht über die entsprechende [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Berechtigung für eine Spalte in der FileTable verfügt, wird der Dateisystemzugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="a87da-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="a87da-182">Sicherung und FileTables</span><span class="sxs-lookup"><span data-stu-id="a87da-182">Backup and FileTables</span></span>  
 <span data-ttu-id="a87da-183">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zum Sichern einer FileTable verwenden, werden die FILESTREAM-Daten zusammen mit den strukturierten Daten in der Datenbank gesichert</span><span class="sxs-lookup"><span data-stu-id="a87da-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="a87da-184">Wenn Sie die FILESTREAM-Daten nicht zusammen mit relationalen Daten sichern möchten, können Sie eine Teilsicherung durchführen, um die FILESTREAM-Dateigruppen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="a87da-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="a87da-185">**Transaktionskonsistenz von FileTable-Sicherungen**</span><span class="sxs-lookup"><span data-stu-id="a87da-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="a87da-186">Viele Verwaltungsprogramme und Vorgänge (einschließlich Sicherung, Protokollsicherung und Transaktionsreplikation) lesen transaktional konsistente Daten, indem sie die Transaktionsprotokolle lesen.</span><span class="sxs-lookup"><span data-stu-id="a87da-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="a87da-187">Derzeit werden als Teil einer Transaktion alle aktualisierten FILESTREAM-Daten gelesen.</span><span class="sxs-lookup"><span data-stu-id="a87da-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="a87da-188">Wenn nicht transaktionaler Zugriff nicht auf Datenbankebene aktiviert ist, arbeiten diese Programme und Vorgänge mit vollständiger Transaktionskonsistenz.</span><span class="sxs-lookup"><span data-stu-id="a87da-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="a87da-189">Wenn jedoch vollständiger nicht transaktionaler Zugriff aktiviert ist, könnte eine FileTable Daten enthalten, die später aktualisiert wurden (über ein nicht transaktionales Update) als die Transaktion, die das Programm oder der Prozess aus dem Transaktionsprotokoll liest.</span><span class="sxs-lookup"><span data-stu-id="a87da-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="a87da-190">Das heißt, dass eine Wiederherstellung einer bestimmten Transaktion zu einem bestimmten Zeitpunkt FILESTREAM-Daten enthalten kann, die aktueller als die betreffende Transaktion sind.</span><span class="sxs-lookup"><span data-stu-id="a87da-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="a87da-191">Dies ist das erwartete Verhalten, wenn nicht transaktionale Updates in FileTables zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a87da-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="a87da-192">SQL Server Profiler und FileTables</span><span class="sxs-lookup"><span data-stu-id="a87da-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a87da-193">Profiler kann Vorgänge zum Öffnen und Schließen von Dateien in Windows in der Ablaufverfolgungsausgabe für in einer FileTable gespeicherte Dateien aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="a87da-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="a87da-194">Überwachung und FileTables</span><span class="sxs-lookup"><span data-stu-id="a87da-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="a87da-195">Eine FileTable kann genau wie jede andere Tabelle überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="a87da-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="a87da-196">Win32-Zugriffsmuster sind jedoch keine satzbasierten Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="a87da-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="a87da-197">Eine einzelne Aktion im Dateisystem wird in mehrere Transact-SQL-DML-Vorgänge umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a87da-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="a87da-198">Das Öffnen einer Datei in Microsoft Word wird beispielsweise in mehrere open/close/create/rename/delete-Vorgänge und entsprechende Transact-SQL-DML-Aktivitäten umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a87da-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="a87da-199">Dies führt zu ausführlichen Überwachungsdatensätzen in Situationen, in denen es schwierig ist, Datensätze zwischen Dateisystemaktionen und entsprechenden Transact-SQL-DML-Überwachungsdatensätzen zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="a87da-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="a87da-200">DBCC und FileTables</span><span class="sxs-lookup"><span data-stu-id="a87da-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="a87da-201">Sie können die Einschränkungen für eine FileTable, einschließlich systemdefinierter Einschränkungen, mithilfe von DBCC CHECKCONSTRAINTS überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a87da-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a87da-202">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a87da-202">See Also</span></span>  
 <span data-ttu-id="a87da-203">[FileTable-Kompatibilität mit anderen SQL Server-Funktionen](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="a87da-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="a87da-204">FileTable-DDL, Funktionen, gespeicherte Prozeduren und Sichten</span><span class="sxs-lookup"><span data-stu-id="a87da-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
