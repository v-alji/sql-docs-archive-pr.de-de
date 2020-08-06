---
title: Berichts Parameter Konzept (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697530"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="741b0-102">Berichtsparameter-Konzept (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="741b0-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="741b0-103">Sie können einem Bericht Parameter hinzufügen, um verknüpfte Berichte zu verknüpfen, die Berichtsdarstellung zu steuern, Berichtsdaten zu filtern oder den Bereich eines Berichts auf bestimmte Benutzer oder Orte einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="741b0-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="741b0-104">Berichtsparameter werden wie folgt erstellt:</span><span class="sxs-lookup"><span data-stu-id="741b0-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="741b0-105">Automatisch, wenn Sie eine Datasetabfrage definieren, die Abfragevariablen enthält.</span><span class="sxs-lookup"><span data-stu-id="741b0-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="741b0-106">Für jede Abfragevariable werden ein entsprechender Dataset-Abfrageparameter und ein Berichtsparameter mit den gleichen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="741b0-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="741b0-107">Ein Abfrageparameter kann ein Verweis auf eine Abfragevariable oder einen Eingabeparameter für eine gespeicherte Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="741b0-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="741b0-108">Automatisch, wenn Sie einem freigegebenen Dataset einen Verweis hinzufügen, der Abfrageparameter enthält.</span><span class="sxs-lookup"><span data-stu-id="741b0-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="741b0-109">Manuell, wenn Sie im Bereich "Berichtsdaten" Berichtsparameter erstellen.</span><span class="sxs-lookup"><span data-stu-id="741b0-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="741b0-110">Parameter gehören zu den integrierten Auflistungen, die Sie in einen Ausdruck in einem Bericht einschließen können.</span><span class="sxs-lookup"><span data-stu-id="741b0-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="741b0-111">Da Ausdrücke verwendet werden, um Werte in der gesamten Berichtsdefinition zu definieren, können Sie Parameter verwenden, um die Berichtsdarstellung zu steuern oder um Werte an verwandte Unterberichte oder Berichte zu übergeben, die ebenfalls Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="741b0-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="741b0-112">Weitere Informationen finden Sie unter [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md)" basiert.</span><span class="sxs-lookup"><span data-stu-id="741b0-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="741b0-113">Parameter werden häufig verwendet, um Berichtsdaten zu filtern, bevor und nachdem die Daten an den Bericht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="741b0-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="741b0-114">Weitere Informationen finden Sie unter [Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="741b0-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="741b0-115">Wenn Sie einen Bericht entwerfen, werden Berichtsparameter in der Berichtsdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="741b0-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="741b0-116">Wenn Sie einen Bericht veröffentlichen, werden Berichtsparameter getrennt von der Berichtsdefinition gespeichert und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="741b0-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="741b0-117">Nachdem Sie den Bericht auf dem Berichtsserver gespeichert haben, können Sie wie folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="741b0-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="741b0-118">Ändern Sie Berichtsparameterwerte direkt auf dem Berichtsserver, unabhängig von der Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="741b0-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="741b0-119">Erstellen Sie mehrere verknüpfte Berichte. Jeder verknüpfte Bericht ist ein Link zur Berichtsdefinition mit einem separaten Satz von Parameterwerten, die auf dem Berichtsserver unabhängig verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="741b0-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="741b0-120">Wenn Sie vorhaben, Berichtsmomentaufnahmen, Verläufe oder Abonnements für einen veröffentlichten Bericht zu erstellen, müssen Sie die Auswirkungen von Berichtsparametern auf die Entwurfsanforderungen für den Bericht kennen.</span><span class="sxs-lookup"><span data-stu-id="741b0-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741b0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="741b0-121">See Also</span></span>  
 <span data-ttu-id="741b0-122">[Konzepte der Berichterstellung &#40;Berichts-Generator und SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="741b0-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="741b0-123">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="741b0-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="741b0-124">Tutorial: Add a Parameter to Your Report (Report Builder) (Tutorial: Hinzufügen eines Parameters zu einem Bericht (Berichts-Generator))</span><span class="sxs-lookup"><span data-stu-id="741b0-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
