---
title: Anzeigen oder Ändern der Eigenschaften einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724742"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="da04d-102">Anzeigen oder Ändern der Eigenschaften einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="da04d-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="da04d-103">In diesem Thema wird die Vorgehensweise zum Anzeigen oder Ändern der Eigenschaften einer Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da04d-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="da04d-104">Nachdem Sie eine Datenbankeigenschaft geändert haben, tritt die Änderung sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="da04d-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="da04d-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="da04d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="da04d-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="da04d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="da04d-107">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="da04d-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="da04d-108">Security</span><span class="sxs-lookup"><span data-stu-id="da04d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="da04d-109">**So zeigen Sie die Eigenschaften einer Datenbank an oder ändern diese mit:**</span><span class="sxs-lookup"><span data-stu-id="da04d-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="da04d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da04d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="da04d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da04d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="da04d-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="da04d-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="da04d-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="da04d-113">Recommendations</span></span>  
  
-   <span data-ttu-id="da04d-114">Ist AUTO_CLOSE auf ON festgelegt, geben einige Spalten in der [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalogsicht sowie die DATABASEPROPERTYEX-Funktion den Wert NULL zurück, da die Datenbank nicht für den Abruf der Daten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="da04d-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="da04d-115">Führen Sie eine USE-Anwendung zum Öffnen der Datenbank aus, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="da04d-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="da04d-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="da04d-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="da04d-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="da04d-117">Permissions</span></span>  
 <span data-ttu-id="da04d-118">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="da04d-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="da04d-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da04d-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="da04d-120">So zeigen Sie die Eigenschaften einer Datenbank an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="da04d-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="da04d-121">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="da04d-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="da04d-122">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die anzuzeigende Datenbank, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="da04d-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="da04d-123">Wählen Sie im Dialogfeld **Datenbankeigenschaften** eine anzuzeigende Seite aus, um die entsprechenden Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da04d-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="da04d-124">Wählen Sie z. B. die Seite **Dateien** aus, um Daten- und Protokolldateiinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da04d-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="da04d-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da04d-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="da04d-126">So zeigen Sie eine Eigenschaft einer Datenbank mit DATABASEPROPERTYEX an</span><span class="sxs-lookup"><span data-stu-id="da04d-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="da04d-127">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="da04d-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="da04d-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="da04d-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="da04d-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da04d-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="da04d-130">In diesem Beispiel wird die Systemfunktion [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) verwendet, um den Status der AUTO_SHRINK-Datenbankoption in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="da04d-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="da04d-131">Der Rückgabewert 1 bedeutet, dass die Option auf ON festgelegt ist, und der Rückgabewert 0 bedeutet, dass die Option auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="da04d-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="da04d-132">So zeigen Sie die Eigenschaften einer Datenbank durch das Abfragen von sys.databases an</span><span class="sxs-lookup"><span data-stu-id="da04d-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="da04d-133">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="da04d-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="da04d-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="da04d-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="da04d-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da04d-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="da04d-136">In diesem Beispiel wird die [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalogsicht abgefragt, um mehrere Eigenschaften der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da04d-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="da04d-137">In diesem Beispiel wird die Datenbank-ID-Nummer (`database_id`), der Schreibschutz- oder Lese-/Schreibstatus der Datenbank (`is_read_only`), die Sortierung für die Datenbank (`collation_name`) und der Datenbank-Kompatibilitätsgrad (`compatibility_level`) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="da04d-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="da04d-138">So ändern Sie die Eigenschaften einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="da04d-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="da04d-139">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="da04d-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="da04d-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="da04d-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="da04d-141">Kopieren Sie das folgende Beispiel, und fügen Sie es in das Abfragefenster ein.</span><span class="sxs-lookup"><span data-stu-id="da04d-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="da04d-142">Im Beispiel wird der Momentaufnahmen-Isolationsstatus für die Datenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] bestimmt und der Zustand der Eigenschaft geändert. Anschließend wird die Änderung überprüft.</span><span class="sxs-lookup"><span data-stu-id="da04d-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="da04d-143">Um den Momentaufnahmen-Isolationsstatus zu bestimmen, wählen Sie die erste `SELECT` -Anweisung aus und klicken auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da04d-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="da04d-144">Um den Momentaufnahmen-Isolationsstatus zu ändern, wählen Sie die `ALTER DATABASE` -Anweisung aus und klicken auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da04d-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="da04d-145">Um die Änderung zu überprüfen, wählen Sie die zweite `SELECT` -Anweisung aus und klicken auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da04d-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="da04d-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da04d-146">See Also</span></span>  
 <span data-ttu-id="da04d-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="da04d-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="da04d-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="da04d-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="da04d-149">[ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="da04d-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="da04d-150">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="da04d-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="da04d-151">[ALTER DATABASE-Kompatibilitätsgrad &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="da04d-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="da04d-152">ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="da04d-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
