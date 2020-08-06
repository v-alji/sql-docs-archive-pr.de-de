---
title: Zusammenführen von Partitionen (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616762"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="42b35-102">Zusammenführen von Partitionen (XMLA)</span><span class="sxs-lookup"><span data-stu-id="42b35-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="42b35-103">Wenn Partitionen denselben Aggregations Entwurf und dieselbe Struktur aufweisen, können Sie die Partition zusammenführen, indem Sie den [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) -Befehl in XML for Analysis (XMLA) verwenden.</span><span class="sxs-lookup"><span data-stu-id="42b35-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="42b35-104">Das Zusammenführen von Partitionen ist ein wichtiger Vorgang, wenn Sie Partitionen verwalten, insbesondere wenn es sich hierbei um Partitionen mit Vergangenheitsdaten handelt, die nach Datum partitioniert sind.</span><span class="sxs-lookup"><span data-stu-id="42b35-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="42b35-105">Beispielsweise verwendet ein finanzieller Cube möglicherweise zwei Partitionen:</span><span class="sxs-lookup"><span data-stu-id="42b35-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="42b35-106">Eine Partition stellt die finanziellen Daten für das aktuelle Jahr dar und verwendet relationale OLAP-(ROLAP-)Speichereinstellungen in Echtzeit für die Leistung.</span><span class="sxs-lookup"><span data-stu-id="42b35-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="42b35-107">Eine andere Partition enthält finanzielle Daten für vergangene Jahre und verwendet mehrdimensionale OLAP-(MOLAP-)Speichereinstellungen für die Speicherung.</span><span class="sxs-lookup"><span data-stu-id="42b35-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="42b35-108">Beide Partitionen verwenden andere Speichereinstellungen, jedoch den gleichen Aggregationsentwurf.</span><span class="sxs-lookup"><span data-stu-id="42b35-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="42b35-109">Anstatt den Cube am Ende des Jahres mit Vergangenheitsdaten zahlreicher Jahre zu verarbeiten, können Sie auch den `MergePartitions`-Befehl verwenden, um die Partition für das aktuelle Jahr mit der Partition für die vergangenen Jahre zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="42b35-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="42b35-110">Dadurch werden die Aggregationsdaten beibehalten, ohne dass eine möglicherweise zeitaufwendige vollständige Verarbeitung des Cubes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="42b35-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="42b35-111">Angeben von Partitionen für die Zusammenführung</span><span class="sxs-lookup"><span data-stu-id="42b35-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="42b35-112">Wenn der `MergePartitions` Befehl ausgeführt wird, werden die Aggregations Daten, die in den in der [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) -Eigenschaft angegebenen Quell Partitionen gespeichert sind, der in der [target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) -Eigenschaft angegebenen Ziel Partition hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="42b35-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42b35-113">Die `Source`-Eigenschaft kann mehrere Partitionsobjektverweise enthalten.</span><span class="sxs-lookup"><span data-stu-id="42b35-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="42b35-114">Für die `Target`-Eigenschaft gilt dies jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="42b35-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="42b35-115">Damit die Zusammenführung erfolgreich ist, müssen sowohl die in der `Source`- als auch die in der `Target`-Eigenschaft angegebenen Partitionen in der gleichen Measuregruppe enthalten sein und den gleichen Aggregationsentwurf verwenden.</span><span class="sxs-lookup"><span data-stu-id="42b35-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="42b35-116">Andernfalls tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="42b35-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="42b35-117">Die in der `Source`-Eigenschaft angegebenen Partitionen werden gelöscht, nachdem der Befehl `MergePartitions` erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="42b35-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="42b35-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="42b35-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="42b35-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42b35-119">Description</span></span>  
 <span data-ttu-id="42b35-120">Im folgenden Beispiel werden alle Partitionen in der Measure-Gruppe **Customer Counts** des **Adventure Works** -Cubes in der **Adventure Works DW** -Beispiel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank in die **Customers_2004** Partition zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="42b35-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="42b35-121">Code</span><span class="sxs-lookup"><span data-stu-id="42b35-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42b35-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42b35-122">See Also</span></span>  
 [<span data-ttu-id="42b35-123">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="42b35-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
