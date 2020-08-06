---
title: Festlegen oder Ändern der Datenbanksortierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622697"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="44b71-102">Festlegen oder Ändern der Datenbanksortierung</span><span class="sxs-lookup"><span data-stu-id="44b71-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="44b71-103">In diesem Thema wird beschrieben, wie die Datenbanksortierung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]festgelegt und geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="44b71-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="44b71-104">Wenn keine Sortierung angegeben wird, wird die Sortierung des Servers verwendet.</span><span class="sxs-lookup"><span data-stu-id="44b71-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="44b71-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="44b71-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44b71-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="44b71-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44b71-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="44b71-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="44b71-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="44b71-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="44b71-109">Security</span><span class="sxs-lookup"><span data-stu-id="44b71-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44b71-110">**Festlegen oder Ändern der Datenbanksortierung mit:**</span><span class="sxs-lookup"><span data-stu-id="44b71-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="44b71-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44b71-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="44b71-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44b71-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44b71-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="44b71-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="44b71-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="44b71-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="44b71-115">Windows-Nur-Unicode-Sortierungen können nur mit der COLLATE-Klausel verwendet werden, um Sortierungen auf die Datentypen `nchar`, `nvarchar` und `ntext` bei Daten auf Spalten- und Ausdrucksebene anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="44b71-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="44b71-116">Sie können nicht mit der COLLATE-Klausel verwendet werden, um die Sortierung einer Datenbank oder Serverinstanz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="44b71-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="44b71-117">Wenn die angegebene Sortierung oder die Sortierung des Objekts, auf das verwiesen wird, eine Codepage verwendet, die nicht von Windows unterstützt wird, zeigt [!INCLUDE[ssDE](../../includes/ssde-md.md)] einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="44b71-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="44b71-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="44b71-118">Recommendations</span></span>  
  
-   <span data-ttu-id="44b71-119">Die Namen der unterstützten Sortierungen finden Sie unter [Name der Windows-Sortierung &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) und [SQL Server-Sortierungsname &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql). Alternativ können Sie die Systemfunktion [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) verwenden.</span><span class="sxs-lookup"><span data-stu-id="44b71-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="44b71-120">Das Ändern der Datenbanksortierung ändert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="44b71-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="44b71-121">Alle `char`-, `varchar`-, `text`-, `nchar`-, `nvarchar`- und `ntext`-Spalten in Systemtabellen erhalten die neue Sortierung.</span><span class="sxs-lookup"><span data-stu-id="44b71-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="44b71-122">Sämtliche vorhandene `char`-, `varchar`-, `text`-, `nchar`-, `nvarchar`- und `ntext`-Parameter und skalare Rückgabewerte für gespeicherte Prozeduren und benutzerdefinierte Funktionen erhalten die neue Sortierung.</span><span class="sxs-lookup"><span data-stu-id="44b71-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="44b71-123">Die `char`-, `varchar`-, `text`-, `nchar`-, `nvarchar`- und `ntext`-Systemdatentypen sowie alle benutzerdefinierten Datentypen, die auf Systemdatentypen basieren, erhalten die neue Sortierung.</span><span class="sxs-lookup"><span data-stu-id="44b71-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="44b71-124">Sie können die Sortierung von neuen Objekten, die in einer Benutzerdatenbank erstellt werden, mithilfe der COLLATE-Klausel der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung ändern.</span><span class="sxs-lookup"><span data-stu-id="44b71-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="44b71-125">Diese Anweisung ändert jedoch nicht die Sortierung der Spalten in vorhandenen benutzerdefinierten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="44b71-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="44b71-126">Letztere können mithilfe der COLLATE-Klausel der [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql)-Anweisung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="44b71-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44b71-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="44b71-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44b71-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="44b71-128">Permissions</span></span>  
 <span data-ttu-id="44b71-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="44b71-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="44b71-130">Erfordert die CREATE DATABASE-Berechtigung in der **Master** -Datenbank oder die Berechtigung CREATE ANY DATABASE oder ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="44b71-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="44b71-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="44b71-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="44b71-132">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="44b71-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44b71-133">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44b71-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="44b71-134">So legen Sie die Datenbanksortierung oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="44b71-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="44b71-135">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, erweitern Sie diese Instanz und dann **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="44b71-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="44b71-136">Wenn Sie eine neue Datenbank erstellen, klicken mit der rechten Maustaste auf **Datenbanken** , und klicken Sie anschließend auf **Neue Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="44b71-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="44b71-137">Wenn Sie die Standardsortierung nicht möchten, klicken auf die Seite **Optionen** , und wählen aus der Dropdownliste **Sortierung** eine Sortierung aus.</span><span class="sxs-lookup"><span data-stu-id="44b71-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="44b71-138">Wenn eine Datenbank bereits vorhanden ist, können Sie alternativ mit der rechten Maustaste auf die Datenbank klicken, die geändert werden soll, und auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="44b71-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="44b71-139">Klicken Sie auf die Seite **Optionen** , und wählen Sie aus der Dropdownliste **Sortierung** eine Sortierung aus.</span><span class="sxs-lookup"><span data-stu-id="44b71-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="44b71-140">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="44b71-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="44b71-141">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44b71-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="44b71-142">So legen Sie die Datenbanksortierung fest</span><span class="sxs-lookup"><span data-stu-id="44b71-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="44b71-143">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="44b71-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="44b71-144">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="44b71-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="44b71-145">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="44b71-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="44b71-146">In diesem Beispiel wird gezeigt, wie die [COLLATE-Klausel](/sql/t-sql/statements/collations) verwendet wird, um einen Sortierungsnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="44b71-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="44b71-147">Im folgenden Beispiel wird die Datenbank mit dem Namen `MyOptionsTest` erstellt, die die Sortierung `Latin1_General_100_CS_AS_SC` verwendet.</span><span class="sxs-lookup"><span data-stu-id="44b71-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="44b71-148">Nachdem Sie die Datenbank erstellt haben, führen Sie die `SELECT` -Anweisung aus, um die Einstellung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="44b71-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="44b71-149">So ändern Sie die Datenbanksortierung</span><span class="sxs-lookup"><span data-stu-id="44b71-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="44b71-150">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="44b71-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="44b71-151">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="44b71-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="44b71-152">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="44b71-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="44b71-153">In diesem Beispiel wird gezeigt, wie die [COLLATE-Klausel](/sql/t-sql/statements/collations) in einer [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung verwendet wird, um den Sortierungsnamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="44b71-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="44b71-154">Führen Sie die `SELECT` -Anweisung aus, um die Änderung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="44b71-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="44b71-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44b71-155">See Also</span></span>  
 <span data-ttu-id="44b71-156">[Sortierung und Unicode-Unterstützung](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="44b71-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="44b71-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="44b71-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="44b71-159">[SQL Server-Sortierungsname &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="44b71-160">[Name der Windows-Sortierung &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="44b71-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="44b71-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="44b71-162">[Rangfolge von Sortierungen &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="44b71-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="44b71-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="44b71-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44b71-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="44b71-166">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44b71-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
