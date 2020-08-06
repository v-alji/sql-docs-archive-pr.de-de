---
title: Umbenennen einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617095"
---
# <a name="rename-a-database"></a><span data-ttu-id="37564-102">Umbenennen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="37564-102">Rename a Database</span></span>
  <span data-ttu-id="37564-103">In diesem Thema wird beschrieben, wie eine benutzerdefinierte Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="37564-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="37564-104">Der Name der Datenbank kann alle Zeichen enthalten, die den Regeln für Bezeichner entsprechen.</span><span class="sxs-lookup"><span data-stu-id="37564-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="37564-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="37564-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37564-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="37564-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37564-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="37564-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="37564-108">Security</span><span class="sxs-lookup"><span data-stu-id="37564-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="37564-109">**So benennen Sie eine Datenbank um mit:**</span><span class="sxs-lookup"><span data-stu-id="37564-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="37564-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37564-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="37564-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37564-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="37564-112">**Nachverfolgung:**  [Nach dem Umbenennen einer Datenbank](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="37564-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37564-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="37564-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="37564-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="37564-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="37564-115">Systemdatenbanken können nicht umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="37564-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37564-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="37564-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37564-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="37564-117">Permissions</span></span>  
 <span data-ttu-id="37564-118">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="37564-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37564-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37564-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="37564-120">So benennen Sie eine Datenbank um</span><span class="sxs-lookup"><span data-stu-id="37564-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="37564-121">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="37564-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="37564-122">Stellen Sie sicher, dass die Datenbank zurzeit nicht verwendet wird, und fahren Sie dann mit der [Festlegung des Einzelbenutzermodus für die Datenbank](set-a-database-to-single-user-mode.md)fort.</span><span class="sxs-lookup"><span data-stu-id="37564-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="37564-123">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die Datenbank, die umbenannt werden soll, und klicken Sie anschließend auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="37564-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="37564-124">Geben Sie den neuen Datenbanknamen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="37564-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="37564-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37564-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="37564-126">So benennen Sie eine Datenbank um</span><span class="sxs-lookup"><span data-stu-id="37564-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="37564-127">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="37564-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="37564-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="37564-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="37564-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="37564-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="37564-130">In diesem Beispiel wird der Name der Datenbank `AdventureWorks2012` in `Northwind`geändert.</span><span class="sxs-lookup"><span data-stu-id="37564-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a><span data-ttu-id="37564-131">Nachverfolgung: nach dem Umbenennen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="37564-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="37564-132">Sichern Sie die **master** -Datenbank nach jedem Umbenennen einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="37564-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37564-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37564-133">See Also</span></span>  
 <span data-ttu-id="37564-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37564-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="37564-135">Datenbankbezeichner</span><span class="sxs-lookup"><span data-stu-id="37564-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
