---
title: Index neu erstellen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619259"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="939ca-102">Index neu erstellen (Task)</span><span class="sxs-lookup"><span data-stu-id="939ca-102">Rebuild Index Task</span></span>
  <span data-ttu-id="939ca-103">Mit dem Task Index neu erstellen werden Indizes in Tabellen und Sichten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="939ca-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="939ca-104">Weitere Informationen zum Verwalten von Indizes finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="939ca-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="939ca-105">Mithilfe des Tasks Index neu erstellen kann ein Paket Indizes in einer einzelnen Datenbank oder mehreren Datenbanken neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="939ca-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="939ca-106">Falls mit dem Task nur die Indizes in einer einzelnen Datenbank neu erstellt werden, können Sie die Sichten und Tabellen auswählen, deren Indizes neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="939ca-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="939ca-107">Dieser Task kapselt eine ALTER INDEX REBUILD-Anweisung mit den folgenden Indexneuerstellungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="939ca-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="939ca-108">Geben Sie einen Prozentsatz für FILLFACTOR an, oder verwenden Sie den ursprünglichen Wert für FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="939ca-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="939ca-109">Legen Sie PAD_INDEX = ON fest, um den mit FILLFACTOR angegebenen freien Speicherplatz den Zwischenebenenseiten des Indexes zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="939ca-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="939ca-110">Legen Sie SORT_IN_TEMPDB = ON fest, um das Zwischenergebnis der Sortierung zu speichern, mit dem der Index in tempdb neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="939ca-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="939ca-111">Wenn diese Option auf OFF festgelegt ist, wird das Ergebnis in derselben Datenbank wie der Index gespeichert.</span><span class="sxs-lookup"><span data-stu-id="939ca-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="939ca-112">Legen Sie IGNORE_DUP_KEY = ON fest, damit ein Einfügevorgang für mehrere Zeilen, der Datensätze einschließt, die UNIQUE-Einschränkungen verletzen, diejenigen Datensätze einfügen kann, die keine UNIQUE-Einschränkungen verletzen.</span><span class="sxs-lookup"><span data-stu-id="939ca-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="939ca-113">Legen Sie ONLINE = ON fest, um keine Tabellensperren zu verwenden, damit Abfragen oder Updates für die zugrunde liegende Tabelle während der Neuindizierung fortgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="939ca-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="939ca-114">Onlineindexvorgänge sind nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="939ca-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="939ca-115">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="939ca-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="939ca-116">Weitere Informationen zur ALTER INDEX-Anweisung und zu den Indexneuerstellungsoptionen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="939ca-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="939ca-117">Die Zeit, die der Task zum Erstellen der vom Task ausgeführten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung benötigt, ist proportional zur Anzahl der vom Task neu erstellten Indizes.</span><span class="sxs-lookup"><span data-stu-id="939ca-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="939ca-118">Falls für den Task konfiguriert ist, dass die Indizes in allen Tabellen und Sichten in einer Datenbank mit vielen Indizes neu erstellt werden, oder dass Indizes in mehreren Datenbanken neu erstellt werden, kann das Generieren der Transact-SQL-Anweisung lange dauern.</span><span class="sxs-lookup"><span data-stu-id="939ca-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="939ca-119">Konfiguration des Tasks "Index neu erstellen"</span><span class="sxs-lookup"><span data-stu-id="939ca-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="939ca-120">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="939ca-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="939ca-121">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="939ca-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="939ca-122">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="939ca-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="939ca-123">Task „Index neu erstellen“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="939ca-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="939ca-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="939ca-124">Related Tasks</span></span>  
 <span data-ttu-id="939ca-125">Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="939ca-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939ca-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="939ca-126">See Also</span></span>  
 <span data-ttu-id="939ca-127">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="939ca-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="939ca-128">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="939ca-128">Control Flow</span></span>](control-flow.md)  
  
  
