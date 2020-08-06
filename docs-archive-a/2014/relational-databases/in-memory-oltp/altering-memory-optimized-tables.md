---
title: Ändern von speicheroptimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
author: rothja
ms.author: jroth
ms.openlocfilehash: 4eedc6fdb45efc6c87765cd2208ead90c1887c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621506"
---
# <a name="altering-memory-optimized-tables"></a><span data-ttu-id="04ab2-102">Ändern von speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="04ab2-102">Altering Memory-Optimized Tables</span></span>
  <span data-ttu-id="04ab2-103">Das Ausführen von Änderungsvorgängen (ALTER) in speicheroptimierten Tabellen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="04ab2-103">Performing ALTER operations on memory-optimized tables is not supported.</span></span> <span data-ttu-id="04ab2-104">Hierzu zählen beispielsweise das Ändern von bucket_count, das Hinzufügen oder Entfernen eines Indexes und das Hinzufügen oder Entfernen einer Spalte.</span><span class="sxs-lookup"><span data-stu-id="04ab2-104">This includes such operations as changing the bucket_count, adding or removing an index, and adding or removing a column.</span></span> <span data-ttu-id="04ab2-105">Dieses Thema stellt Richtlinien zum Aktualisieren speicheroptimierter Tabellen bereit.</span><span class="sxs-lookup"><span data-stu-id="04ab2-105">This topic provides guidelines on how to update memory-optimized tables.</span></span>  
  
## <a name="updating-the-definition-of-a-memory-optimized-table"></a><span data-ttu-id="04ab2-106">Aktualisieren der Definition einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="04ab2-106">Updating the Definition of a Memory-Optimized Table</span></span>  
 <span data-ttu-id="04ab2-107">Zum Aktualisieren der Definition einer speicheroptimierten Tabelle müssen Sie eine neue Tabelle mit der aktualisierten Tabellendefinition erstellen, die Daten in die neue Tabelle kopieren und festlegen, dass ab jetzt die neue Tabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="04ab2-107">Updating the definition of a memory-optimized table requires you to create a new table with the updated table definition, copy the data to the new table, and start using the new table.</span></span> <span data-ttu-id="04ab2-108">Wenn die Tabelle nicht schreibgeschützt ist, muss hierfür die Arbeitsauslastung der Tabelle beendet werden, um sicherzustellen, dass keine Änderungen an der Tabelle vorgenommen werden, während die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="04ab2-108">Unless the table is read-only, this requires stopping the workload on the table, to ensure no changes are made to the table while the data copy is performed.</span></span>  
  
 <span data-ttu-id="04ab2-109">Im folgenden Verfahren werden die notwendigen Schritte zum Aktualisieren einer Tabelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="04ab2-109">The following procedure outlines the steps required to update a table.</span></span> <span data-ttu-id="04ab2-110">In diesem Beispiel wird durch das Update ein Index hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="04ab2-110">In this example, the update adds an index.</span></span> <span data-ttu-id="04ab2-111">Dieses Verfahren behält den Namen der Tabelle bei und erfordert zwei Datenkopiervorgänge: einmal in eine temporäre Tabelle und einmal in die neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-111">This procedure preserves the name of the table and requires two data copy operations: once to a temporary table, and once to the new table.</span></span> <span data-ttu-id="04ab2-112">Das Ändern von bucket_count für einen Index oder das Hinzufügen und Entfernen einer Spalte können auf die gleiche Weise erfolgen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-112">Changing the bucket_count of an index or adding or removing a column is performed the same way.</span></span>  
  
1.  <span data-ttu-id="04ab2-113">Beenden Sie die Arbeitsauslastung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-113">Stop the workload on the table.</span></span>  
  
2.  <span data-ttu-id="04ab2-114">Generieren Sie ein Skript für die Tabelle, und fügen Sie dem Skript den neuen Index hinzu.</span><span class="sxs-lookup"><span data-stu-id="04ab2-114">Generate script for the table and add the new index to the script.</span></span>  
  
