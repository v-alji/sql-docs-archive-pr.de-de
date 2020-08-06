---
title: Statistiken aktualisieren (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607913"
---
# <a name="update-statistics-task"></a><span data-ttu-id="a3ced-102">Statistiken aktualisieren (Task)</span><span class="sxs-lookup"><span data-stu-id="a3ced-102">Update Statistics Task</span></span>
  <span data-ttu-id="a3ced-103">Der Task "Statistiken aktualisieren" aktualisiert Informationen zur Verteilung von Schlüsselwerten für eine oder mehrere Statistikgruppen (Auflistungen) in der angegebenen Tabelle oder indizierten Sicht.</span><span class="sxs-lookup"><span data-stu-id="a3ced-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="a3ced-104">Weitere Informationen finden Sie unter [Verwalten von Statistiken für Tabellen in SQL Data Warehouse](../../relational-databases/statistics/statistics.md).</span><span class="sxs-lookup"><span data-stu-id="a3ced-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="a3ced-105">Mithilfe des Tasks Statistiken aktualisieren kann ein Paket Statistiken für eine einzelne Datenbank oder mehrere Datenbanken aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a3ced-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="a3ced-106">Falls mit dem Task nur die Statistiken in einer einzelnen Datenbank aktualisiert werden, können Sie die Sichten oder Tabellen auswählen, deren Statistiken aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3ced-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="a3ced-107">Sie können das Update so konfigurieren, dass alle Statistiken, nur Spaltenstatistiken oder nur Indexstatistiken aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3ced-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="a3ced-108">Dieser Task kapselt eine UPDATE STATISTICS-Anweisung, einschließlich der folgenden Argumente und Klauseln:</span><span class="sxs-lookup"><span data-stu-id="a3ced-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="a3ced-109">Das Argument *table_name* oder *view_name* .</span><span class="sxs-lookup"><span data-stu-id="a3ced-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="a3ced-110">Wenn alle Statistiken aktualisiert werden, wird die WITH ALL-Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3ced-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="a3ced-111">Wenn nur Spalten aktualisiert werden, wird die WITH COLUMN-Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3ced-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="a3ced-112">Wenn nur Indizes aktualisiert werden, wird die WITH INDEX-Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3ced-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="a3ced-113">Wenn der Task Statistiken aktualisieren Statistiken in mehreren Datenbanken aktualisiert, werden mehrere UPDATE STATISTICS-Anweisungen ausgeführt, wobei pro Tabelle oder Sicht eine Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3ced-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="a3ced-114">Alle Instanzen von UPDATE STATISTICS verwenden dieselbe Klausel aber unterschiedliche Werte für *table_name* oder *view_name* .</span><span class="sxs-lookup"><span data-stu-id="a3ced-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="a3ced-115">Weitere Informationen finden Sie unter [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) und [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a3ced-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a3ced-116">Die Zeit, die der Task zum Erstellen der vom Task ausgeführten Transact-SQL-Anweisung benötigt, ist proportional zur Anzahl der vom Task aktualisierten Statistiken.</span><span class="sxs-lookup"><span data-stu-id="a3ced-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="a3ced-117">Falls für den Task konfiguriert ist, dass die Statistiken in allen Tabellen und Sichten in einer Datenbank mit vielen Indizes aktualisiert werden, oder dass Statistiken in mehreren Datenbanken aktualisiert werden, kann das Generieren der Transact-SQL-Anweisung lange dauern.</span><span class="sxs-lookup"><span data-stu-id="a3ced-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="a3ced-118">Konfiguration des Tasks "Statistiken aktualisieren"</span><span class="sxs-lookup"><span data-stu-id="a3ced-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="a3ced-119">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="a3ced-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a3ced-120">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="a3ced-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="a3ced-121">Klicken Sie auf das folgende Thema, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a3ced-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a3ced-122">Task „Statistiken aktualisieren“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ced-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="a3ced-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a3ced-123">Related Tasks</span></span>  
 <span data-ttu-id="a3ced-124">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="a3ced-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a3ced-125">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="a3ced-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3ced-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3ced-126">See Also</span></span>  
 <span data-ttu-id="a3ced-127">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a3ced-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="a3ced-128">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="a3ced-128">Control Flow</span></span>](control-flow.md)  
  
  
