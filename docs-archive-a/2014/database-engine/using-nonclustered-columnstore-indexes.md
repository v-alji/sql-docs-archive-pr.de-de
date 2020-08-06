---
title: Verwenden nicht gruppierter columnstore-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700191"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="56106-102">Verwenden nicht gruppierter Columnstore-Indizes</span><span class="sxs-lookup"><span data-stu-id="56106-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="56106-103">Beschreibt wichtige Aufgaben für die Verwendung eines nicht gruppierten Columnstore-Indexes für eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="56106-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="56106-104">Eine Übersicht über Columnstore-Indizes finden Sie unter [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="56106-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="56106-105">Informationen zum Verwenden von gruppierten Columnstore-Indizes finden Sie unter [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="56106-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="56106-106">Inhalte</span><span class="sxs-lookup"><span data-stu-id="56106-106">Contents</span></span>

-   [<span data-ttu-id="56106-107">Erstellen eines nicht gruppierten Columnstore-Indexes</span><span class="sxs-lookup"><span data-stu-id="56106-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="56106-108">Ändern der Daten in einem nicht gruppierten columnstore-Index</span><span class="sxs-lookup"><span data-stu-id="56106-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="56106-109">Erstellen eines nicht gruppierten columnstore-Indexes</span><span class="sxs-lookup"><span data-stu-id="56106-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="56106-110">Zum Laden von Daten in einen nicht gruppierten columnstore--Index laden Sie zuerst Daten in eine herkömmliche rowstore-Tabelle, die als Heap oder gruppierter Index gespeichert ist, und verwenden Sie dann [Create columnstore-Index &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) , um einen columnstore--Index zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56106-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="56106-111">![Laden von Daten in einen columnstore-Index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Laden von Daten in einen columnstore-Index")</span><span class="sxs-lookup"><span data-stu-id="56106-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="56106-112">Ändern der Daten in einem nicht gruppierten columnstore-Index</span><span class="sxs-lookup"><span data-stu-id="56106-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="56106-113">Wenn Sie einen nicht gruppierten Columnstore-Index für eine Tabelle erstellen, können Sie die Daten in dieser Tabelle nicht mehr direkt ändern.</span><span class="sxs-lookup"><span data-stu-id="56106-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="56106-114">Eine Abfrage mit INSERT, UPDATE, MERGE oder DELETE schlägt fehl und gibt eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="56106-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="56106-115">Um Daten in der Tabelle hinzuzufügen oder zu ändern, können Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="56106-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="56106-116">Deaktivieren Sie den columnstore--Index.</span><span class="sxs-lookup"><span data-stu-id="56106-116">Disable the columnstore index.</span></span> <span data-ttu-id="56106-117">Anschließend können Sie die Daten in der Tabelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="56106-117">You can then update the data in the table.</span></span> <span data-ttu-id="56106-118">Wenn Sie den Columnstore-Index deaktivieren, können Sie den Columnstore-Index nach dem Aktualisieren der Daten neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56106-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="56106-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="56106-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="56106-120">Löschen Sie den columnstore--Index, aktualisieren Sie die Tabelle, und erstellen Sie dann den columnstore--Index mit CREATE columnstore-Index neu.</span><span class="sxs-lookup"><span data-stu-id="56106-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="56106-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="56106-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="56106-122">Laden Sie Daten in eine Stagingtabelle ohne Columnstore-Index.</span><span class="sxs-lookup"><span data-stu-id="56106-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="56106-123">Erstellen Sie einen Columnstore-Index für die Stagingtabelle.</span><span class="sxs-lookup"><span data-stu-id="56106-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="56106-124">Wechseln Sie für die Stagingtabelle in eine leere Partition der Haupttabelle.</span><span class="sxs-lookup"><span data-stu-id="56106-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="56106-125">Wechseln Sie für eine Partition in der Tabelle mit dem Columnstore-Index in eine leere Stagingtabelle.</span><span class="sxs-lookup"><span data-stu-id="56106-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="56106-126">Wenn die Stagingtabelle über einen Columnstore-Index verfügt, deaktivieren Sie den Columnstore-Index.</span><span class="sxs-lookup"><span data-stu-id="56106-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="56106-127">Nehmen Sie die gewünschten Updates vor.</span><span class="sxs-lookup"><span data-stu-id="56106-127">Perform any updates.</span></span> <span data-ttu-id="56106-128">Erstellen bzw. erstellen Sie den Columnstore-Index neu.</span><span class="sxs-lookup"><span data-stu-id="56106-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="56106-129">Wechseln Sie für die Stagingtabelle zurück in die (nun leere) Partition der Haupttabelle.</span><span class="sxs-lookup"><span data-stu-id="56106-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




