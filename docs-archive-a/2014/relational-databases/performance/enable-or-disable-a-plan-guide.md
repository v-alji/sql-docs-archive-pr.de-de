---
title: Aktivieren oder Deaktivieren einer Planhinweisliste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721413"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="e19aa-102">Aktivieren oder Deaktivieren einer Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="e19aa-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="e19aa-103">Sie können Planhinweislisten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktivieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e19aa-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e19aa-104">Es können entweder eine einzelne Planhinweisliste oder alle Planhinweislisten in einer Datenbank aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e19aa-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="e19aa-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e19aa-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e19aa-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e19aa-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e19aa-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e19aa-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e19aa-108">Security</span><span class="sxs-lookup"><span data-stu-id="e19aa-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e19aa-109">**So deaktivieren und aktivieren Sie Planhinweislisten mit:**</span><span class="sxs-lookup"><span data-stu-id="e19aa-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="e19aa-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e19aa-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e19aa-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e19aa-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e19aa-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e19aa-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e19aa-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e19aa-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e19aa-114">Das Löschen oder Ändern einer Funktion, einer gespeicherten Prozedur oder eines DML-Triggers, auf die bzw. den in einer Planhinweisliste verwiesen wird, verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="e19aa-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="e19aa-115">Überprüfen Sie die oben aufgeführten Objekte vor dem Löschen oder Ändern immer auf Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="e19aa-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="e19aa-116">Das Deaktivieren einer deaktivierten bzw. das Aktivieren einer aktivierten Planhinweisliste hat keine Auswirkung und kann ausgeführt werden, ohne einen Fehler zu verursachen.</span><span class="sxs-lookup"><span data-stu-id="e19aa-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e19aa-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e19aa-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e19aa-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e19aa-118">Permissions</span></span>  
 <span data-ttu-id="e19aa-119">Das Deaktivieren oder Aktivieren einer OBJECT-Planhinweisliste erfordert die ALTER-Berechtigung für das Objekt (z. B. Funktion, gespeicherte Prozedur), auf das von der Planhinweisliste verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e19aa-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="e19aa-120">Für alle anderen Planhinweislisten ist die ALTER DATABASE-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e19aa-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e19aa-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e19aa-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="e19aa-122">So deaktivieren oder aktivieren Sie eine Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="e19aa-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="e19aa-123">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine Planhinweisliste deaktivieren oder aktivieren möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e19aa-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="e19aa-124">Klicken Sie auf das Pluszeichen, um den Ordner **Planhinweislisten** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e19aa-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="e19aa-125">Klicken Sie mit der rechten Maustaste auf die Planhinweisliste, die deaktiviert oder aktiviert werden soll, und wählen Sie entweder **Deaktivieren** oder **Aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e19aa-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="e19aa-126">Überprüfen Sie im Dialogfeld **Planhinweisliste deaktivieren** oder **Planhinweisliste aktivieren** , ob die ausgewählte Aktion erfolgreich war, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="e19aa-127">So deaktivieren oder aktivieren Sie alle Planhinweislisten in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e19aa-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="e19aa-128">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine Planhinweisliste deaktivieren oder aktivieren möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e19aa-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="e19aa-129">Klicken Sie mit der rechten Maustaste auf den Ordner **Planhinweislisten** , und wählen Sie dann **Alle aktivieren** oder **Alle deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e19aa-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="e19aa-130">Überprüfen Sie im Dialogfeld **Alle Planhinweislisten deaktivieren** oder **Alle Planhinweislisten aktivieren** , ob die ausgewählte Aktion erfolgreich war, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e19aa-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e19aa-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="e19aa-132">So deaktivieren oder aktivieren Sie eine Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="e19aa-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="e19aa-133">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e19aa-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e19aa-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e19aa-135">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="e19aa-136">So deaktivieren oder aktivieren Sie alle Planhinweislisten in einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e19aa-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="e19aa-137">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e19aa-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e19aa-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e19aa-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e19aa-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="e19aa-140">Weitere Informationen finden Sie unter [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e19aa-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
