---
title: Anzeigen einer Liste der Datenbanken in einer Instanz von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724753"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="d56b3-102">Anzeigen einer Liste der Datenbanken in einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="d56b3-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="d56b3-103">In diesem Thema wird beschrieben, wie eine Liste mit Datenbanken für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d56b3-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d56b3-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d56b3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d56b3-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d56b3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d56b3-106">Security</span><span class="sxs-lookup"><span data-stu-id="d56b3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d56b3-107">**So zeigen Sie eine Liste der Datenbanken in einer Instanz von SQL Server an mit:**</span><span class="sxs-lookup"><span data-stu-id="d56b3-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="d56b3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d56b3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d56b3-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d56b3-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d56b3-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d56b3-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d56b3-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d56b3-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d56b3-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d56b3-112">Permissions</span></span>  
 <span data-ttu-id="d56b3-113">Wenn der Aufrufer von **sys.databases** nicht der Besitzer der Datenbank und die Datenbank keine **master** - oder **tempdb**-Datenbank ist, ist zum Anzeigen der entsprechenden Zeile mindestens die Berechtigung ALTER ANY DATABASE oder VIEW ANY DATABASE auf Serverebene bzw. die Berechtigung CREATE DATABASE für die **master** -Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d56b3-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="d56b3-114">Die Datenbank, mit der der Aufrufer eine Verbindung hergestellt hat, kann immer in **sys.databases**angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d56b3-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d56b3-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d56b3-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="d56b3-116">So zeigen Sie eine Liste der Datenbanken in einer Instanz von SQL Server an</span><span class="sxs-lookup"><span data-stu-id="d56b3-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="d56b3-117">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d56b3-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d56b3-118">Erweitern Sie **Datenbanken**, um eine Liste aller Datenbanken in der Instanz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d56b3-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d56b3-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d56b3-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="d56b3-120">So zeigen Sie eine Liste der Datenbanken in einer Instanz von SQL Server an</span><span class="sxs-lookup"><span data-stu-id="d56b3-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="d56b3-121">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="d56b3-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d56b3-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d56b3-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d56b3-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d56b3-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d56b3-124">Das Beispiel gibt für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]eine Liste mit den Datenbanken zurück.</span><span class="sxs-lookup"><span data-stu-id="d56b3-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d56b3-125">Die Liste enthält die Namen der Datenbanken, die dazugehörigen Datenbank-IDs und die Datumsangaben zur Datenbankerstellung.</span><span class="sxs-lookup"><span data-stu-id="d56b3-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="d56b3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d56b3-126">See Also</span></span>  
 <span data-ttu-id="d56b3-127">[Datenbanken und Dateikatalogsichten &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d56b3-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="d56b3-128">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d56b3-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
