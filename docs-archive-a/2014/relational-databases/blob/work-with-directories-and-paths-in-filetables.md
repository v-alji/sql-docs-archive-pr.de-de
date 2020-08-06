---
title: Arbeiten mit Verzeichnissen und Pfaden in FileTables | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], directories
ms.assetid: f1e45900-bea0-4f6f-924e-c11e1f98ab62
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4641159e894b764cbee4d7f02085f3ceb8e6d87d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695710"
---
# <a name="work-with-directories-and-paths-in-filetables"></a><span data-ttu-id="b2a11-102">Arbeiten mit Verzeichnissen und Pfaden in FileTables</span><span class="sxs-lookup"><span data-stu-id="b2a11-102">Work with Directories and Paths in FileTables</span></span>
  <span data-ttu-id="b2a11-103">Beschreibt die Verzeichnisstruktur, mit der die Dateien in FileTables gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b2a11-103">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
##  <a name="how-to-work-with-directories-and-paths-in-filetables"></a><a name="HowToDirectories"></a> <span data-ttu-id="b2a11-104">Vorgehensweise: Arbeiten mit Verzeichnissen und Pfaden in FileTables</span><span class="sxs-lookup"><span data-stu-id="b2a11-104">How To: Work with Directories and Paths in FileTables</span></span>  
 <span data-ttu-id="b2a11-105">Sie können die folgenden drei Funktionen verwenden, um mit FileTable-Verzeichnissen in [!INCLUDE[tsql](../../includes/tsql-md.md)]zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="b2a11-105">You can use the following 3 functions to work with FileTable directories in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
