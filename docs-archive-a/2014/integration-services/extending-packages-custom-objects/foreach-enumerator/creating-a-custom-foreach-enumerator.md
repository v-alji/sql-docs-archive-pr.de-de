---
title: Erstellen eines benutzerdefinierten Foreach-Enumerators | Microsoft-Dokumentation
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
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615452"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="ce38f-102">Erstellen eines benutzerdefinierten Foreach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="ce38f-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="ce38f-103">Die Schritte zum Erstellen eines benutzerdefinierten Foreach-Enumerators ähneln denen jedes anderen benutzerdefinierten Objekts für [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ce38f-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ce38f-104">Erstellen Sie eine neue Klasse, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="ce38f-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="ce38f-105">Für einen Foreach-Enumerator ist <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> die Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="ce38f-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="ce38f-106">Weisen Sie das Attribut zu, das den Typ des Objekts für die Klasse identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ce38f-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="ce38f-107">Für einen Foreach-Enumerator ist <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> das Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce38f-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="ce38f-108">Überschreiben Sie die Implementierung der Methoden und Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="ce38f-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="ce38f-109">Für einen Foreach-Enumerator ist die <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>-Methode die wichtigste.</span><span class="sxs-lookup"><span data-stu-id="ce38f-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="ce38f-110">Entwickeln Sie optional eine individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ce38f-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="ce38f-111">Für einen Foreach-Enumerator ist dazu eine Klasse erforderlich, die die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="ce38f-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="ce38f-112">Ein benutzerdefinierter Enumerator wird vom <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>-Container gehostet.</span><span class="sxs-lookup"><span data-stu-id="ce38f-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="ce38f-113">Zur Laufzeit ruft der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>-Container die <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>-Methode des benutzerdefinierten Enumerators auf.</span><span class="sxs-lookup"><span data-stu-id="ce38f-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="ce38f-114">Der benutzerdefinierte Enumerator gibt ein Objekt zurück, mit dem die `IEnumerable`-Schnittstelle implementiert wird, wie beispielsweise `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="ce38f-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="ce38f-115"><xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> führt anschließend eine Iteration über jedes Element in der Auflistung durch, gibt den Wert des aktuellen Elements durch eine benutzerdefinierte Variable an und führt die Ablaufsteuerung im Container aus.</span><span class="sxs-lookup"><span data-stu-id="ce38f-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="ce38f-116">Erste Schritte mit einem benutzerdefinierten ForEach-Enumerator</span><span class="sxs-lookup"><span data-stu-id="ce38f-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="ce38f-117">Erstellen von Projekten und Klassen</span><span class="sxs-lookup"><span data-stu-id="ce38f-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="ce38f-118">Da alle verwalteten Foreach-Enumeratoren von der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>-Basisklasse abgeleitet sind, besteht der erste Schritt beim Erstellen eines benutzerdefinierten Foreach-Enumerators darin, in Ihrer bevorzugten verwalteten Programmiersprache ein Klassenbibliotheksprojekt anzulegen und eine Klasse zu generieren, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="ce38f-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="ce38f-119">In dieser abgeleiteten Klasse überschreiben Sie die Methoden und Eigenschaften der Basisklasse, um die benutzerdefinierten Funktionen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce38f-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="ce38f-120">Erstellen Sie in der gleichen Lösung ein zweites Klassenbibliotheksprojekt für die individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ce38f-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="ce38f-121">Für eine einfache Bereitstellung sollten Sie eine eigene Assembly für die Benutzeroberfläche verwenden, da Sie so den Foreach-Enumerator oder seine Benutzeroberfläche unabhängig aktualisieren und erneut bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="ce38f-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="ce38f-122">Konfigurieren Sie beide Projekte für das Signieren der Assemblys, die bei der Erstellung erzeugt werden, mit einer Schlüsseldatei mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="ce38f-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="ce38f-123">Anwenden des DtsForEachEnumerator-Attributs</span><span class="sxs-lookup"><span data-stu-id="ce38f-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="ce38f-124">Wenden Sie das <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>-Attribut der Klasse zu, die Sie erstellt haben, um sie als Foreach-Enumerator zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="ce38f-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="ce38f-125">Dieses Attribut stellt Entwurfszeitinformationen bereit, z. B. Name und Beschreibung des Foreach-Enumerators.</span><span class="sxs-lookup"><span data-stu-id="ce38f-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="ce38f-126">Die- `Name` Eigenschaft wird in der Dropdown Liste der verfügbaren Enumeratoren auf der Registerkarte **Sammlung** des Dialog Felds **foreach-Schleifen-Editor** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce38f-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="ce38f-127">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A>-Eigenschaft, um den Foreach-Enumerator mit der individuellen Benutzeroberfläche zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ce38f-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="ce38f-128">Um das für diese Eigenschaft erforderliche öffentliche Schlüsseltoken zu erhalten, können Sie **sn.exe -t** verwenden. Damit zeigen Sie das öffentliche Schlüsseltoken aus der Schlüsselpaardatei (.snk) an, die Sie für das Signieren der Benutzeroberflächenassembly verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ce38f-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="ce38f-129">Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Enumerators</span><span class="sxs-lookup"><span data-stu-id="ce38f-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="ce38f-130">Die Schritte zum Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Foreach-Enumerators in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] ähneln denen für andere Arten benutzerdefinierter Objekte stark.</span><span class="sxs-lookup"><span data-stu-id="ce38f-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="ce38f-131">Weitere Informationen finden Sie unter [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) (Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten).</span><span class="sxs-lookup"><span data-stu-id="ce38f-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="ce38f-132">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="ce38f-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ce38f-133">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="ce38f-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ce38f-134">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="ce38f-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ce38f-135">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce38f-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce38f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce38f-136">See Also</span></span>  
 <span data-ttu-id="ce38f-137">[Codieren eines benutzerdefinierten Foreach-Enumerators](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="ce38f-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="ce38f-138">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten ForEach-Enumerator</span><span class="sxs-lookup"><span data-stu-id="ce38f-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
