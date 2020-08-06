---
title: Entwickeln einer Benutzeroberfläche für eine Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697025"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="e5dab-102">Entwickeln einer Benutzeroberfläche für eine Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="e5dab-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="e5dab-103">Komponentenentwickler können für eine Komponente eine benutzerdefinierte Benutzeroberfläche bereitstellen, die in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] angezeigt wird, wenn die Komponente bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="e5dab-104">Bei der Implementierung einer benutzerdefinierten Benutzeroberfläche werden Ihnen Benachrichtigungen bereitgestellt, wenn die Komponente zur Datenflusstask hinzugefügt oder aus diesem gelöscht wird und wenn für die Komponente Hilfe angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="e5dab-105">Wenn Sie keine individuelle Benutzeroberfläche für Ihre Komponente bereitstellen, können die Benutzer die Komponente und ihre benutzerdefinieren Eigenschaften auch mithilfe des erweiterten Editors konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e5dab-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="e5dab-106">Sie können sicherstellen, dass der erweiterte Editor es Benutzern ermöglicht, mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A>- und <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>-Eigenschaften von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> benutzerdefinierte Eigenschaftswerte ggf. entsprechend zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e5dab-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="e5dab-107">Weitere Informationen finden Sie in [Entwurfszeitmethoden einer Datenflusskomponente](design-time-methods-of-a-data-flow-component.md) unter „Erstellen von benutzerdefinierten Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="e5dab-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="e5dab-108">Festlegen der UITypeName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e5dab-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="e5dab-109">Für die Bereitstellung einer benutzerdefinierten Benutzeroberfläche muss der Entwickler die <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>-Eigenschaft von <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> auf den Namen einer Klasse festlegen, die die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="e5dab-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="e5dab-110">Bei Festlegung dieser Eigenschaft durch die Komponente wird die benutzerdefinierte Oberfläche von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] geladen und aufgerufen, wenn die Komponente im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="e5dab-111">Die <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>-Eigenschaft ist eine durch Trennzeichen getrennte Zeichenfolge, die den vollqualifizierten Namen des Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="e5dab-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="e5dab-112">Die folgende Liste zeigt die Elemente, die den Typ identifizieren, in Reihenfolge, an:</span><span class="sxs-lookup"><span data-stu-id="e5dab-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="e5dab-113">Name des Typs</span><span class="sxs-lookup"><span data-stu-id="e5dab-113">Type name</span></span>

-   <span data-ttu-id="e5dab-114">Assemblyname</span><span class="sxs-lookup"><span data-stu-id="e5dab-114">Assembly name</span></span>

-   <span data-ttu-id="e5dab-115">Dateiversion</span><span class="sxs-lookup"><span data-stu-id="e5dab-115">File version</span></span>

-   <span data-ttu-id="e5dab-116">Kultur</span><span class="sxs-lookup"><span data-stu-id="e5dab-116">Culture</span></span>

