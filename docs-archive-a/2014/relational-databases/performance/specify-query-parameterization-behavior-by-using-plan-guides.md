---
title: Angeben des Abfrageparametrisierungsverhaltens mithilfe von Planhinweislisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622603"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="228a4-102">Angeben des Abfrageparametrisierungsverhaltens mithilfe von Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="228a4-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="228a4-103">Wenn die PARAMETERIZATION-Datenbankoption auf SIMPLE festgelegt ist, kann der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abfrageoptimierer die Abfragen ggf. parametrisieren.</span><span class="sxs-lookup"><span data-stu-id="228a4-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="228a4-104">Dies bedeutet, dass alle eventuell in einer Abfrage enthaltenen Literalwerte durch Parameter ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="228a4-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="228a4-105">Dieses Verfahren wird als einfache Parametrisierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="228a4-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="228a4-106">Wenn die einfache Parametrisierung aktiviert ist, können Sie nicht steuern, welche Abfragen parametrisiert werden sollen und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="228a4-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="228a4-107">Sie können jedoch angeben, dass alle Abfragen einer Datenbank parametrisiert werden sollen, indem Sie die PARAMETERIZATION-Datenbankoption auf FORCED festlegen.</span><span class="sxs-lookup"><span data-stu-id="228a4-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="228a4-108">Dieses Verfahren wird als erzwungene Parametrisierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="228a4-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="228a4-109">Sie können das Parametrisierungsverhalten einer Datenbank überschreiben, in dem Sie Planhinweislisten verwenden. Es gibt dabei folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="228a4-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="228a4-110">Wenn die PARAMETERIZATION-Datenbankoption auf SIMPLE festgelegt ist, können Sie angeben, dass für eine bestimmte Abfrageklasse die erzwungene Parametrisierung versucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="228a4-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="228a4-111">Erstellen Sie dazu eine TEMPLATE-Planhinweisliste für die parametrisierte Form der Abfrage, und geben Sie den PARAMETERIZATION FORCED-Abfragehinweis in der gespeicherten Prozedur [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) an.</span><span class="sxs-lookup"><span data-stu-id="228a4-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="228a4-112">Betrachten Sie diese Art, Planhinweislisten zu verwenden, als Verfahren, die erzwungene Parametrisierung nur für eine bestimmte, jedoch nicht alle Abfrageklassen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="228a4-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="228a4-113">Wenn die PARAMETERIZATION-Datenbankoption auf FORCED festgelegt ist, können Sie angeben, dass für eine bestimmte Abfrageklasse nur die einfache Parametrisierung versucht werden soll, jedoch nicht die erzwungene Parametrisierung.</span><span class="sxs-lookup"><span data-stu-id="228a4-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="228a4-114">Erstellen Sie dazu eine TEMPLATE-Planhinweisliste für die erzwungene parametrisierte Form der Abfrage, und geben Sie in **sp_create_plan_guide**den PARAMETERIZATION SIMPLE-Abfragehinweis an.</span><span class="sxs-lookup"><span data-stu-id="228a4-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="228a4-115">Betrachten Sie die folgende Abfrage in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="228a4-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="228a4-116">Als Datenbankadministrator haben Sie bestimmt, dass Sie die erzwungene Parametrisierung nicht für alle Abfragen der Datenbank aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="228a4-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="228a4-117">Sie sind jedoch darauf bedacht, den Aufwand zu vermeiden, alle Abfragen neu zu kompilieren, obwohl sie syntaktisch mit vorherigen Abfragen gleichwertig sind und sich lediglich durch ihre konstanten Literalwerte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="228a4-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="228a4-118">Mit anderen Worten möchten Sie solche Abfragen parametrisieren, sodass für diese Art von Abfragen ein Abfrageplan wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="228a4-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="228a4-119">Führen Sie in diesem Fall die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="228a4-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="228a4-120">Rufen Sie die parametrisierte Form der Abfrage ab.</span><span class="sxs-lookup"><span data-stu-id="228a4-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="228a4-121">Die einzig sichere Möglichkeit, diesen Wert zum Verwenden in **sp_create_plan_guide** abzurufen, besteht in der Verwendung der gespeicherten Systemprozedur [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="228a4-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="228a4-122">Erstellen Sie die Planhinweisliste für die parametrisierte Form der Abfrage, indem Sie den PARAMETERIZATION FORCED-Abfragehinweis angeben.</span><span class="sxs-lookup"><span data-stu-id="228a4-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="228a4-123">Im Rahmen der Parametrisierung einer Abfrage weist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den Parametern, die die Literalwerte ersetzen, abhängig von Wert und Größe der Literalwerte, einen Datentyp zu.</span><span class="sxs-lookup"><span data-stu-id="228a4-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="228a4-124">Der gleiche Vorgang erfolgt beim Wert der konstanten Literale, die an den **@stmt** Output-Parameter von **sp_get_query_template**übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="228a4-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="228a4-125">Da der Datentyp, der im- **@params** Argument **sp_create_plan_guide** angegeben ist, mit dem der Abfrage identisch sein muss, wenn er von parametrisiert wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , müssen Sie möglicherweise mehr als eine Plan Hinweis Liste erstellen, um den gesamten Bereich möglicher Parameterwerte für die Abfrage abzudecken.</span><span class="sxs-lookup"><span data-stu-id="228a4-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="228a4-126">Verwenden Sie das folgende Skript, um die parametrisierte Abfrage und anschließend eine Planhinweisliste dafür zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="228a4-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="228a4-127">Auf ähnliche Weise können Sie in einer Datenbank mit bereits aktivierter erzwungener Parametrisierung sicherstellen, dass die Beispielabfrage und andere, mit Ausnahme ihrer konstanten Literalwerte, syntaktisch gleichwertige Abfragen gemäß den Regeln für die einfache Parametrisierung parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="228a4-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="228a4-128">Geben Sie dazu in der OPTION-Klausel PARAMETERIZATION SIMPLE anstelle von PARAMETERIZATION FORCED an.</span><span class="sxs-lookup"><span data-stu-id="228a4-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="228a4-129">Durch TEMPLATE-Planhinweislisten wird eine Übereinstimmung zwischen Anweisungen und batchweise übermittelten Abfragen hergestellt, die nur aus einer einzigen Anweisung bestehen.</span><span class="sxs-lookup"><span data-stu-id="228a4-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="228a4-130">Für Anweisungen innerhalb von Batches mit mehreren Anweisungen können TEMPLATE-Planhinweislisten keine Übereinstimmungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="228a4-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
