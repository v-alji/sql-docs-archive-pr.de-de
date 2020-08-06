---
title: Dataseteigenschaften (Dialogfeld), Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726570"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="2613a-102">Dataseteigenschaften (Dialogfeld), Parameter</span><span class="sxs-lookup"><span data-stu-id="2613a-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="2613a-103">Wählen Sie im Dialogfeld **Dataseteigenschaften** die Option **Parameter** aus, um Abfrageparameter, einschließlich Abfrageparameter, die einen Link zu Berichtsparametern herstellen, hinzuzufügen, zu ändern und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2613a-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="2613a-104">Bei jedem Ändern der Abfrage auf der Abfrageregisterkarte wird der Abfragebefehl analysiert.</span><span class="sxs-lookup"><span data-stu-id="2613a-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="2613a-105">Für jeden Abfrageparameter, der identifiziert wird, wird ein Berichtsparameter mit einem identischen Namen erstellt, bei dem Groß-/Kleinschreibung beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="2613a-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="2613a-106">Standardmäßig wird der Abfrageparameter der Abfrageparameterliste automatisch hinzugefügt und mit dem entsprechenden Berichtsparameter verknüpft.</span><span class="sxs-lookup"><span data-stu-id="2613a-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="2613a-107">Wenn die Standardwerte eines Berichtsparameters von einem anderen Berichtsparameter, der mit einem Abfrageparameter verknüpft ist, abhängig sind, ist die Reihenfolge der Berichtsparameter (wie sie im Dialogfeld **Berichtsparametereigenschaften** angezeigt wird) entscheidend.</span><span class="sxs-lookup"><span data-stu-id="2613a-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="2613a-108">Berichtsparameter weiter unten in der Liste können auf Berichtsparameter weiter oben in der Liste verweisen.</span><span class="sxs-lookup"><span data-stu-id="2613a-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="2613a-109">Weitere Informationen zu Berichtsparametern finden Sie unter [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="2613a-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2613a-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2613a-110">Options</span></span>  
 <span data-ttu-id="2613a-111">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="2613a-111">**Add**</span></span>  
 <span data-ttu-id="2613a-112">Fügt der Liste einen neuen Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="2613a-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="2613a-113">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="2613a-113">**Delete**</span></span>  
 <span data-ttu-id="2613a-114">Entfernt den ausgewählten Parameter aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="2613a-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="2613a-115">**Parametername**</span><span class="sxs-lookup"><span data-stu-id="2613a-115">**Parameter name**</span></span>  
 <span data-ttu-id="2613a-116">Geben Sie auf der Registerkarte **Abfrage** des Dialogfelds **Dataseteigenschaften** den Namen eines Abfrageparameters ein, den Sie zum Dataset hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="2613a-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="2613a-117">**Parameterwert**</span><span class="sxs-lookup"><span data-stu-id="2613a-117">**Parameter value**</span></span>  
 <span data-ttu-id="2613a-118">Geben Sie einen Wert für den Abfrageparameter ein.</span><span class="sxs-lookup"><span data-stu-id="2613a-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="2613a-119">Dies kann ein statischer Wert sein oder ein Ausdruck, der sich auf ein Objekt innerhalb des Berichts bezieht. Der Ausdruck darf sich jedoch nicht auf Berichtselemente oder Felder beziehen.</span><span class="sxs-lookup"><span data-stu-id="2613a-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="2613a-120">Standardmäßig enthält **Wert** einen Ausdruck, der auf einen Berichtsparameter verweist.</span><span class="sxs-lookup"><span data-stu-id="2613a-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="2613a-121">**Pfeil nach oben**</span><span class="sxs-lookup"><span data-stu-id="2613a-121">**Up arrow**</span></span>  
 <span data-ttu-id="2613a-122">Verschiebt den ausgewählten Parameter in der Liste nach oben.</span><span class="sxs-lookup"><span data-stu-id="2613a-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="2613a-123">**Pfeil nach unten**</span><span class="sxs-lookup"><span data-stu-id="2613a-123">**Down arrow**</span></span>  
 <span data-ttu-id="2613a-124">Verschiebt den ausgewählten Parameter in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="2613a-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2613a-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2613a-125">See Also</span></span>  
 <span data-ttu-id="2613a-126">[Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2613a-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="2613a-127">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2613a-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="2613a-128">Ändern der Reihenfolge von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2613a-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