|<span data-ttu-id="b2a11-106">Für dieses Ergebnis</span><span class="sxs-lookup"><span data-stu-id="b2a11-106">To get this result</span></span>|<span data-ttu-id="b2a11-107">Verwenden Sie diese Funktion</span><span class="sxs-lookup"><span data-stu-id="b2a11-107">Use this function</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="b2a11-108">Ermitteln des UNC-Pfades auf der Stammebene für eine bestimmte FileTable oder die aktuelle Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b2a11-108">Get the root-level UNC path for a specific FileTable or for the current database.</span></span>|[<span data-ttu-id="b2a11-109">FileTableRootPath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2a11-109">FileTableRootPath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/filetablerootpath-transact-sql)|  
|<span data-ttu-id="b2a11-110">Ermitteln eines absoluten oder relativen UNC-Pfades für eine Datei oder ein Verzeichnis in einer FileTable.</span><span class="sxs-lookup"><span data-stu-id="b2a11-110">Get an absolute or relative UNC path for a file or directory in a FileTable.</span></span>|[<span data-ttu-id="b2a11-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2a11-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)|  
|<span data-ttu-id="b2a11-112">Ermitteln des ID-Wertes "path_locator" für die angegebene Datei bzw. das angegebene Verzeichnis in einer FileTable unter Angabe des Pfades.</span><span class="sxs-lookup"><span data-stu-id="b2a11-112">Get the path locator ID value for the specified file or directory in a FileTable, by providing the path.</span></span>|[<span data-ttu-id="b2a11-113">GetPathLocator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2a11-113">GetPathLocator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getpathlocator-transact-sql)|  
  
##  <a name="how-to-use-relative-paths-for-portable-code"></a><a name="BestPracticeRelativePaths"></a><span data-ttu-id="b2a11-114">Vorgehensweise: Verwenden von relativen Pfaden für portablen Code</span><span class="sxs-lookup"><span data-stu-id="b2a11-114">How to: Use Relative Paths for Portable Code</span></span>  
 <span data-ttu-id="b2a11-115">Um Code und Anwendungen vom aktuellen Computer und von der Datenbank unabhängig zu halten, sollten Sie keinen Code schreiben, der auf absoluten Dateipfaden basiert.</span><span class="sxs-lookup"><span data-stu-id="b2a11-115">To keep code and applications independent of the current computer and database, avoid writing code that relies on absolute file paths.</span></span> <span data-ttu-id="b2a11-116">Rufen Sie stattdessen den vollständigen Pfad für eine Datei mit der Funktion [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) und der Funktion [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)zur Laufzeit ab, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2a11-116">Instead, get the complete path for a file at run time by using the [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) and [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)) functions together, as shown in the following example.</span></span> <span data-ttu-id="b2a11-117">Die `GetFileNamespacePath`-Funktion gibt standardmäßig den relativen Pfad der Datei unter dem Stammpfad der Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="b2a11-117">By default, the `GetFileNamespacePath` function returns the relative path of the file under the root path for the database.</span></span>  
  
```sql  
USE database_name;  
DECLARE @root nvarchar(100);  
DECLARE @fullpath nvarchar(1000);  
  
SELECT @root = FileTableRootPath();  
SELECT @fullpath = @root + file_stream.GetFileNamespacePath()  
    FROM filetable_name  
    WHERE name = N'document_name';  
  
PRINT @fullpath;  
GO  
```  
  
##  <a name="important-restrictions"></a><a name="restrictions"></a> <span data-ttu-id="b2a11-118">Wichtige Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b2a11-118">Important restrictions</span></span>  
  
###  <a name="nesting-level"></a><a name="nesting"></a> <span data-ttu-id="b2a11-119">Schachtelungsebene</span><span class="sxs-lookup"><span data-stu-id="b2a11-119">Nesting level</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2a11-120">Es ist nicht möglich, mehr als 15 Ebenen von Unterverzeichnissen im FileTable-Verzeichnis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b2a11-120">You cannot store more than 15 levels of subdirectories in the FileTable directory.</span></span> <span data-ttu-id="b2a11-121">Wenn Sie 15 Unterverzeichnisebenen speichern, kann die niedrigste Ebene keine Dateien enthalten, da diese Dateien eine zusätzliche Ebene darstellen würden.</span><span class="sxs-lookup"><span data-stu-id="b2a11-121">When you store 15 levels of subdirectories, then the lowest level cannot contain files, since these files would represent an additional level.</span></span>  
  
###  <a name="length-of-full-path-name"></a><a name="fqnlength"></a> <span data-ttu-id="b2a11-122">Länge des vollständigen Pfadnamens</span><span class="sxs-lookup"><span data-stu-id="b2a11-122">Length of full path name</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2a11-123">Das NTFS-Dateisystem unterstützt Pfadnamen, die viel länger als die 260-Zeichen-Grenze der Windows-Shell und der meisten Windows-APIs sind.</span><span class="sxs-lookup"><span data-stu-id="b2a11-123">The NTFS file system supports path names that are much longer than the 260-character limit of the Windows shell and most Windows APIs.</span></span> <span data-ttu-id="b2a11-124">Daher ist es möglich, Dateien in der Dateihierarchie einer FileTable mit Transact-SQL zu erstellen. Diese können Sie mit dem Windows-Explorer oder vielen anderen Windows-Anwendungen weder anzeigen noch öffnen, da der vollständige Pfadname 260 Zeichen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b2a11-124">Therefore it is possible to create files in the file hierarchy of a FileTable by using Transact-SQL that you cannot view or open with Windows Explorer or many other Windows applications, because the full path name exceeds 260 characters.</span></span> <span data-ttu-id="b2a11-125">Sie können jedoch weiterhin mit Transact-SQL auf diese Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b2a11-125">However you can continue to access these files by using Transact-SQL.</span></span>  
  
##  <a name="the-full-path-to-an-item-stored-in-a-filetable"></a><a name="fullpath"></a> <span data-ttu-id="b2a11-126">Der vollständige Pfad zu einem in einer FileTable gespeicherten Element</span><span class="sxs-lookup"><span data-stu-id="b2a11-126">The full path to an item stored in a FileTable</span></span>  
 <span data-ttu-id="b2a11-127">Der vollständige Pfad zu einer Datei oder einem Verzeichnis, der in einer FileTable gespeichert wurde, beginnt mit den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="b2a11-127">The full path to a file or directory stored in a FileTable begins with the following elements:</span></span>  
  
1.  <span data-ttu-id="b2a11-128">Die für den FILESTREAM-Datei-E/A-Zugriff auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzebene aktivierte Freigabe.</span><span class="sxs-lookup"><span data-stu-id="b2a11-128">The share enabled for FILESTREAM file I/O access at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level.</span></span>  
  
2.  <span data-ttu-id="b2a11-129">Der auf Datenbankebene angegebene **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="b2a11-129">The **DIRECTORY_NAME** specified at the database level.</span></span>  
  
3.  <span data-ttu-id="b2a11-130">Das auf FileTable-Ebene angegebene **FILETABLE_DIRECTORY** .</span><span class="sxs-lookup"><span data-stu-id="b2a11-130">The **FILETABLE_DIRECTORY** specified at the FileTable level.</span></span>  
  
 <span data-ttu-id="b2a11-131">Die resultierende Hierarchie sieht etwa folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="b2a11-131">The resulting hierarchy looks like this:</span></span>  
  
 `\\<machine>\<instance-level FILESTREAM share>\<database-level directory>\<FileTable directory>\`  
  
 <span data-ttu-id="b2a11-132">Diese Verzeichnishierarchie bildet den Stamm des FileTable-Namespace.</span><span class="sxs-lookup"><span data-stu-id="b2a11-132">This directory hierarchy forms the root of the FileTable's file namespace.</span></span> <span data-ttu-id="b2a11-133">Unter dieser Verzeichnishierarchie werden die FILESTREAM-Daten für die FileTable als Dateien wie auch als Unterverzeichnisse gespeichert, die auch Dateien und Unterverzeichnisse enthalten können.</span><span class="sxs-lookup"><span data-stu-id="b2a11-133">Under this directory hierarchy, the FILESTREAM data for the FileTable is stored as files, and as subdirectories which can also contain files and subdirectories.</span></span>  
  
 <span data-ttu-id="b2a11-134">Bitte denken Sie daran, dass die unter der FILESTREAM-Freigabe auf Instanzebene erstellte Verzeichnishierarchie eine virtuelle Verzeichnishierarchie ist.</span><span class="sxs-lookup"><span data-stu-id="b2a11-134">It is important to keep in mind that the directory hierarchy created under the instance-level FILESTREAM share is a virtual directory hierarchy.</span></span> <span data-ttu-id="b2a11-135">Diese Hierarchie wird in der Datenbank [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert und nicht physisch im NTFS-Dateisystem dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b2a11-135">This hierarchy is stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and is not represented physically in the NTFS file system.</span></span> <span data-ttu-id="b2a11-136">Alle Vorgänge, die unter der FILESTREAM-Freigabe und in den enthaltenen FileTables auf Dateien und Verzeichnisse zugreifen, werden durch eine im Dateisystem eingebettete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Komponente abgefangen und behandelt.</span><span class="sxs-lookup"><span data-stu-id="b2a11-136">All operations that access files and directories under the FILESTREAM share and in the FileTables that it contains are intercepted and handled by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component embedded in the file system.</span></span>  
  
##  <a name="the-semantics-of-the-root-directories-at-the-instance-database-and-filetable-levels"></a><a name="roots"></a> <span data-ttu-id="b2a11-137">Die Semantik der Stammverzeichnisse auf der Instanz-, Datenbank- und FileTable-Ebene</span><span class="sxs-lookup"><span data-stu-id="b2a11-137">The semantics of the root directories at the instance, database, and FileTable levels</span></span>  
 <span data-ttu-id="b2a11-138">Diese Verzeichnishierarchie achtet auf die folgende Semantik:</span><span class="sxs-lookup"><span data-stu-id="b2a11-138">This directory hierarchy observes the following semantics:</span></span>  
  
-   <span data-ttu-id="b2a11-139">Die FILESTREAM-Freigabe auf Instanzebene wird von einem Administrator konfiguriert und als Eigenschaft des Servers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2a11-139">The instance-level FILESTREAM share is configured by an administrator and stored as a property of the server.</span></span> <span data-ttu-id="b2a11-140">Sie können diese Freigabe mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager umbenennen.</span><span class="sxs-lookup"><span data-stu-id="b2a11-140">You can rename this share by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="b2a11-141">Ein Umbenennungsvorgang wird erst wirksam, wenn der Server neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b2a11-141">A renaming operation does not take effect until the server is restarted.</span></span>  
  
-   <span data-ttu-id="b2a11-142">Der **DIRECTORY_NAME** auf Datenbankebene ist standardmäßig NULL, wenn Sie eine neue Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="b2a11-142">The database-level **DIRECTORY_NAME** is null by default when you create a new database.</span></span> <span data-ttu-id="b2a11-143">Ein Administrator kann diesen Namen festlegen oder mit der Anweisung **ALTER DATABASE** ändern.</span><span class="sxs-lookup"><span data-stu-id="b2a11-143">An administrator can set or change this name by using the **ALTER DATABASE** statement.</span></span> <span data-ttu-id="b2a11-144">Der Name muss in dieser Instanz eindeutig sein, wobei nicht zwischen Groß- und Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="b2a11-144">The name must be unique (in a case-insensitive comparison) in that instance.</span></span>  
  
-   <span data-ttu-id="b2a11-145">In der Regel geben Sie den **FILETABLE_DIRECTORY** -Namen als Teil der Anweisung **CREATE TABLE** beim Erstellen einer FileTable an.</span><span class="sxs-lookup"><span data-stu-id="b2a11-145">You typically provide the **FILETABLE_DIRECTORY** name as part of the **CREATE TABLE** statement when you create a FileTable.</span></span> <span data-ttu-id="b2a11-146">Sie können diesen Namen mit dem Befehl **ALTER TABLE** ändern.</span><span class="sxs-lookup"><span data-stu-id="b2a11-146">You can change this name by using the **ALTER TABLE** command.</span></span>  
  
-   <span data-ttu-id="b2a11-147">Es ist nicht möglich, diese Stammverzeichnisse kann durch Datei-E/A-Vorgänge umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="b2a11-147">You cannot rename these root directories through file I/O operations.</span></span>  
  
-   <span data-ttu-id="b2a11-148">Es ist nicht möglich, diese Stammverzeichnisse mit exklusiven Dateihandles zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b2a11-148">You cannot open these root directories with exclusive file handles.</span></span>  
  
##  <a name="the-is_directory-column-in-the-filetable-schema"></a><a name="is_directory"></a> <span data-ttu-id="b2a11-149">Die is_directory-Spalte im FileTable-Schema</span><span class="sxs-lookup"><span data-stu-id="b2a11-149">The is_directory column in the FileTable schema</span></span>  
 <span data-ttu-id="b2a11-150">In der folgenden Tabelle wird die Interaktion zwischen der Spalte **is_directory** und der Spalte **file_stream** beschrieben, die die FILESTREAM-Daten in einer FileTable enthält.</span><span class="sxs-lookup"><span data-stu-id="b2a11-150">The following table describes the interaction between the **is_directory** column and the **file_stream** column that contains the FILESTREAM data in a FileTable.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="b2a11-151">*is_directory* **Wert**</span><span class="sxs-lookup"><span data-stu-id="b2a11-151">*is_directory* **value**</span></span>|<span data-ttu-id="b2a11-152">*file_stream* **Wert**</span><span class="sxs-lookup"><span data-stu-id="b2a11-152">*file_stream* **value**</span></span>|<span data-ttu-id="b2a11-153">**Verhalten**</span><span class="sxs-lookup"><span data-stu-id="b2a11-153">**Behavior**</span></span>|  
|<span data-ttu-id="b2a11-154">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2a11-154">FALSE</span></span>|<span data-ttu-id="b2a11-155">NULL</span><span class="sxs-lookup"><span data-stu-id="b2a11-155">NULL</span></span>|<span data-ttu-id="b2a11-156">Dies ist eine ungültige Kombination, die von einer systemdefinierten Einschränkung abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="b2a11-156">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
|<span data-ttu-id="b2a11-157">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2a11-157">FALSE</span></span>|\<value>|<span data-ttu-id="b2a11-158">Das Element stellt eine Datei dar.</span><span class="sxs-lookup"><span data-stu-id="b2a11-158">The item represents a file.</span></span>|  
|<span data-ttu-id="b2a11-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2a11-159">TRUE</span></span>|<span data-ttu-id="b2a11-160">NULL</span><span class="sxs-lookup"><span data-stu-id="b2a11-160">NULL</span></span>|<span data-ttu-id="b2a11-161">Das Element stellt ein Verzeichnis dar.</span><span class="sxs-lookup"><span data-stu-id="b2a11-161">The item represents a directory.</span></span>|  
|<span data-ttu-id="b2a11-162">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2a11-162">TRUE</span></span>|\<value>|<span data-ttu-id="b2a11-163">Dies ist eine ungültige Kombination, die von einer systemdefinierten Einschränkung abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="b2a11-163">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
  
##  <a name="using-virtual-network-names-vnns-with-alwayson-availability-groups"></a><a name="alwayson"></a> <span data-ttu-id="b2a11-164">Verwenden von virtuellen Netzwerknamen mit (VNNs) AlwaysOn-Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="b2a11-164">Using Virtual Network Names (VNNs) with AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="b2a11-165">Wenn die Datenbank, die FILESTREAM- oder FileTable-Daten enthält, zu einer AlwaysOn-Verfügbarkeitsgruppe gehört:</span><span class="sxs-lookup"><span data-stu-id="b2a11-165">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="b2a11-166">Die FILESTREAM-Funktion und die FileTable-Funktion akzeptieren oder geben virtuelle Netzwerknamen (VNNs) statt Computernamen zurück.</span><span class="sxs-lookup"><span data-stu-id="b2a11-166">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="b2a11-167">Weitere Informationen zu diesen Funktionen finden Sie unter [Filestream- und FileTable-Funktionen &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2a11-167">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="b2a11-168">Bei allen Zugriffen auf FILESTREAM- oder FileTable-Daten über Dateisystem-APIs sollten VNNs statt der Computernamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2a11-168">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span> <span data-ttu-id="b2a11-169">Weitere Informationen finden Sie unter [FILESTREAM und FileTable bei Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2a11-169">For more information, see [FILESTREAM and FileTable with AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a11-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2a11-170">See Also</span></span>  
 <span data-ttu-id="b2a11-171">[Aktivieren der erforderlichen Komponenten für FileTable](enable-the-prerequisites-for-filetable.md) </span><span class="sxs-lookup"><span data-stu-id="b2a11-171">[Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md) </span></span>  
 <span data-ttu-id="b2a11-172">[Erstellen, Ändern und Löschen von FileTables](create-alter-and-drop-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="b2a11-172">[Create, Alter, and Drop FileTables](create-alter-and-drop-filetables.md) </span></span>  
 <span data-ttu-id="b2a11-173">[Zugreifen auf FileTables mit Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="b2a11-173">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="b2a11-174">Zugreifen auf FileTables mit Datei-E/A-APIs</span><span class="sxs-lookup"><span data-stu-id="b2a11-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
