---
title: Migrieren von Abfrage Plänen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718685"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="514a6-102">Migrieren von Abfrageplänen</span><span class="sxs-lookup"><span data-stu-id="514a6-102">Migrate Query Plans</span></span>
  <span data-ttu-id="514a6-103">Im Allgemeinen führt das Upgrade einer Datenbank auf die aktuellste Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu einer besseren Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="514a6-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="514a6-104">Bei unternehmenswichtigen Abfragen, deren Leistung sorgfältig optimiert wurde, möchten Sie jedoch möglicherweise vor dem Upgrade die entsprechenden Abfragepläne aufzeichnen. Zu diesem Zweck können Sie für jede Abfrage eine Planhinweisliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="514a6-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="514a6-105">Falls der Abfrageoptimierer nach der Aktualisierung für immer mehr Abfragen einen weniger effizienten Plan wählt, können Sie die Planhinweislisten aktivieren und den Abfrageoptimierer zwingen, die alten Pläne zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="514a6-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="514a6-106">Führen Sie die folgenden Schritte durch, um vor der Aktualisierung Planhinweislisten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="514a6-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="514a6-107">Zeichnen Sie den aktuellen Plan für jede unternehmenskritische Abfrage auf, indem Sie die gespeicherte Prozedur [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) verwenden und den Abfrageplan im Use Plan-Abfrage Hinweis angeben.</span><span class="sxs-lookup"><span data-stu-id="514a6-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="514a6-108">Vergewissern Sie sich, dass die Planhinweisliste auf die Abfrage angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="514a6-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="514a6-109">Aktualisieren Sie die Datenbank auf die neuere Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="514a6-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="514a6-110">Die Pläne werden in der aktualisierten Datenbank in den Planhinweislisten persistent gespeichert und können gegebenenfalls herangezogen werden, falls es nach dem Upgrade zu einer Regression bei der Planverwendung kommt.</span><span class="sxs-lookup"><span data-stu-id="514a6-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="514a6-111">Wir empfehlen jedoch, die Planhinweislisten nicht sofort nach der Aktualisierung zu aktivieren, da Sie sonst eventuell nicht die Vorzüge besserer Pläne in der neuen Version oder die Vorteile von Neukompilierungen aufgrund aktualisierter Statistiken nutzen können.</span><span class="sxs-lookup"><span data-stu-id="514a6-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="514a6-112">Falls nach der Aktualisierung weniger effiziente Pläne gewählt werden, können Sie alle oder einen Teil der Planhinweislisten aktivieren, um die neuen Pläne zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="514a6-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="514a6-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="514a6-113">Example</span></span>  
 <span data-ttu-id="514a6-114">Im folgenden Beispiel wird gezeigt, wie Sie vor der Aktualisierung durch Erstellen einer Planhinweisliste den Plan für eine Abfrage aufzeichnen können.</span><span class="sxs-lookup"><span data-stu-id="514a6-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="514a6-115">Schritt 1: Abrufen des Plans</span><span class="sxs-lookup"><span data-stu-id="514a6-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="514a6-116">Der in der Planhinweisliste aufgezeichnete Abfrageplan muss im XML-Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="514a6-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="514a6-117">Abfragepläne im XML-Format können auf folgende Weise erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="514a6-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="514a6-118">Mit SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="514a6-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="514a6-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="514a6-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="514a6-120">Abfragen der query_plan Spalte der dynamischen Verwaltungsfunktion [sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="514a6-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="514a6-121">Die [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Ereignis Klassen [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)und [Showplan XML for Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="514a6-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="514a6-122">Im folgenden Beispiel wird der Abfrageplan für die Anweisung `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` abgerufen, indem dynamische Verwaltungssichten abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="514a6-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="514a6-123">Schritt 2: Erstellen des Planhinweises zum Erzwingen des Plans</span><span class="sxs-lookup"><span data-stu-id="514a6-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="514a6-124">Fügen Sie den in der Planhinweisliste enthaltenen (und mit einer der oben beschriebenen Methoden bezogenen) Abfrageplan im XML-Format als Zeichenfolgenliteral in den USE PLAN-Abfragehinweis ein, der in der OPTION-Klausel von sp_create_plan_guide angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="514a6-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="514a6-125">Grenzen Sie alle im XML-Plan enthaltenen Anführungszeichen (') durch ein zweites Anführungszeichen ab, bevor Sie die Planhinweisliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="514a6-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="514a6-126">Ein Plan, der `WHERE A.varchar = 'This is a string'` enthält, muss z. B. abgegrenzt werden, indem der Code zu `WHERE A.varchar = ''This is a string''` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="514a6-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="514a6-127">Im folgenden Beispiel wird eine Planhinweisliste für den in Schritt 1 abgerufenen Abfrageplan erstellt und der XML-Showplan für die Abfrage in den `@hints`-Parameter eingefügt.</span><span class="sxs-lookup"><span data-stu-id="514a6-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="514a6-128">Aus Platzgründen ist im Beispiel nur ein Teil des Showplans angegeben.</span><span class="sxs-lookup"><span data-stu-id="514a6-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="514a6-129">Schritt 3: Überprüfen, ob die Planhinweisliste auf die Abfrage angewendet wird</span><span class="sxs-lookup"><span data-stu-id="514a6-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="514a6-130">Führen Sie die Abfrage noch einmal aus, und überprüfen Sie den erzeugten Abfrageplan.</span><span class="sxs-lookup"><span data-stu-id="514a6-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="514a6-131">Dieser Plan sollte mit dem in der Planhinweisliste angegebenen Plan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="514a6-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514a6-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="514a6-132">See Also</span></span>  
 <span data-ttu-id="514a6-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="514a6-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="514a6-134">[Abfragehinweise (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="514a6-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="514a6-135">Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="514a6-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
