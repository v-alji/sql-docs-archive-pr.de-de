---
title: Anzeigen von Kollokations Informationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622689"
---
# <a name="view-collation-information"></a><span data-ttu-id="1449c-102">Anzeigen von Sortierungsinformationen</span><span class="sxs-lookup"><span data-stu-id="1449c-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="1449c-103">Sie können die Sortierung eines Servers, einer Datenbank oder Spalte in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mithilfe der Menüoptionen des Objekt-Explorers oder mit [!INCLUDE[tsql](../../includes/tsql-md.md)] anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1449c-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="1449c-104">So zeigen Sie eine Sortierungseinstellung an</span><span class="sxs-lookup"><span data-stu-id="1449c-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="1449c-105">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="1449c-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="1449c-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1449c-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="1449c-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1449c-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1449c-108">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1449c-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1449c-109">**So zeigen Sie eine Sortierungseinstellung für einen Server (Instanz von SQL Server) im Objekt-Explorer an**</span><span class="sxs-lookup"><span data-stu-id="1449c-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="1449c-110">Stellen Sie mithilfe des Objekt-Explorers eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1449c-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1449c-111">Klicken Sie mit der rechten Maustaste auf die Spalte, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1449c-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="1449c-112">**Wenn die Sortierungseigenschaft leer ist, ist die Spalte kein Zeichendatentyp.**</span><span class="sxs-lookup"><span data-stu-id="1449c-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="1449c-113">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="1449c-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1449c-114">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die Datenbank, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1449c-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="1449c-115">**So zeigen Sie eine Sortierungseinstellung für eine Spalte im Objekt-Explorer an**</span><span class="sxs-lookup"><span data-stu-id="1449c-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="1449c-116">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="1449c-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1449c-117">Erweitern Sie **Datenbanken**, die Datenbank und anschließend **Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="1449c-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="1449c-118">Erweitern Sie die Tabelle, die die Spalte enthält, und erweitern Sie dann **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="1449c-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="1449c-119">Klicken Sie mit der rechten Maustaste auf die Spalte, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1449c-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="1449c-120">Wenn die Sortierungseigenschaft leer ist, ist die Spalte nicht vom Zeichendatentyp.</span><span class="sxs-lookup"><span data-stu-id="1449c-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1449c-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1449c-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="1449c-122">**So zeigen Sie die Sortierungseinstellung eines Servers an**</span><span class="sxs-lookup"><span data-stu-id="1449c-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="1449c-123">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1449c-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="1449c-124">Geben Sie im Abfragefenster die folgende Anweisung ein, die die SERVERPROPERTY-Systemfunktion verwendet:</span><span class="sxs-lookup"><span data-stu-id="1449c-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="1449c-125">Alternativ können Sie die gespeicherte Systemprozedur "sp_helpsort" verwenden.</span><span class="sxs-lookup"><span data-stu-id="1449c-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="1449c-126">**So zeigen Sie alle von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unterstützten Sortierreihenfolgen an**</span><span class="sxs-lookup"><span data-stu-id="1449c-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="1449c-127">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1449c-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="1449c-128">Geben Sie im Abfragefenster die folgende Anweisung ein, die die SERVERPROPERTY-Systemfunktion verwendet:</span><span class="sxs-lookup"><span data-stu-id="1449c-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="1449c-129">**So zeigen Sie die Sortierungseinstellung einer Datenbank an**</span><span class="sxs-lookup"><span data-stu-id="1449c-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="1449c-130">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1449c-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="1449c-131">Geben Sie im Abfragefenster die folgende Anweisung ein, die die sys.databases-Systemkatalogsicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1449c-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="1449c-132">Alternativ können Sie die DATABASEPROPERTYEX-Systemfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="1449c-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="1449c-133">**So zeigen Sie die Sortierungseinstellung einer Spalte an**</span><span class="sxs-lookup"><span data-stu-id="1449c-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="1449c-134">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1449c-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="1449c-135">Geben Sie im Abfragefenster die folgende Anweisung ein, die die sys.columns-Systemkatalogsicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1449c-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1449c-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1449c-136">See Also</span></span>  
 <span data-ttu-id="1449c-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1449c-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="1449c-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1449c-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="1449c-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1449c-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="1449c-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1449c-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="1449c-141">[Rangfolge von Sortierungen &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1449c-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="1449c-142">sp_helpsort &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1449c-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