3.  <span data-ttu-id="04ab2-115">Generieren Sie ein Skript für die schemagebundenen Objekte (hauptsächlich systemintern kompilierte gespeicherte Prozeduren), die auf T verweisen, und für deren Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-115">Generate script for the schema-bound objects (mainly natively compiled stored procedures) referencing T and their permissions.</span></span>  
  
     <span data-ttu-id="04ab2-116">Die schemagebundenen Objekte, die auf die Tabelle verweisen, können mit der folgenden Abfrage ermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="04ab2-116">The schema-bound objects referencing the table can be found using the following query:</span></span>  
  
    ```sql  
    declare @t nvarchar(255) = N'<table name>'  
  
    select r.referencing_schema_name, r.referencing_entity_name  
    from sys.dm_sql_referencing_entities (@t, 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
    where r.is_caller_dependent = 0 and m.is_schema_bound=1;  
    ```  
  
     <span data-ttu-id="04ab2-117">Ein Skript für die Berechtigungen einer gespeicherten Prozedur kann mit folgendem [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="04ab2-117">The permissions of a stored procedure can be scripted using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
    ```sql  
    declare @sp nvarchar(255) = N'<procedure name>'  
    declare @permissions nvarchar(max) = N''  
  
    select @permissions += dp.state_desc + N' ' + dp.permission_name + N' ON ' +   
       quotename(schema_name(o.schema_id)) + N'.' + quotename(o.name) + N' TO ' +  
       quotename(u.name) + N'; ' + char(13)  
    from sys.database_permissions as dp  
  
    join sys.database_principals as u  
       on u.principal_id = dp.grantee_principal_id  
  
    join sys.objects as o  
       on o.object_id = dp.major_id  
    where dp.class = 1 /* object */  
       and dp.minor_id = 0 and o.object_id=object_id(@sp);  
  
    select @permissions  
    ```  
  
4.  <span data-ttu-id="04ab2-118">Erstellen Sie eine Kopie der Tabelle, und kopieren Sie die Daten aus der ursprünglichen Tabelle in die Tabellenkopie.</span><span class="sxs-lookup"><span data-stu-id="04ab2-118">Create a copy of the table and copy the data from the original table to the copy of the table.</span></span> <span data-ttu-id="04ab2-119">Die Kopie kann mit den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] <sup>1</sup>erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="04ab2-119">The copy can be created using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]<sup>1</sup>.</span></span>  
  
    ```sql  
    select * into dbo.T_copy from dbo.T  
    ```  
  
     <span data-ttu-id="04ab2-120">Wenn genügend Arbeitsspeicher verfügbar ist, `T_copy` kann eine Speicher optimierte Tabelle sein, wodurch die Daten schneller kopiert werden.<sup> 2</sup></span><span class="sxs-lookup"><span data-stu-id="04ab2-120">If there is enough available memory, `T_copy` could be a memory-optimized table, which makes the data copy faster.<sup>2</sup></span></span>  
  
5.  <span data-ttu-id="04ab2-121">Löschen Sie die schemagebundenen Objekte, die auf die ursprüngliche Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-121">Drop the schema-bound objects referencing the original table.</span></span>  
  
6.  <span data-ttu-id="04ab2-122">Löschen Sie die ursprüngliche Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-122">Drop the original table.</span></span>  
  
7.  <span data-ttu-id="04ab2-123">Erstellen Sie die neue Tabelle (`T`) mit dem Skript, das den neuen Index enthält.</span><span class="sxs-lookup"><span data-stu-id="04ab2-123">Create the new table (`T`) with the script containing the new index.</span></span>  
  
8.  <span data-ttu-id="04ab2-124">Kopieren Sie die Daten von `T_copy` nach `T`.</span><span class="sxs-lookup"><span data-stu-id="04ab2-124">Copy the data from `T_copy` to `T`.</span></span>  
  
