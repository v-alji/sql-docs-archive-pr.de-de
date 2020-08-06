---
title: Anzeigen von Informationen zum Daten- und Protokollspeicherplatz einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725874"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="84938-102">Anzeigen von Informationen zum Daten- und Protokollspeicherplatz einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="84938-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="84938-103">In diesem Thema wird beschrieben, wie die Informationen zum Daten- und Protokollspeicherplatz einer Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="84938-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="84938-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="84938-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="84938-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="84938-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="84938-106">Security</span><span class="sxs-lookup"><span data-stu-id="84938-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="84938-107">**So zeigen Sie Informationen zum Daten- und Protokollspeicherplatz einer Datenbank an mit:**</span><span class="sxs-lookup"><span data-stu-id="84938-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="84938-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84938-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="84938-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84938-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84938-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="84938-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84938-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="84938-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="84938-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="84938-112">Permissions</span></span>  
 <span data-ttu-id="84938-113">Die Berechtigung zum Ausführen von **sp_spaceused** wird der **public** -Rolle erteilt.</span><span class="sxs-lookup"><span data-stu-id="84938-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="84938-114">Nur Mitglieder der festen Datenbankrolle **db_owner** können den Parameter **@updateusage** angeben.</span><span class="sxs-lookup"><span data-stu-id="84938-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="84938-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84938-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="84938-116">So zeigen Sie Informationen zum Daten- und Protokollspeicherplatz einer Datenbank an</span><span class="sxs-lookup"><span data-stu-id="84938-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="84938-117">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="84938-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="84938-118">Erweitern Sie **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="84938-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="84938-119">Klicken Sie mit der rechten Maustaste auf eine Datenbank, zeigen Sie auf **Berichte**, zeigen Sie auf **Standardberichte**, und klicken Sie dann auf **Datenträgerverwendung**.</span><span class="sxs-lookup"><span data-stu-id="84938-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="84938-120">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84938-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="84938-121">So zeigen Sie Informationen zum Daten- und Protokollspeicherplatz einer Datenbank mit sp_spaceused an</span><span class="sxs-lookup"><span data-stu-id="84938-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="84938-122">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="84938-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="84938-123">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="84938-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="84938-124">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="84938-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="84938-125">In diesem Beispiel wird die gespeicherte Systemprozedur [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) verwendet, um Speicherplatzinformationen für die `Vendor` -Tabelle und ihre Indizes zu melden.</span><span class="sxs-lookup"><span data-stu-id="84938-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="84938-126">So zeigen Sie Daten und Protokollspeicherplatzinformationen für eine Datenbank durch das Abfragen von sys.database_files an</span><span class="sxs-lookup"><span data-stu-id="84938-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="84938-127">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="84938-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="84938-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="84938-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="84938-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="84938-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="84938-130">In diesem Beispiel wird die Katalogsicht [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) abgefragt, um bestimmte Informationen zu den Daten- und Protokolldateien in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="84938-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="84938-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84938-131">See Also</span></span>  
 <span data-ttu-id="84938-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="84938-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="84938-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="84938-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="84938-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="84938-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="84938-135">[Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="84938-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="84938-136">Löschen von Daten- oder Protokolldateien aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="84938-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
