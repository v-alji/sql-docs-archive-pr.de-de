---
title: 'Lektion 3: Definieren eines Datasets für den Tabellenbericht (Reporting Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615856"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="3ddba-102">Lektion 3: Definieren eines Datasets für den Tabellenbericht (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3ddba-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="3ddba-103">Nachdem Sie die Datenquelle festgelegt haben, müssen Sie ein Dataset definieren.</span><span class="sxs-lookup"><span data-stu-id="3ddba-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="3ddba-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]sind die Daten, die Sie in Berichten verwenden, in einem *Dataset*enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ddba-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="3ddba-105">Ein Dataset umfasst einen Zeiger auf eine Datenquelle sowie eine Abfrage, die vom Bericht verwendet werden, sowie berechnete Felder und Variablen.</span><span class="sxs-lookup"><span data-stu-id="3ddba-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="3ddba-106">Sie können den Abfrage-Designer im Berichts-Designer verwenden, um die Abfrage zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="3ddba-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="3ddba-107">In diesem Lernprogramm erstellen Sie eine Abfrage, die Bestellinformationen aus der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** -Datenbank abruft.</span><span class="sxs-lookup"><span data-stu-id="3ddba-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="3ddba-108">So definieren Sie eine Transact-SQL-Abfrage für Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="3ddba-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="3ddba-109">Klicken Sie im **Berichtsdaten** Bereich auf **neu**, und klicken Sie dann auf **DataSet...**. Das Dialogfeld **Dataseteigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3ddba-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3ddba-110">Geben Sie in das Feld **Name** den Namen **AdventureWorksDataset**ein.</span><span class="sxs-lookup"><span data-stu-id="3ddba-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="3ddba-111">Klicken Sie auf **Ein in den eigenen Bericht eingebettetes Dataset verwenden**.</span><span class="sxs-lookup"><span data-stu-id="3ddba-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="3ddba-112">Der Name der Datenquelle, "AdventureWorks2012", muss im Feld **Datenquelle** eingetragen sein, und als **Abfragetyp** muss **Text**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ddba-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="3ddba-113">Geben Sie die folgende Transact-SQL-Abfrage entweder manuell oder durch Kopieren und Einfügen in das Feld **Abfrage** ein.</span><span class="sxs-lookup"><span data-stu-id="3ddba-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="3ddba-114">(Optional) klicken Sie auf die Schaltfläche **Abfrage-Designer** .</span><span class="sxs-lookup"><span data-stu-id="3ddba-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="3ddba-115">Die Abfrage wird im textbasierten Abfrage-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ddba-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="3ddba-116">Sie können zum grafischen Abfrage-Designer wechseln, indem Sie auf **Als Text bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="3ddba-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="3ddba-117">Zeigen Sie die Ergebnisse der Abfrage an, indem Sie auf der Symbolleiste des Abfrage-Designers auf die Schaltfläche Ausführen **(!)** klicken.</span><span class="sxs-lookup"><span data-stu-id="3ddba-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="3ddba-118">Daraufhin werden die Daten von sechs Feldern aus vier verschiedenen Tabellen in der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ddba-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3ddba-119">Diese Abfrage nutzt Transact-SQL-Funktionen wie Aliase.</span><span class="sxs-lookup"><span data-stu-id="3ddba-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="3ddba-120">Beispielsweise wird die Tabelle SalesOrderHeader als "soh" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3ddba-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="3ddba-121">Klicken Sie auf **OK** , um den Abfrage-Designer zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3ddba-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="3ddba-122">Klicken Sie auf **OK** , um das Dialogfeld **Dataseteigenschaften** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="3ddba-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="3ddba-123">Die Felder des **AdventureWorksDataset** -Datasets werden im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ddba-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="3ddba-124">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="3ddba-124">Next Task</span></span>  
 <span data-ttu-id="3ddba-125">Damit haben Sie erfolgreich eine Abfrage angegeben, die Daten für Ihren Bericht abruft.</span><span class="sxs-lookup"><span data-stu-id="3ddba-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="3ddba-126">Als Nächstes erstellen Sie das Berichtslayout.</span><span class="sxs-lookup"><span data-stu-id="3ddba-126">Next, you will create the report layout.</span></span> <span data-ttu-id="3ddba-127">Weitere Informationen finden Sie unter [Lektion 4: Hinzufügen einer Tabelle zum Bericht (Reporting Services)](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ddba-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddba-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ddba-128">See Also</span></span>  
 <span data-ttu-id="3ddba-129">[Abfrage Entwurfs Tools in Berichts-Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3ddba-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="3ddba-130">[SQL Server Verbindungstyp &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3ddba-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="3ddba-131">Tutorial: Schreiben von Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3ddba-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
