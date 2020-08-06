---
title: MSSQLSERVER_2814 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618039"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="ccb88-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="ccb88-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="ccb88-103">Details</span><span class="sxs-lookup"><span data-stu-id="ccb88-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccb88-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ccb88-104">Product Name</span></span>|<span data-ttu-id="ccb88-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ccb88-105">SQL Server</span></span>|  
|<span data-ttu-id="ccb88-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ccb88-106">Event ID</span></span>|<span data-ttu-id="ccb88-107">2814</span><span class="sxs-lookup"><span data-stu-id="ccb88-107">2814</span></span>|  
|<span data-ttu-id="ccb88-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ccb88-108">Event Source</span></span>|<span data-ttu-id="ccb88-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ccb88-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ccb88-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ccb88-110">Component</span></span>|<span data-ttu-id="ccb88-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ccb88-111">SQLEngine</span></span>|  
|<span data-ttu-id="ccb88-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="ccb88-112">Symbolic Name</span></span>|<span data-ttu-id="ccb88-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="ccb88-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="ccb88-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ccb88-114">Message Text</span></span>|<span data-ttu-id="ccb88-115">Es wurde ein mögliche unbegrenzte Neukompilierung für SQLHANDLE %hs, PlanHandle %hs, Startoffset %d, Endoffset %d erkannt.</span><span class="sxs-lookup"><span data-stu-id="ccb88-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="ccb88-116">Die letzte Ursache für die Neukompilierung war %d.</span><span class="sxs-lookup"><span data-stu-id="ccb88-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ccb88-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ccb88-117">Explanation</span></span>  
 <span data-ttu-id="ccb88-118">Eine oder mehrere Anweisungen haben bewirkt, dass der Abfragebatch mindestens 50 Mal neu kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ccb88-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="ccb88-119">Die angegebene Anweisung sollte korrigiert werden, um weitere Neukompilierungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ccb88-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="ccb88-120">In der folgenden Tabelle werden die Ursachen für die Neukompilierung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ccb88-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="ccb88-121">Ursachencode</span><span class="sxs-lookup"><span data-stu-id="ccb88-121">Reason code</span></span>|<span data-ttu-id="ccb88-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ccb88-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ccb88-123">1</span><span class="sxs-lookup"><span data-stu-id="ccb88-123">1</span></span>|<span data-ttu-id="ccb88-124">Schema geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-124">Schema changed</span></span>|  
|<span data-ttu-id="ccb88-125">2</span><span class="sxs-lookup"><span data-stu-id="ccb88-125">2</span></span>|<span data-ttu-id="ccb88-126">Statistiken geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-126">Statistics changed</span></span>|  
|<span data-ttu-id="ccb88-127">3</span><span class="sxs-lookup"><span data-stu-id="ccb88-127">3</span></span>|<span data-ttu-id="ccb88-128">Verzögerte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="ccb88-128">Deferred compile</span></span>|  
|<span data-ttu-id="ccb88-129">4</span><span class="sxs-lookup"><span data-stu-id="ccb88-129">4</span></span>|<span data-ttu-id="ccb88-130">Festgelegte Option geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-130">Set option changed</span></span>|  
|<span data-ttu-id="ccb88-131">5</span><span class="sxs-lookup"><span data-stu-id="ccb88-131">5</span></span>|<span data-ttu-id="ccb88-132">Temp. Tabelle geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-132">Temp table changed</span></span>|  
|<span data-ttu-id="ccb88-133">6</span><span class="sxs-lookup"><span data-stu-id="ccb88-133">6</span></span>|<span data-ttu-id="ccb88-134">Remote-Rowset geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="ccb88-135">7</span><span class="sxs-lookup"><span data-stu-id="ccb88-135">7</span></span>|<span data-ttu-id="ccb88-136">For Browse-Berechtigungen geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="ccb88-137">8</span><span class="sxs-lookup"><span data-stu-id="ccb88-137">8</span></span>|<span data-ttu-id="ccb88-138">Abfragebenachrichtigungsumgebung geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="ccb88-139">9</span><span class="sxs-lookup"><span data-stu-id="ccb88-139">9</span></span>|<span data-ttu-id="ccb88-140">Partitionierte Sicht geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-140">Partition view changed</span></span>|  
|<span data-ttu-id="ccb88-141">10</span><span class="sxs-lookup"><span data-stu-id="ccb88-141">10</span></span>|<span data-ttu-id="ccb88-142">Cursoroptionen geändert</span><span class="sxs-lookup"><span data-stu-id="ccb88-142">Cursor options changed</span></span>|  
|<span data-ttu-id="ccb88-143">11</span><span class="sxs-lookup"><span data-stu-id="ccb88-143">11</span></span>|<span data-ttu-id="ccb88-144">Option (Neukompilierung) angefordert</span><span class="sxs-lookup"><span data-stu-id="ccb88-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="ccb88-145">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ccb88-145">User Action</span></span>  
  
1.  <span data-ttu-id="ccb88-146">Zeigen Sie die Anweisung an, die die Neukompilierung verursacht, indem Sie die folgende Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="ccb88-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="ccb88-147">Ersetzen Sie die Platzhalter *sql_handle*, *starting_offset*, *ending_offset* und *plan_handle* durch die in der Fehlermeldung angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="ccb88-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="ccb88-148">Beachten Sie, dass die Spalten **database_name** und **object_name** für Ad-hoc- und vorbereitete [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen den Wert NULL haben.</span><span class="sxs-lookup"><span data-stu-id="ccb88-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="ccb88-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="ccb88-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="ccb88-150">, OBJECT_NAME (st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="ccb88-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="ccb88-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="ccb88-151">, st.text</span></span>  
  
     <span data-ttu-id="ccb88-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="ccb88-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="ccb88-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="ccb88-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="ccb88-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="ccb88-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="ccb88-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="ccb88-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="ccb88-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="ccb88-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="ccb88-157">Ändern Sie auf Grundlage der Beschreibung des Ursachencodes die Anweisung, den Batch oder die Prozedur, um Neukompilierungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ccb88-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="ccb88-158">Eine gespeicherte Prozedur kann z. B. eine oder mehrere SET-Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ccb88-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="ccb88-159">Diese Anweisungen sollten aus der Prozedur entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ccb88-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="ccb88-160">Weitere Beispiele für die Ursachen von Neukompilierungen und Lösungen finden Sie unter [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005 (Probleme bei der Batchkompilierung, Neukompilierung und beim Zwischenspeichern von Ausführungsplänen in SQL Server 2005)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="ccb88-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="ccb88-161">Wenn das Problem wiederholt auftritt, wenden Sie sich an den Microsoft-Kundendienst.</span><span class="sxs-lookup"><span data-stu-id="ccb88-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb88-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb88-162">See Also</span></span>  
 [<span data-ttu-id="ccb88-163">SQL:StmtRecompile (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="ccb88-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
