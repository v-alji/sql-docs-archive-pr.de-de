---
title: Verwenden von SQL Server Profiler zum Erstellen und Testen von Planhinweislisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701078"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="3aa15-102">Verwenden von SQL Server Profiler zum Erstellen und Testen von Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="3aa15-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="3aa15-103">Wenn Sie eine Planhinweisliste erstellen, können Sie durch Verwenden von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] den genauen Abfragetext aufzeichnen, um diesen im *statement_text* -Argument der gespeicherten Prozedur **sp_create_plan_guide** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aa15-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="3aa15-104">Damit kann sichergestellt werden, dass die Planhinweisliste zum Zeitpunkt der Kompilierung mit der Abfrage in Übereinstimmung gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="3aa15-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="3aa15-105">Nach dem Erstellen der Planhinweisliste kann [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auch verwendet werden, um zu testen, ob die Planhinweisliste tatsächlich in Übereinstimmung mit der Abfrage gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="3aa15-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="3aa15-106">Im Allgemeinen sollten Sie Planhinweislisten mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] testen, um zu überprüfen, dass Ihre Abfrage mit Ihrer Planhinweisliste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3aa15-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="3aa15-107">Aufzeichnen von Abfragetext mithilfe von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3aa15-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="3aa15-108">Wenn Sie eine Abfrage ausführen und den Text mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genau so aufzeichnen, wie er an [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]übermittelt wurde, können Sie eine Planhinweisliste des Typs SQL oder TEMPLATE erstellen, die genau mit dem Abfragetext übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3aa15-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="3aa15-109">Damit wird sichergestellt, dass die Planhinweisliste vom Abfrageoptimierer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3aa15-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="3aa15-110">Angenommen, die folgende Abfrage wird durch eine Anwendung als eigenständiger Batch übermittelt:</span><span class="sxs-lookup"><span data-stu-id="3aa15-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="3aa15-111">Nehmen wir jetzt an, Sie möchten diese Abfrage mithilfe eines Vorgangs zur Zusammenführungsjoins ausführen, von SHOWPLAN wird jedoch angezeigt, dass die Abfrage keine Zusammenführungsjoin verwendet.</span><span class="sxs-lookup"><span data-stu-id="3aa15-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="3aa15-112">Es ist nicht möglich, die Abfrage direkt in der Anwendung zu ändern. Also erstellen Sie stattdessen eine Planhinweisliste, um anzugeben, dass der MERGE JOIN-Abfragehinweis zum Kompilierzeitpunkt an die Abfrage angehängt wird.</span><span class="sxs-lookup"><span data-stu-id="3aa15-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="3aa15-113">Um den Text genau so aufzuzeichnen, wie er von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] empfangen wird, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="3aa15-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3aa15-114">Starten Sie eine [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ablaufverfolgung, und stellen Sie dabei sicher, dass der **SQL:BatchStarting** -Ereignistyp ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3aa15-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="3aa15-115">Führen Sie Abfrage mithilfe der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="3aa15-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="3aa15-116">Halten Sie die [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="3aa15-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="3aa15-117">Klicken Sie auf das **SQL:BatchStarting** -Ereignis, das der Abfrage entspricht.</span><span class="sxs-lookup"><span data-stu-id="3aa15-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="3aa15-118">Klicken Sie mit der rechten Maustaste auf dieses Ereignis, und wählen Sie **Ereignisdaten extrahieren**aus.</span><span class="sxs-lookup"><span data-stu-id="3aa15-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3aa15-119">Versuchen Sie nicht, den Batchtext zu kopieren, indem Sie ihn im unteren Bereich des Profiler-Ablaufverfolgungsfensters markieren.</span><span class="sxs-lookup"><span data-stu-id="3aa15-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="3aa15-120">Das kann dazu führen, dass die von Ihnen erstellte Planhinweisliste nicht mit dem ursprünglichen Batch übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3aa15-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="3aa15-121">Speichern Sie die Ereignisdaten in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="3aa15-121">Save the event data to a file.</span></span> <span data-ttu-id="3aa15-122">Das ist der Batchtext.</span><span class="sxs-lookup"><span data-stu-id="3aa15-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="3aa15-123">Öffnen Sie die Batchtextdatei in Editor, und kopieren Sie den Text in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="3aa15-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="3aa15-124">Erstellen Sie die Planhinweisliste, und fügen Sie den kopierten Text zwischen die Anführungszeichen (**''**) ein, die für das **@stmt** -Argument angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3aa15-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="3aa15-125">Sie müssen alle einfachen Anführungszeichen im Argument mit Escapezeichen versehen, **@stmt** indem Sie Ihnen ein weiteres einzelnes Anführungszeichen voranstellen.</span><span class="sxs-lookup"><span data-stu-id="3aa15-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="3aa15-126">Achten Sie darauf, beim Einfügen dieser einfachen Anführungszeichen keine weiteren Zeichen hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3aa15-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="3aa15-127">So muss z. B. das Datumsliteral **'** 20000101 **'** als **''** 20000101 **''** abgegrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="3aa15-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="3aa15-128">Die Planhinweisliste sieht dann folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="3aa15-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="3aa15-129">Testen von Planhinweislisten mithilfe von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3aa15-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="3aa15-130">Um zu überprüfen, ob eine Planhinweisliste mit einer Abfrage in Übereinstimmung gebracht wird, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="3aa15-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3aa15-131">Starten Sie eine [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ablaufverfolgung, und stellen Sie dabei sicher, dass der **Showplan XML** -Ereignistyp ausgewählt ist (dieser befindet sich unter dem Knoten **Leistung** ).</span><span class="sxs-lookup"><span data-stu-id="3aa15-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="3aa15-132">Führen Sie Abfrage mithilfe der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="3aa15-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="3aa15-133">Halten Sie die [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="3aa15-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="3aa15-134">Suchen Sie das **Showplan XML** -Ereignis für die betroffene Abfrage.</span><span class="sxs-lookup"><span data-stu-id="3aa15-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3aa15-135">Das Ereignis **Showplan XML for Query Compile** kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3aa15-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="3aa15-136">**PlanGuideDB** ist in diesem Ereignis nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3aa15-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="3aa15-137">Wenn die Planhinweisliste vom Typ OBJECT oder SQL ist, überprüfen Sie, ob das **Showplan XML** -Ereignis die Attribute **PlanGuideDB** und **PlanGuideName** für die Planhinweisliste enthält, die mit der Abfrage übereinstimmen soll.</span><span class="sxs-lookup"><span data-stu-id="3aa15-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="3aa15-138">Handelt es sich um eine Planhinweisliste vom Typ TEMPLATE, überprüfen Sie, ob das **Showplan XML** -Ereignis die Attribute **TemplatePlanGuideDB** und **TemplatePlanGuideName** für die erwartete Planhinweisliste enthält.</span><span class="sxs-lookup"><span data-stu-id="3aa15-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="3aa15-139">Damit wird die Funktionsfähigkeit der Planhinweisliste überprüft.</span><span class="sxs-lookup"><span data-stu-id="3aa15-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="3aa15-140">Diese Attribute sind im **\<StmtSimple>** -Element des Plans enthalten.</span><span class="sxs-lookup"><span data-stu-id="3aa15-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa15-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aa15-141">See Also</span></span>  
 [<span data-ttu-id="3aa15-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa15-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
