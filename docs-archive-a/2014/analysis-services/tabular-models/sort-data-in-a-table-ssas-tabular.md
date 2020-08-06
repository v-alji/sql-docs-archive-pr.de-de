---
title: Sortieren von Daten in einer Tabelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694718"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="81afd-102">Sortieren von Daten in einer Tabelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="81afd-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="81afd-103">Sie können Daten in einer oder mehreren Spalten nach Text (A bis Z oder Z bis A) und Zahlen (kleinsten zu größten oder größten zu kleinsten) sortieren.</span><span class="sxs-lookup"><span data-stu-id="81afd-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="81afd-104">So sortieren Sie die Daten in einer Tabelle anhand einer Textspalte</span><span class="sxs-lookup"><span data-stu-id="81afd-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="81afd-105">Wählen Sie im Modell-Designer eine Spalte mit alphanumerischen Daten oder einen Zellbereich in einer Spalte aus, oder stellen Sie sicher, dass sich die aktive Zelle in einer Tabellenspalte befindet, die alphanumerische Daten enthält. Klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="81afd-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="81afd-106">Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="81afd-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="81afd-107">Um in aufsteigender alphanumerischer Reihenfolge zu sortieren, klicken Sie auf **Von A bis Z sortieren**.</span><span class="sxs-lookup"><span data-stu-id="81afd-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="81afd-108">Um in absteigender alphanumerischer Reihenfolge zu sortieren, klicken Sie auf **Von Z bis A sortieren**.</span><span class="sxs-lookup"><span data-stu-id="81afd-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81afd-109">In einigen Fällen können vor Daten, die aus anderen Anwendungen importiert werden, Leerzeichen eingefügt sein.</span><span class="sxs-lookup"><span data-stu-id="81afd-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="81afd-110">Sie müssen diese Leerzeichen entfernen, um die Daten ordnungsgemäß sortieren zu können.</span><span class="sxs-lookup"><span data-stu-id="81afd-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="81afd-111">So sortieren Sie die Daten in einer Tabelle anhand einer numerischen Spalte</span><span class="sxs-lookup"><span data-stu-id="81afd-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="81afd-112">Wählen Sie im Modell-Designer eine Spalte mit alphanumerischen Daten oder einen Zellbereich in einer Spalte aus, oder stellen Sie sicher, dass sich die aktive Zelle in einer Tabellenspalte befindet, die alphanumerische Daten enthält. Klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="81afd-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="81afd-113">Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="81afd-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="81afd-114">Um von niedrigen Zahlen zu hohen Zahlen zu sortieren, klicken Sie auf **Nach Größe sortieren (aufsteigend)**.</span><span class="sxs-lookup"><span data-stu-id="81afd-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="81afd-115">Um von hohen Zahlen zu niedrigen Zahlen zu sortieren, klicken Sie auf **Nach Größe sortieren (absteigend).**</span><span class="sxs-lookup"><span data-stu-id="81afd-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81afd-116">Wenn die Ergebnisse nicht die erwarteten sind, enthält die Spalte möglicherweise als Text und nicht als Zahlen gespeicherte Zahlen.</span><span class="sxs-lookup"><span data-stu-id="81afd-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="81afd-117">Zum Beispiel werden aus einigen Abrechnungssystemen importierte negative Zahlen oder Zahlen, denen ein ' (Apostroph) vorangeht, als Text gespeichert.</span><span class="sxs-lookup"><span data-stu-id="81afd-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81afd-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81afd-118">See Also</span></span>  
 <span data-ttu-id="81afd-119">[Filtern und Sortieren von Daten &#40;tabellarischen SSAS-&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="81afd-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="81afd-120">[Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="81afd-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="81afd-121">Rollen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="81afd-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
