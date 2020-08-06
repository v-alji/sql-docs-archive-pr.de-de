---
title: Erweitern eines Datasets mithilfe der Transformation für Zusammenführungsjoin | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609981"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="88283-102">Erweitern eines Datasets mithilfe der Transformation für Zusammenführungsjoins</span><span class="sxs-lookup"><span data-stu-id="88283-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="88283-103">Das Paket muss bereits mindestens einen Datenflusstask und zwei Datenflusskomponenten enthalten, die Eingaben für die Transformation für Zusammenführungsjoins bereitstellen, damit Sie eine Transformation für Zusammenführungsjoins hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="88283-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="88283-104">Die Transformation für Zusammenführungsjoin erfordert zwei sortierte Eingaben.</span><span class="sxs-lookup"><span data-stu-id="88283-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="88283-105">Weitere Informationen finden Sie unter [Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="88283-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="88283-106">So erweitern Sie ein Dataset</span><span class="sxs-lookup"><span data-stu-id="88283-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="88283-107">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="88283-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="88283-108">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88283-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="88283-109">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**die Transformation für Zusammenführungsjoin auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="88283-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="88283-110">Verbinden Sie die Transformation für Zusammenführungsjoins mit dem Datenfluss, indem Sie den Konnektor von einer Datenquelle oder einer vorherigen Transformation auf die Transformation für Zusammenführungsjoins ziehen.</span><span class="sxs-lookup"><span data-stu-id="88283-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="88283-111">Doppelklicken Sie auf die Transformation für Zusammenführungsjoin.</span><span class="sxs-lookup"><span data-stu-id="88283-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="88283-112">Wählen Sie im Dialogfeld **Transformations-Editor für Zusammenführungsjoins** den zu verwendenden Jointyp in der Liste **Jointyp** aus.</span><span class="sxs-lookup"><span data-stu-id="88283-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88283-113">Wenn Sie den Typ **Linker äußerer Join** auswählen, können Sie auf **Eingaben vertauschen** klicken, um die Eingaben zu vertauschen und den linken äußeren Join in einen rechten äußeren Join zu ändern.</span><span class="sxs-lookup"><span data-stu-id="88283-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="88283-114">Ziehen Sie Spalten in der linken Eingabe auf Spalten in der rechten Eingabe, um die Joinspalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88283-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="88283-115">Falls die Spalten denselben Namen haben, können Sie das **entsprechende Kontrollkästchen** aktivieren, damit die Transformation für Zusammenführungsjoin den Join automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="88283-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88283-116">Joins können nur zwischen Spalten mit der gleichen Sortierposition erstellt werden, und die Joins müssen in der von der Sortierposition angegebenen Reihenfolge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="88283-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="88283-117">Wenn Sie versuchen, die Joins außerhalb der Reihenfolge zu erstellen, werden Sie vom **Transformations-Editor für Zusammenführungsjoin** aufgefordert, zusätzliche Joins für die ausgelassenen Sortierreihenfolgepositionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88283-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88283-118">Standardmäßig wird die Ausgabe nach den Joinspalten sortiert.</span><span class="sxs-lookup"><span data-stu-id="88283-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="88283-119">Aktivieren Sie in der linken und rechten Eingabe die Kontrollkästchen zusätzlicher Spalten, die in die Ausgabe eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88283-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="88283-120">Joinspalten sind standardmäßig eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="88283-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="88283-121">Aktualisieren Sie optional die Namen von Ausgabespalten in der **Ausgabealias** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="88283-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="88283-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="88283-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="88283-123">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88283-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88283-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88283-124">See Also</span></span>  
 <span data-ttu-id="88283-125">[Transformation für Zusammenführungsjoin](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="88283-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="88283-126">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="88283-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="88283-127">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="88283-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="88283-128">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="88283-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
