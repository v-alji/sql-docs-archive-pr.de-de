---
title: T-SQL-Anweisung ausführen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697065"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="30977-102">T-SQL-Anweisung ausführen (Task)</span><span class="sxs-lookup"><span data-stu-id="30977-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="30977-103">Mit dem Task T-SQL-Anweisung ausführen werden Transact-SQL-Anweisungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30977-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="30977-104">Weitere Informationen finden Sie unter [Transact-SQL-Referenz &#40;Datenbank-Engine&#41;](/sql/t-sql/language-reference) und [Integration Services-Abfragen &#40;SSIS&#41;](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="30977-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="30977-105">Dieser Task ist mit dem Task SQL ausführen vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="30977-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="30977-106">Der Task T-SQL-Anweisung ausführen unterstützt jedoch nur die Transact-SQL-Version der SQL-Sprache und kann nicht zum Ausführen von Anweisungen auf Servern verwendet werden, die andere Dialekte der SQL-Sprache verwenden.</span><span class="sxs-lookup"><span data-stu-id="30977-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="30977-107">Falls Sie parametrisierte Abfragen ausführen müssen, speichern Sie die Abfrageergebnisse in Variablen, oder verwenden Sie Eigenschaftsausdrücke. Sie sollten den Task SQL ausführen anstelle des Tasks T-SQL-Anweisung ausführen verwenden.</span><span class="sxs-lookup"><span data-stu-id="30977-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="30977-108">Weitere Informationen finden Sie unter [Execute SQL Task](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="30977-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="30977-109">Konfiguration des Tasks "T-SQL-Anweisung ausführen"</span><span class="sxs-lookup"><span data-stu-id="30977-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="30977-110">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="30977-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="30977-111">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="30977-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="30977-112">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="30977-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="30977-113">Task „T-SQL-Anweisung ausführen“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="30977-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="30977-114">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="30977-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="30977-115">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="30977-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="30977-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30977-116">See Also</span></span>  
 <span data-ttu-id="30977-117">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="30977-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="30977-118">[Ablaufsteuerung](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="30977-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="30977-119">MERGE in Integration Services-Paketen</span><span class="sxs-lookup"><span data-stu-id="30977-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
