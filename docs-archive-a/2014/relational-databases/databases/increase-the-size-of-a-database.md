---
title: Erhöhen der Größe einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725869"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="8c272-102">Erhöhen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="8c272-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="8c272-103">Dieses Thema beschreibt, wie eine Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]vergrößert wird.</span><span class="sxs-lookup"><span data-stu-id="8c272-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8c272-104">Datenbanken können entweder durch Vergrößern von vorhandenen Daten- oder Protokolldateien oder durch Hinzufügen neuer Dateien erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="8c272-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="8c272-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8c272-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c272-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8c272-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c272-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8c272-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8c272-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8c272-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c272-109">**So erhöhen Sie die Größe einer Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="8c272-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="8c272-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c272-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c272-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c272-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c272-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8c272-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8c272-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8c272-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8c272-114">Sie können keine Dateien hinzufügen oder entfernen, während eine BACKUP-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c272-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c272-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8c272-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c272-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8c272-116">Permissions</span></span>  
 <span data-ttu-id="8c272-117">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8c272-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c272-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c272-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="8c272-119">So erhöhen Sie die Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="8c272-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="8c272-120">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="8c272-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8c272-121">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die zu vergrößernde Datenbank, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8c272-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8c272-122">Wählen Sie unter **Datenbankeigenschaften**die Seite **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="8c272-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="8c272-123">Ändern Sie den Wert in der Spalte **Anfangsgröße (MB)** der entsprechenden Datei, um die Größe einer vorhandenen Datei zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="8c272-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="8c272-124">Sie müssen jedoch die Größe der Datenbank um mindestens 1 MB erhöhen.</span><span class="sxs-lookup"><span data-stu-id="8c272-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="8c272-125">Um die Größe der Datenbank durch das Hinzufügen einer neuen Datei zu erhöhen, klicken Sie auf **Hinzufügen** und geben die Werte für die neue Datei ein.</span><span class="sxs-lookup"><span data-stu-id="8c272-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="8c272-126">Weitere Informationen finden Sie unter [Hinzufügen von Daten oder Protokolldateien mit einer Datenbank](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="8c272-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="8c272-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c272-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c272-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c272-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="8c272-129">So erhöhen Sie die Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="8c272-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="8c272-130">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8c272-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c272-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8c272-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c272-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8c272-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8c272-133">In diesem Beispiel wird die Größe der Datei `test1dat3`erhöht.</span><span class="sxs-lookup"><span data-stu-id="8c272-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="8c272-134">Weitere Beispiele finden Sie unter [ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="8c272-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c272-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c272-135">See Also</span></span>  
 <span data-ttu-id="8c272-136">[Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="8c272-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="8c272-137">Verkleinern einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="8c272-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
