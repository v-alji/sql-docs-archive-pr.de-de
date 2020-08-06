---
title: Anzeigen einer gespeicherten Ablaufverfolgung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726822"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="e8bea-102">Anzeigen einer gespeicherten Ablaufverfolgung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e8bea-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="e8bea-103">In diesem Thema wird beschrieben, wie Sie integrierte Funktionen verwenden, um eine gespeicherte Ablaufverfolgung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8bea-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="e8bea-104">So zeigen Sie eine bestimmte Ablaufverfolgung an</span><span class="sxs-lookup"><span data-stu-id="e8bea-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="e8bea-105">Führen Sie **fn_trace_getinfo** aus, und geben Sie die ID der Ablaufverfolgung an, zu der Informationen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8bea-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="e8bea-106">Diese Funktion gibt eine Tabelle zurück, in der die Ablaufverfolgung, die Ablaufverfolgungseigenschaft und Informationen zur Eigenschaft aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="e8bea-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="e8bea-107">Rufen Sie die Funktion folgendermaßen auf:</span><span class="sxs-lookup"><span data-stu-id="e8bea-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="e8bea-108">So zeigen Sie alle vorhandenen Ablaufverfolgungen an</span><span class="sxs-lookup"><span data-stu-id="e8bea-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="e8bea-109">Führen Sie **fn_trace_getinfo** aus, indem Sie `0` oder `default`angeben.</span><span class="sxs-lookup"><span data-stu-id="e8bea-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="e8bea-110">Diese Funktion gibt eine Tabelle zurück, in der alle Ablaufverfolgungen, deren Eigenschaften und Informationen zu diesen Eigenschaften aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="e8bea-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="e8bea-111">Rufen Sie die Funktion folgendermaßen auf:</span><span class="sxs-lookup"><span data-stu-id="e8bea-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="e8bea-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e8bea-112">.NET Framework Security</span></span>  
 <span data-ttu-id="e8bea-113">Um die integrierte **fn_trace_getinfo**-Funktion auszuführen, benötigt der Benutzer die folgende Berechtigung:</span><span class="sxs-lookup"><span data-stu-id="e8bea-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="e8bea-114">ALTER TRACE auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="e8bea-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bea-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8bea-115">See Also</span></span>  
 <span data-ttu-id="e8bea-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8bea-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="e8bea-117">Anzeigen und Analysieren von Ablaufverfolgungen mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e8bea-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
