---
title: Zusammenführen von Daten mithilfe der Transformation für UNION ALL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621092"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="8f597-102">Zusammenführen von Daten mithilfe der Transformation für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="8f597-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="8f597-103">Das Paket muss bereits mindestens einen Datenflusstask und zwei Datenquellen enthalten, damit Sie eine Transformation für UNION ALL hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="8f597-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="8f597-104">Die Transformation für UNION ALL kombiniert mehrere Eingaben.</span><span class="sxs-lookup"><span data-stu-id="8f597-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="8f597-105">Die erste Eingabe, die mit der Transformation verbunden wird, ist die Verweiseingabe, und die nachfolgend verbundenen Eingaben sind die sekundären Eingaben.</span><span class="sxs-lookup"><span data-stu-id="8f597-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="8f597-106">Die Ausgabe enthält die Spalten in der Verweiseingabe.</span><span class="sxs-lookup"><span data-stu-id="8f597-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="8f597-107">So kombinieren Sie Eingaben in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="8f597-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="8f597-108">Doppelklicken Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]im Projektmappen-Explorer auf das Paket, um es im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu öffnen, und klicken Sie dann auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="8f597-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="8f597-109">Ziehen Sie aus **Toolbox**die Transformation für UNION ALL auf die Entwurfsoberfläche der Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="8f597-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="8f597-110">Verbinden Sie die Transformation für UNION ALL mit dem Datenfluss, indem Sie einen Konnektor von der Datenquelle oder einer vorherigen Transformation auf die Transformation für UNION ALL ziehen.</span><span class="sxs-lookup"><span data-stu-id="8f597-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="8f597-111">Doppelklicken Sie auf die Transformation für UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="8f597-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="8f597-112">Ordnen Sie im **Transformations-Editor für UNION ALL**eine Spalte aus einer Eingabe einer Spalte in der Liste **Name der Ausgabespalte** zu. Klicken Sie dazu auf eine Zeile, und wählen Sie dann eine Spalte in der Eingabeliste aus.</span><span class="sxs-lookup"><span data-stu-id="8f597-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="8f597-113">Wählen Sie **\<ignore>** in der Eingabeliste aus, um das Zuordnen der Spalte zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="8f597-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f597-114">Für die Zuordnung von zwei Spalten müssen die Metadaten der Spalten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8f597-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f597-115">Für Spalten in einer sekundären Eingabe, die keinen Verweisspalten zugeordnet sind, werden in der Ausgabe NULL-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8f597-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="8f597-116">Ändern Sie optional die Namen von Spalten in der **Name der Ausgabespalte** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="8f597-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="8f597-117">Wiederholen Sie die Schritte 5 und 6 für jede Spalte in jeder Eingabe.</span><span class="sxs-lookup"><span data-stu-id="8f597-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="8f597-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f597-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="8f597-119">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8f597-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f597-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f597-120">See Also</span></span>  
 <span data-ttu-id="8f597-121">[Transformation für UNION ALL](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="8f597-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="8f597-122">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="8f597-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="8f597-123">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="8f597-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="8f597-124">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="8f597-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
