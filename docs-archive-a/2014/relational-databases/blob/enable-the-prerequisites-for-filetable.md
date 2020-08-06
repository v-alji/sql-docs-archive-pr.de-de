---
title: Aktivieren der erforderlichen Komponenten für FileTable | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607847"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="0643b-102">Aktivieren der erforderlichen Komponenten für FileTable</span><span class="sxs-lookup"><span data-stu-id="0643b-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="0643b-103">Beschreibt, wie die erforderlichen Komponenten zum Erstellen und Verwenden von FileTables aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0643b-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="0643b-104">Aktivieren der erforderlichen Komponenten für FileTable</span><span class="sxs-lookup"><span data-stu-id="0643b-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="0643b-105">Aktivieren Sie zum Aktivieren der erforderlichen Komponenten zum Erstellen und Verwenden von FileTables die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="0643b-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="0643b-106">**Auf Instanzebene:**</span><span class="sxs-lookup"><span data-stu-id="0643b-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="0643b-107">Aktivieren von FILESTREAM auf Instanzebene</span><span class="sxs-lookup"><span data-stu-id="0643b-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="0643b-108">**Auf Datenbankebene:**</span><span class="sxs-lookup"><span data-stu-id="0643b-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="0643b-109">Bereitstellen einer FILESTREAM-Dateigruppe auf der Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="0643b-110">Aktivieren des nicht transaktionalen Zugriffs auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="0643b-111">Angeben eines Verzeichnisses für FileTables auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="0643b-112">Aktivieren von FILESTREAM auf Instanzebene</span><span class="sxs-lookup"><span data-stu-id="0643b-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="0643b-113">FileTables erweitern die Funktionen der FILESTREAM-Funktion von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0643b-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0643b-114">Daher muss FILESTREAM für Datei-E/A-Zugriff auf der Windows-Ebene und in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktiviert werden, bevor Sie FileTables erstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0643b-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="0643b-115">Vorgehensweise: Aktivieren von FILESTREAM auf Instanzebene</span><span class="sxs-lookup"><span data-stu-id="0643b-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="0643b-116">Informationen zum Aktivieren von FILESTREAM finden Sie unter [Aktivieren und Konfigurieren von FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="0643b-117">Wenn Sie `sp_configure` aufrufen, um FILESTREAM auf Instanzebene zu aktivieren, müssen Sie die filestream_access_level-Option auf 2 festlegen.</span><span class="sxs-lookup"><span data-stu-id="0643b-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="0643b-118">Weitere Informationen finden Sie unter [Filestream-Zugriffsebene (Serverkonfigurationsoption)](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="0643b-119">Vorgehensweise: Zulassen von FILESTREAM durch die Firewall</span><span class="sxs-lookup"><span data-stu-id="0643b-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="0643b-120">Informationen zum Zulassen von FILESTREAM durch die Firewall finden Sie unter [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="0643b-121">Bereitstellen einer FILESTREAM-Dateigruppe auf der Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="0643b-122">Bevor Sie FileTables in einer Datenbank erstellen können, muss die Datenbank eine FILESTREAM-Dateigruppe haben.</span><span class="sxs-lookup"><span data-stu-id="0643b-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="0643b-123">Weitere Informationen zu dieser Voraussetzung finden Sie unter [Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="0643b-124">Aktivieren des nicht transaktionalen Zugriffs auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="0643b-125">Über FileTables können Windows-Anwendungen ein Windows-Dateihandle für FILESTREAM-Daten abrufen, ohne dass hierfür eine Transaktion erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0643b-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="0643b-126">Um diesen nicht transaktionalen Zugriff auf in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gespeicherte Dateien zuzulassen, müssen Sie die gewünschte Ebene des nicht transaktionalen Zugriffs auf Datenbankebene für jede Datenbank angeben, die FileTables enthält.</span><span class="sxs-lookup"><span data-stu-id="0643b-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="0643b-127">Vorgehensweise: Überprüfen, ob nicht transaktionaler Zugriff auf Datenbanken aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="0643b-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="0643b-128">Fragen Sie die Katalogsicht [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) ab, und überprüfen Sie die Spalten **non_transacted_access** und **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="0643b-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="0643b-129">Vorgehensweise: Aktivieren von nicht transaktionalem Zugriff auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="0643b-130">Die verfügbaren Stufen des nicht transaktionalen Zugriffs sind FULL, READ_ONLY und OFF.</span><span class="sxs-lookup"><span data-stu-id="0643b-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="0643b-131">**Angeben der Ebene des nicht transaktionalen Zugriffs mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0643b-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="0643b-132">Wenn Sie **eine neue Datenbank erstellen**, rufen Sie die [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)-Anweisung mit der FILESTREAM-Option **NON_TRANSACTED_ACCESS** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="0643b-133">Wenn Sie **eine vorhandene Datenbank ändern**, rufen Sie die [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)-Anweisung mit der FILESTREAM-Option **NON_TRANSACTED_ACCESS** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="0643b-134">**Angeben der Ebene des nicht transaktionalen Zugriffs mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0643b-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="0643b-135">Sie können die Ebene des nicht transaktionalen Zugriffs im Feld **FILESTREAM Nicht durchgeführter Zugriff** der Seite **Optionen** des Dialogfelds **Datenbankeigenschaften** angeben.</span><span class="sxs-lookup"><span data-stu-id="0643b-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="0643b-136">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Datenbankeigenschaften &#40;Seite Optionen&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="0643b-137">Angeben eines Verzeichnisses für FileTables auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="0643b-138">Wenn Sie nicht transaktionalen Zugriff auf Dateien auf Datenbankebene aktivieren, können Sie gleichzeitig optional einen Verzeichnisnamen mit der **DIRECTORY_NAME** -Option angeben.</span><span class="sxs-lookup"><span data-stu-id="0643b-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="0643b-139">Wenn Sie keinen Verzeichnisnamen angeben, wenn Sie nicht transaktionalen Zugriff aktivieren, müssen Sie diesen später angeben, bevor Sie FileTables in der Datenbank erstellen können.</span><span class="sxs-lookup"><span data-stu-id="0643b-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="0643b-140">In der FileTable-Ordnerhierarchie wird dieses Verzeichnis auf Datenbankebene das untergeordnete Element des Freigabenamens, das für FILESTREAM auf Instanzebene angegeben wurde, und das übergeordnete Element von den in der Datenbank erstellten FileTables.</span><span class="sxs-lookup"><span data-stu-id="0643b-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="0643b-141">Weitere Informationen finden Sie unter [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="0643b-142">Vorgehensweise: Angeben eines Verzeichnisses für Dateitabellen auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="0643b-143">Der angegebene Name muss in der Instanz für Verzeichnisse auf Datenbankebene eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0643b-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="0643b-144">**Angeben eines Verzeichnisses für FileTables mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0643b-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="0643b-145">Wenn Sie **eine neue Datenbank erstellen**, rufen Sie die [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)-Anweisung mit der FILESTREAM-Option **DIRECTORY_NAME** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="0643b-146">Wenn Sie **eine vorhandene Datenbank ändern**, rufen Sie die [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)-Anweisung mit der FILESTREAM-Option **DIRECTORY_NAME** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="0643b-147">Wenn Sie diese Optionen verwenden, um den Verzeichnisnamen zu ändern, muss die Datenbank exklusiv gesperrt sein und darf keine offenen Dateihandles aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0643b-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="0643b-148">Wenn Sie **eine Datenbank anfügen**, rufen Sie die [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)-Anweisung mit der **FOR ATTACH**-Option und der FILESTREAM-Option **DIRECTORY_NAME** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="0643b-149">Wenn Sie **eine Datenbank wiederherstellen**, rufen Sie die [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)-Anweisung mit der FILESTREAM-Option **DIRECTORY_NAME** auf.</span><span class="sxs-lookup"><span data-stu-id="0643b-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="0643b-150">**Angeben eines Verzeichnisses für FileTables mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0643b-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="0643b-151">Sie können im Feld **FILESTREAM Verzeichnisname** der Seite **Optionen** des Dialogfelds **Datenbankeigenschaften** einen Verzeichnisnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="0643b-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="0643b-152">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Datenbankeigenschaften &#40;Seite Optionen&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="0643b-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a><span data-ttu-id="0643b-153">Vorgehensweise: Anzeigen vorhandener Verzeichnisnamen für die Instanz</span><span class="sxs-lookup"><span data-stu-id="0643b-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="0643b-154">Fragen Sie zum Anzeigen einer Liste vorhandener Verzeichnisnamen für die Instanz die [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)-Katalogsicht ab, und überprüfen Sie die **filestream_database_directory_name**-Spalte.</span><span class="sxs-lookup"><span data-stu-id="0643b-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="0643b-155">Anforderungen und Einschränkungen für das Verzeichnis auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="0643b-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="0643b-156">Das Festlegen von **DIRECTORY_NAME** ist beim Aufrufen von **CREATE DATABASE** oder **ALTER DATABASE** optional.</span><span class="sxs-lookup"><span data-stu-id="0643b-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="0643b-157">Wenn Sie keinen Wert für **DIRECTORY_NAME** angeben, bleibt der Verzeichnisname NULL.</span><span class="sxs-lookup"><span data-stu-id="0643b-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="0643b-158">Sie können jedoch erst FileTables in der Datenbank erstellen, wenn Sie einen Wert für **DIRECTORY_NAME** auf Datenbankebene angeben.</span><span class="sxs-lookup"><span data-stu-id="0643b-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="0643b-159">Der Verzeichnisname, den Sie angeben, muss den Anforderungen des Dateisystems im Hinblick auf einen gültigen Verzeichnisnamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0643b-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="0643b-160">Wenn die Datenbank FileTables enthält, können Sie den **DIRECTORY_NAME** nicht auf einen NULL-Wert zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="0643b-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="0643b-161">Wenn Sie eine Datenbank anfügen oder wiederherstellen, schlägt der Vorgang fehl, wenn die neue Datenbank über einen Wert für **DIRECTORY_NAME** verfügt, der bereits in der Zielinstanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0643b-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="0643b-162">Geben Sie einen eindeutigen Wert für **DIRECTORY_NAME** an, wenn Sie **CREATE DATABASE FOR ATTACH** oder **RESTORE DATABASE**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0643b-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="0643b-163">Wenn Sie eine vorhandene Datenbank auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]aktualisieren, ist der Wert von **DIRECTORY_NAME** NULL.</span><span class="sxs-lookup"><span data-stu-id="0643b-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="0643b-164">Wenn Sie nicht transaktionalen Zugriff auf Datenbankebene aktivieren oder deaktivieren, wird nicht überprüft, ob der Verzeichnisname angegeben wurde oder ob er eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="0643b-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="0643b-165">Wenn Sie eine Datenbank löschen, die für FileTables aktiviert wurde, werden das Verzeichnis auf Datenbankebene und alle Verzeichnisstrukturen aller FileTables darunter entfernt.</span><span class="sxs-lookup"><span data-stu-id="0643b-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
