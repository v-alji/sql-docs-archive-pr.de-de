---
title: Statistikaktualisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- updating statistics
- statistics [SQL Server], updating
ms.assetid: 4b97c0b4-03ff-4cfb-9c3f-3b33290b7a2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 28491dda23c2ba9402e91dc051249f5bdcdf28d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621406"
---
# <a name="update-statistics"></a><span data-ttu-id="280e9-102">Statistikaktualisierung</span><span class="sxs-lookup"><span data-stu-id="280e9-102">Update Statistics</span></span>
  <span data-ttu-id="280e9-103">Sie können Abfrageoptimierungsstatistiken für eine Tabelle oder indizierte Sicht in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="280e9-103">You can update query optimization statistics on a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="280e9-104">Standardmäßig nimmt der Abfrageoptimierer erforderliche Updates der Statistiken automatisch vor, um den Abfrageplan zu verbessern. In einigen Fällen können Sie die Abfrageleistung mit UPDATE STATISTICS oder der gespeicherten Prozedur `sp_updatestats` verbessern, um Statistiken häufiger zu aktualisieren, als von der Standardeinstellung vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="280e9-104">By default, the query optimizer already updates statistics as necessary to improve the query plan; in some cases you can improve query performance by using UPDATE STATISTICS or the stored procedure `sp_updatestats` to update statistics more frequently than the default updates.</span></span>  
  
 <span data-ttu-id="280e9-105">Durch das Update von Statistiken wird sichergestellt, dass Abfragen anhand aktueller Statistiken kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="280e9-105">Updating statistics ensures that queries compile with up-to-date statistics.</span></span> <span data-ttu-id="280e9-106">Dies führt jedoch dazu, dass Abfragen neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="280e9-106">However, updating statistics causes queries to recompile.</span></span> <span data-ttu-id="280e9-107">Es empfiehlt sich, Statistiken nicht zu oft zu aktualisieren und die Vorteile optimierter Abfragepläne gegen den Zeitaufwand für die Neukompilierung von Abfragen abzuwägen.</span><span class="sxs-lookup"><span data-stu-id="280e9-107">We recommend not updating statistics too frequently because there is a performance tradeoff between improving query plans and the time it takes to recompile queries.</span></span> <span data-ttu-id="280e9-108">Die Entscheidung hängt von der verwendeten Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="280e9-108">The specific tradeoffs depend on your application.</span></span> <span data-ttu-id="280e9-109">UPDATE STATISTICS-Vorgänge können mithilfe von tempdb die Stichprobenzeilen zum Erstellen von Statistiken sortieren.</span><span class="sxs-lookup"><span data-stu-id="280e9-109">UPDATE STATISTICS can use tempdb to sort the sample of rows for building statistics.</span></span>  
  
 <span data-ttu-id="280e9-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="280e9-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="280e9-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="280e9-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="280e9-112">Security</span><span class="sxs-lookup"><span data-stu-id="280e9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="280e9-113">**So aktualisieren Sie ein Statistikobjekt mit:**</span><span class="sxs-lookup"><span data-stu-id="280e9-113">**To update a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="280e9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="280e9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="280e9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="280e9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="280e9-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="280e9-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="280e9-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="280e9-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="280e9-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="280e9-118">Permissions</span></span>  
 <span data-ttu-id="280e9-119">Bei der Verwendung von UPDATE STATISTICS oder beim Vornehmen von Änderungen mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ist für die Tabelle oder Sicht die ALTER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="280e9-119">If using UPDATE STATISTICS or making changes through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], requires ALTER permission on the table or view.</span></span> <span data-ttu-id="280e9-120">Wenn Sie `sp_updatestats`verwenden, ist die Mitgliedschaft in der festen Serverrolle **sysadmin** oder der Besitz der Datenbank (**dbo**) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="280e9-120">If using `sp_updatestats`, requires membership in the **sysadmin** fixed server role, or ownership of the database (**dbo**).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="280e9-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="280e9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-update-a-statistics-object"></a><span data-ttu-id="280e9-122">So aktualisieren Sie ein Statistikobjekt</span><span class="sxs-lookup"><span data-stu-id="280e9-122">To update a statistics object</span></span>  
  
1.  <span data-ttu-id="280e9-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie die Statistik aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="280e9-123">In **Object Explorer**, click the plus sign to expand the database in which you want to update the statistic.</span></span>  
  
2.  <span data-ttu-id="280e9-124">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="280e9-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="280e9-125">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Statistik aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="280e9-125">Click the plus sign to expand the table in which you want to update the statistic.</span></span>  
  
4.  <span data-ttu-id="280e9-126">Klicken Sie auf das Pluszeichen, um den Ordner **Statistik** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="280e9-126">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="280e9-127">Klicken Sie mit der rechten Maustaste auf das Statistikobjekt, das Sie aktualisieren möchten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="280e9-127">Right-click the statistics object you wish to update and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="280e9-128">Aktivieren Sie im Dialogfeld **Statistik Eigenschaften-**_statistics_name_ das Kontrollkästchen **Statistiken für diese Spalten aktualisieren** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="280e9-128">In the **Statistics Properties -**_statistics_name_ dialog box, select the **Update statistics for these columns** check box and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="280e9-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="280e9-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-a-specific-statistics-object"></a><span data-ttu-id="280e9-130">So aktualisieren Sie ein bestimmtes Statistikobjekt</span><span class="sxs-lookup"><span data-stu-id="280e9-130">To update a specific statistics object</span></span>  
  
1.  <span data-ttu-id="280e9-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="280e9-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="280e9-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="280e9-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="280e9-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="280e9-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example updates the statistics for the AK_SalesOrderDetail_rowguid index of the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;   
    GO  
    ```  
  
#### <a name="to-update-all-statistics-in-a-table"></a><span data-ttu-id="280e9-134">So aktualisieren Sie alle Statistiken in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="280e9-134">To update all statistics in a table</span></span>  
  
1.  <span data-ttu-id="280e9-135">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="280e9-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="280e9-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="280e9-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="280e9-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="280e9-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all indexes on the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail;   
    GO  
    ```  
  
 <span data-ttu-id="280e9-138">Weitere Informationen finden Sie unter [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql)erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="280e9-138">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
#### <a name="to-update-all-statistics-in-a-database"></a><span data-ttu-id="280e9-139">So aktualisieren Sie alle Statistiken in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="280e9-139">To update all statistics in a database</span></span>  
  
1.  <span data-ttu-id="280e9-140">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="280e9-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="280e9-141">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="280e9-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="280e9-142">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="280e9-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all tables in the database.   
    EXEC sp_updatestats;  
    ```  
  
 <span data-ttu-id="280e9-143">Weitere Informationen finden Sie unter [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="280e9-143">For more information, see [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span></span>  
  
  
