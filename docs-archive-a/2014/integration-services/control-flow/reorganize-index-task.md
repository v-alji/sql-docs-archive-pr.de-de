---
title: Index neu organisieren (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.reorganizeindextask.f1
helpviewer_keywords:
- reorganizing indexes
- Reorganize Index task [Integration Services]
- indexes [Integration Services]
ms.assetid: 9ed87861-e5c3-4fcd-8760-d112f4c0af0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f910391bd3a5a35770bb677bc17c91a00ace457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619257"
---
# <a name="reorganize-index-task"></a><span data-ttu-id="347bd-102">Index neu organisieren (Task)</span><span class="sxs-lookup"><span data-stu-id="347bd-102">Reorganize Index Task</span></span>
  <span data-ttu-id="347bd-103">Mit dem Task Index neu organisieren werden Indizes in Tabellen und Sichten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken neu organisiert.</span><span class="sxs-lookup"><span data-stu-id="347bd-103">The Reorganize Index task reorganizes indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="347bd-104">Weitere Informationen zum Verwalten von Indizes finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="347bd-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="347bd-105">Mithilfe des Tasks Index neu organisieren kann ein Paket Indizes in einer einzelnen Datenbank oder mehreren Datenbanken neu organisieren.</span><span class="sxs-lookup"><span data-stu-id="347bd-105">By using the Reorganize Index task, a package can reorganize indexes in a single database or multiple databases.</span></span> <span data-ttu-id="347bd-106">Falls mit dem Task nur die Indizes in einer einzelnen Datenbank neu organisiert werden, können Sie die Sichten oder Tabellen auswählen, deren Indizes neu organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="347bd-106">If the task reorganizes only the indexes in a single database, you can choose the views or the tables whose indexes the task reorganizes.</span></span> <span data-ttu-id="347bd-107">Der Task Index neu organisieren schließt außerdem eine Option zum Komprimieren von großen Objekten ein.</span><span class="sxs-lookup"><span data-stu-id="347bd-107">The Reorganize Index task also includes an option to compact large object data.</span></span> <span data-ttu-id="347bd-108">Große Objektdaten weisen den Datentyp `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` oder `xml` auf.</span><span class="sxs-lookup"><span data-stu-id="347bd-108">Large object data is data with the `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, or `xml` data type.</span></span> <span data-ttu-id="347bd-109">Weitere Informationen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="347bd-109">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="347bd-110">Der Task Index neu organisieren kapselt die ALTER INDEX-Anweisung von Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="347bd-110">The Reorganize Index task encapsulates the Transact-SQL ALTER INDEX statement.</span></span> <span data-ttu-id="347bd-111">Wenn Sie große Objekte komprimieren möchten, verwendet die Anweisung die REORGANIZE WITH (LOB_COMPACTION = ON)-Klausel. Andernfalls ist LOB_COMPACTION auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="347bd-111">If you choose to compact large object data, the statement uses the REORGANIZE WITH (LOB_COMPACTION = ON) clause, otherwise LOB_COMPACTION is set to OFF.</span></span> <span data-ttu-id="347bd-112">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="347bd-112">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="347bd-113">Die Zeit, die der Task zum Erstellen der vom Task ausgeführten Transact-SQL-Anweisung benötigt, ist proportional zur Anzahl der vom Task neu organisierten Indizes.</span><span class="sxs-lookup"><span data-stu-id="347bd-113">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of indexes the task reorganizes.</span></span> <span data-ttu-id="347bd-114">Falls für den Task konfiguriert ist, dass die Indizes in allen Tabellen und Sichten in einer Datenbank mit vielen Indizes neu organisiert werden, oder dass Indizes in mehreren Datenbanken neu organisiert werden, kann das Generieren der Transact-SQL-Anweisung lange dauern.</span><span class="sxs-lookup"><span data-stu-id="347bd-114">If the task is configured to reorganize indexes in all the tables and views in a database that holds a large number of indexes, or to reorganize indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-reorganize-index-task"></a><span data-ttu-id="347bd-115">Konfiguration des Tasks "Index neu organisieren"</span><span class="sxs-lookup"><span data-stu-id="347bd-115">Configuration of the Reorganize Index Task</span></span>  
 <span data-ttu-id="347bd-116">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="347bd-116">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="347bd-117">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="347bd-117">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="347bd-118">Klicken Sie auf das folgende Thema, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="347bd-118">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="347bd-119">Task „Index neu organisieren“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="347bd-119">Reorganize Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/reorganize-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="347bd-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="347bd-120">Related Tasks</span></span>  
 <span data-ttu-id="347bd-121">Weitere Informationen zum Anzeigen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="347bd-121">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347bd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="347bd-122">See Also</span></span>  
 <span data-ttu-id="347bd-123">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="347bd-123">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="347bd-124">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="347bd-124">Control Flow</span></span>](control-flow.md)  
  
  
