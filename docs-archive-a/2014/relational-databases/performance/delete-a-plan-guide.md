---
title: Löschen einer Planhinweisliste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698001"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="24825-102">Löschen einer Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="24825-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="24825-103">Sie können eine Planhinweisliste in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="24825-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="24825-104">Mit [!INCLUDE[tsql](../../includes/tsql-md.md)]können Sie auch alle Planhinweislisten in einer Datenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="24825-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="24825-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="24825-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="24825-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="24825-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="24825-107">Security</span><span class="sxs-lookup"><span data-stu-id="24825-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="24825-108">**So löschen Sie eine Planhinweisliste mit:**</span><span class="sxs-lookup"><span data-stu-id="24825-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="24825-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="24825-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="24825-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="24825-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="24825-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="24825-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="24825-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="24825-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="24825-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="24825-113">Permissions</span></span>  
 <span data-ttu-id="24825-114">Das Löschen einer OBJECT-Planhinweisliste erfordert die ALTER-Berechtigung für das Objekt (z. B. Funktion, gespeicherte Prozedur), auf das von der Planhinweisliste verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24825-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="24825-115">Für alle anderen Planhinweislisten ist die ALTER DATABASE-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24825-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="24825-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="24825-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="24825-117">So löschen Sie eine Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="24825-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="24825-118">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine Planhinweisliste löschen möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="24825-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="24825-119">Klicken Sie auf das Pluszeichen, um den Ordner **Planhinweislisten** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="24825-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="24825-120">Klicken Sie mit der rechten Maustaste auf die Planhinweisliste, die Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="24825-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="24825-121">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Planhinweisliste ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="24825-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="24825-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="24825-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="24825-123">So löschen Sie eine einzelne Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="24825-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="24825-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="24825-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="24825-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="24825-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="24825-126">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="24825-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="24825-127">So löschen Sie alle Planhinweislisten in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="24825-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="24825-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="24825-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="24825-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="24825-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="24825-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="24825-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="24825-131">Weitere Informationen finden Sie unter [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="24825-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