-   <span data-ttu-id="e5dab-117">Öffentliches Schlüsseltoken</span><span class="sxs-lookup"><span data-stu-id="e5dab-117">Public key token</span></span>

 <span data-ttu-id="e5dab-118">Im folgenden Codebeispiel wird eine Klasse veranschaulicht, die von der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse abgeleitet wird und die die <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>-Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="e5dab-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="e5dab-119">Implementieren der IDtsComponentUI-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5dab-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="e5dab-120">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>-Schnittstelle enthält Methoden, die der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer aufruft, wenn eine Komponente hinzugefügt, gelöscht oder bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="e5dab-121">Komponentenentwickler können zur Interaktion mit den Benutzern der Komponente Code in der Implementierung dieser Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="e5dab-122">Diese Klasse wird in der Regel in einer Assembly implementiert, die von der Komponente selbst getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="e5dab-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="e5dab-123">Die Verwendung einer separaten Assembly ist zwar nicht erforderlich, doch dadurch kann der Entwickler die Komponente und die Benutzeroberfläche unabhängig voneinander erstellen und bereitstellen, und der Speicherbedarf der Komponente wird gering gehalten.</span><span class="sxs-lookup"><span data-stu-id="e5dab-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="e5dab-124">Durch die Implementierung einer benutzerdefinierten Benutzeroberfläche hat der Komponentenentwickler mehr Steuerungsmöglichkeiten für die Komponente, wenn diese im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e5dab-125">So kann die Komponente Code zu der <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>-Methode hinzufügen, die aufgerufen wird, wenn eine Komponte erstmals zum Datenflusstask hinzugefügt wird, und einen Assistenten anzeigen, der den Benutzer durch die anfängliche Konfiguration der Komponente begleitet.</span><span class="sxs-lookup"><span data-stu-id="e5dab-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="e5dab-126">Nachdem Sie eine Klasse erstellt haben, die die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>-Schnittstelle implementiert, müssen Sie Code hinzufügen, mit dem auf Interaktionen der Benutzer mit der Komponente reagiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="e5dab-127">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>-Methode stellt die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle der Komponente bereit und wird vor den <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>- und <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>-Methoden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="e5dab-128">Dieser Verweis sollte in einer privaten Membervariablen gespeichert und zur anschließenden Änderung der Metadaten der Komponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5dab-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="e5dab-129">Ändern einer Komponente und Beibehalten von Änderungen</span><span class="sxs-lookup"><span data-stu-id="e5dab-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="e5dab-130">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle wird der <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>-Methode als Parameter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e5dab-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="e5dab-131">Dieser Verweis sollte in einer Membervariablen vom Benutzeroberflächencode zwischengespeichert werden und dann verwendet werden, um die Komponente als Reaktion auf Interaktionen der Benutzer mit der Benutzeroberfläche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e5dab-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="e5dab-132">Obwohl Sie die Komponente direkt über die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle ändern können, ist es vorteilhafter, eine Instanz von <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>-Methode zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="e5dab-133">Wenn Sie die Komponente direkt mithilfe der Schnittstelle bearbeiten, umgehen Sie die Schutzmaßnahmen zur Überprüfung der Komponente.</span><span class="sxs-lookup"><span data-stu-id="e5dab-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="e5dab-134">Die Verwendung der Entwurfszeitinstanz der Komponente über <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> hat den Vorteil, sicherzustellen, dass die Komponente, die an ihr vorgenommenen Änderungen steuern kann.</span><span class="sxs-lookup"><span data-stu-id="e5dab-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="e5dab-135">Der Rückgabewert der <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>-Methode bestimmt, ob die an einer Komponente vorgenommenen Änderungen beibehalten oder verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="e5dab-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="e5dab-136">Wenn diese Methode `false` zurückgibt, dann werden alle Änderungen verworfen; bei `true` werden die Änderungen an der Komponente beibehalten und durch eine Kennzeichnung angegeben, dass das Paket gespeichert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e5dab-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="e5dab-137">Verwenden der Dienste des SSIS-Designers</span><span class="sxs-lookup"><span data-stu-id="e5dab-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="e5dab-138">Der `IServiceProvider`-Parameter der <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>-Methode bietet Zugriff auf die folgenden Dienste des [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designers:</span><span class="sxs-lookup"><span data-stu-id="e5dab-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="e5dab-139">Dienst</span><span class="sxs-lookup"><span data-stu-id="e5dab-139">Service</span></span>|<span data-ttu-id="e5dab-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e5dab-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="e5dab-141">Wird verwendet, um zu bestimmen, ob die Komponente als Teil eines Kopier-/Einfüge- oder Ausschneide-/Einfügevorgangs generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e5dab-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="e5dab-142">Wird verwendet, um auf vorhandene Verbindungen zuzugreifen oder neue Verbindungen im Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="e5dab-143">Wird verwendet, um Ereignisse von Datenflusskomponenten aufzuzeichnen, wenn Sie alle Fehler und Warnungen, die von der Komponente ausgelöst wurden, erfassen, und nicht nur den letzten Fehler oder die letzte Warnung, empfangen müssen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="e5dab-144">Wird verwendet, um auf vorhandene Variablen zuzugreifen oder neue Variablen im Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="e5dab-145">Wird von Datenflusskomponenten für den Zugriff auf den übergeordneten Datenflusstask und andere Komponenten im Datenfluss verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5dab-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="e5dab-146">Diese Funktion könnte z. B. verwendet werden, um eine Komponente wie den Assistent für langsam veränderliche Dimensionen zu entwickeln, der bei Bedarf zusätzliche Datenflusskomponenten erstellt und verbindet.</span><span class="sxs-lookup"><span data-stu-id="e5dab-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="e5dab-147">Diese Dienste bieten Komponentenentwicklern die Möglichkeit, Objekte in dem Paket, in das die Komponete geladen ist, zu erstellen bzw. auf diese zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e5dab-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="e5dab-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5dab-148">Sample</span></span>
 <span data-ttu-id="e5dab-149">Im folgenden Codebeispiel wird die Integration einer benutzerdefinierten Benutzeroberflächenklasse gezeigt, die die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>-Schnittstelle implementiert, sowie ein Windows Form, das als Editor für eine Komponente dient.</span><span class="sxs-lookup"><span data-stu-id="e5dab-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="e5dab-150">Benutzerdefinierte Benutzeroberflächenklasse</span><span class="sxs-lookup"><span data-stu-id="e5dab-150">Custom User Interface Class</span></span>
 <span data-ttu-id="e5dab-151">Das folgende Codebeispiel zeigt die Klasse, die die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="e5dab-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="e5dab-152">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>-Methode erstellt den Komponenten-Editor und zeigt dann das Formular an.</span><span class="sxs-lookup"><span data-stu-id="e5dab-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="e5dab-153">Der Rückgabewert des Formulars bestimmt, ob die an der Komponente vorgenommenen Änderungen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="e5dab-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="e5dab-154">Benutzerdefinierter Editor</span><span class="sxs-lookup"><span data-stu-id="e5dab-154">Custom Editor</span></span>
 <span data-ttu-id="e5dab-155">Das folgende Codebeispiel zeigt die Implementierung des Windows Form, das während des Aufrufs der <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>-Methode angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e5dab-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="e5dab-156">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="e5dab-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e5dab-157">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="e5dab-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e5dab-158">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="e5dab-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e5dab-159">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e5dab-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5dab-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5dab-160">See Also</span></span>
 [<span data-ttu-id="e5dab-161">Erstellen einer benutzerdefinierten Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="e5dab-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


