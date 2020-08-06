---
title: Aktivieren und Deaktivieren von Change Data Capture (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617862"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="1232f-102">Aktivieren und Deaktivieren von Change Data Capture (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1232f-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="1232f-103">In diesem Thema wird beschrieben, wie Sie Change Data Capture für Datenbanken und Tabelle aktivieren und deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="1232f-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="1232f-104">Aktivieren von Change Data Capture für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="1232f-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="1232f-105">Bevor eine Aufzeichnungsinstanz für einzelne Tabellen erstellt werden kann, muss ein Mitglied der festen Serverrolle `sysadmin` zuerst die Datenbank für Change Data Capture aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1232f-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="1232f-106">Dies erfolgt durch Ausführen der gespeicherten Prozedur [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) im Kontext der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1232f-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="1232f-107">Um zu bestimmen, ob die Datenbank bereits aktiviert ist, fragen Sie die `is_cdc_enabled`-Spalte in der `sys.databases`-Katalogsicht ab.</span><span class="sxs-lookup"><span data-stu-id="1232f-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="1232f-108">Wenn eine Datenbank für Change Data Capture aktiviert ist, werden das `cdc`-Schema, der `cdc`-Benutzer, Metadatentabellen und andere Systemobjekte für die Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="1232f-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="1232f-109">Das `cdc`-Schema enthält die Metadatentabellen für Change Data Capture, und sobald die Quelltabellen für Change Data Capture aktiviert wurden, dienen die einzelnen Änderungstabellen als Repository für die Änderungsdaten.</span><span class="sxs-lookup"><span data-stu-id="1232f-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="1232f-110">Das `cdc`-Schema enthält außerdem zugeordnete Systemfunktionen, die verwendet werden, um Änderungsdaten abzufragen.</span><span class="sxs-lookup"><span data-stu-id="1232f-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="1232f-111">Change Data Capture erfordert die exklusive Verwendung des `cdc`-Schemas und des `cdc`-Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1232f-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="1232f-112">Wenn entweder ein Schema oder ein Datenbankbenutzer namens *cdc* schon in der Datenbank vorhanden ist, kann diese so lange für Change Data Capture nicht aktiviert werden, bis das Schema oder der Benutzer gelöscht oder umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="1232f-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="1232f-113">Ein Beispiel für das Aktivieren einer Datenbank finden Sie in der Vorlage "Datenbank für Change Data Capture aktivieren".</span><span class="sxs-lookup"><span data-stu-id="1232f-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1232f-114">Um die Vorlagen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu suchen, rufen Sie **Ansicht**auf, klicken Sie auf **Vorlagen-Explorer**, und wählen Sie dann **SQL Server-Vorlagen**aus.</span><span class="sxs-lookup"><span data-stu-id="1232f-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="1232f-115">**Change Data Capture** ist ein Unterordner.</span><span class="sxs-lookup"><span data-stu-id="1232f-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="1232f-116">In diesem Ordner finden Sie alle Vorlagen, auf die in diesem Thema verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1232f-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="1232f-117">Es gibt auch ein **Vorlagen-Explorer** -Symbol auf der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="1232f-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="1232f-118">Deaktivieren von Change Data Capture für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="1232f-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="1232f-119">Ein Mitglied der `sysadmin` Fixed-Server Rolle kann die gespeicherte Prozedur [sys. sp_cdc_disable_db &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) im Daten Bank Kontext ausführen, um Change Data Capture für eine Datenbank zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1232f-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="1232f-120">Es ist nicht notwendig, einzelne Tabellen zu deaktivieren, bevor Sie die Datenbank deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1232f-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="1232f-121">Durch das Deaktivieren der Datenbank werden alle mit ihr verbundenen Change Data Capture-Metadaten entfernt, einschließlich des `cdc`-Benutzers und -Schemas und der Change Data Capture-Aufträge.</span><span class="sxs-lookup"><span data-stu-id="1232f-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="1232f-122">Durch Change Data Capture erstellte Gatingrollen werden jedoch nicht automatisch entfernt und müssen explizit gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="1232f-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="1232f-123">Um zu bestimmen, ob die Datenbank aktiviert ist, fragen Sie die `is_cdc_enabled`-Spalte in der sys.databases-Katalogsicht ab.</span><span class="sxs-lookup"><span data-stu-id="1232f-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="1232f-124">Wenn eine Datenbank, für die Change Data Capture aktiviert ist, gelöscht wird, werden Change Data Capture-Aufträge automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="1232f-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="1232f-125">Ein Beispiel für das Deaktivieren einer Datenbank finden Sie in der Vorlage "Datenbank für Change Data Capture deaktivieren".</span><span class="sxs-lookup"><span data-stu-id="1232f-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1232f-126">Um die Vorlagen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu suchen, rufen Sie **Ansicht**auf, klicken Sie auf **Vorlagen-Explorer**, und klicken Sie dann auf **SQL Server-Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="1232f-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="1232f-127">**Change Data Capture** ist ein Unterordner, in dem Sie alle Vorlagen finden, auf die in diesem Thema verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1232f-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="1232f-128">Es gibt auch ein **Vorlagen-Explorer** -Symbol auf der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="1232f-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="1232f-129">Aktivieren von Change Data Capture für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="1232f-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="1232f-130">Nachdem eine Datenbank für Change Data Capture aktiviert ist, können Mitglieder der festen Datenbankrolle `db_owner` eine Aufzeichnungsinstanz für einzelne Quelltabellen mithilfe der gespeicherten Prozedur `sys.sp_cdc_enable_table` erstellen.</span><span class="sxs-lookup"><span data-stu-id="1232f-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="1232f-131">Um zu bestimmen, ob eine Quelltabelle bereits für Change Data Capture aktiviert ist, überprüfen Sie die is_tracked_by_cdc column-Spalte in der`sys.tables`-Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="1232f-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="1232f-132">Wenn Sie eine Aufzeichnungsinstanz erstellen, können Sie die folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="1232f-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="1232f-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="1232f-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="1232f-134">Standardmäßig werden alle Spalten in der Quelltabelle als aufgezeichnete Spalten identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1232f-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="1232f-135">Wenn nur eine Teilmenge der Spalten nachverfolgt werden muss, z. b. aus Datenschutz-oder Leistungsgründen, verwenden Sie den- *@captured_column_list* Parameter, um die Teilmenge der Spalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1232f-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="1232f-136">Standardmäßig befindet sich die Änderungstabelle in der Standarddateigruppe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1232f-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="1232f-137">Datenbankbesitzer, die die Platzierung einzelner Änderungs Tabellen steuern möchten, können den- *@filegroup_name* Parameter verwenden, um eine bestimmte Datei Gruppe für die Änderungs Tabelle anzugeben, die der Aufzeichnungs Instanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1232f-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="1232f-138">Die benannte Dateigruppe muss bereits vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1232f-138">The named filegroup must already exist.</span></span> <span data-ttu-id="1232f-139">Im Allgemeinen empfehlen wir, Änderungstabellen in eine von den Quelltabellen getrennte Dateigruppe einzufügen.</span><span class="sxs-lookup"><span data-stu-id="1232f-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="1232f-140">`Enable a Table Specifying Filegroup Option`Ein Beispiel für die Verwendung des-Parameters finden Sie in der Vorlage *@filegroup_name* .</span><span class="sxs-lookup"><span data-stu-id="1232f-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="1232f-141">Der Zweck der benannten Rolle besteht darin, den Zugriff auf die Änderungsdaten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1232f-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="1232f-142">Die angegebene Rolle kann eine vorhandene feste Serverrolle oder eine Datenbankrolle sein.</span><span class="sxs-lookup"><span data-stu-id="1232f-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="1232f-143">Wenn die angegebene Rolle nicht bereits vorhanden ist, wird automatisch eine Datenbankrolle mit diesem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1232f-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="1232f-144">Mitglieder der Rollen `sysadmin` oder `db_owner` haben vollen Zugriff auf die Daten in den Änderungstabellen.</span><span class="sxs-lookup"><span data-stu-id="1232f-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="1232f-145">Alle anderen Benutzer müssen über die SELECT-Berechtigung für alle aufgezeichneten Spalten der Quelltabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="1232f-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="1232f-146">Ist eine Rolle angegeben, müssen Benutzer, die nicht Mitglieder der Rollen `sysadmin` oder `db_owner` sind, darüber hinaus Mitglieder der angegebenen Rolle sein.</span><span class="sxs-lookup"><span data-stu-id="1232f-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="1232f-147">Wenn Sie keine Gating-Rolle verwenden möchten, legen Sie den- *@role_name* Parameter explizit auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="1232f-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="1232f-148">Ein Beispiel für das Aktivieren einer Tabelle ohne Gatingrolle finden Sie unter `Enable a Table Without Using a Gating Role`.</span><span class="sxs-lookup"><span data-stu-id="1232f-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="1232f-149">Eine Aufzeichnungsinstanz umfasst immer eine Tabellenwertfunktion, um alle Änderungstabelleneinträge zurückzugeben, die innerhalb eines definierten Intervalls auftreten.</span><span class="sxs-lookup"><span data-stu-id="1232f-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="1232f-150">Diese Funktion wird benannt, indem der Name der Aufzeichnungsinstanz an "cdc.fn_cdc_get_all_changes_" angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1232f-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="1232f-151">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1232f-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="1232f-152">Wenn der-Parameter *@supports_net_changes* auf 1 festgelegt ist, wird auch eine NET Changes-Funktion für die Aufzeichnungs Instanz generiert.</span><span class="sxs-lookup"><span data-stu-id="1232f-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="1232f-153">Diese Funktion gibt für jede einzelne Zeile, die innerhalb des beim Aufruf angegebenen Intervalls geändert wurde, nur eine Änderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1232f-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="1232f-154">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1232f-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="1232f-155">Zur Unterstützung von Abfragen für Nettoänderungen muss die Quelltabelle einen Primärschlüssel oder einen eindeutigen Index aufweisen, damit die Zeilen eindeutig identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="1232f-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="1232f-156">Wenn ein eindeutiger Index verwendet wird, muss der Name des Indexes mithilfe des- *@index_name* Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1232f-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="1232f-157">Die für den Primärschlüssel oder den eindeutigen Index definierten Spalten müssen in der Liste der aufgezeichneten Quellspalten enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="1232f-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="1232f-158">Ein Beispiel zur Erläuterung der Erstellung einer Aufzeichnungsinstanz mit beiden Abfragefunktionen finden Sie in der Vorlage `Enable a Table for All and Net Changes Queries`.</span><span class="sxs-lookup"><span data-stu-id="1232f-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="1232f-159">Wenn Change Data Capture für eine Tabelle mit einem vorhandenen Primärschlüssel aktiviert ist und der- *@index_name* Parameter nicht zum Identifizieren eines alternativen eindeutigen Indexes verwendet wird, verwendet die Change Data Capture Funktion den Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1232f-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="1232f-160">Nachfolgende Änderungen am Primärschlüssel sind nicht zulässig, ohne zuerst Change Data Capture für die Tabelle zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1232f-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="1232f-161">Dies gilt unabhängig davon, ob Unterstützung für Abfragen für Nettoänderungen angefordert wurde, als Change Data Capture konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="1232f-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="1232f-162">Wenn zum Zeitpunkt der Aktivierung für Change Data Capture für eine Tabelle kein Primärschlüssel vorhanden ist, wird das nachträgliche Hinzufügen eines Primärschlüssels von Change Data Capture ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1232f-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="1232f-163">Da Change Data Capture keinen Primärschlüssel verwendet, der nach der Aktivierung der Tabelle erstellt wurde, können der Schlüssel und die Schlüsselspalten ohne Einschränkungen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1232f-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="1232f-164">Deaktivieren von Change Data Capture für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="1232f-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="1232f-165">Mitglieder der festen Datenbankrolle `db_owner` können eine Aufzeichnungsinstanz für einzelne Quelltabellen mithilfe der gespeicherten Prozedur `sys.sp_cdc_disable_table` entfernen.</span><span class="sxs-lookup"><span data-stu-id="1232f-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="1232f-166">Um zu bestimmen, ob eine Quelltabelle zurzeit für Change Data Capture aktiviert ist, überprüfen Sie die `is_tracked_by_cdc`-Spalte in der`sys.tables`-Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="1232f-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="1232f-167">Wenn nach dem Deaktivieren keine Tabelle für die Datenbank aktiviert sind, werden die Change Data Capture-Aufträge ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="1232f-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="1232f-168">Wenn eine Tabelle, für die Change Data Capture aktiviert ist, gelöscht wird, werden Change Data Capture-Metadaten, die mit der Tabelle verbunden sind, automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="1232f-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="1232f-169">Ein Beispiel für das Deaktivieren einer Tabelle finden Sie in der Vorlage "Eine Aufzeichnungsinstanz für eine Tabelle deaktivieren".</span><span class="sxs-lookup"><span data-stu-id="1232f-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1232f-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1232f-170">See Also</span></span>  
 <span data-ttu-id="1232f-171">[Nachverfolgen von Datenänderungen &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1232f-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="1232f-172">[Über Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1232f-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="1232f-173">[Arbeiten mit Änderungsdaten &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1232f-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="1232f-174">Verwalten und Überwachen von Change Data Capture &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1232f-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