9. <span data-ttu-id="04ab2-125">Erstellen Sie die verweisenden schemagebundenen Objekte neu, und wenden Sie die Berechtigungen an.</span><span class="sxs-lookup"><span data-stu-id="04ab2-125">Recreate the referencing schema-bound objects and apply the permissions.</span></span>  
  
10. <span data-ttu-id="04ab2-126">Starten Sie die Arbeitsauslastung auf `T`.</span><span class="sxs-lookup"><span data-stu-id="04ab2-126">Start the workload on `T`.</span></span>  
  
 <span data-ttu-id="04ab2-127"><sup>1</sup> beachten Sie, dass `T_copy` in diesem Beispiel auf dem Datenträger persistent gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="04ab2-127"><sup>1</sup> Note that `T_copy` is persisted to disk in this example.</span></span> <span data-ttu-id="04ab2-128">Wenn eine Sicherung von `T` verfügbar ist, kann `T_copy` eine nicht dauerhafte oder eine temporäre Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="04ab2-128">If a backup of `T` is available, `T_copy` could be a temporary or a non-durable table.</span></span>  
  
 <span data-ttu-id="04ab2-129"><sup>2</sup> es muss genügend Arbeitsspeicher für vorhanden sein `T_copy` .</span><span class="sxs-lookup"><span data-stu-id="04ab2-129"><sup>2</sup> There must be enough memory for `T_copy`.</span></span> <span data-ttu-id="04ab2-130">Der Arbeitsspeicher wird bei `DROP TABLE` nicht sofort freigegeben.</span><span class="sxs-lookup"><span data-stu-id="04ab2-130">Memory is not freed immediately on `DROP TABLE`.</span></span> <span data-ttu-id="04ab2-131">Wenn `T_copy` speicheroptimiert ist, muss genügend Arbeitsspeicher für zwei zusätzliche Kopien von `T` verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="04ab2-131">If `T_copy` is memory optimized, there needs to be enough memory for two additional copies of `T`.</span></span> <span data-ttu-id="04ab2-132">Wenn `T_copy` eine datenträgerbasierte Tabelle ist, wird nur Speicher für eine zusätzliche Kopie von `T` benötigt, da der Garbage Collector erst entsprechende Schritte ausführen muss, nachdem die alte Version von `T` gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="04ab2-132">If `T_copy` is a disk-based table, there only needs to be enough memory for one additional copy of `T`, due to the garbage collector needing to catch up after dropping the old version of `T`.</span></span>  
  
## <a name="changing-schema-powershell"></a><span data-ttu-id="04ab2-133">Ändern des Schemas (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="04ab2-133">Changing Schema (PowerShell)</span></span>  
 <span data-ttu-id="04ab2-134">Die folgenden PowerShell-Skripts bereiten Schemaänderungen vor und generieren diese, indem Skripts für die Tabelle und die zugehörigen Berechtigungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="04ab2-134">The following PowerShell scripts prepare and generate for schema changes by scripting the table and associated permissions.</span></span>  
  
```powershell
prepare_schema_change.ps1 <serverName> <databaseName> <schemaName> <tableName>
```
  
 <span data-ttu-id="04ab2-135">Dieses Skript erwartet als Argumente eine Tabelle und erstellt im aktuellen Ordner ein Skript für das Objekt und dessen Berechtigungen sowie für verweisende schemagebundene Objekte und deren Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-135">This script takes as arguments a table, and scripts the object and its permissions and referencing schema-bound objects and their permissions in the current folder.</span></span> <span data-ttu-id="04ab2-136">Insgesamt werden 7 Skripts für das Aktualisieren des Schemas der Eingabetabelle generiert:</span><span class="sxs-lookup"><span data-stu-id="04ab2-136">A total of 7 scripts are generated for updating the schema of the input table:</span></span>  
  
-   <span data-ttu-id="04ab2-137">Kopiert Daten in eine temporäre Tabelle (einen Heap).</span><span class="sxs-lookup"><span data-stu-id="04ab2-137">Copy data to a temporary table (a heap).</span></span>  
  
