---
title: Erstellen, Ändern und Löschen von FileTables | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609270"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="3eb24-102">Erstellen, Ändern und Löschen von FileTables</span><span class="sxs-lookup"><span data-stu-id="3eb24-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="3eb24-103">Beschreibt, wie eine neue FileTable erstellt bzw. eine vorhandene FileTable geändert oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="3eb24-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="3eb24-104">Erstellen einer FileTable</span><span class="sxs-lookup"><span data-stu-id="3eb24-104">Creating a FileTable</span></span>  
 <span data-ttu-id="3eb24-105">Eine FileTable ist eine spezialisierte Benutzertabelle, die ein vordefiniertes und festes Schema aufweist.</span><span class="sxs-lookup"><span data-stu-id="3eb24-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="3eb24-106">Dieses Schema speichert FILESTREAM-Daten, Datei- und Verzeichnisinformationen sowie Dateiattribute.</span><span class="sxs-lookup"><span data-stu-id="3eb24-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="3eb24-107">Weitere Informationen zum FileTable-Beispielschema finden Sie unter [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="3eb24-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="3eb24-108">Sie können mit Transact-SQL oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine neue FileTable erstellen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="3eb24-109">Da eine FileTable ein festes Schema hat, müssen Sie keine Liste von Spalten angeben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="3eb24-110">Mit der einfachen Syntax zum Erstellen einer FileTable können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="3eb24-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="3eb24-111">Einen Verzeichnisnamen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-111">A directory name.</span></span> <span data-ttu-id="3eb24-112">In der FileTable-Ordnerhierarchie wird dieses Verzeichnis auf Tabellenebene das untergeordnete Element des Datenbankverzeichnisses, das auf Datenbankebene angegeben wurde, und das übergeordnete Element der in der Tabelle gespeicherten Dateien oder Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="3eb24-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="3eb24-113">Den Namen der Sortierung, der in der Spalte **Name** der FileTable für Dateinamen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3eb24-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="3eb24-114">Die Namen, die für die 3 automatisch erstellten PRIMARY KEY- und UNIQUE-Einschränkungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="3eb24-115">Vorgehensweise: Erstellen einer Dateitabelle</span><span class="sxs-lookup"><span data-stu-id="3eb24-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="3eb24-116">**Erstellen einer FileTable mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3eb24-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="3eb24-117">Erstellen Sie eine FileTable, indem Sie die Option [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) mit der Option **AS FileTable** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="3eb24-118">Da eine FileTable ein festes Schema hat, müssen Sie keine Liste von Spalten angeben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="3eb24-119">Sie können die folgenden beiden Einstellungen für die neue FileTable angeben:</span><span class="sxs-lookup"><span data-stu-id="3eb24-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="3eb24-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="3eb24-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="3eb24-121">Gibt das Verzeichnis an, das als Stammverzeichnis für alle in der FileTable gespeicherten Dateien und Verzeichnisse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3eb24-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="3eb24-122">Dieser Name sollte für alle FileTable-Verzeichnisnamen in der Datenbank eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3eb24-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="3eb24-123">Bei Eindeutigkeitsvergleichen wird die Groß-/Kleinschreibung nicht beachtet, unabhängig von den aktuellen Sortiereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="3eb24-124">Dieser Wert hat weist den Datentyp **nvarchar(255)** auf und verwendet die feste Sortierung **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="3eb24-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="3eb24-125">Der Verzeichnisname, den Sie angeben, muss den Anforderungen des Dateisystems im Hinblick auf einen gültigen Verzeichnisnamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="3eb24-126">Dieser Name sollte für alle FileTable-Verzeichnisnamen in der Datenbank eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3eb24-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="3eb24-127">Bei Eindeutigkeitsvergleichen wird die Groß-/Kleinschreibung nicht beachtet, unabhängig von den aktuellen Sortiereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="3eb24-128">Wenn Sie beim Erstellen der FileTable keinen Verzeichnisnamen angeben, wird der Name der FileTable selbst als Verzeichnisname verwendet.</span><span class="sxs-lookup"><span data-stu-id="3eb24-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="3eb24-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="3eb24-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="3eb24-130">Gibt den Namen der Sortierung an, die auf die **Name** -Spalte in der FileTable angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3eb24-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="3eb24-131">Zur Einhaltung der Windows-Dateinamensemantik darf bei der angegebenen Sortierung die **Groß-/Kleinschreibung** nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3eb24-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="3eb24-132">Wenn Sie keinen Wert für **FILETABLE_COLLATE_FILENAME**oder **database_default**angeben, erbt die Spalte die Sortierung der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3eb24-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="3eb24-133">Wenn bei der aktuellen Datenbanksortierung die Groß-/Kleinschreibung beachtet wird, wird ein Fehler ausgelöst, und der **CREATE TABLE** -Vorgang schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="3eb24-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="3eb24-134">Sie können auch die Namen angeben, die für die 3 automatisch erstellten PRIMARY KEY- und UNIQUE-Einschränkungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="3eb24-135">Wenn Sie keine Namen angeben, dann werden diese vom System generiert, wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="3eb24-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="3eb24-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="3eb24-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="3eb24-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="3eb24-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="3eb24-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="3eb24-139">**Beispiele**</span><span class="sxs-lookup"><span data-stu-id="3eb24-139">**Examples**</span></span>  
  
 <span data-ttu-id="3eb24-140">Im folgenden Beispiel wird eine neue FileTable erstellt, und für **FILETABLE_DIRECTORY** und **FILETABLE_COLLATE_FILENAME**werden benutzerdefinierte Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="3eb24-141">Im folgenden Beispiel wird zudem eine neue FileTable erstellt.</span><span class="sxs-lookup"><span data-stu-id="3eb24-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="3eb24-142">Da keine benutzerdefinierten Werte angegeben werden, wird der Wert von **FILETABLE_DIRECTORY** zum Namen der FileTable, der Wert von **FILETABLE_COLLATE_FILENAME** wird zu database_default, und die PRIMARY KEY- und die UNIQUE-Einschränkung erhalten jeweils von System generierte Namen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="3eb24-143">**Erstellen einer FileTable mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3eb24-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="3eb24-144">Erweitern Sie im Objekt-Explorer unter der ausgewählten Datenbank die Objekte, klicken Sie dann mit der rechten Maustaste auf den Ordner **Tabellen** , und wählen Sie dann **Neue FileTable**aus.</span><span class="sxs-lookup"><span data-stu-id="3eb24-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="3eb24-145">Mit dieser Option wird ein neues Skriptfenster geöffnet, das eine Transact-SQL-Skriptvorlage enthält, die Sie zum Erstellen einer FileTable anpassen und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3eb24-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="3eb24-146">Passen Sie das Skript einfach mit der Option **Werte für Vorlagenparameter angeben** im Menü **Abfrage** an.</span><span class="sxs-lookup"><span data-stu-id="3eb24-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="3eb24-147">Anforderungen und Einschränkungen beim Erstellen einer FileTable</span><span class="sxs-lookup"><span data-stu-id="3eb24-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="3eb24-148">Sie können eine vorhandene Tabelle nicht ändern, um sie in eine FileTable zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3eb24-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="3eb24-149">Das zuvor auf der Datenbankebene angegebene übergeordnete Verzeichnis muss einen Wert ungleich NULL haben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="3eb24-150">Informationen zum Angeben des Verzeichnisses auf Datenbankebene finden Sie unter [Aktivieren der erforderlichen Komponenten für FileTable](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="3eb24-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="3eb24-151">Da eine FileTable eine FILESTREAM-Spalte enthält, erfordert eine FileTable eine gültige FILESTREAM-Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="3eb24-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="3eb24-152">Zum Erstellen einer FileTable können Sie optional eine gültige FILESTREAM-Dateigruppe als Teil des **CREATE TABLE** -Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="3eb24-153">Wenn Sie keine Dateigruppe angeben, verwendet die FileTable die Standard-FILESTREAM-Dateigruppe für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3eb24-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="3eb24-154">Wenn die Datenbank keine FILESTREAM-Dateigruppe aufweist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3eb24-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="3eb24-155">Sie können keinen Tabellenconstraint als Teil einer **CREATE TABLE...AS FILETABLE**-Anweisung erstellen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="3eb24-156">Sie können die Einschränkung jedoch später mit einer **ALTER TABLE** -Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="3eb24-157">Sie können keine FileTable in der **tempdb** -Datenbank oder in einer der anderen Systemdatenbanken erstellen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="3eb24-158">Eine FileTable kann nicht als temporäre Tabelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3eb24-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="3eb24-159">Ändern einer FileTable</span><span class="sxs-lookup"><span data-stu-id="3eb24-159">Altering a FileTable</span></span>  
 <span data-ttu-id="3eb24-160">Da eine FileTable ein vordefiniertes und festes Schema aufweist, können Sie keine Spalten hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="3eb24-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="3eb24-161">Sie können einer FileTable jedoch benutzerdefinierte Indizes, Trigger, Einschränkungen und andere Optionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="3eb24-162">Informationen zum Aktivieren bzw. Deaktivieren des FileTable-Namespace (einschließlich der systemdefinierten Einschränkungen) mithilfe der ALTER TABLE-Anweisung finden Sie unter [Verwalten von FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="3eb24-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="3eb24-163">Vorgehensweise: Ändern des Verzeichnisses für eine Dateitabelle</span><span class="sxs-lookup"><span data-stu-id="3eb24-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="3eb24-164">**Ändern des Verzeichnisses für eine FileTable mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3eb24-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="3eb24-165">Rufen Sie die ALTER TABLE-Anweisung auf, und geben Sie einen gültigen neuen Wert für die SET-Option von **FILETABLE_DIRECTORY** an.</span><span class="sxs-lookup"><span data-stu-id="3eb24-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="3eb24-166">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="3eb24-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="3eb24-167">**Ändern des Verzeichnisses für eine FileTable mit SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3eb24-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="3eb24-168">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine FileTable, und wählen Sie **Eigenschaften** aus, um das Dialogfeld **Tabelleneigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="3eb24-169">Geben Sie auf der Seite **FileTable** einen neuen Wert für **Name des FileTable-Verzeichnisses**ein.</span><span class="sxs-lookup"><span data-stu-id="3eb24-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="3eb24-170">Anforderungen und Einschränkungen beim Ändern einer FileTable</span><span class="sxs-lookup"><span data-stu-id="3eb24-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="3eb24-171">Sie können den Wert von **FILETABLE_COLLATE_FILENAME**nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3eb24-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="3eb24-172">Die systemdefinierten Spalten einer FileTable können nicht geändert, gelöscht oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3eb24-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="3eb24-173">Sie können einer FileTable keine neuen Benutzerspalten, berechnete Spalten oder persistente berechnete Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="3eb24-174">Löschen einer FileTable</span><span class="sxs-lookup"><span data-stu-id="3eb24-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="3eb24-175">Mithilfe der normalen Syntax für die [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)-Anweisung können Sie eine FileTable löschen.</span><span class="sxs-lookup"><span data-stu-id="3eb24-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="3eb24-176">Beim Löschen einer FileTable werden auch die folgenden Objekte gelöscht:</span><span class="sxs-lookup"><span data-stu-id="3eb24-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="3eb24-177">Alle Spalten der FileTable und alle der Tabelle zugeordneten Objekte, z. B. Indizes, Einschränkungen und Trigger, werden ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3eb24-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="3eb24-178">Das FileTable-Verzeichnis und die Unterverzeichnisse, die es enthielt, aus der FILESTREAM-Datei und der Verzeichnishierarchie der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3eb24-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="3eb24-179">Der DROP TABLE-Befehl schlägt fehl, wenn geöffnete Dateihandles im Dateinamespace der Dateitabelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3eb24-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="3eb24-180">Informationen zum Schließen von geöffneten Handles finden Sie unter [Verwalten von FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="3eb24-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="3eb24-181">Beim Erstellen einer FileTable werden andere Datenbankobjekte erstellt</span><span class="sxs-lookup"><span data-stu-id="3eb24-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="3eb24-182">Wenn Sie eine neue FileTable erstellen, werden auch einige systemdefinierte Indizes und Einschränkungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="3eb24-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="3eb24-183">Sie können diese Objekte nicht ändern oder löschen; sie verschwinden nur, wenn die FileTable selbst gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="3eb24-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="3eb24-184">Um eine Liste dieser Objekte anzuzeigen, fragen Sie die Katalogsicht [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="3eb24-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="3eb24-185">**Indizes, die erstellt werden, wenn Sie eine neue FileTable erstellen**</span><span class="sxs-lookup"><span data-stu-id="3eb24-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="3eb24-186">Wenn Sie eine neue FileTable erstellen, werden auch die folgenden systemdefinierten Indizes erstellt:</span><span class="sxs-lookup"><span data-stu-id="3eb24-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3eb24-187">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3eb24-187">**Columns**</span></span>|<span data-ttu-id="3eb24-188">**Indextyp**</span><span class="sxs-lookup"><span data-stu-id="3eb24-188">**Index type**</span></span>|  
|<span data-ttu-id="3eb24-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="3eb24-189">[path_locator] ASC</span></span>|<span data-ttu-id="3eb24-190">Nicht gruppierter Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="3eb24-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="3eb24-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="3eb24-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="3eb24-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="3eb24-192">[name] ASC</span></span>|<span data-ttu-id="3eb24-193">Eindeutig und nicht gruppiert</span><span class="sxs-lookup"><span data-stu-id="3eb24-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="3eb24-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="3eb24-194">[stream_id] ASC</span></span>|<span data-ttu-id="3eb24-195">Eindeutig und nicht gruppiert</span><span class="sxs-lookup"><span data-stu-id="3eb24-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="3eb24-196">**Einschränkungen, die erstellt werden, wenn Sie eine neue FileTable erstellen**</span><span class="sxs-lookup"><span data-stu-id="3eb24-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="3eb24-197">Wenn Sie eine neue FileTable erstellen, werden auch die folgenden systemdefinierten Einschränkungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="3eb24-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="3eb24-198">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3eb24-198">Constraints</span></span>|<span data-ttu-id="3eb24-199">Erzwingung</span><span class="sxs-lookup"><span data-stu-id="3eb24-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="3eb24-200">Standardeinschränkungen in den folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="3eb24-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="3eb24-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="3eb24-201">**creation_time**</span></span> <br /> <span data-ttu-id="3eb24-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="3eb24-202">**is_archive**</span></span> <br /> <span data-ttu-id="3eb24-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="3eb24-203">**is_directory**</span></span> <br /> <span data-ttu-id="3eb24-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="3eb24-204">**is_hidden**</span></span> <br /> <span data-ttu-id="3eb24-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="3eb24-205">**is_offline**</span></span> <br /> <span data-ttu-id="3eb24-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="3eb24-206">**is_readonly**</span></span> <br /> <span data-ttu-id="3eb24-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="3eb24-207">**is_system**</span></span> <br /> <span data-ttu-id="3eb24-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="3eb24-208">**is_temporary**</span></span> <br /> <span data-ttu-id="3eb24-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="3eb24-209">**last_access_time**</span></span> <br /> <span data-ttu-id="3eb24-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="3eb24-210">**last_write_time**</span></span> <br /> <span data-ttu-id="3eb24-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="3eb24-211">**path_locator**</span></span> <br /> <span data-ttu-id="3eb24-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="3eb24-212">**stream_id**</span></span>|<span data-ttu-id="3eb24-213">Die systemdefinierten Standardeinschränkungen erzwingen Standardwerte für die angegebenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="3eb24-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="3eb24-214">Check-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3eb24-214">Check constraints</span></span>|<span data-ttu-id="3eb24-215">Die systemdefinierten CHECK-Einschränkungen erzwingen die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="3eb24-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="3eb24-216">Gültige Dateinamen</span><span class="sxs-lookup"><span data-stu-id="3eb24-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="3eb24-217">Gültige Dateiattribute</span><span class="sxs-lookup"><span data-stu-id="3eb24-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="3eb24-218">Übergeordnetes Objekt muss ein Verzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="3eb24-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="3eb24-219">Namespacehierarchie ist während der Dateibearbeitung gesperrt.</span><span class="sxs-lookup"><span data-stu-id="3eb24-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="3eb24-220">**Benennungskonvention für die systemdefinierten Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="3eb24-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="3eb24-221">Die Namen der oben beschriebenen systemdefinierten Einschränkungen weisen das Format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** auf, wobei gilt:</span><span class="sxs-lookup"><span data-stu-id="3eb24-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="3eb24-222">*<constraint_type>* ist CK (CHECK-Einschränkung), DF (Standardeinschränkung), FK (Fremdschlüssel), PK (Primärschlüssel) oder UQ (UNIQUE-Einschränkung).</span><span class="sxs-lookup"><span data-stu-id="3eb24-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="3eb24-223">*\<uniquifier>* ist eine vom System generierte Zeichenfolge, die den Namen eindeutig macht.</span><span class="sxs-lookup"><span data-stu-id="3eb24-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="3eb24-224">Diese Zeichenfolge kann den FileTable-Namen und einen eindeutigen Bezeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="3eb24-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb24-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3eb24-225">See Also</span></span>  
 [<span data-ttu-id="3eb24-226">Verwalten von FileTables</span><span class="sxs-lookup"><span data-stu-id="3eb24-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
