---
title: Partitions Quelle (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694746"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="93dc7-102">Dialogfeld 'Partitionsquelle' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="93dc7-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="93dc7-103">Mithilfe des Dialogfelds **Partitionsquelle** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie die Quelle der Faktentabellendaten für eine Partition angeben.</span><span class="sxs-lookup"><span data-stu-id="93dc7-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="93dc7-104">Das Dialogfeld **Partitionsquelle** können Sie wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="93dc7-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="93dc7-105">Klicken Sie im Cube-Designer auf der Registerkarte **Partitionen** auf die Schaltfläche **...** einer Zelle des Rasters **Partitionen** einer im Bereich **Measuregruppen** ausgewählten Measuregruppe.</span><span class="sxs-lookup"><span data-stu-id="93dc7-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="93dc7-106">Klicken Sie in **im Fenster** Eigenschaften **auf die Schaltfläche** ... **eines Eigenschaftswerts** Quelle **eines** Partition [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]-Objekts.</span><span class="sxs-lookup"><span data-stu-id="93dc7-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="93dc7-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="93dc7-107">Options</span></span>  
  
|<span data-ttu-id="93dc7-108">Option</span><span class="sxs-lookup"><span data-stu-id="93dc7-108">Option</span></span>|<span data-ttu-id="93dc7-109">Definition</span><span class="sxs-lookup"><span data-stu-id="93dc7-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="93dc7-110">**Bindungstyp**</span><span class="sxs-lookup"><span data-stu-id="93dc7-110">**Binding type**</span></span>|<span data-ttu-id="93dc7-111">Wählen Sie den Bindungstyp für die Quelle der angegebenen Partition aus.</span><span class="sxs-lookup"><span data-stu-id="93dc7-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="93dc7-112">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="93dc7-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="93dc7-113">**Tabellen Bindung**: Wählen Sie diese Option aus, um den Bereich **Tabellen Bindungs Details** anzuzeigen und anzugeben, dass die Partition an die Inhalte einer Tabelle in einer Datenquelle oder Datenquellen Sicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="93dc7-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="93dc7-114">Weitere Informationen zum Bereich mit **Tabellenbindungsdetails** finden Sie unter [Tabellenbindungsdetails &#40;Dialogfeld „Partitionsquelle“, Analysis Services – mehrdimensionale Daten&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="93dc7-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="93dc7-115">**Detail**: Wählen Sie diese Option aus, um den Bereich **Abfrage Bindungs Details** anzuzeigen und anzugeben, dass die Partition an den Inhalt einer Abfrage gebunden ist, die für eine Datenquelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="93dc7-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="93dc7-116">Weitere Informationen zum Bereich mit **Abfragebindungsdetails** finden Sie unter [Abfragebindungsdetails &#40;Dialogfeld „Partitionsquelle“, Analysis Services – mehrdimensionale Daten&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="93dc7-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="93dc7-117">**Detail**</span><span class="sxs-lookup"><span data-stu-id="93dc7-117">**Detail**</span></span>|<span data-ttu-id="93dc7-118">Zeigt abhängig vom Wert der Option **Bindungstyp** entweder die Details im Dialogfeld **Tabellenbindung** oder **Abfragebindung** an.</span><span class="sxs-lookup"><span data-stu-id="93dc7-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93dc7-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93dc7-119">See Also</span></span>  
 <span data-ttu-id="93dc7-120">[Partitionen &#40;Cube-Designer-&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="93dc7-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="93dc7-121">Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="93dc7-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
