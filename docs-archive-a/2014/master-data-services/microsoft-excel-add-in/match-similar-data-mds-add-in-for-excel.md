---
title: Abgleichen ähnlicher Daten (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699879"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="e0d9b-102">Abgleichen ähnlicher Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="e0d9b-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="e0d9b-103">Verwenden Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]die Data Quality Services-Funktion (DQS), um in den Daten nach Ähnlichkeiten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="e0d9b-104">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="e0d9b-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="e0d9b-105">Verwenden Sie die standardmäßige Data Quality Services-Wissensdatenbank, oder</span><span class="sxs-lookup"><span data-stu-id="e0d9b-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="e0d9b-106">Erstellen Sie eine eigene benutzerdefinierte DQS-Wissensdatenbank und Abgleichrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="e0d9b-107">Weitere Informationen finden Sie unter [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0d9b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e0d9b-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="e0d9b-109">Sie müssen über ein Arbeitsblatt mit von MDS verwalteten Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="e0d9b-110">Weitere Informationen finden Sie unter [Laden von Daten aus MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e0d9b-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-111">Optional.</span></span> <span data-ttu-id="e0d9b-112">Sie können andere Daten vor dem Überprüfen auf Ähnlichkeiten mit den von MDS verwalteten Daten kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="e0d9b-113">Weitere Informationen finden Sie unter [Kombinieren von Daten &#40;MDS-Add-In für Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="e0d9b-114">So suchen Sie mithilfe der Standard-Wissensdatenbank nach Ähnlichkeiten</span><span class="sxs-lookup"><span data-stu-id="e0d9b-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="e0d9b-115">Klicken Sie im Arbeitsblatt mit den von MDS verwalteten Daten in der Gruppe **Data Quality** auf **Daten abgleichen**.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="e0d9b-116">Wählen Sie im Dialogfeld **Daten abgleichen** in der Liste **DQS-Wissensdatenbank** die Option **DQS-Daten (Standard)** aus.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="e0d9b-117">Für jede Spalte, die abzugleichende Daten enthält, fügen Sie eine Zeile im Dialogfeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="e0d9b-118">Informationen zu den Feldern in diesem Dialogfeld finden Sie unter [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="e0d9b-119">Klicken Sie auf **OK**, wenn die Summe aller Gewichtungswerte 100 Prozent beträgt.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="e0d9b-120">So suchen Sie mithilfe einer benutzerdefinierten Wissensdatenbank nach Ähnlichkeiten</span><span class="sxs-lookup"><span data-stu-id="e0d9b-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="e0d9b-121">Klicken Sie im Arbeitsblatt mit den von MDS verwalteten Daten in der Gruppe **Data Quality** auf **Daten abgleichen**.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="e0d9b-122">Wählen Sie in der Liste **DQS-Wissensdatenbank** den Namen der benutzerdefinierten Wissensdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="e0d9b-123">Wählen Sie für jede Spalte im Arbeitsblatt eine DQS-Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="e0d9b-124">Klicken Sie auf **OK**, nachdem alle DQS-Domänen Spalten im Arbeitsblatt zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e0d9b-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e0d9b-125">Next Steps</span></span>  
  
-   <span data-ttu-id="e0d9b-126">Zeigen Sie weitere Informationen an, um zu ermitteln, welche Daten ähnlich sind.</span><span class="sxs-lookup"><span data-stu-id="e0d9b-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="e0d9b-127">Weitere Informationen finden Sie unter [Spalten für Data Quality-Abgleich &#40;MDS-Add-In für Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e0d9b-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d9b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0d9b-128">See Also</span></span>  
 <span data-ttu-id="e0d9b-129">[Data Quality-Abgleich im MDS-Add-in für Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e0d9b-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="e0d9b-130">Datenabgleich</span><span class="sxs-lookup"><span data-stu-id="e0d9b-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
