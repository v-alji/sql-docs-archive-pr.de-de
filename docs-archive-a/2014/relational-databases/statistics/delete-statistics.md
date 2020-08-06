---
title: Löschen von Statistiken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621417"
---
# <a name="delete-statistics"></a><span data-ttu-id="61c84-102">Löschen von Statistiken</span><span class="sxs-lookup"><span data-stu-id="61c84-102">Delete Statistics</span></span>
  <span data-ttu-id="61c84-103">Statistiken aus Tabellen und Sichten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] können Sie löschen mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c84-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="61c84-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="61c84-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="61c84-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="61c84-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61c84-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="61c84-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="61c84-107">Security</span><span class="sxs-lookup"><span data-stu-id="61c84-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61c84-108">**So löschen Sie Statistiken aus einer Tabelle oder einer Sicht mit:**</span><span class="sxs-lookup"><span data-stu-id="61c84-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="61c84-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61c84-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="61c84-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61c84-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61c84-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="61c84-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="61c84-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="61c84-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="61c84-113">Gehen Sie vorsichtig vor, wenn Sie Statistiken löschen.</span><span class="sxs-lookup"><span data-stu-id="61c84-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="61c84-114">Dieser Vorgang kann sich auf den vom Abfrageoptimierer ausgewählten Ausführungsplan auswirken.</span><span class="sxs-lookup"><span data-stu-id="61c84-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="61c84-115">Statistiken für Indizes können mit DROP STATISTICS nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="61c84-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="61c84-116">Die Statistiken bleiben so lange vorhanden wie der Index.</span><span class="sxs-lookup"><span data-stu-id="61c84-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61c84-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="61c84-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61c84-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="61c84-118">Permissions</span></span>  
 <span data-ttu-id="61c84-119">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="61c84-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="61c84-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61c84-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="61c84-121">So löschen Sie Statistiken aus einer Tabelle oder einer Sicht</span><span class="sxs-lookup"><span data-stu-id="61c84-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="61c84-122">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie die Statistik löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="61c84-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="61c84-123">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="61c84-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="61c84-124">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie eine Statistik löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="61c84-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="61c84-125">Klicken Sie auf das Pluszeichen, um den Ordner **Statistik** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="61c84-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="61c84-126">Klicken Sie mit der rechten Maustaste auf das Statistikobjekt, das Sie löschen möchten, und wählen Sie dann **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="61c84-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="61c84-127">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Statistik ausgewählt ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61c84-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="61c84-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61c84-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="61c84-129">So löschen Sie Statistiken aus einer Tabelle oder einer Sicht</span><span class="sxs-lookup"><span data-stu-id="61c84-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="61c84-130">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61c84-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61c84-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61c84-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61c84-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="61c84-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="61c84-133">Weitere Informationen finden Sie unter [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61c84-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
