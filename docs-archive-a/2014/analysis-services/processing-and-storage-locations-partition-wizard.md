---
title: Verarbeitungs-und Speicherorte (Partitions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725033"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="35436-102">Speicherorte zum Verarbeiten und Speichern (Partitions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="35436-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="35436-103">Mithilfe der Seite **Speicherorte zum Verarbeiten und Speichern** können Sie die [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz des Cubes angeben, der die Partition besitzt, sowie die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz, die die Daten für die Partition speichert.</span><span class="sxs-lookup"><span data-stu-id="35436-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="35436-104">Sie können eine Partition als Remotepartition definieren, indem Sie entweder eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Remoteinstanz oder einen vom Standardspeicherort abweichenden Speicherort angeben.</span><span class="sxs-lookup"><span data-stu-id="35436-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="35436-105">Weitere Informationen zu Remotepartitionen finden Sie unter [Remotepartitionen](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="35436-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="35436-106">Verarbeitungsstandort (Optionen)</span><span class="sxs-lookup"><span data-stu-id="35436-106">Processing location Options</span></span>  
 <span data-ttu-id="35436-107">**Aktuelle Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="35436-107">**Current server instance**</span></span>  
 <span data-ttu-id="35436-108">Macht die aktuelle [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz für die Verarbeitung der Partition verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="35436-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="35436-109">**Remotedatenquelle für SQL Server Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="35436-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="35436-110">Macht eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Remoteinstanz für die Verarbeitung dieser Partition verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="35436-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="35436-111">Wählen Sie aus der Dropdownliste die Datenquelle aus, die die für die Verarbeitung der Partition verantwortliche [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Remoteinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="35436-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35436-112">Wenn Sie eine Datenquelle auswählen, in der die Eigenschaft der `Initial Catalog`-Verbindungszeichenfolge nicht auf eine gültige [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank festgelegt ist, oder wenn die in der Eigenschaft der `Initial Catalog`-Verbindungszeichenfolge angegebene Datenbank keine Remotepartitionen unterstützt (d. h. die `MasterDatasourceID`-Eigenschaft der angegebenen Datenbank ist nicht auf einen gültigen Wert festgelegt), tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="35436-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="35436-113">**Neu**</span><span class="sxs-lookup"><span data-stu-id="35436-113">**New**</span></span>  
 <span data-ttu-id="35436-114">Erstellt eine neue Datenquelle, die die für die Verarbeitung der Partition verantwortliche [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Remoteinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="35436-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="35436-115">Speicherort (Optionen)</span><span class="sxs-lookup"><span data-stu-id="35436-115">Storage location Options</span></span>  
 <span data-ttu-id="35436-116">**Standardmäßiger Serverstandort**</span><span class="sxs-lookup"><span data-stu-id="35436-116">**Default server location**</span></span>  
 <span data-ttu-id="35436-117">Legt den Datenordner der aktuellen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz als Speicherort der Aggregations- und Indizierungsdaten für die Partition fest.</span><span class="sxs-lookup"><span data-stu-id="35436-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="35436-118">**Angegebener Ordner**</span><span class="sxs-lookup"><span data-stu-id="35436-118">**Specified folder**</span></span>  
 <span data-ttu-id="35436-119">Gibt den Speicherort der Aggregations- und Indizierungsdaten für die Partition an.</span><span class="sxs-lookup"><span data-stu-id="35436-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="35436-120">**...**</span><span class="sxs-lookup"><span data-stu-id="35436-120">**...**</span></span>  
 <span data-ttu-id="35436-121">Zeigt das Dialogfeld **Nach Remoteordner suchen** an, in dem Sie einen Ordner für **Angegebener Ordner**auswählen können.</span><span class="sxs-lookup"><span data-stu-id="35436-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35436-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35436-122">See Also</span></span>  
 <span data-ttu-id="35436-123">[Partitions-Assistent (F1-Hilfe &#40;Analysis Services-mehrdimensionalen Daten&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="35436-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="35436-124">[Partitionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="35436-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="35436-125">Dialog Feld "Remote Ordner suchen" &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="35436-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  
