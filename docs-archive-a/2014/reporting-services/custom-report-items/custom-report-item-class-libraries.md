---
title: Klassenbibliotheken für ein benutzerdefiniertes Berichtselement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608406"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="dda05-102">Klassenbibliotheken für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="dda05-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="dda05-103">Benutzerdefinierte Berichtselemente verwenden Klassen aus dem `Microsoft.ReportDesigner`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="dda05-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="dda05-104">Die Klassen, die zum Implementieren eines benutzerdefinierten Berichtselements verwendet werden, können in zwei Hauptkategorien gruppiert werden: eindeutige Klassen zur Unterstützung der Infrastruktur eines benutzerdefinierten Berichtselements und verwaltete Wrapperklassen, die die Funktionalität von relevanten RDL-Elementen (Report Definition Language) kapseln.</span><span class="sxs-lookup"><span data-stu-id="dda05-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="dda05-105">Ein Codebeispiel für die Verwendung dieser Klassen finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="dda05-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="dda05-106">Infrastrukturklassen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="dda05-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="dda05-107">Die folgenden Klassen werden zum Implementieren eines benutzerdefinierten Berichtselements verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda05-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dda05-108">Die nachfolgenden Tabellen stellen keine vollständige Liste dar. Sie enthalten nur die am häufigsten verwendeten Eigenschaften und Methoden für jede Klasse.</span><span class="sxs-lookup"><span data-stu-id="dda05-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="dda05-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="dda05-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="dda05-110">Dies ist die Hauptklasse eines benutzerdefinierten Berichtselements.</span><span class="sxs-lookup"><span data-stu-id="dda05-110">This is the main custom report item class.</span></span> <span data-ttu-id="dda05-111">Die Hauptklasse der Implementierung eines benutzerdefinierten Berichtselements muss von dieser Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="dda05-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="dda05-112">Öffentliche Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dda05-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="dda05-113">Der Name des benutzerdefinierten Berichtselements.</span><span class="sxs-lookup"><span data-stu-id="dda05-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="dda05-114">Der Typ des benutzerdefinierten Berichtselements.</span><span class="sxs-lookup"><span data-stu-id="dda05-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="dda05-115">Ein <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>-Objekt, das die während der Entwurfszeit angegebenen Dateneigenschaften für ein benutzerdefiniertes Berichtselement kapselt.</span><span class="sxs-lookup"><span data-stu-id="dda05-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="dda05-116">Eine Auflistung benutzerdefinierter Eigenschaften für das benutzerdefinierte Berichtselement.</span><span class="sxs-lookup"><span data-stu-id="dda05-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="dda05-117">Die Höhe der Steuerung für ein benutzerdefiniertes Berichtselement.</span><span class="sxs-lookup"><span data-stu-id="dda05-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="dda05-118">Die Breite der Steuerung für ein benutzerdefiniertes Berichtselement.</span><span class="sxs-lookup"><span data-stu-id="dda05-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="dda05-119">Ein Container für die Eigenschaften auf Berichtsebene, z. B. die Liste der Datasets in dem Bericht.</span><span class="sxs-lookup"><span data-stu-id="dda05-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="dda05-120">Das alternative Berichtselementobjekt, das verwendet werden muss, wenn die Laufzeitsteuerung für das benutzerdefinierte Berichtselement nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="dda05-121">Die Stileigenschaften für das benutzerdefinierte Berichtselement.</span><span class="sxs-lookup"><span data-stu-id="dda05-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="dda05-122">Ein Gestaltungsfenster für die interaktive Bearbeitung der Steuerung.</span><span class="sxs-lookup"><span data-stu-id="dda05-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="dda05-123">Die `ISite` der Komponente.</span><span class="sxs-lookup"><span data-stu-id="dda05-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="dda05-124">Ein Array von benutzerdefinierten Verben für das Kontextmenü der Steuerung.</span><span class="sxs-lookup"><span data-stu-id="dda05-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-125">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="dda05-126">Aktiviert die interaktive Bearbeitung der Steuerung.</span><span class="sxs-lookup"><span data-stu-id="dda05-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="dda05-127">Wird als Reaktion auf das Doppelklicken oder Drücken der EINGABETASTE auf der Steuerung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dda05-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="dda05-128">Deaktiviert die interaktive Bearbeitung der Steuerung.</span><span class="sxs-lookup"><span data-stu-id="dda05-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="dda05-129">Gibt ein Objekt zurück, das einen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="dda05-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="dda05-130">Wird aufgerufen, wenn ein neues benutzerdefiniertes Berichtselement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="dda05-131">Zeichnet die gesamte Oberfläche der Steuerung neu.</span><span class="sxs-lookup"><span data-stu-id="dda05-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="dda05-132">Wird aufgerufen, wenn ein Objekt auf die Steuerung gezogen wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="dda05-133">Wird als Reaktion auf das `Paint`-Ereignis aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dda05-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="dda05-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="dda05-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="dda05-135">Dieses Attribut wird zur Identifizierung des Typs des benutzerdefinierten Berichtselements verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda05-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="dda05-136">Der Name muss dem Wert des <>- `Name` Attributs des- `ReportItem` Elements in der Berichts-Designer Konfigurationsdatei entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dda05-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-137">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="dda05-138">Erstellt das CustomReportItemAttribute-Objekt.</span><span class="sxs-lookup"><span data-stu-id="dda05-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="dda05-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="dda05-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="dda05-140">Dieses Attribut wird zum Festlegen des Anzeigenamens für den Designer des benutzerdefinierten Berichtselements verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda05-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-141">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="dda05-142">Erstellt das LocalizedNameAttribute-Objekt.</span><span class="sxs-lookup"><span data-stu-id="dda05-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="dda05-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="dda05-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="dda05-144">Die `Adornment`-Klasse wird von der Entwurfszeitkomponente eines benutzerdefinierten Berichtselements verwendet, um Bereiche außerhalb des Hauptrechtecks der Entwurfsoberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dda05-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="dda05-145">Diese Bereiche behandeln Benutzeroberflächenereignisse wie Mausklicks und Drag und Drop-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="dda05-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-146">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="dda05-147">Wird aufgerufen, wenn `Adornment` aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="dda05-148">Wird aufgerufen, wenn `Adornment` deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="dda05-149">Wird als Reaktion auf das `Paint`-Ereignis aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dda05-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="dda05-150">Wird aufgerufen, wenn ein Objekt in `Adornment` gezogen wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="dda05-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="dda05-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="dda05-152">Diese Klasse wird zum Bereitstellen einer Auflistung von Anzeigediensten verwendet, die vom benutzerdefinierten Berichtselement zum Unterstützen von `Adornment`-Objekten für die Entwurfszeitkomponente eines benutzerdefinierten Berichtselements genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="dda05-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="dda05-153">Öffentliche Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dda05-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="dda05-154">Die Begrenzungen des Gestaltungsfensters.</span><span class="sxs-lookup"><span data-stu-id="dda05-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="dda05-155">Der Bereich des Gestaltungsfensters.</span><span class="sxs-lookup"><span data-stu-id="dda05-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="dda05-156">Ein Grafikontext für das Gestaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="dda05-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-157">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="dda05-158">Gibt die Begrenzungen der Komponente zurück, die in Designerrahmenkoordinaten umgewandelt wurden.</span><span class="sxs-lookup"><span data-stu-id="dda05-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="dda05-159">Führt dazu, dass das Gestaltungsfenster ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="dda05-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="dda05-160">Gibt einen Punkt in Bildschirmkoordinaten zurück, der in Gestaltungsfensterkoordinaten umgewandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="dda05-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="dda05-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="dda05-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="dda05-162">Diese Klasse kann von der Entwurfszeitsteuerung eines benutzerdefinierten Berichtselements verwendet werden, um den Ausdrucks-Editor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="dda05-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="dda05-163">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="dda05-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="dda05-164">Ruft den mit dem angegebenen Objektwert initialisierten Ausdrucks-Editor auf.</span><span class="sxs-lookup"><span data-stu-id="dda05-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="dda05-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="dda05-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="dda05-166">Diese Klasse ist eine Auflistung von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Feldern und wird zum Unterstützen von Drag und Drop-Vorgängen in der Entwurfsumgebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda05-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="dda05-167">Erbt von `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="dda05-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="dda05-168">Öffentliche Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dda05-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="dda05-169">Der Name des Datasets mit den Feldern, die abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="dda05-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="dda05-170">Die Auflistung von Feldern (`Microsoft.ReportDesigner.Field`), die abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dda05-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dda05-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dda05-171">See Also</span></span>  
 <span data-ttu-id="dda05-172">[Berichts Definitions Sprache &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dda05-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="dda05-173">[Erstellen einer Laufzeitkomponente für ein benutzerdefiniertes Berichts Element](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="dda05-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="dda05-174">Erstellen einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="dda05-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
