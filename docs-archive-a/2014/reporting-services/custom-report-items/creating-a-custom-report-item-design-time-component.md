---
title: Erstellen einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608408"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="c19f6-102">Erstellen einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="c19f6-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="c19f6-103">Die Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement ist eine Steuerung, die in der Berichts-Designer-Umgebung von Visual Studio verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c19f6-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="c19f6-104">Diese Komponente bietet eine aktivierte Entwurfsoberfläche, die Drag und Drop-Vorgänge, Integration in den Eigenschaftenbrowser von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] und die Möglichkeit zum Bereitstellen von Editoren für benutzerdefinierte Eigenschaften zulassen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="c19f6-105">Mit der Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement können Benutzer ein benutzerdefiniertes Berichtselement auf einem Bericht in der Entwurfsumgebung positionieren, benutzerdefinierte Dateneigenschaften auf dem benutzerdefinierten Berichtselement festlegen und das benutzerdefinierte Berichtselement anschließend als Teil des Berichtsprojekts speichern.</span><span class="sxs-lookup"><span data-stu-id="c19f6-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="c19f6-106">Die mit der Entwurfszeitkomponente der Entwicklungsumgebung festgelegten Eigenschaften werden von der Host-Entwurfsumgebung serialisiert und deserialisiert und dann als Elemente in der RDL-Datei (Report Definition Language, Berichtsdefinitionssprache) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c19f6-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="c19f6-107">Wenn der Bericht vom Berichtsprozessor ausgeführt wird, werden die mit der Entwurfszeitkomponente festgelegten Eigenschaften vom Berichtsprozessor an eine Laufzeitkomponente für ein benutzerdefiniertes Berichtselement übergeben, die das benutzerdefinierte Berichtselement rendert und wieder an den Berichtsprozessor zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c19f6-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c19f6-108">Die Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement wird als [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Komponente implementiert.</span><span class="sxs-lookup"><span data-stu-id="c19f6-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="c19f6-109">In diesem Dokument werden Implementierungsdetails beschrieben, die für die Entwurfszeitkomponente eines benutzerdefinierten Berichtselements spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c19f6-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="c19f6-110">Weitere Informationen zum Entwickeln von Komponenten mit [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] finden Sie in der MSDN Library unter [Komponenten in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576).</span><span class="sxs-lookup"><span data-stu-id="c19f6-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="c19f6-111">Ein Beispiel für ein vollständig implementiertes benutzerdefiniertes Berichtselement finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="c19f6-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="c19f6-112">Implementieren einer Entwurfszeitkomponente</span><span class="sxs-lookup"><span data-stu-id="c19f6-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="c19f6-113">Die Hauptklasse einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement wird von der `Microsoft.ReportDesigner.CustomReportItemDesigner`-Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="c19f6-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="c19f6-114">Zusätzlich zu den Standardattributen für eine [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Steuerung sollte die Komponentenklasse ein `CustomReportItem`-Attribut definieren.</span><span class="sxs-lookup"><span data-stu-id="c19f6-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="c19f6-115">Dieses Attribut muss dem in der Datei reportserver.config festgelegten Namen des benutzerdefinierten Berichtselements entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="c19f6-116">Eine Liste der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Attribute finden Sie unter "Attribute" in der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c19f6-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="c19f6-117">Im folgenden Codebeispiel wird gezeigt, wie Attribute auf eine Entwurfszeitsteuerung für ein benutzerdefiniertes Berichtselement angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="c19f6-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="c19f6-118">Initialisieren der Komponente</span><span class="sxs-lookup"><span data-stu-id="c19f6-118">Initializing the Component</span></span>  
 <span data-ttu-id="c19f6-119">Sie übergeben benutzerspezifische Eigenschaften für ein benutzerdefiniertes Berichtselement mit einer <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c19f6-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="c19f6-120">Die Implementierung der `CustomReportItemDesigner`-Klasse sollte die `InitializeNewComponent`-Methode überschreiben, um eine neue Instanz der <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>-Klasse Ihrer Komponente zu erstellen und sie auf die Standardwerte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="c19f6-121">Im folgenden Codebeispiel wird ein Beispiel dafür gezeigt, wie die Klasse einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement die `CustomReportItemDesigner.InitializeNewComponent`-Methode überschreibt, um die <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>-Klasse der Komponente zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="c19f6-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="c19f6-122">Ändern von Komponenteneigenschaften</span><span class="sxs-lookup"><span data-stu-id="c19f6-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="c19f6-123">Sie können `CustomData`-Eigenschaften auf verschiedene Arten in der Entwurfsumgebung ändern.</span><span class="sxs-lookup"><span data-stu-id="c19f6-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="c19f6-124">Mit dem [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Eigenschaftenbrowser können Sie jede Eigenschaft ändern, die von der Entwurfszeitkomponente verfügbar gemacht wurde und die mit dem <xref:System.ComponentModel.BrowsableAttribute>-Attribut gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="c19f6-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="c19f6-125">Außerdem können Sie Eigenschaften ändern, indem Sie Elemente auf die Entwurfsoberfläche des benutzerdefinierten Berichtselements ziehen oder mit der rechten Maustaste auf die Steuerung in der Entwurfsumgebung klicken und im Kontextmenü **Eigenschaften** auswählen, um ein benutzerdefiniertes Eigenschaftenfenster aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="c19f6-126">Im folgenden Codebeispiel wird eine `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData`-Eigenschaft gezeigt, auf die das <xref:System.ComponentModel.BrowsableAttribute>-Attribut angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="c19f6-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="c19f6-127">Sie können für Ihre Entwurfszeitkomponente ein Dialogfeld für benutzerdefinierte Eigenschaften bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="c19f6-128">Die Implementierung des Editors für benutzerdefinierte Eigenschaften sollte von der <xref:System.ComponentModel.ComponentEditor>-Klasse erben und eine Instanz eines Dialogfelds erstellen, die für die Bearbeitung der Eigenschaften verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c19f6-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="c19f6-129">Im folgenden Beispiel wird die Implementierung einer Klasse, die von <xref:System.ComponentModel.ComponentEditor> erbt, und ein Dialogfeld eines Editors für benutzerdefinierte Eigenschaften dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c19f6-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="c19f6-130">Das Dialogfeld des Editors für benutzerdefinierte Eigenschaften kann den Ausdrucks-Editor des Berichts-Designers aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="c19f6-131">Im folgenden Beispiel wird der Ausdrucks-Editor aufgerufen, wenn der Benutzer das erste Element im Kombinationsfeld auswählt:</span><span class="sxs-lookup"><span data-stu-id="c19f6-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="c19f6-132">Verwenden von Designerverben</span><span class="sxs-lookup"><span data-stu-id="c19f6-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="c19f6-133">Ein Designerverb ist ein mit einem Ereignishandler verknüpfter Menübefehl.</span><span class="sxs-lookup"><span data-stu-id="c19f6-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="c19f6-134">Sie können Designerverben hinzufügen, die im Kontextmenü einer Komponente angezeigt werden, wenn die Laufzeitsteuerung für ein benutzerdefiniertes Berichtselement in der Entwurfsumgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c19f6-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="c19f6-135">Mit der `Verbs`-Eigenschaft können Sie die Liste der verfügbaren Designerverben von der Laufzeitkomponente zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c19f6-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="c19f6-136">Im folgenden Codebeispiel wird gezeigt, wie ein Designerverb und ein Ereignishandler zu <xref:System.ComponentModel.Design.DesignerVerbCollection> hinzugefügt wird, sowie der Ereignishandlercode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c19f6-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="c19f6-137">Verwenden von Randsteuerelementen</span><span class="sxs-lookup"><span data-stu-id="c19f6-137">Using Adornments</span></span>  
 <span data-ttu-id="c19f6-138">Klassen für ein benutzerdefiniertes Berichtselement können auch eine `Microsoft.ReportDesigner.Design.Adornment`-Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="c19f6-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="c19f6-139">Ein Randsteuerelement ermöglicht es der Steuerung für ein benutzerdefiniertes Berichtselement, Bereiche außerhalb des Hauptrechtecks der Entwurfsoberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c19f6-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="c19f6-140">Diese Bereiche behandeln Benutzeroberflächenereignisse wie Mausklicks und Drag und Drop-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="c19f6-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="c19f6-141">`Adornment`Bei der im-Namespace definierten-Klasse [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` handelt es sich um eine Pass-Through-Implementierung der-Klasse, die <xref:System.Windows.Forms.Design.Behavior.Adorner> in Windows Forms gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="c19f6-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="c19f6-142">Eine vollständige Dokumentation zur-Klasse finden Sie unter Übersicht über den `Adorner` [Verhaltens Dienst](https://go.microsoft.com/fwlink/?LinkId=116673) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="c19f6-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="c19f6-143">Beispielcode, der eine- `Microsoft.ReportDesigner.Design.Adornment` Klasse implementiert, finden Sie unter [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="c19f6-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="c19f6-144">Weitere Informationen zum Programmieren und Verwenden von Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] finden Sie in diesen Themen in der MSDN Library:</span><span class="sxs-lookup"><span data-stu-id="c19f6-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="c19f6-145">Entwurfszeitattribute für Komponenten</span><span class="sxs-lookup"><span data-stu-id="c19f6-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="c19f6-146">Komponenten in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c19f6-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="c19f6-147">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="c19f6-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c19f6-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c19f6-148">See Also</span></span>  
 <span data-ttu-id="c19f6-149">[Architektur des benutzerdefinierten Berichts Elements](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c19f6-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="c19f6-150">[Erstellen einer Laufzeitkomponente für ein benutzerdefiniertes Berichts Element](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="c19f6-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="c19f6-151">[Klassenbibliotheken für benutzerdefinierte Berichts Elemente](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="c19f6-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="c19f6-152">Vorgehensweise: Bereitstellen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="c19f6-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
