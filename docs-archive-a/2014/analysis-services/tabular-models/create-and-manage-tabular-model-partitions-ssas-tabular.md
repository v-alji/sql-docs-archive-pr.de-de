---
title: Erstellen und Verwalten von Tabellen Modell Partitionen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620525"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="0ae7b-102">Erstellen und Verwalten von Tabellenmodellpartitionen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="0ae7b-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="0ae7b-103">Durch Partitionen wird eine Tabelle logisch unterteilt.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="0ae7b-104">Jede Partition kann unabhängig von anderen Partitionen verarbeitet (aktualisiert) werden.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="0ae7b-105">Während der Modellerstellung werden die für ein Modell definierten Partitionen in ein bereitgestelltes Modell dupliziert.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="0ae7b-106">Nach der Bereitstellung können Sie diese Partitionen mit dem Dialogfeld **Partitionen** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mithilfe eines Skripts verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="0ae7b-107">In den Tasks in diesem Thema wird beschrieben, wie Partitionen für ein bereitgestelltes Modell erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="0ae7b-108">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="0ae7b-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="0ae7b-109">So erstellen Sie eine neue Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="0ae7b-110">So kopieren Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="0ae7b-111">So führen Sie zwei oder mehr Partitionen zusammen</span><span class="sxs-lookup"><span data-stu-id="0ae7b-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="0ae7b-112">So löschen Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="0ae7b-113">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="0ae7b-113">Tasks</span></span>  
 <span data-ttu-id="0ae7b-114">Um Partitionen für die bereitgestellte Datenbank eines tabellarischen Modells zu erstellen und zu verwalten, verwenden Sie das Dialogfeld **Partitionen** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ae7b-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0ae7b-115">Um das Dialogfeld **Partitionen** anzuzeigen, klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]mit der rechten Maustaste auf eine Tabelle und klicken dann auf **Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="0ae7b-116">So erstellen Sie eine neue Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="0ae7b-117">Klicken Sie im Dialogfeld **Partitionen** auf die Schaltfläche **Neu** .</span><span class="sxs-lookup"><span data-stu-id="0ae7b-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="0ae7b-118">Geben Sie in **Partitionsname**einen Namen für die Partition ein.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="0ae7b-119">Der Name der Standardpartition wird für jede neue Partition inkrementell erhöht.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="0ae7b-120">Geben Sie unter **SQL-Anweisung**eine SQL-Abfrageanweisung in das Abfragefenster ein, durch die die Spalten und Klauseln definiert werden, die Sie in die Partition einschließen möchten, oder fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="0ae7b-121">Um die Anweisung zu überprüfen, klicken Sie auf **Syntax überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="0ae7b-122">So kopieren Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="0ae7b-123">Wählen Sie im Dialogfeld **Partitionen** in der Liste **Partitionen** die Partition aus, die Sie kopieren möchten, und klicken Sie dann auf die Schaltfläche **Kopieren** .</span><span class="sxs-lookup"><span data-stu-id="0ae7b-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="0ae7b-124">Geben Sie in **Partitionsname**einen neuen Namen für die Partition ein.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="0ae7b-125">Bearbeiten Sie die SQL-Abfrageanweisung unter **SQL-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="0ae7b-126">So führen Sie Partitionen zusammen</span><span class="sxs-lookup"><span data-stu-id="0ae7b-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="0ae7b-127">Wählen Sie im Dialogfeld **Partitionen** in der Liste **Partitionen** mithilfe von STRG-Klicken die Partitionen aus, die Sie zusammenführen möchten, und klicken Sie dann auf die Schaltfläche **Zusammenführen** .</span><span class="sxs-lookup"><span data-stu-id="0ae7b-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ae7b-128">Beim Zusammenführen von Partitionen werden die Partitionsmetadaten nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="0ae7b-129">Administratoren müssen die SQL-Anweisung ändern, damit bei den Verarbeitungsvorgängen der resultierenden Partition alle Daten in der zusammengeführten Partition verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0ae7b-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="0ae7b-130">So löschen Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="0ae7b-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="0ae7b-131">Wählen Sie im Dialogfeld **Partitionen** in der Liste **Partitionen** die Partition aus, die Sie löschen möchten, und klicken Sie dann auf die Schaltfläche **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="0ae7b-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae7b-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ae7b-132">See Also</span></span>  
 <span data-ttu-id="0ae7b-133">[Tabellarische Modell Partitionen &#40;tabellarischen SSAS-&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="0ae7b-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="0ae7b-134">Verarbeiten von Tabellenmodellpartitionen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="0ae7b-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
