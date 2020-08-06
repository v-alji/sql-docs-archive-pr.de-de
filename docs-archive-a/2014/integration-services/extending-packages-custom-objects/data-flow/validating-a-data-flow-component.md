---
title: Überprüfen einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ReinitializeMetaData method
- Validate method
- component validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- data flow components [Integration Services], validating
- validation [Integration Services]
ms.assetid: 1a7d5925-b387-4e31-af7f-c7f3c5151040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9a78588c1e75697235e62e8955b65da466a37ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616120"
---
# <a name="validating-a-data-flow-component"></a><span data-ttu-id="974c9-102">Überprüfen einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="974c9-102">Validating a Data Flow Component</span></span>
  <span data-ttu-id="974c9-103">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse wird bereitgestellt, um die Ausführung einer Komponente zu verhindern, die nicht korrekt konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="974c9-103">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is provided to prevent execution of a component that is not configured correctly.</span></span> <span data-ttu-id="974c9-104">Verwenden Sie diese Methode, wenn Sie überprüfen wollen, ob eine Komponente die erwartete Anzahl an Eingabe- und Ausgabeobjekten aufweist, die Werte der benutzerdefinierten Eigenschaften der Komponente zulässig sind, und Verbindungen, falls erforderlich, angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="974c9-104">Use this method to verify that a component has the expected number of input and output objects, that the custom properties of the component have acceptable values, and that any connections, if required, are specified.</span></span> <span data-ttu-id="974c9-105">Sie können diese Methode auch verwenden, um zu überprüfen, ob die Spalten in der Eingabe- und Ausgabeauflistung die korrekten Datentypen enthalten und der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> jeder Spalte ordnungsgemäß für die Komponente festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="974c9-105">Use this method also to verify that the columns in the input and output collections have the correct data types and that the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> of each column is set appropriately for the component.</span></span> <span data-ttu-id="974c9-106">Durch die Basisklassenimplementierung wird der Überprüfungsprozess unterstützt, indem die Eingabespaltenauflistung der Komponente überprüft und sichergestellt wird, dass jede Spalte in der Auflistung auf eine Spalte in <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> der Upstreamkomponente verweist.</span><span class="sxs-lookup"><span data-stu-id="974c9-106">The base class implementation assists in the validation process by checking the input column collection of the component and ensuring that each column in the collection refers to a column in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> of the upstream component.</span></span>  
  
