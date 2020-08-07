---
title: MSSQLSERVER_137 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620965"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="a8484-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="a8484-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="a8484-103">Details</span><span class="sxs-lookup"><span data-stu-id="a8484-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8484-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a8484-104">Product Name</span></span>|<span data-ttu-id="a8484-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8484-105">SQL Server</span></span>|  
|<span data-ttu-id="a8484-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a8484-106">Event ID</span></span>|<span data-ttu-id="a8484-107">137</span><span class="sxs-lookup"><span data-stu-id="a8484-107">137</span></span>|  
|<span data-ttu-id="a8484-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a8484-108">Event Source</span></span>|<span data-ttu-id="a8484-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a8484-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a8484-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a8484-110">Component</span></span>|<span data-ttu-id="a8484-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a8484-111">SQLEngine</span></span>|  
|<span data-ttu-id="a8484-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a8484-112">Symbolic Name</span></span>|<span data-ttu-id="a8484-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="a8484-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="a8484-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a8484-114">Message Text</span></span>|<span data-ttu-id="a8484-115">Die "%.\*ls"-Skalarvariable muss deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a8484-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8484-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a8484-116">Explanation</span></span>  
 <span data-ttu-id="a8484-117">Dieser Fehler tritt auf, wenn in einem SQL-Skript eine Variable verwendet wird, ohne dass die Variable zuerst deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="a8484-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="a8484-118">Im folgenden Beispiel wird der Fehler 137 für die Set-und die SELECT-Anweisung zurückgegeben, da **@mycol** nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="a8484-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="a8484-119">SET @mycol = 'ContactName';</span><span class="sxs-lookup"><span data-stu-id="a8484-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="a8484-120">SELECT @mycol;</span><span class="sxs-lookup"><span data-stu-id="a8484-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="a8484-121">Eine der etwas komplizierteren Ursachen für diesen Fehler ist u. a. die Verwendung einer Variablen, die außerhalb der EXECUTE-Anweisung deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="a8484-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="a8484-122">Beispielsweise **@mycol** ist die in der SELECT-Anweisung angegebene Variable für die SELECT-Anweisung lokal. Sie befindet sich daher außerhalb der EXECUTE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a8484-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="a8484-123">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="a8484-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="a8484-124">GO</span><span class="sxs-lookup"><span data-stu-id="a8484-124">GO</span></span>  
  
 <span data-ttu-id="a8484-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="a8484-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="a8484-126">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="a8484-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="a8484-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span><span class="sxs-lookup"><span data-stu-id="a8484-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8484-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a8484-128">User Action</span></span>  
 <span data-ttu-id="a8484-129">Überprüfen Sie, ob alle in einem SQL-Skript verwendeten Variablen deklariert wurden, bevor sie an anderer Stelle im Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8484-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="a8484-130">Schreiben Sie das Skript um, sodass es nicht auf Variablen in der EXECUTE-Anweisung verweist, die außerhalb davon deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="a8484-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="a8484-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a8484-131">For example:</span></span>  
  
 <span data-ttu-id="a8484-132">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="a8484-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="a8484-133">GO</span><span class="sxs-lookup"><span data-stu-id="a8484-133">GO</span></span>  
  
 <span data-ttu-id="a8484-134">DECLARE @mycol nvarchar(20) ;</span><span class="sxs-lookup"><span data-stu-id="a8484-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="a8484-135">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="a8484-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="a8484-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span><span class="sxs-lookup"><span data-stu-id="a8484-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8484-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8484-137">See Also</span></span>  
 <span data-ttu-id="a8484-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8484-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="a8484-139">[SET-Anweisungen (Transact-SQL)](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8484-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="a8484-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a8484-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
