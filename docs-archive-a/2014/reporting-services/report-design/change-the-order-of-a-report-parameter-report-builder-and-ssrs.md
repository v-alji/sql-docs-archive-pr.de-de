---
title: Ändern der Reihenfolge von Berichtsparametern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722518"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="13eeb-102">Ändern der Reihenfolge von Berichtsparametern (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="13eeb-102">Change the Order of a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="13eeb-103">Ändern Sie die Reihenfolge der Berichtsparameter, wenn ein abhängiger Parameter vor dem Parameter angeordnet ist, von dem er abhängt.</span><span class="sxs-lookup"><span data-stu-id="13eeb-103">Change the order of report parameters when you have a dependent parameter that is listed before the parameter it is dependent on.</span></span> <span data-ttu-id="13eeb-104">Die Reihenfolge der Parameter spielt eine wichtige Rolle, wenn Sie mit kaskadierenden Parametern arbeiten, oder wenn Sie möchten, dass der Standardwert für einen Parameter angezeigt wird, bevor die Benutzer Werte für andere Parameter auswählen.</span><span class="sxs-lookup"><span data-stu-id="13eeb-104">Parameter order is important when you have cascading parameters, or when you want to show users the default value for one parameter before they choose values for other parameters.</span></span> <span data-ttu-id="13eeb-105">Ein abhängiger Berichtsparameter enthält entweder in der Abfrage der Standardwerte oder in der Abfrage der gültigen Werte einen Verweis auf einen Abfrageparameter, der auf einen Berichtsparameter verweist, der in der Parameterliste im Berichtsdatenbereich nach ihm angeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="13eeb-105">A dependent report parameter contains a reference, in either its default values query or valid values query, to a query parameter that points to a report parameter that is after it in the parameter list in the Report Data pane.</span></span>  
  
 <span data-ttu-id="13eeb-106">Die Reihenfolge der Parameter auf der Symbolleiste des Berichts-Viewers hängt von der Reihenfolge der Parameter im Berichtsdatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="13eeb-106">The order that you see parameters display on the report viewer toolbar is determined by the order of the parameters in the Report Data pane.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a><span data-ttu-id="13eeb-107">So ändern Sie die Reihenfolge von Berichtsparametern</span><span class="sxs-lookup"><span data-stu-id="13eeb-107">To change the order of report parameters</span></span>  
  
1.  <span data-ttu-id="13eeb-108">Erweitern Sie im Berichtsdatenbereich den Knoten Parameter.</span><span class="sxs-lookup"><span data-stu-id="13eeb-108">In the Report Data pane, expand the Parameters node.</span></span>  
  
2.  <span data-ttu-id="13eeb-109">Klicken Sie auf einen Parameter, und verschieben Sie ihn mit den Pfeilschaltflächen im Berichtsdatenbereich in der Liste nach oben oder nach unten.</span><span class="sxs-lookup"><span data-stu-id="13eeb-109">Click a parameter and use the up and down arrow buttons on the Report Data pane toolbar to move the parameter higher or lower in the list.</span></span> <span data-ttu-id="13eeb-110">In der folgenden Grafik wird der Berichtsdatenbereich im Berichts-Generator dargestellt.</span><span class="sxs-lookup"><span data-stu-id="13eeb-110">The following image shows the Report Data pane in Report Builder.</span></span>  
  
     <span data-ttu-id="13eeb-111">![Berichtsdaten Bereich](../media/reportdatapane.png "Berichtsdatenbereich")</span><span class="sxs-lookup"><span data-stu-id="13eeb-111">![Report Data Pane](../media/reportdatapane.png "Report Data Pane")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13eeb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13eeb-112">See Also</span></span>  
 <span data-ttu-id="13eeb-113">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="13eeb-113">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="13eeb-114">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="13eeb-114">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="13eeb-115">[Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13eeb-115">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13eeb-116">[Tutorial: Hinzufügen eines Parameters zu einem Bericht &#40;Berichts-Generator&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="13eeb-116">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="13eeb-117">[Hinzufügen von datasetfiltern, Datenbereichs Filtern und Gruppen Filtern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="13eeb-117">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="13eeb-118">Verweise auf Parameters-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="13eeb-118">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
