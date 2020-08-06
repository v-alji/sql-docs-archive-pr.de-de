---
title: Filtern des Quellcubes für eine Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610188"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="05e70-102">Filtern des Quellcubes für eine Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="05e70-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="05e70-103">Wenn Sie eine Mining Struktur erstellen, die auf Daten in einem mehrdimensionalen Modell (einem OLAP-Cube) basiert, *können Sie* den Cube, auf dem die Mining Struktur basiert, segmentieren.</span><span class="sxs-lookup"><span data-stu-id="05e70-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="05e70-104">Durch die Aufteilung in Slices können Sie Teilmengen der Daten erstellen. Diese dienen als Art von Filter für die Daten, die zum Trainieren des Miningmodells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05e70-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="05e70-105">So teilen Sie einen Cube in Slices auf</span><span class="sxs-lookup"><span data-stu-id="05e70-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="05e70-106">Wählen Sie im Data Mining-Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] die Registerkarte **Mining Struktur** oder **Mining Modelle** aus.</span><span class="sxs-lookup"><span data-stu-id="05e70-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="05e70-107">Wählen Sie im Menü **Mining Modell** die Option **Mining Struktur Cube Slice definieren**aus.</span><span class="sxs-lookup"><span data-stu-id="05e70-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="05e70-108">Das Dialogfeld **Cube Slice** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="05e70-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="05e70-109">Wählen Sie in der Spalte **Dimension** des Dialog Felds **Cube Slice** die Dimension aus, die Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="05e70-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="05e70-110">Wählen Sie eine Ebene einer Hierarchie aus, und verwenden Sie dabei die Liste in der Spalte **Hierarchie** .</span><span class="sxs-lookup"><span data-stu-id="05e70-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="05e70-111">Wählen Sie einen Operator aus der Liste in der Spalte **Operator** aus, der beim Aufbau der Filterbedingung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e70-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="05e70-112">Klicken Sie in der Spalte **Filter** auf das Feld.</span><span class="sxs-lookup"><span data-stu-id="05e70-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="05e70-113">Es wird ein Dialogfeld geöffnet, das alle Elemente in der angegebenen Hierarchieebene enthält.</span><span class="sxs-lookup"><span data-stu-id="05e70-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="05e70-114">Wählen Sie das Element bzw. die Elemente aus, die Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="05e70-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="05e70-115">Klicken Sie im Dialogfeld Mitglied auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="05e70-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="05e70-116">Klicken Sie im Dialogfeld **Cube Slice** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="05e70-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="05e70-117">Der Quellcube wird jetzt entsprechend der Cubeslice-Definition gefiltert.</span><span class="sxs-lookup"><span data-stu-id="05e70-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e70-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05e70-118">See Also</span></span>  
 <span data-ttu-id="05e70-119">[Mining Struktur Tasks und-Anleitungen](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="05e70-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="05e70-120">Erstellen einer neuen OLAP-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="05e70-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
