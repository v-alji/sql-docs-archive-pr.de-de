---
title: Partitions-Assistent (F1-Hilfe) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Partition Wizard
ms.assetid: 3b6d7053-aeef-4d9e-af70-f5b40256e859
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa8c0e94c2b18ffbd1228752bd7cb4ad4f684acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615644"
---
# <a name="partition-wizard-f1-help-analysis-services---multidimensional-data"></a><span data-ttu-id="8ccab-102">Partitions-Assistent (F1-Hilfe) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="8ccab-102">Partition Wizard F1 Help (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="8ccab-103">Mit dem Partitions-Assistent können Sie Partitionen für eine Measuregruppe in einem Cube definieren.</span><span class="sxs-lookup"><span data-stu-id="8ccab-103">You can use the Partition Wizard to define partitions for a measure group in a cube.</span></span> <span data-ttu-id="8ccab-104">Standardmäßig wird für jede Measuregruppe in einem Cube eine Partition definiert.</span><span class="sxs-lookup"><span data-stu-id="8ccab-104">By default, a single partition is defined for each measure group in a cube.</span></span> <span data-ttu-id="8ccab-105">Große Partitionen können sich jedoch auf die Zugriffs- und Verarbeitungsleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="8ccab-105">Access and processing performance, however, can degrade for large partitions.</span></span> <span data-ttu-id="8ccab-106">Wenn Sie mehrere Partitionen erstellen, die jeweils einen Teil der Daten für eine Measuregruppe enthalten, können Sie die Zugriffs- und Verarbeitungsleistung für die Measuregruppe verbessern.</span><span class="sxs-lookup"><span data-stu-id="8ccab-106">By creating multiple partitions, each containing a portion of the data for a measure group, you can improve the access and processing performance for that measure group.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="8ccab-107">Wenn auf der Seite **Quellinformationen angeben** oder **Zeilen einschränken** Zeilen doppelt eingefügt werden, können Partitionen mit fehlerhaften Daten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ccab-107">It is possible to create partitions that may contain incorrect data by including duplicate rows in the **Specify Source Information** or **Restrict Rows** pages.</span></span>  
  
 <span data-ttu-id="8ccab-108">Mit dem Partitions-Assistent werden Sie durch die folgenden Schritte geführt:</span><span class="sxs-lookup"><span data-stu-id="8ccab-108">The Partition Wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="8ccab-109">Auswählen der Datenquellensicht für die Partition.</span><span class="sxs-lookup"><span data-stu-id="8ccab-109">Selecting the data source view for the partition.</span></span>  
  
-   <span data-ttu-id="8ccab-110">Erstellen eines Filters für die in der Partition enthaltenen Datensätze.</span><span class="sxs-lookup"><span data-stu-id="8ccab-110">Creating a filter for the records included in the partition.</span></span>  
  
-   <span data-ttu-id="8ccab-111">Festlegen des Verarbeitungs- und Speicherortes.</span><span class="sxs-lookup"><span data-stu-id="8ccab-111">Setting the processing and storage locations.</span></span>  
  
-   <span data-ttu-id="8ccab-112">Benennen und Speichern der Partition.</span><span class="sxs-lookup"><span data-stu-id="8ccab-112">Naming and saving the partition.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ccab-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ccab-113">In This Section</span></span>  
  
-   [<span data-ttu-id="8ccab-114">Quell Informationen &#40;Partitions-Assistenten angeben&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-114">Specify Source Information &#40;Partition Wizard&#41;</span></span>](specify-source-information-partition-wizard.md)  
  
-   [<span data-ttu-id="8ccab-115">Assistent zum Einschränken von Zeilen &#40;Partitionen&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-115">Restrict Rows &#40;Partition Wizard&#41;</span></span>](restrict-rows-partition-wizard.md)  
  
-   [<span data-ttu-id="8ccab-116">Verarbeitungs-und Speicherorte &#40;Partitions-Assistent&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-116">Processing and Storage Locations &#40;Partition Wizard&#41;</span></span>](processing-and-storage-locations-partition-wizard.md)  
  
-   [<span data-ttu-id="8ccab-117">Assistenten &#40;Partitions-Assistent wird abgeschlossen&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-117">Completing the Wizard &#40;Partition Wizard&#41;</span></span>](completing-the-wizard-partition-wizard.md)  
  
-   [<span data-ttu-id="8ccab-118">Dialog Feld "Remote Ordner suchen" &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-118">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ccab-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ccab-119">See Also</span></span>  
 [<span data-ttu-id="8ccab-120">Partitionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="8ccab-120">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
