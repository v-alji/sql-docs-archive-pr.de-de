---
title: Berechnungs Tools (Registerkarte ' KPIs ', Cube-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bb8470173b0a413795fb7b5e3213bb50aa8ee43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610281"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="db09d-102">Berechnungstools (Registerkarte 'KPIs', Cube-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="db09d-102">Calculation Tools (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="db09d-103">Mithilfe des Bereichs **Berechnungstools** auf der Registerkarte **KPIs** im Cube-Designer können Sie Metadaten, Funktionen und Vorlagen durchsuchen, die zum Verwenden in KPIs (Key Performance Indicators) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="db09d-103">Use the **Calculation Tools** pane on the **KPIs** tab in Cube Designer to explore metadata, functions, and templates available for use in Key Performance Indicators (KPIs).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-104">Der Bereich wird nur in der Formularansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db09d-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="db09d-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="db09d-105">Options</span></span>  
 <span data-ttu-id="db09d-106">**Metadaten**</span><span class="sxs-lookup"><span data-stu-id="db09d-106">**Metadata**</span></span>  
 <span data-ttu-id="db09d-107">Zeigt die Metadaten für den ausgewählten Cube an.</span><span class="sxs-lookup"><span data-stu-id="db09d-107">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="db09d-108">Ziehen Sie ein ausgewähltes Element in den Bereich des **KPI-Formular-Editors** , um die MDX-Syntax (Multidimensional Expressions) für dieses Element am ausgewählten Speicherort in dem Bereich einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="db09d-108">Drag a selected element to the **KPI Form Editor** pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="db09d-109">**Funktionen**</span><span class="sxs-lookup"><span data-stu-id="db09d-109">**Functions**</span></span>  
 <span data-ttu-id="db09d-110">Zeigt die verfügbaren Funktionen für Ausdrücke und Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="db09d-110">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="db09d-111">Ziehen Sie ein ausgewähltes Element in den Bereich des KPI-Formular-Editors \*\*\*\* , um die MDX-Syntax für dieses Element am ausgewählten Speicherort in dem Bereich einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="db09d-111">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-112">Im Projektmodus liest das Dialogfeld **Berechnungstools** Informationen für diese Option aus einer XML-Datei mit dem Namen "MDXFunctions.xml", die in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="db09d-112">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="db09d-113">Im Onlinemodus werden die Information für diese Optionen aus dem MDSCHEMA_FUNCTIONS-Schemarowset für die Instanz abgerufen.</span><span class="sxs-lookup"><span data-stu-id="db09d-113">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="db09d-114">**Vorlagen**</span><span class="sxs-lookup"><span data-stu-id="db09d-114">**Templates**</span></span>  
 <span data-ttu-id="db09d-115">Zeigt die vordefinierten Vorlagen an, die für KPIs verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="db09d-115">Displays the predefined templates available for KPIs.</span></span>  
  
 <span data-ttu-id="db09d-116">Ziehen Sie ein ausgewähltes Element in den Bereich des KPI-Formular-Editors \*\*\*\* , um die MDX-Syntax für dieses Element am ausgewählten Speicherort in dem Bereich einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="db09d-116">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="db09d-117">Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="db09d-117">Context Menu</span></span>  
 <span data-ttu-id="db09d-118">Wenn Sie mit der rechten Maustaste auf eines der im Bereich **Berechnungstools** angezeigten Elemente klicken, wird ein Kontextmenü angezeigt, das die folgenden Optionen enthält:</span><span class="sxs-lookup"><span data-stu-id="db09d-118">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="db09d-119">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="db09d-119">**Copy**</span></span>  
 <span data-ttu-id="db09d-120">Wählen Sie diese Option aus, um das in **Metadaten** oder **Funktionen** ausgewählte Element in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="db09d-120">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-121"> Diese Option wird nicht angezeigt, wenn **Vorlagen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="db09d-121">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-122"> Diese Option ist nicht verfügbar, wenn das ausgewählte Element nicht kopiert werden kann. Das gilt z. B. für den Ordner **Mengen** einer Dimension, die unter **Metadaten** angezeigt wird, oder für den Funktionsgruppenordner für eine Funktion, die unter **Funktionen**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="db09d-122">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="db09d-123">**Elemente filtern**</span><span class="sxs-lookup"><span data-stu-id="db09d-123">**Filter Members**</span></span>  
 <span data-ttu-id="db09d-124">Wählen Sie diese Option aus, um das Dialogfeld **Elemente filtern** anzuzeigen und die angezeigten Elemente nach dem ausgewählten Element in **Metadaten**zu filtern.</span><span class="sxs-lookup"><span data-stu-id="db09d-124">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="db09d-125">Weitere Informationen zum Dialogfeld **Elemente filtern** finden Sie unter [Dialogfeld „Elemente filtern“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="db09d-125">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-126"> Diese Option wird nur angezeigt, wenn **Metadaten** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="db09d-126">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-127"> Die Option ist nur verfügbar, wenn eine Ebene für ein Attribut in **Metadaten**ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="db09d-127">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="db09d-128">**Vorlage hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="db09d-128">**Add Template**</span></span>  
 <span data-ttu-id="db09d-129">Wählen Sie diese Option aus, um dem Cubeskript ein neues berechnetes Element, eine neue benannte Menge oder einen Skriptbefehl auf der Basis der ausgewählten Vorlage hinzuzufügen und den **KPI-Formular-Editor** in der Formularansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="db09d-129">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **KPI Form Editor** in form view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db09d-130"> Diese Option wird nur angezeigt, wenn **Metadaten** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="db09d-130">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db09d-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db09d-131">See Also</span></span>  
 <span data-ttu-id="db09d-132">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="db09d-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="db09d-133">[KPIs &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="db09d-133">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="db09d-134">[Symbolleiste &#40;Registerkarte ' KPIs ', Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="db09d-134">[Toolbar &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="db09d-135">[KPI-Planer &#40;Registerkarte KPIs, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="db09d-135">[KPI Organizer &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="db09d-136">[KPI-Formular-Editor &#40;Registerkarte KPIs, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="db09d-136">[KPI Form Editor &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="db09d-137">KPI-Browser &#40;Registerkarte KPIs, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="db09d-137">KPI Browser &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  
