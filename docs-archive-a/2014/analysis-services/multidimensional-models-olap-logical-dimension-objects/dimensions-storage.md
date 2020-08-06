---
title: Dimensions Speicher | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696273"
---
# <a name="dimension-storage"></a><span data-ttu-id="93d0b-102">Speichern von Dimensionen</span><span class="sxs-lookup"><span data-stu-id="93d0b-102">Dimension Storage</span></span>
  <span data-ttu-id="93d0b-103">Dimensionen in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] unterstützen zwei Speicher Modi:</span><span class="sxs-lookup"><span data-stu-id="93d0b-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="93d0b-104">Relationale OLAP (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="93d0b-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="93d0b-105">Mehrdimensionale OLAP (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="93d0b-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="93d0b-106">Durch den Speichermodus werden der Speicherort und die Form der Daten einer Dimension bestimmt.</span><span class="sxs-lookup"><span data-stu-id="93d0b-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="93d0b-107">MOLAP ist der Standardspeichermodus für Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="93d0b-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="93d0b-108">**Verwandte Themen:**[Speicher Modi und Verarbeitung von Partitionen](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="93d0b-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="93d0b-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="93d0b-109">MOLAP</span></span>  
 <span data-ttu-id="93d0b-110">Daten für eine Dimension, die MOLAP verwendet, werden in einer mehrdimensionalen Struktur in einer Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gespeichert.</span><span class="sxs-lookup"><span data-stu-id="93d0b-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="93d0b-111">Diese mehrdimensionale Struktur wird erstellt und aufgefüllt, wenn die Dimension verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="93d0b-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="93d0b-112">MOLAP-Dimensionen ermöglichen eine bessere Abfrageleistung als ROLAP-Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="93d0b-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="93d0b-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="93d0b-113">ROLAP</span></span>  
 <span data-ttu-id="93d0b-114">Die Daten für eine Dimension, die ROLAP verwendet, werden eigentlich in den Tabellen gespeichert, die zum Definieren der Dimension verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93d0b-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="93d0b-115">Der ROLAP-Speichermodus kann verwendet werden, um große Dimensionen ohne Kopieren großer Datenmengen zu unterstützen, allerdings zu Lasten der Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="93d0b-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="93d0b-116">Da die Dimension direkt von den Tabellen in der Datenquellensicht abhängt, die zum Definieren der Dimension verwendet wurden, unterstützt der ROLAP-Speichermodus auch Echtzeit-OLAP.</span><span class="sxs-lookup"><span data-stu-id="93d0b-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93d0b-117">Wenn eine Dimension den ROLAP-Speichermodus verwendet und die Dimension in einen Cube eingeschlossen ist, der die MOLAP-Speicherung verwendet, muss auf jede Schemaänderung an der zugehörigen Quelltabelle die sofortige Verarbeitung des Cubes folgen.</span><span class="sxs-lookup"><span data-stu-id="93d0b-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="93d0b-118">Erfolgt die Verarbeitung nicht, kann dies zu inkonsistenten Ergebnissen führen, wenn der Cube abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="93d0b-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="93d0b-119">**Verwandte Themen:**[automatisieren Analysis Services administrative Aufgaben mit SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="93d0b-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d0b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93d0b-120">See Also</span></span>  
 [<span data-ttu-id="93d0b-121">Speichermodi und Verarbeitung von Partitionen</span><span class="sxs-lookup"><span data-stu-id="93d0b-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