-   <span data-ttu-id="04ab2-138">Löscht schemagebundene Objekte, die auf die Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-138">Drop schema-bound objects referencing the table.</span></span>  
  
-   <span data-ttu-id="04ab2-139">Löschen Sie die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-139">Drop the table.</span></span>  
  
-   <span data-ttu-id="04ab2-140">Erstellt die Tabelle mit dem neuen Schema neu und wendet die Berechtigungen erneut an.</span><span class="sxs-lookup"><span data-stu-id="04ab2-140">Recreate the table with the new schema and reapply permissions.</span></span>  
  
-   <span data-ttu-id="04ab2-141">Kopiert die Daten aus der temporären Tabelle in die neu erstellte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-141">Copy data from the temporary table to the recreated table.</span></span>  
  
-   <span data-ttu-id="04ab2-142">Erstellt die schemagebundenen Objekte, die auf die Tabelle verweisen, und deren Berechtigungen neu.</span><span class="sxs-lookup"><span data-stu-id="04ab2-142">Recreate schema-bound objects referencing the table and their permissions.</span></span>  
  
-   <span data-ttu-id="04ab2-143">Löscht die temporäre Tabelle.</span><span class="sxs-lookup"><span data-stu-id="04ab2-143">Drop the temporary table.</span></span>  
  
 <span data-ttu-id="04ab2-144">Das Skript für Schritt 4 sollte entsprechend geändert werden, um die gewünschten Schemaänderungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04ab2-144">The script for step 4 should be updated to reflect the desired schema changes.</span></span> <span data-ttu-id="04ab2-145">Wenn in den Spalten der Tabelle Änderungen vorgenommen werden, sollten die Skripts für die Schritte 5 (Kopieren von Daten aus temporärer Tabelle) und 6 (gespeicherte Prozeduren neu erstellen) nach Bedarf aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="04ab2-145">If there are any changes in the columns of the table, the scripts for steps 5 (copy data from temporary table) and 6 (recreate stored procedures) should be updated as necessary.</span></span>  
  