## <a name="validate-method"></a><span data-ttu-id="974c9-107">Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="974c9-107">Validate Method</span></span>  
 <span data-ttu-id="974c9-108">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>-Methode wird wiederholt aufgerufen, wenn eine Komponente im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="974c9-108">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method is called repeatedly when a component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="974c9-109">Sie können an den Designer und die Benutzer der Komponente über den <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus>-Enumerationsrückgabewert und durch die Anzeige von Warnungen und Fehlern ein Feedback bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="974c9-109">You can provide feedback to the designer and to users of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration return value, and by posting warnings and errors.</span></span> <span data-ttu-id="974c9-110">Die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus>-Enumeration enthält drei Werte, die verschiedene Fehlerstadien anzeigen, und einen vierten <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>-Wert, der angibt, ob die Komponente ordnungsgemäß konfiguriert und bereit zur Ausführung ist.</span><span class="sxs-lookup"><span data-stu-id="974c9-110">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration contains three values that indicate various stages of failure, and a fourth, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>, that indicates whether the component is correctly configured and ready to execute.</span></span>  
  
 <span data-ttu-id="974c9-111">Der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA>-Wert zeigt an, dass ein Fehler in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> besteht, und dass die Komponente die Fehler beheben kann.</span><span class="sxs-lookup"><span data-stu-id="974c9-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> value indicates that an error exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>, and that the component can repair the errors.</span></span> <span data-ttu-id="974c9-112">Wenn eine Komponente einen Metadatenfehler feststellt, den sie beheben kann, sollte sie den Fehler nicht in der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>-Methode beheben und <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> sollte bei der Überprüfung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="974c9-112">If a component encounters a metadata error that it can repair, it should not fix the error in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> should not be modified during validation.</span></span> <span data-ttu-id="974c9-113">Stattdessen sollte die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>-Methode nur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> zurückgeben, und die Komponente sollte den Fehler in einem Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>-Methode, wie weiter unten in diesem Abschnitt beschrieben, beheben.</span><span class="sxs-lookup"><span data-stu-id="974c9-113">Instead, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method should return only <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA>, and the component should repair the error in a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method, as described later in this section.</span></span>  
  
 <span data-ttu-id="974c9-114">Der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN>-Wert zeigt an, dass die Komponente einen Fehler aufweist, der durch Bearbeitung der Komponente im Designer behoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="974c9-114">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN> value indicates that the component has an error that can be rectified by editing the component in the designer.</span></span> <span data-ttu-id="974c9-115">Der Fehler wird typischerweise durch eine benutzerdefinierte Eigenschaft oder eine erforderliche Verbindung verursacht, die nicht angegeben oder nicht ordnungsgemäß eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="974c9-115">The error is typically caused by a custom property or a required connection that is not specified or is set incorrectly.</span></span>  
  
 <span data-ttu-id="974c9-116">Der endgültige Fehlerwert ist <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>, wodurch angezeigt wird, dass die Komponente Fehler gefunden hat, die nur auftreten dürften, wenn die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>-Eigenschaft entweder durch Bearbeiten des Paket-XML oder durch Verwenden des Objektmodells direkt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="974c9-116">The final error value is <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>, which indicates that the component has discovered errors that should only occur if the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property has been modified directly, either by editing the package XML or by using the object model.</span></span> <span data-ttu-id="974c9-117">Dieser Fehlertyp tritt z. B. auf, wenn eine Komponente nur eine einzelne Eingabe hinzugefügt hat, aber bei der Überprüfung festgestellt wird, dass mehr als eine Eingabe in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="974c9-117">For example, this kind of error occurs when a component has added only a single input, but validation discovers that more than one input exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="974c9-118">Fehler, die diesen Rückgabewert generieren, können nur behoben werden, indem die Komponente durch Verwenden der Schaltfläche **Zurücksetzen** im Dialogfeld **Erweiterter Editor** zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="974c9-118">Errors that generate this return value can only be repaired by resetting the component by using the **Reset** button in the **Advanced Editor** dialog box.</span></span>  
  
 <span data-ttu-id="974c9-119">Neben der Rückgabe von Fehlerwerten stellen Komponenten Feedback bereit, indem sie während der Überprüfung Warnungen und Fehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="974c9-119">Besides returning error values, components provide feedback by posting warnings or errors during validation.</span></span> <span data-ttu-id="974c9-120">Dieser Mechanismus wird durch die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>- und <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>-Methoden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="974c9-120">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods provide this mechanism.</span></span> <span data-ttu-id="974c9-121">Wenn diese Methoden aufgerufen werden, werden diese Ereignisse im Fenster **Fehlerliste** von [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] angezeigt.</span><span class="sxs-lookup"><span data-stu-id="974c9-121">When these methods are called, these events are posted in the **Error List** window of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="974c9-122">Komponentenentwickler können dann für die Benutzer direktes Feedback über die aufgetretenen Fehler bereitstellen bzw. erläutern, wie diese behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="974c9-122">Component developers can then provide direct feedback to users on the errors that have occurred, and if appropriate, how to correct them.</span></span>  
  
 <span data-ttu-id="974c9-123">Im folgenden Codebeispiel wird eine überschriebene Implementierung von <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="974c9-123">The following code example shows an overridden implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    bool pbCancel = false;  
  
    // Validate that there is one input.  
    if (ComponentMetaData.InputCollection.Count != 1)  
    {  
    ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, out pbCancel);  
    return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Validate that the UserName custom property is set.  
    if (ComponentMetaData.CustomPropertyCollection["UserName"].Value == null || ((string)ComponentMetaData.CustomPropertyCollection["UserName"].Value).Length == 0)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISBROKEN;  
    }  
  
    // Validate that there is one output.  
    if (ComponentMetaData.OutputCollection.Count != 1)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Let the base class verify that the input column reflects the output   
    // of the upstream component.  
    return base.Validate();  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
  
 Dim pbCancel As Boolean = False  
  
 ' Validate that there is one input.  
 If Not (ComponentMetaData.InputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Validate that the UserName custom property is set.  
 If ComponentMetaData.CustomPropertyCollection("UserName").Value Is Nothing OrElse CType(ComponentMetaData.CustomPropertyCollection("UserName").Value, String).Length = 0 Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISBROKEN   
 End If   
  
 ' Validate that there is one output.  
 If Not (ComponentMetaData.OutputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Let the base class verify that the input column reflects the output   
 ' of the upstream component.  
  
 Return MyBase.Validate   
  
End Function  
```  
  
## <a name="reinitializemetadata-method"></a><span data-ttu-id="974c9-124">ReinitializeMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="974c9-124">ReinitializeMetaData Method</span></span>  
 <span data-ttu-id="974c9-125">Die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>-Methode wird vom [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer aufgerufen, wenn Sie eine Komponente bearbeiten, die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> von der zugehörigen <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>-Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="974c9-125">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer whenever you edit a component that returns <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> from its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method.</span></span> <span data-ttu-id="974c9-126">Komponenten sollten Code enthalten, der die Probleme erkennt und behebt, die während der Überprüfung von der Komponente identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="974c9-126">Components should contain code that detects and corrects the problems identified by the component during validation.</span></span>  
  
 <span data-ttu-id="974c9-127">Im folgenden Beispiel wird eine Komponente gezeigt, die während der Überprüfung Probleme feststellt und diese mittels <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>-Methode behebt.</span><span class="sxs-lookup"><span data-stu-id="974c9-127">The following example shows a component that detects problems during validation and fixes these errors in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method.</span></span>  
  
```csharp  
private bool areInputColumnsValid = true;  
public override DTSValidationStatus Validate()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
    bool Cancel = false;  
    foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
    {  
        try  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
        }  
        catch  
        {  
            ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, out Cancel);  
            areInputColumnsValid = false;  
            return DTSValidationStatus.VS_NEEDSNEWMETADATA;  
        }  
    }  
  
    return DTSValidationStatus.VS_ISVALID;  
}  
public override void ReinitializeMetaData()  
{  
    if (!areInputColumnsValid)  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection[0];  
        IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
        foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
  
            if (vColumn == null)  
                input.InputColumnCollection.RemoveObjectByID(column.ID);  
        }  
        areInputColumnsValid = true;  
    }  
}  
```  
  
```vb  
Private areInputColumnsValid As Boolean = True   
  
Public  Overrides Function Validate() As DTSValidationStatus   
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
 Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
 Dim Cancel As Boolean = False   
 For Each column As IDTSInputColumn100 In input.InputColumnCollection   
   Try   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
   Catch   
     ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, Cancel)   
     areInputColumnsValid = False   
     Return DTSValidationStatus.VS_NEEDSNEWMETADATA   
   End Try   
 Next   
 Return DTSValidationStatus.VS_ISVALID   
End Function   
  
Public  Overrides Sub ReinitializeMetaData()   
 If Not areInputColumnsValid Then   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
   Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
   For Each column As IDTSInputColumn100 In input.InputColumnCollection   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
     If vColumn Is Nothing Then   
       input.InputColumnCollection.RemoveObjectByID(column.ID)   
     End If   
   Next   
   areInputColumnsValid = True   
 End If   
End Sub  
```  
  
<span data-ttu-id="974c9-128">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="974c9-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="974c9-129">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="974c9-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="974c9-130">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="974c9-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="974c9-131">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="974c9-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
