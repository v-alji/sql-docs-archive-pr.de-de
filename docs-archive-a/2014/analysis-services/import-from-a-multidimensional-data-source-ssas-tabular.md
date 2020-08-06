---
title: Importieren aus einer mehrdimensionalen Datenquelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622274"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="68458-102">Importieren von einer mehrdimensionalen Datenquelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="68458-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="68458-103">Sie können eine Analysis Services-Cubedatenbank als Datenquelle für ein tabellarisches Modell verwenden.</span><span class="sxs-lookup"><span data-stu-id="68458-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="68458-104">Um Daten aus einem Analysis Services-Cube zu importieren, müssen Sie eine MDX-Abfrage zur Auswahl der zu importierenden Daten definieren.</span><span class="sxs-lookup"><span data-stu-id="68458-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="68458-105">Alle Daten, die in einer SQL Server Analysis Services-Datenbank enthalten sind, können in ein Modell importiert werden.</span><span class="sxs-lookup"><span data-stu-id="68458-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="68458-106">Sie können die gesamte oder einen Teil einer Dimension extrahieren oder Slices und Aggregate aus dem Cube abrufen, z. B. die Summe der monatlichen Verkäufe für das aktuelle Jahr usw. Beachten Sie jedoch, dass alle Daten, die Sie aus einem Cube importieren, vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="68458-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="68458-107">Wenn Sie eine Abfrage definieren, die Measures aus mehreren Dimensionen abruft, werden die Daten daher für jede Dimension in eine separate Spalte importiert.</span><span class="sxs-lookup"><span data-stu-id="68458-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="68458-108">Analysis Services-Cubes müssen die Version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]oder [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]aufweisen.</span><span class="sxs-lookup"><span data-stu-id="68458-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="68458-109">So importieren Sie Daten aus einem Analysis Services-Cube</span><span class="sxs-lookup"><span data-stu-id="68458-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="68458-110">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf das Menü **Modell** und dann auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="68458-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="68458-111">Wählen Sie auf der Seite **Mit einer Datenquelle verbinden** die Option **Microsoft Analysis Services**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="68458-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="68458-112">Führen Sie die Schritte im Tabellenimport-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="68458-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="68458-113">Auf der Seite **MDX-Abfrage angeben** können Sie eine MDX-Abfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="68458-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="68458-114">Zur Verwendung des MDX-Abfrage-Designers klicken Sie auf der Seite **MDX-Abfrage angeben**auf Entwurf.</span><span class="sxs-lookup"><span data-stu-id="68458-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68458-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68458-115">See Also</span></span>  
 <span data-ttu-id="68458-116">[Importieren von Daten &#40;tabellarischen SSAS-&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="68458-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="68458-117">Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="68458-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
