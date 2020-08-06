---
title: Kombinieren von Daten (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698385"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="cb3ed-102">Kombinieren von Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="cb3ed-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="cb3ed-103">Kombinieren Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]Daten aus zwei Arbeitsblättern, wenn Sie Daten vor der Veröffentlichung vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="cb3ed-104">In diesem Verfahren kombinieren Sie Daten aus zwei Arbeitsblättern in einem Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="cb3ed-105">Anschließend können Sie weitere Vergleiche ausführen und bestimmen, welche Daten ggf. im MDS-Repository veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb3ed-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cb3ed-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="cb3ed-107">Sie müssen über ein Arbeitsblatt mit von MDS verwalteten Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="cb3ed-108">Weitere Informationen finden Sie unter [Laden von Daten aus MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cb3ed-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="cb3ed-109">Sie müssen über ein Arbeitsblatt verfügen, in dem Daten enthalten sind, die Sie mit von MDS verwalteten Daten kombinieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="cb3ed-110">Dieses Blatt muss über eine Kopfzeile verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="cb3ed-111">So kombinieren Sie nicht verwaltete Daten zu einem von MDS verwalteten Blatt</span><span class="sxs-lookup"><span data-stu-id="cb3ed-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="cb3ed-112">Klicken Sie auf dem Blatt, das die von MDS verwalteten Daten enthält, in der Gruppe **Veröffentlichen und Überprüfen** auf **Daten kombinieren**.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="cb3ed-113">Klicken Sie im Dialogfeld **Daten kombinieren** neben dem Textfeld **Mit MDS-Daten zu kombinierender Bereich** auf das Symbol.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="cb3ed-114">Das Dialogfeld wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="cb3ed-115">Klicken Sie auf das Blatt mit den Daten, die Sie kombinieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="cb3ed-116">Heben Sie alle Zellen im Blatt hervor, die Sie kombinieren möchten, einschließlich der Kopfzeile.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="cb3ed-117">Klicken Sie im Dialogfeld **Daten kombinieren** auf das Symbol.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="cb3ed-118">Das Dialogfeld wird erweitert.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="cb3ed-119">Wählen Sie unter **Entsprechende Spalte**eine Spalte für eine unter der MDS-Entität aufgeführte Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="cb3ed-120">Es sind nicht für alle MDS-Spalten entsprechende Spalten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="cb3ed-121">Klicken Sie auf **Kombinieren**.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-121">Click **Combine**.</span></span> <span data-ttu-id="cb3ed-122">Eine Spalte **QUELLE** wird angezeigt und gibt an, ob die Daten aus MDS oder einer externen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="cb3ed-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cb3ed-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cb3ed-123">Next Steps</span></span>  
  
-   <span data-ttu-id="cb3ed-124">Informationen zur Ermittlung von Ähnlichkeiten zwischen von MDS verwalteten Daten und externen Daten finden Sie unter [Abgleichen ähnlicher Daten (Master Data Services)](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="cb3ed-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3ed-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb3ed-125">See Also</span></span>  
 <span data-ttu-id="cb3ed-126">[Daten &#40;MDS-Add-in für Excel werden geladen&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="cb3ed-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="cb3ed-127">Data Quality-Abgleich im MDS-Add-In für Excel</span><span class="sxs-lookup"><span data-stu-id="cb3ed-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
