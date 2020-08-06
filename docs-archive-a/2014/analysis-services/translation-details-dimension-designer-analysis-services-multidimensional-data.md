---
title: Übersetzungs Details (Registerkarte "Übersetzungen", Dimensions-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723074"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="ce1e1-102">Übersetzungsdetails (Registerkarte Übersetzungen, Dimensions-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="ce1e1-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ce1e1-103">Mithilfe des Bereichs **Übersetzungsdetails** auf der Registerkarte **Übersetzungen** im Dimensions-Designer können Sie Übersetzungen für die aktuell ausgewählte Dimension definieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="ce1e1-104">**So zeigen Sie den Bereich Übersetzungsdetails an**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="ce1e1-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt, und öffnen Sie dann die gewünschte Dimension.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="ce1e1-106">Klicken Sie auf die Registerkarte **Übersetzungen** .</span><span class="sxs-lookup"><span data-stu-id="ce1e1-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ce1e1-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ce1e1-107">Options</span></span>  
 <span data-ttu-id="ce1e1-108">**Standardsprache**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-108">**Default Language**</span></span>  
 <span data-ttu-id="ce1e1-109">Legt die Namen der Dimensionsobjekte in der Standardsprache fest.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="ce1e1-110">**Objekttyp**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-110">**Object Type**</span></span>  
 <span data-ttu-id="ce1e1-111">Zeigt die Eigenschaft an, die übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-111">Displays the property that will be translated.</span></span> <span data-ttu-id="ce1e1-112">Es können nur Objekte und Eigenschaften übersetzt werden, für die Werte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="ce1e1-113">Die folgenden Eigenschaften können übersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="ce1e1-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="ce1e1-114">Dimension</span><span class="sxs-lookup"><span data-stu-id="ce1e1-114">Dimension</span></span>  
  
     <span data-ttu-id="ce1e1-115">`Caption`- und `AttributeAllMember`-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce1e1-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="ce1e1-116">attribute</span><span class="sxs-lookup"><span data-stu-id="ce1e1-116">Attribute</span></span>  
  
     <span data-ttu-id="ce1e1-117">`Caption`- `AttributeHierarchyDisplayFolder`-Eigenschaft und `NamingTemplate`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ce1e1-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce1e1-118">Die `NamingTemplate`-Eigenschaft ist nur für übergeordnete Attribute verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="ce1e1-119">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="ce1e1-119">Hierarchy</span></span>  
  
     <span data-ttu-id="ce1e1-120">`Caption`- und `AllMemberName`-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce1e1-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="ce1e1-121">Ebene</span><span class="sxs-lookup"><span data-stu-id="ce1e1-121">Level</span></span>  
  
     <span data-ttu-id="ce1e1-122">`Caption`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ce1e1-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="ce1e1-123">Geben Sie den Eigenschaftswert des Dimensionsobjekts in der ausgewählten Sprache an, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="ce1e1-124">In Abhängigkeit von der bearbeiteten Eigenschaft werden zusätzliche Dialogfelder geöffnet, wenn Sie auf die Schaltfläche mit den Auslassungspunkten (**...**) klicken:</span><span class="sxs-lookup"><span data-stu-id="ce1e1-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="ce1e1-125">`NamingTemplate`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ce1e1-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="ce1e1-126">Zeigt das [Dialogfeld „Vorlage zur Ebenenbenennung“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md) an.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="ce1e1-127">`Caption`-Eigenschaft (für Attribute)</span><span class="sxs-lookup"><span data-stu-id="ce1e1-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="ce1e1-128">Zeigt das [Dialogfeld „Attributdatenübersetzung“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ce1e1-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="ce1e1-129">Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="ce1e1-129">Shortcut Menu</span></span>  
 <span data-ttu-id="ce1e1-130">Die folgenden Optionen sind im Kontextmenü verfügbar, das angezeigt wird, wenn Sie im Bereich **Übersetzungsdetails** mit der rechten Maustaste auf eine Übersetzung klicken:</span><span class="sxs-lookup"><span data-stu-id="ce1e1-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="ce1e1-131">**Neue Übersetzung**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-131">**New Translation**</span></span>  
 <span data-ttu-id="ce1e1-132">Wählen Sie diese Option aus, um das Dialogfeld **Sprache auswählen** anzuzeigen und um eine neue Übersetzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="ce1e1-133">Die Übersetzung wird im Raster **Übersetzungsdetails** als neue Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="ce1e1-134">**Übersetzung löschen**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-134">**Delete Translation**</span></span>  
 <span data-ttu-id="ce1e1-135">Wählen Sie diese Option aus, um die ausgewählte Übersetzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1e1-136">Diese Option ist nur aktiviert, wenn Sie mit der rechten Maustaste auf eine Zelle geklickt haben, um die Übersetzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="ce1e1-137">**Neue Beschriftungs Spalte**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-137">**New Caption Column**</span></span>  
 <span data-ttu-id="ce1e1-138">Wählen Sie diese Option aus, um das Dialogfeld **Attributdatenübersetzung** anzuzeigen und um eine neue Beschriftungsspalte zu definieren, wenn Sie im Raster **Übersetzungsdetails** ein Attribut ändern.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="ce1e1-139">Zum Aktivieren dieser Option müssen Sie im Raster der Übersetzungsdetails \*\*\*\* eine Zelle in der Übersetzungsspalte eines Attributs auswählen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1e1-140">Diese Option ist nur aktiviert, wenn Sie mit der rechten Maustaste auf eine Zelle geklickt haben, um die Übersetzungsspalte eines Attributs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="ce1e1-141">**Beschriftungsspalte bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="ce1e1-142">Wählen Sie diese Option aus, um das Dialogfeld **Attributdatenübersetzung** anzuzeigen und um eine vorhandene Beschriftungsspalte zu bearbeiten, wenn Sie im Raster **Übersetzungsdetails** ein Attribut ändern.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1e1-143"> Die Option ist nur aktiviert, wenn im Raster der Übersetzungsdetails eine Zelle in einer Übersetzungsspalte ausgewählt werden muss, die eine Beschriftungsspalte für ein\ \*\*\** Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="ce1e1-144">**Beschriftungsspalte löschen**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="ce1e1-145">Wählen Sie diese Option aus, um im Raster **Übersetzungsdetails** die Beschriftungsspalte für das ausgewählte Attribut zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1e1-146">Diese Option ist nur aktiviert, wenn Sie in einer Übersetzungsspalte, die eine Beschriftungsspalte für ein Attribut enthält, mit der rechten Maustaste auf eine Zelle geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="ce1e1-147">**Alle Attribute anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ce1e1-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="ce1e1-148">Wählen Sie diese Option aus, um alle für die ausgewählte Dimension definierten Attribute anzuzeigen, einschließlich der Attribute, deren Attributhierarchien deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="ce1e1-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce1e1-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce1e1-149">See Also</span></span>  
 [<span data-ttu-id="ce1e1-150">Übersetzungen &#40;Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="ce1e1-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
