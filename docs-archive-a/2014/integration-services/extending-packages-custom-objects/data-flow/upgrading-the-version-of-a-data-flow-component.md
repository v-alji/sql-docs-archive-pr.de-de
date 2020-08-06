---
title: Aktualisieren der Version einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622783"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="51d77-102">Aktualisieren der Version einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="51d77-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="51d77-103">Pakete, die mit einer älteren Version der Komponente erstellt wurden, enthalten möglicherweise Metadaten, die nicht mehr gültig sind, beispielsweise benutzerdefinierte Eigenschaften, deren Verwendung in neueren Versionen der Komponenten geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="51d77-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="51d77-104">Sie können die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse überschreiben, um die zuvor in älteren Paketen gespeicherten Metadaten zu aktualisieren, sodass die aktuellen Eigenschaften der Komponente wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="51d77-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51d77-105">Wenn Sie eine benutzerdefinierte Komponente für eine neue Version von [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] neu kompilieren, müssen Sie den Wert der <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A>-Eigenschaft nicht ändern, wenn sich die Eigenschaften der Komponente nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="51d77-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51d77-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51d77-106">Example</span></span>  
 <span data-ttu-id="51d77-107">Das folgende Beispiel enthält Code aus Version 2.0 einer fiktiven Datenflusskomponente.</span><span class="sxs-lookup"><span data-stu-id="51d77-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="51d77-108">Die neue Versionsnummer wird in der <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A>-Eigenschaft von <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> definiert.</span><span class="sxs-lookup"><span data-stu-id="51d77-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="51d77-109">Die Komponente weist eine Eigenschaft auf, durch die definiert wird, wie numerische Werte behandelt werden, die einen bestimmten Schwellenwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="51d77-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="51d77-110">In Version 1.0 der fiktiven Komponente hieß diese Eigenschaft `RaiseErrorOnInvalidValue`, und es war ein boolescher Wert von True oder False zulässig.</span><span class="sxs-lookup"><span data-stu-id="51d77-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="51d77-111">In Version 2.0 der fiktiven Komponente wurde die Eigenschaft in `InvalidValueHandling` umbenannt. Es ist nun einer von vier möglichen Werten aus einer benutzerdefinierten Enumeration zulässig.</span><span class="sxs-lookup"><span data-stu-id="51d77-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="51d77-112">Von der überschriebenen <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A>-Methode im folgenden Beispiel werden die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="51d77-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="51d77-113">Ruft die aktuelle Version der Komponente ab.</span><span class="sxs-lookup"><span data-stu-id="51d77-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="51d77-114">Ruft den Wert der alten benutzerdefinierten Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="51d77-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="51d77-115">Entfernt die alte Eigenschaft aus der Auflistung mit den benutzerdefinierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="51d77-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="51d77-116">Legt, wenn möglich, den Wert der neuen benutzerdefinierten Eigenschaft basierend auf dem Wert der alten Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="51d77-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="51d77-117">Legt die Versionsmetadaten auf die aktuelle Version der Komponente fest</span><span class="sxs-lookup"><span data-stu-id="51d77-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51d77-118">Die Datenfluss-Engine übergibt seine eigene Versionsnummer an die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A>-Methode im *pipelineVersion*-Parameter.</span><span class="sxs-lookup"><span data-stu-id="51d77-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="51d77-119">Dieser Parameter ist in Version 1.0 von [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] nicht von Nutzen, kann aber in nachfolgenden Versionen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="51d77-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="51d77-120">Im Beispielcode werden nur die beiden Enumerationswerte verwendet, die direkt den vorherigen booleschen Werten der benutzerdefinierten Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="51d77-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="51d77-121">Die anderen verfügbaren Enumerationswerte können vom Benutzer über die benutzerdefinierte Benutzeroberfläche der Komponente im erweiterten Editor oder programmgesteuert ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="51d77-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="51d77-122">Informationen zum Anzeigen von Enumerationswerten für eine benutzerdefinierte Eigenschaft im erweiterten Editor finden Sie in [Entwurfszeitmethoden einer Datenflusskomponente](design-time-methods-of-a-data-flow-component.md) unter „Erstellen von benutzerdefinierten Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="51d77-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="51d77-123">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="51d77-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="51d77-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="51d77-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="51d77-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="51d77-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="51d77-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="51d77-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
