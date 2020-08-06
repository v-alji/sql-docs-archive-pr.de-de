---
title: Erstellen und Verwalten von Partitionen in der Arbeitsbereichs Datenbank (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616208"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="d376d-102">Erstellen und Verwalten von Partitionen in der Arbeitsbereichsdatenbank (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="d376d-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="d376d-103">Durch Partitionen wird eine Tabelle logisch unterteilt.</span><span class="sxs-lookup"><span data-stu-id="d376d-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="d376d-104">Die einzelnen Partitionen können dann unabhängig voneinander oder parallel mit anderen Partitionen verarbeitet (aktualisiert) werden.</span><span class="sxs-lookup"><span data-stu-id="d376d-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="d376d-105">Durch Partitionen kann sich die Skalierbarkeit und Verwaltbarkeit großer Datenbanken verbessern.</span><span class="sxs-lookup"><span data-stu-id="d376d-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="d376d-106">Standardmäßig verfügt jede Tabelle über eine Partition, die alle Spalten einschließt.</span><span class="sxs-lookup"><span data-stu-id="d376d-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="d376d-107">In den Tasks in diesem Thema wird beschrieben, wie Partitionen in der Arbeitsbereichs Datenbank des Modells mithilfe des Dialog Felds **Partitions-Manager** in erstellt und verwaltet werden.[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d376d-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="d376d-108">Nachdem ein Modell für eine andere Analysis Services-Instanz bereitgestellt wurde, können Datenbankadministratoren Partitionen im (bereitgestellten) Modell mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="d376d-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d376d-109">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Tabellenmodellpartitionen &#40;SSAS – tabellarisch&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d376d-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="d376d-110">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="d376d-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="d376d-111">So erstellen Sie eine neue Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="d376d-112">So kopieren Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="d376d-113">So löschen Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="d376d-114">Partitionen in der Arbeitsbereichsdatenbank des Modells können nicht mithilfe des Dialogfelds Partitions-Manager zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d376d-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="d376d-115">Partitionen können in einem bereitgestellten Modell nur mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d376d-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="d376d-116">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d376d-116">Tasks</span></span>  
 <span data-ttu-id="d376d-117">Um Partitionen zu erstellen und zu verwalten, verwenden Sie das Dialogfeld **Partitions-Manager** .</span><span class="sxs-lookup"><span data-stu-id="d376d-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="d376d-118">Sie öffnen das Dialogfeld **Partitions-Manager** , indem Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Tabelle** und dann auf **Partitionen**klicken.</span><span class="sxs-lookup"><span data-stu-id="d376d-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="d376d-119">So erstellen Sie eine neue Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="d376d-120">Wählen Sie im Modell-Designer die Tabelle aus, für die Sie eine Partition definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d376d-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="d376d-121">Klicken Sie auf das Menü **Tabelle** und dann auf **Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="d376d-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="d376d-122">Überprüfen Sie, ob im **Partitions-Manager**im Listenfeld **Tabelle** die richtige Tabelle angezeigt wird, oder wählen Sie die zu partitionierende Tabelle aus, und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d376d-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="d376d-123">Geben Sie in **Partitionsname**einen Namen für die Partition ein.</span><span class="sxs-lookup"><span data-stu-id="d376d-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="d376d-124">Der Name der Standardpartition wird für jede neue Partition inkrementell erhöht.</span><span class="sxs-lookup"><span data-stu-id="d376d-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="d376d-125">Sie können die in die Partition einzufügenden Zeilen und Spalten auswählen, indem Sie den Tabellenvorschaumodus oder eine SQL-Abfrage verwenden, die im Abfrage-Editor-Modus erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d376d-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="d376d-126">Klicken Sie nahe der oberen rechten Ecke des Vorschaufensters auf die Schaltfläche **Tabellenvorschau** , um den Tabellenvorschaumodus (Standard) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d376d-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="d376d-127">Wählen Sie die in die Partition einzuschließenden Spalten aus, indem Sie das Kontrollkästchen neben dem Spaltennamen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d376d-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="d376d-128">Um Zeilen zu filtern, klicken Sie mit der rechten Maustaste auf einen Zellenwert, und klicken Sie auf **Nach dem Wert der ausgewählten Zelle filtern**.</span><span class="sxs-lookup"><span data-stu-id="d376d-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="d376d-129">Klicken Sie nahe der oberen rechten Ecke des Vorschaufensters auf die Schaltfläche **Abfrage-Editor** , um eine SQL-Anweisung zu verwenden. Geben Sie anschließend im Abfragefenster eine SQL-Abfrage-Anweisung ein (oder kopieren und fügen Sie die Anweisung aus einem anderen Text ein).</span><span class="sxs-lookup"><span data-stu-id="d376d-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="d376d-130">Um die Anweisung zu überprüfen, klicken Sie auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="d376d-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="d376d-131">Um den Abfrage-Designer zu verwenden, klicken Sie auf **Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="d376d-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="d376d-132">So kopieren Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="d376d-133">Überprüfen Sie, ob im **Partitions-Manager**im Listenfeld **Tabelle** die richtige Tabelle angezeigt wird, oder wählen Sie die Tabelle mit der zu kopierenden Partition aus.</span><span class="sxs-lookup"><span data-stu-id="d376d-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="d376d-134">Wählen Sie in der Liste **Partitionen** die zu kopierende Partition aus, und klicken Sie auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="d376d-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="d376d-135">Geben Sie in **Partitionsname**einen neuen Namen für die Partition ein.</span><span class="sxs-lookup"><span data-stu-id="d376d-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="d376d-136">So löschen Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="d376d-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="d376d-137">Überprüfen Sie, ob im **Partitions-Manager**im Listenfeld **Tabelle** die richtige Tabelle angezeigt wird, oder wählen Sie die zu löschende Partition aus.</span><span class="sxs-lookup"><span data-stu-id="d376d-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="d376d-138">Wählen Sie in der Liste **Partitionen** die zu löschende Partition aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d376d-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d376d-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d376d-139">See Also</span></span>  
 <span data-ttu-id="d376d-140">[Partitionen &#40;tabellarischen SSAS-&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d376d-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d376d-141">Verarbeiten von Partitionen in der Arbeitsbereichs Datenbank &#40;tabellarischen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="d376d-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
