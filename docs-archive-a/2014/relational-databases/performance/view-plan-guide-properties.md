---
title: Anzeigen der Eigenschaften der Planhinweisliste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699513"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="e3ff1-102">Anzeigen der Eigenschaften der Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="e3ff1-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="e3ff1-103">Sie können die Eigenschaften von Planhinweislisten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ff1-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="e3ff1-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3ff1-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3ff1-106">Security</span><span class="sxs-lookup"><span data-stu-id="e3ff1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3ff1-107">**So zeigen Sie die Eigenschaften von Planhinweislisten an mit:**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="e3ff1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3ff1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3ff1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ff1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3ff1-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e3ff1-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3ff1-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e3ff1-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3ff1-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e3ff1-112">Permissions</span></span>  
 <span data-ttu-id="e3ff1-113">Die Sichtbarkeit der Metadaten in Katalogsichten ist auf sicherungsfähige Elemente beschränkt, bei denen der Benutzer entweder der Besitzer ist oder für die dem Benutzer eine Berechtigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3ff1-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3ff1-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="e3ff1-115">So zeigen Sie die Eigenschaften einer Planhinweisliste an</span><span class="sxs-lookup"><span data-stu-id="e3ff1-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="e3ff1-116">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie die Eigenschaften einer Planhinweisliste anzeigen möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="e3ff1-117">Klicken Sie auf das Pluszeichen, um den Ordner **Planhinweislisten** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="e3ff1-118">Klicken Sie mit der rechten Maustaste auf die Planhinweisliste, deren Eigenschaften Sie anzeigen möchten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="e3ff1-119">Die folgenden Eigenschaften werden im Dialogfeld **Die Eigenschaften der Planhinweisliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="e3ff1-120">**Hinweise**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-120">**Hints**</span></span>  
     <span data-ttu-id="e3ff1-121">Zeigt die Abfragehinweise oder den Abfrageplan zur Anwendung auf die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e3ff1-122">Wenn ein Abfrageplan als Hinweis gekennzeichnet ist, wird die XML-Showplanausgabe für den Plan angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="e3ff1-123">**Ist deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-123">**Is disabled**</span></span>  
     <span data-ttu-id="e3ff1-124">Zeigt den Status der Planhinweisliste an.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="e3ff1-125">Mögliche Werte sind **True** und **False**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="e3ff1-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-126">**Name**</span></span>  
     <span data-ttu-id="e3ff1-127">Zeigt den Namen der Planhinweisliste an.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="e3ff1-128">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-128">**Parameters**</span></span>  
     <span data-ttu-id="e3ff1-129">Wenn es sich beim Bereichstyp um SQL oder TEMPLATE handelt, wird hiermit der Name und Datentyp aller Parameter angezeigt, die in die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="e3ff1-130">**Bereichsbatch**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-130">**Scope batch**</span></span>  
     <span data-ttu-id="e3ff1-131">Zeigt den Batchtext an, in dem die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="e3ff1-132">**Name von Bereichsobjekt**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-132">**Scope object name**</span></span>  
     <span data-ttu-id="e3ff1-133">Wenn es sich beim Bereichstyp um OBJECT handelt, wird hiermit der Name der gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur, benutzerdefinierten Skalarfunktion, aus mehreren Anweisungen bestehenden Funktion mit Tabellenrückgabe oder des DML-Triggers angezeigt, die bzw. der die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="e3ff1-134">**Name von Bereichsschema**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-134">**Scope schema name**</span></span>  
     <span data-ttu-id="e3ff1-135">Wenn es sich beim Bereichstyp um OBJECT handelt, wird hiermit der Name des Schemas angezeigt, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="e3ff1-136">**Bereichstyp**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-136">**Scope type**</span></span>  
     <span data-ttu-id="e3ff1-137">Zeigt den Typ der Entität an, in dem die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="e3ff1-138">Dies gibt den Kontext zum Abgleich der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung mit der Planhinweisliste an.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="e3ff1-139">Mögliche Werte sind **OBJECT**, **SQL**und **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="e3ff1-140">**Anweisung**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-140">**Statement**</span></span>  
     <span data-ttu-id="e3ff1-141">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung an, auf die die Planhinweisliste angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="e3ff1-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3ff1-143">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ff1-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="e3ff1-144">So zeigen Sie die Eigenschaften einer Planhinweisliste an</span><span class="sxs-lookup"><span data-stu-id="e3ff1-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="e3ff1-145">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3ff1-146">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3ff1-147">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3ff1-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="e3ff1-148">Weitere Informationen finden Sie unter [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e3ff1-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
