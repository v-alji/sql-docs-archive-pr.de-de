---
title: Ändern von Ansichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617858"
---
# <a name="modify-views"></a><span data-ttu-id="fbe68-102">Ändern von Sichten</span><span class="sxs-lookup"><span data-stu-id="fbe68-102">Modify Views</span></span>
  <span data-ttu-id="fbe68-103">Nachdem eine Sicht definiert wurde, können Sie ihre Definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ändern, ohne die Sicht mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen und neu erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="fbe68-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fbe68-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="fbe68-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fbe68-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="fbe68-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fbe68-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fbe68-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fbe68-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fbe68-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fbe68-108">**So ändern Sie eine Sicht mit:**</span><span class="sxs-lookup"><span data-stu-id="fbe68-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="fbe68-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fbe68-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fbe68-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fbe68-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fbe68-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="fbe68-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fbe68-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fbe68-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fbe68-113">Das Ändern einer Sicht hat keine Auswirkungen auf abhängige Objekte, z. B. gespeicherte Prozeduren oder Trigger, es sei denn, die Definition der Sicht wird so geändert, dass das abhängige Objekt nicht mehr gültig ist.</span><span class="sxs-lookup"><span data-stu-id="fbe68-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="fbe68-114">Wird eine derzeit verwendete Sicht mithilfe von ALTER VIEW geändert, belegt [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Sicht mit einer exklusiven Schemasperre.</span><span class="sxs-lookup"><span data-stu-id="fbe68-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="fbe68-115">Wenn die Sperre erteilt wird und keine aktiven Benutzer der Sicht vorhanden sind, löscht [!INCLUDE[ssDE](../../includes/ssde-md.md)] alle Kopien der Sicht aus dem Prozedurcache.</span><span class="sxs-lookup"><span data-stu-id="fbe68-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="fbe68-116">Vorhandene Pläne, die auf die Sicht verweisen, bleiben im Cache, werden aber beim Aufrufen erneut kompiliert.</span><span class="sxs-lookup"><span data-stu-id="fbe68-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="fbe68-117">ALTER VIEW kann auf indizierte Sichten angewendet werden; ALTER VIEW löscht jedoch vorbehaltlos alle Indizes in der Sicht.</span><span class="sxs-lookup"><span data-stu-id="fbe68-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fbe68-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fbe68-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fbe68-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fbe68-119">Permissions</span></span>  
 <span data-ttu-id="fbe68-120">Für die Ausführung von ALTER VIEW wird zumindest die ALTER-Berechtigung für OBJECT benötigt.</span><span class="sxs-lookup"><span data-stu-id="fbe68-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fbe68-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fbe68-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="fbe68-122">So ändern Sie eine Sicht</span><span class="sxs-lookup"><span data-stu-id="fbe68-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="fbe68-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen neben der Datenbank, in der sich die Sicht befindet, und klicken Sie dann auf das Pluszeichen neben dem Ordner **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="fbe68-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="fbe68-124">Klicken Sie mit der rechten Maustaste auf die Sicht, die Sie ändern möchten, und klicken Sie anschließend auf **Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="fbe68-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="fbe68-125">Nehmen Sie im Diagrammbereich des Abfrage-Designers Änderungen an der Sicht vor, indem Sie eine oder mehrere der folgenden Vorgehensweisen anwenden:</span><span class="sxs-lookup"><span data-stu-id="fbe68-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="fbe68-126">Aktivieren oder deaktivieren Sie die Kontrollkästchen beliebiger Elemente, die Sie hinzufügen oder entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="fbe68-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="fbe68-127">Klicken Sie mit der rechten Maustaste innerhalb des Diagrammbereichs, wählen Sie die Option **Tabelle hinzufügen...** , und wählen Sie im Dialogfeld **Tabelle hinzufügen** dann die weiteren Spalten aus, die Sie der Ansicht hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="fbe68-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="fbe68-128">Klicken Sie mit der rechten Maustaste auf die Titelleiste der Tabelle, die Sie entfernen möchten, und wählen Sie die Option **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="fbe68-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="fbe68-129">Klicken Sie im Menü **Datei** auf **Speichern**_view name_.</span><span class="sxs-lookup"><span data-stu-id="fbe68-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fbe68-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fbe68-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="fbe68-131">So ändern Sie eine Sicht</span><span class="sxs-lookup"><span data-stu-id="fbe68-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="fbe68-132">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="fbe68-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fbe68-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fbe68-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fbe68-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fbe68-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fbe68-135">Im Beispiel wird zuerst eine Sicht erstellt, und anschließend wird die Sicht mithilfe von ALTER VIEW geändert.</span><span class="sxs-lookup"><span data-stu-id="fbe68-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="fbe68-136">Der Sichtdefinition wird eine WHERE-Klausel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fbe68-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="fbe68-137">Weitere Informationen finden Sie unter [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fbe68-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
