---
title: Spalten für Data Quality-Abgleich (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607864"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="ce3d0-102">Spalten für Data Quality-Abgleich (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="ce3d0-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="ce3d0-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Sie nach dem Abgleichen von Daten im Menüband in der Gruppe **Data Quality** auf **Details anzeigen** klicken, um Spalten mit übereinstimmenden Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="ce3d0-104">In der folgenden Tabelle sind die Spalten aufgeführt, die beim Abgleichen von Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="ce3d0-105">Name</span><span class="sxs-lookup"><span data-stu-id="ce3d0-105">Name</span></span>|<span data-ttu-id="ce3d0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce3d0-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ce3d0-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="ce3d0-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="ce3d0-108">Ein eindeutiger Bezeichner, der zum Gruppieren ähnlicher Datensätze verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="ce3d0-109">Alle Zeilen, die einander ähnlich sind, haben die gleiche **CLUSTER_ID**.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="ce3d0-110">Wenn für eine Zeile keine **CLUSTER_ID** angezeigt wird, wurden keine ähnlichen Datensätze gefunden.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="ce3d0-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="ce3d0-111">**RECORD_ID**</span></span>|<span data-ttu-id="ce3d0-112">Ein eindeutiger Bezeichner, der zum Identifizieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="ce3d0-113">Dies ist ein Wert, der zum Identifizieren eines Datensatzes verwendet wird und dem im MDS-Repository gespeicherten Codewert ähnelt.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="ce3d0-114">Er wird jeweils automatisch generiert, wenn ein Abgleich durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="ce3d0-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="ce3d0-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="ce3d0-116">Ein beliebiger Datensatz, mit dem andere Datensätze verglichen werden. Er verfügt nicht über einen Ergebniswert.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="ce3d0-117">**Endergebnis**</span><span class="sxs-lookup"><span data-stu-id="ce3d0-117">**SCORE**</span></span>|<span data-ttu-id="ce3d0-118">Gibt an, welchen Grad an Ähnlichkeit die Datensätze in der Gruppe mit dem Pivotdatensatz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="ce3d0-119">Dieses Ergebnis wird mithilfe von DQS bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-119">This score is determined by DQS.</span></span> <span data-ttu-id="ce3d0-120">Wenn kein Ergebnis angezeigt wird, ist der Datensatz der Pivotdatensatz für andere Datensätze, oder es wurden keine Übereinstimmungen gefunden.</span><span class="sxs-lookup"><span data-stu-id="ce3d0-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce3d0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce3d0-121">See Also</span></span>  
 <span data-ttu-id="ce3d0-122">[Data Quality-Abgleich im MDS-Add-in für Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="ce3d0-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="ce3d0-123">[Ähnliche Daten &#40;MDS-Add-in für Excel vergleichen&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="ce3d0-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="ce3d0-124">Datenabgleich</span><span class="sxs-lookup"><span data-stu-id="ce3d0-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
