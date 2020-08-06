---
title: Laden von Dateien in FileTables | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723934"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="bdf97-102">Laden von Dateien in FileTables</span><span class="sxs-lookup"><span data-stu-id="bdf97-102">Load Files into FileTables</span></span>
  <span data-ttu-id="bdf97-103">Beschreibt, wie Dateien in FileTables geladen und migriert werden.</span><span class="sxs-lookup"><span data-stu-id="bdf97-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="bdf97-104">Laden oder Migrieren von Dateien in FileTables</span><span class="sxs-lookup"><span data-stu-id="bdf97-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="bdf97-105">Die Methode, die Sie zum Laden oder Migrieren von Dateien in eine FileTable auswählen, ist davon abhängig, wo die Dateien aktuell gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="bdf97-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="bdf97-106">Aktueller Speicherort von Dateien</span><span class="sxs-lookup"><span data-stu-id="bdf97-106">Current location of files</span></span>|<span data-ttu-id="bdf97-107">Optionen für die Migration</span><span class="sxs-lookup"><span data-stu-id="bdf97-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="bdf97-108">Dateien sind derzeit im Dateisystem gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bdf97-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bdf97-109">hat keine Informationen über die Dateien.</span><span class="sxs-lookup"><span data-stu-id="bdf97-109">has no knowledge of the files.</span></span>|<span data-ttu-id="bdf97-110">Da eine FileTable im Windows-Dateisystem als Ordner angezeigt wird, können Sie Dateien mithilfe einer der verfügbaren Methoden zum Verschieben oder Kopieren von Dateien ganz einfach in eine neue FileTable laden.</span><span class="sxs-lookup"><span data-stu-id="bdf97-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="bdf97-111">Zu diesen Methoden gehören Windows-Explorer, Befehlszeilenoptionen, einschließlich xcopy und robocopy, sowie benutzerdefinierte Skripts oder Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="bdf97-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="bdf97-112">Sie können einen vorhandenen Ordner nicht in eine FileTable konvertieren.</span><span class="sxs-lookup"><span data-stu-id="bdf97-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="bdf97-113">Dateien sind derzeit im Dateisystem gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bdf97-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bdf97-114">enthält eine Tabelle von Metadaten, die Zeiger auf die Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="bdf97-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="bdf97-115">Der erste Schritt besteht darin, die Dateien mithilfe einer der oben erwähnten Methoden zu verschieben oder zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bdf97-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="bdf97-116">Der zweite Schritt besteht darin, die vorhandene Tabelle von Metadaten so zu aktualisieren, dass diese auf den neuen Speicherort der Dateien zeigt.</span><span class="sxs-lookup"><span data-stu-id="bdf97-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="bdf97-117">Weitere Informationen finden Sie unter [Beispiel: Migrieren von Dateien aus dem Dateisystem in eine FileTable](#HowToMigrateFiles) .</span><span class="sxs-lookup"><span data-stu-id="bdf97-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="bdf97-118">Vorgehensweise: Laden von Dateien in eine Dateitabelle</span><span class="sxs-lookup"><span data-stu-id="bdf97-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="bdf97-119">Zu den Methoden, über die Sie Dateien in eine FileTable laden können, gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="bdf97-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="bdf97-120">Drag & Drop von Dateien aus den Quellordnern in den neuen FileTable-Ordner in Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="bdf97-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="bdf97-121">Verwenden Sie Befehlszeilenoptionen, z. B. MOVE, COPY, XCOPY oder ROBOCOPY, an der Eingabeaufforderung oder in einer Batchdatei oder einem Skript.</span><span class="sxs-lookup"><span data-stu-id="bdf97-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="bdf97-122">Schreiben Sie eine benutzerdefinierte Anwendung in C# oder Visual Basic .NET, die Methoden aus dem **System.IO** -Namespace verwendet, um die Dateien zu verschieben oder zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bdf97-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="bdf97-123">Beispiel: Migrieren von Dateien aus dem Dateisystem in eine Dateitabelle</span><span class="sxs-lookup"><span data-stu-id="bdf97-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="bdf97-124">In diesem Szenario werden die Dateien im Dateisystem gespeichert, und Sie verfügen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über eine Tabelle mit Metadaten, die Zeiger auf die Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="bdf97-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="bdf97-125">Sie möchten die Dateien in eine FileTable verschieben und den ursprünglichen UNC-Pfad für jede Datei in den Metadaten durch den FileTable-UNC-Pfad ersetzen.</span><span class="sxs-lookup"><span data-stu-id="bdf97-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="bdf97-126">Die Funktion [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) hilft Ihnen, dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="bdf97-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="bdf97-127">Nehmen Sie für dieses Beispiel an, dass eine Datenbanktabelle vorhanden ist, `PhotoMetadata` die Daten zu Fotos enthält.</span><span class="sxs-lookup"><span data-stu-id="bdf97-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="bdf97-128">Diese Tabelle hat eine Spalte `UNCPath` des Typs `varchar`(512), der den tatsächlichen UNC-Pfad zu einer JPG-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="bdf97-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="bdf97-129">Um die Bilddateien aus dem Dateisystem in eine FileTable zu migrieren, müssen Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="bdf97-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="bdf97-130">Erstellen Sie eine neue FileTable, in der sich die Dateien befinden.</span><span class="sxs-lookup"><span data-stu-id="bdf97-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="bdf97-131">In diesem Beispiel wird der Tabellenname `dbo.PhotoTable` verwendet; es wird jedoch nicht der Code zum Erstellen der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bdf97-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="bdf97-132">Verwenden Sie xcopy oder ein ähnliches Tool, um die JPG-Dateien mit ihrer Verzeichnisstruktur in das Stammverzeichnis der FileTable zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bdf97-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="bdf97-133">Korrigieren Sie die Metadaten in der Tabelle `PhotoMetadata` mithilfe von Code, der folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="bdf97-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="bdf97-134">Massenladen von Dateien in eine FileTable</span><span class="sxs-lookup"><span data-stu-id="bdf97-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="bdf97-135">Eine FileTable verhält sich bei Massenvorgängen wie eine normale Tabelle, jedoch mit den folgenden Charakteristiken.</span><span class="sxs-lookup"><span data-stu-id="bdf97-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="bdf97-136">Eine FileTable weist systemdefinierte Einschränkungen auf, durch die sichergestellt wird, dass die Namespaceintegrität der Datei und des Verzeichnisses erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="bdf97-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="bdf97-137">Diese Einschränkungen müssen für die Daten überprüft werden, die mit einem Massenvorgang in die FileTable geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="bdf97-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="bdf97-138">Da einige Masseneinfügungsvorgänge das Ignorieren der Tabelleneinschränkungen zulassen, werden folgende Anforderungen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="bdf97-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="bdf97-139">Massenladevorgänge, die Einschränkungen erzwingen, können für eine FileTable sowie alle anderen Tabellen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bdf97-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="bdf97-140">Zu dieser Kategorie gehören die folgenden Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="bdf97-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="bdf97-141">bcp mit CHECK_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-142">BULK INSERT mit CHECK_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) ohne IGNORE_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="bdf97-144">Massenladevorgänge, die keine Einschränkungen erzwingen, führen zu Fehlern, es sei denn, die für FileTable vom System definierten Einschränkungen wurden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdf97-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="bdf97-145">Zu dieser Kategorie gehören die folgenden Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="bdf97-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="bdf97-146">bcp ohne CHECK_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-147">BULK INSERT ohne CHECK_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) mit IGNORE_CONSTRAINTS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="bdf97-149">Vorgehensweise: Massenladen von Dateien in eine Dateitabelle</span><span class="sxs-lookup"><span data-stu-id="bdf97-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="bdf97-150">Sie können verschiedene Methoden zum Massenladen von Dateien in eine FileTable verwenden:</span><span class="sxs-lookup"><span data-stu-id="bdf97-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="bdf97-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="bdf97-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="bdf97-152">Aufruf mit der **CHECK_CONSTRAINTS** -Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-153">Deaktivieren Sie den FileTable-Namespace, und führen Sie den Aufruf ohne die **CHECK_CONSTRAINTS** -Klausel aus.</span><span class="sxs-lookup"><span data-stu-id="bdf97-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="bdf97-154">Aktivieren Sie dann den FileTable-Namespace erneut.</span><span class="sxs-lookup"><span data-stu-id="bdf97-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="bdf97-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="bdf97-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="bdf97-156">Aufruf mit der **CHECK_CONSTRAINTS** -Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-157">Deaktivieren Sie den FileTable-Namespace, und führen Sie den Aufruf ohne die **CHECK_CONSTRAINTS** -Klausel aus.</span><span class="sxs-lookup"><span data-stu-id="bdf97-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="bdf97-158">Aktivieren Sie dann den FileTable-Namespace erneut.</span><span class="sxs-lookup"><span data-stu-id="bdf97-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="bdf97-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK...)** .</span><span class="sxs-lookup"><span data-stu-id="bdf97-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="bdf97-160">Aufruf mit der **IGNORE_CONSTRAINTS** -Klausel.</span><span class="sxs-lookup"><span data-stu-id="bdf97-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="bdf97-161">Deaktivieren Sie den FileTable-Namespace, und führen Sie den Aufruf ohne die **IGNORE_CONSTRAINTS** -Klausel aus.</span><span class="sxs-lookup"><span data-stu-id="bdf97-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="bdf97-162">Aktivieren Sie dann den FileTable-Namespace erneut.</span><span class="sxs-lookup"><span data-stu-id="bdf97-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="bdf97-163">Informationen zum Deaktivieren der FileTable-Einschränkungen finden Sie unter [Verwalten von FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="bdf97-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="bdf97-164">Vorgehensweise: Deaktivieren von Dateitabellen-Einschränkungen zum Massenladen</span><span class="sxs-lookup"><span data-stu-id="bdf97-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="bdf97-165">Um Dateien in einem Massenvorgang in eine FileTable zu laden und dabei den Aufwand zu vermeiden, die systemdefinierten Einschränkungen zu erzwingen, können Sie die Einschränkungen vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bdf97-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="bdf97-166">Weitere Informationen finden Sie unter [Verwalten von FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="bdf97-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf97-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdf97-167">See Also</span></span>  
 <span data-ttu-id="bdf97-168">[Zugreifen auf FileTables mit Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="bdf97-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="bdf97-169">Zugreifen auf FileTables mit Datei-E/A-APIs</span><span class="sxs-lookup"><span data-stu-id="bdf97-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
