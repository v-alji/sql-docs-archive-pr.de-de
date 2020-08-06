---
title: Erstellen einer Planhinweisliste für parametrisierte Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622611"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="d1278-102">Erstellen einer Planhinweisliste für parametrisierte Abfragen</span><span class="sxs-lookup"><span data-stu-id="d1278-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="d1278-103">Eine TEMPLATE-Planhinweisliste zur Übereinstimmung mit eigenständigen Abfragen, die in einer angegebenen Form parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d1278-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="d1278-104">Im folgenden Beispiel wird eine Planhinweisliste erstellt, die mit einer beliebigen Abfrage übereinstimmt, die in einer bestimmten Form parametrisiert wird. Außerdem wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angewiesen, die Parametrisierung der Abfrage zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="d1278-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="d1278-105">Die folgenden beiden Abfragen sind syntaktisch gleichwertig, unterscheiden sich jedoch in ihren konstanten Literalwerten.</span><span class="sxs-lookup"><span data-stu-id="d1278-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="d1278-106">Dies ist die Planhinweisliste für die parametrisierte Form der Abfrage:</span><span class="sxs-lookup"><span data-stu-id="d1278-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="d1278-107">Im vorhergehenden Beispiel entspricht der Wert des `@stmt` -Parameters der parametrisierten Form der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d1278-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="d1278-108">Die einzig zuverlässige Möglichkeit, diesen Wert für die Verwendung in sp_create_plan_guide abzurufen, ist die gespeicherte Systemprozedur [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d1278-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="d1278-109">Mithilfe des folgenden Skripts können Sie die parametrisierte Abfrage abrufen und anschließend eine Planhinweisliste für die Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1278-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1278-110">Der Wert der konstanten Literale in dem an `@stmt` übergebenen `sp_get_query_template` -Parameter kann sich auf den Datentyp auswirken, der für den Parameter, der das Literal ersetzt, gewählt wird.</span><span class="sxs-lookup"><span data-stu-id="d1278-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="d1278-111">Dies wiederum beeinflusst den Planhinweislistenabgleich.</span><span class="sxs-lookup"><span data-stu-id="d1278-111">This will affect plan guide matching.</span></span> <span data-ttu-id="d1278-112">Möglicherweise müssen mehrere Planhinweislisten für verschiedene Parameterwertbereiche erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d1278-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="d1278-113">Sie haben auch die Möglichkeit, TEMPLATE-Planhinweislisten zusammen mit SQL-Planhinweislisten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1278-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="d1278-114">Beispielsweise können Sie eine TEMPLATE-Planhinweisliste erstellen, um sicherzustellen, dass eine bestimmte Abfrageklasse parametrisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d1278-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="d1278-115">Anschließend können Sie eine SQL-Planhinweisliste für die parametrisierte Form dieser Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1278-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