```powershell
# Prepare for schema changes by scripting out the table, as well as associated permissions
# Usage: prepare_schema_change.ps1 server_name db_name schema_name table_name  
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage prepare_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
$object_heap = "$object$(Get-Random)"  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$scripter = New-Object ("Microsoft.SqlServer.Management.SMO.Scripter") ($server)  
  
## initialize table variable  
$tableUrn = $server.Databases[$database].Tables[$object, $schema]  
if($tableUrn.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
## initialize scripting object  
$scriptingOptions = New-Object ("Microsoft.SqlServer.Management.SMO.ScriptingOptions")
$scriptingOptions.Permissions = $True  
$scriptingOptions.ScriptDrops = $True  
  
$scripter.Options = $scriptingOptions;  
  
Write-Host "(1) Scripting SELECT INTO $object_heap for table [$object] to 1_copy_to_heap_for_$schema`_$object.sql"  
Echo "SELECT * INTO $schema.$object_heap FROM $schema.$object WITH (SNAPSHOT)" | Out-File "1_copy_to_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Scripting DROP for procs schema-bound to [$object] 2_drop_procs_$schema`_$object.sql"  
## query referencing schema-bound objects  
$dt = $server.Databases[$database].ExecuteWithResults("select r.referencing_schema_name, r.referencing_entity_name  
from sys.dm_sql_referencing_entities ('$schema.$object', 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
where r.is_caller_dependent = 0 and m.is_schema_bound=1;")  
  
## initialize out file  
Echo "" | Out-File "2_drop_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script object   
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      $scripter.Script($so) | Out-File -Append "2_drop_procs_$schema`_$object.sql"  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
Write-Host "(3) Scripting DROP table for [$object] to 3_drop_table_$schema`_$object.sql"
$scripter.Script($tableUrn) | Out-File "3_drop_table_$schema`_$object.sql";
Write-Host "--done--"  
Write-Host ""  
  
## now script creates  
$scriptingOptions.ScriptDrops = $False  
  
Write-Host "(4) Scripting CREATE table and permissions for [$object] to !please_edit_4_create_table_$schema`_$object.sql"  
Write-Host "***** rename this script to 4_create_table.sql after completing the updates to the schema"
$scripter.Script($tableUrn) | Out-File "!please_edit_4_create_table_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Scripting INSERT INTO table from heap and UPDATE STATISTICS for [$object] to 5_copy_from_heap_$schema`_$object.sql"  
Write-Host "[update this script if columns are added to or removed from the table]"  
Echo "INSERT INTO [$schema].[$object] SELECT * FROM [$schema].[$object_heap]; UPDATE STATISTICS [$schema].[$object] WITH FULLSCAN, NORECOMPUTE" | Out-File "5_copy_from_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Scripting CREATE PROC and permissions for procedures schema-bound to [$object] to 6_create_procs_$schema`_$object.sql"  
Write-Host "[update the procedure definitions if columns are renamed or removed]"  
## initialize out file  
Echo "" | Out-File "6_create_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script the schema-bound object  
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      ForEach($s In $scripter.Script($so))  
        {  
            Echo $s | Out-File -Append "6_create_procs_$schema`_$object.sql"  
            Echo "GO" | Out-File -Append "6_create_procs_$schema`_$object.sql"  
        }  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Scripting DROP $object_heap to 7_drop_heap_$schema`_$object.sql"  
Echo "DROP TABLE $schema.$object_heap" | Out-File "7_drop_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
```  
  
 <span data-ttu-id="04ab2-146">Das folgende PowerShell-Skript führt die Schemaänderungen aus, für die im vorherigen Beispiel ein Skript erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="04ab2-146">The following PowerShell script executes the schema changes that were scripted in the previous sample.</span></span> <span data-ttu-id="04ab2-147">Dieses Skript erwartet eine Tabelle als Argument und führt die Schemaänderungsskripts aus, die für diese Tabelle und die zugehörigen gespeicherten Prozeduren generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="04ab2-147">This script takes as argument a table, and executes the schema change scripts that were generated for that table and the associated stored procedures.</span></span>  
  
 <span data-ttu-id="04ab2-148">Verwendung: execute_schema_change.ps1 *server_name \* \* db_name `schema_name` table_name*</span><span class="sxs-lookup"><span data-stu-id="04ab2-148">Usage: execute_schema_change.ps1 *server_name\*\*db_name`schema_name`table_name*</span></span>  
  
```powershell
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage execute_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$database = $server.Databases[$database]  
$table = $database.Tables[$object, $schema]  
if($table.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
$1 = Get-Item "1_copy_to_heap_$schema`_$object.sql"  
$2 = Get-Item "2_drop_procs_$schema`_$object.sql"  
$3 = Get-Item "3_drop_table_$schema`_$object.sql"  
$4 = Get-Item "4_create_table_$schema`_$object.sql"  
$5 = Get-Item "5_copy_from_heap_$schema`_$object.sql"  
$6 = Get-Item "6_create_procs_$schema`_$object.sql"  
$7 = Get-Item "7_drop_heap_$schema`_$object.sql"  
  
Write-Host "(1) Running SELECT INTO heap for table [$object] from 1_copy_to_heap_for_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $1.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Running DROP for procs schema-bound from [$object] 2_drop_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $2.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(3) Running DROP table for [$object] to 4_drop_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $3.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(4) Running CREATE table and permissions for [$object] from 4_create_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $4.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Running INSERT INTO table from heap for [$object] and UPDATE STATISTICS from 5_copy_from_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $5.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Running CREATE PROC and permissions for procedures schema-bound to [$object] from 6_create_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $6.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Running DROP heap from 7_drop_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $7.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
```  
  
## <a name="see-also"></a><span data-ttu-id="04ab2-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04ab2-149">See Also</span></span>  
 [<span data-ttu-id="04ab2-150">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="04ab2-150">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
