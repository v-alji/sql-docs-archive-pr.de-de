---
title: Erstellen einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617117"
---
# <a name="create-a-database"></a><span data-ttu-id="65400-102">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="65400-102">Create a Database</span></span>
  <span data-ttu-id="65400-103">In diesem Thema wird beschrieben, wie eine Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="65400-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="65400-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="65400-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65400-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="65400-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65400-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="65400-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="65400-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="65400-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="65400-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="65400-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="65400-109">Security</span><span class="sxs-lookup"><span data-stu-id="65400-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65400-110">**So erstellen Sie eine Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="65400-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="65400-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65400-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="65400-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65400-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65400-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="65400-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="65400-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="65400-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="65400-115">Maximal 32.767 Datenbanken können auf einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65400-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="65400-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="65400-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="65400-117">Die CREATE DATABASE-Anweisung muss im Autocommitmodus (dem Standardmodus für die Transaktionsverwaltung) ausgeführt werden und ist in einer expliziten oder impliziten Transaktion nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="65400-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="65400-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="65400-118">Recommendations</span></span>  
  
-   <span data-ttu-id="65400-119">Die [master](master-database.md) -Datenbank sollte immer dann gesichert werden, wenn eine Benutzerdatenbank erstellt, geändert oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="65400-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="65400-120">Wenn Sie eine Datenbank erstellen, sollten die Datendateien möglichst groß sein. Orientieren Sie sich dabei an den maximal zu erwartenden Datenmengen, die in der Datenbank gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="65400-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65400-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="65400-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65400-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="65400-122">Permissions</span></span>  
 <span data-ttu-id="65400-123">Erfordert die Berechtigung CREATE DATABASE in der master-Datenbank oder die Berechtigung CREATE ANY DATABASE oder ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="65400-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="65400-124">Zur Steuerung der Datenträgernutzung einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird die Berechtigung zum Erstellen von Datenbanken in der Regel auf einige wenige Anmeldekonten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="65400-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="65400-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65400-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="65400-126">So erstellen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="65400-126">To create a database</span></span>  
  
1.  <span data-ttu-id="65400-127">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="65400-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="65400-128">Klicken Sie mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Neue Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="65400-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="65400-129">Geben Sie unter **Neue Datenbank**einen Datenbanknamen ein.</span><span class="sxs-lookup"><span data-stu-id="65400-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="65400-130">Zum Erstellen der Datenbank unter Übernahme aller Standardwerte klicken Sie auf **OK**; ansonsten fahren Sie mit den folgenden optionalen Schritten fort.</span><span class="sxs-lookup"><span data-stu-id="65400-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="65400-131">Zum Ändern des Besitzernamens klicken Sie auf ( **…** ), um einen anderen Besitzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="65400-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65400-132">Die Option **Volltextindizierung verwenden** ist immer aktiviert und wird ausgegraut angezeigt, da ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]alle Benutzerdatenbanken volltextfähig sind.</span><span class="sxs-lookup"><span data-stu-id="65400-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="65400-133">Zum Ändern der Standardwerte der Primärdaten- und Transaktionsprotokolldateien klicken Sie im Bereich **Datenbankdateien** auf die entsprechende Zelle und geben den neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="65400-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="65400-134">Weitere Informationen finden Sie unter [Hinzufügen von Daten oder Protokolldateien mit einer Datenbank](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="65400-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="65400-135">Zum Ändern der Sortierung der Datenbank klicken Sie auf die Seite **Optionen** , und wählen dann eine Sortierung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="65400-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="65400-136">Zum Ändern des Wiederherstellungsmodells klicken Sie auf die Seite **Optionen** aus und wählen dann ein Wiederherstellungsmodell aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="65400-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="65400-137">Zum Ändern der Datenbankoptionen klicken Sie auf die Seite **Optionen** aus und ändern anschließend die Datenbankoptionen.</span><span class="sxs-lookup"><span data-stu-id="65400-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="65400-138">Eine Beschreibung jeder Option finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="65400-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="65400-139">Zum Hinzufügen einer neuen Dateigruppe klicken Sie auf die Seite **Dateigruppen** .</span><span class="sxs-lookup"><span data-stu-id="65400-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="65400-140">Klicken Sie auf **Hinzufügen** , und geben Sie dann die Werte für die Dateigruppe ein.</span><span class="sxs-lookup"><span data-stu-id="65400-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="65400-141">Zum Hinzufügen einer erweiterten Eigenschaft zur Datenbank klicken Sie auf die Seite **Erweiterte Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="65400-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="65400-142">Geben Sie in die Spalte **Name** einen Namen für die erweiterte Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="65400-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="65400-143">Geben Sie in die Spalte **Wert** den Text für die erweiterte Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="65400-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="65400-144">Geben Sie beispielsweise eine oder mehrere Angaben zur Beschreibung der Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="65400-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="65400-145">Klicken Sie auf **OK**, um die Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65400-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="65400-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65400-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="65400-147">So erstellen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="65400-147">To create a database</span></span>  
  
1.  <span data-ttu-id="65400-148">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="65400-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65400-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="65400-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65400-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="65400-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="65400-151">In diesem Beispiel wird die Datenbank mit dem Namen `Sales`erstellt.</span><span class="sxs-lookup"><span data-stu-id="65400-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="65400-152">Da das PRIMARY-Schlüsselwort nicht verwendet wird, wird die erste Datei (`Sales`_`dat`) zur primären Datei.</span><span class="sxs-lookup"><span data-stu-id="65400-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="65400-153">Da im SIZE-Parameter für die Datei `Sales`\_`dat` weder MB noch KB angegeben ist, wird die Einheit MB verwendet und in Megabyte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="65400-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="65400-154">Die `Sales`\_`log` wird in Megabyte zugeordnet, weil das Suffix `MB` explizit im `SIZE` -Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="65400-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="65400-155">Weitere Beispiele finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65400-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65400-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65400-156">See Also</span></span>  
 <span data-ttu-id="65400-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="65400-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="65400-158">[Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="65400-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="65400-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65400-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="65400-160">Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="65400-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
