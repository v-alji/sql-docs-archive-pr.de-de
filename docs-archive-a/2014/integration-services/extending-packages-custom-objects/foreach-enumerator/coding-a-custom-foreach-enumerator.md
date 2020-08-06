---
title: Codieren eines benutzerdefinierten Foreach-Enumerators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615454"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="088c5-102">Codieren eines benutzerdefinierten Foreach-Enumerators</span><span class="sxs-lookup"><span data-stu-id="088c5-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="088c5-103">Nachdem Sie eine Klasse erstellt haben, die von der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>-Basisklasse erbt, und das <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>-Attribut auf die Klasse angewendet haben, müssen Sie die Implementierung der Eigenschaften und Methoden der Basisklasse überschreiben, um die benutzerdefinierte Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="088c5-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="088c5-104">Ein funktionierendes Beispiel eines benutzerdefinierten Enumerators finden Sie unter [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md) (Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten ForEach-Enumerator).</span><span class="sxs-lookup"><span data-stu-id="088c5-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="088c5-105">Initialisieren des Enumerators</span><span class="sxs-lookup"><span data-stu-id="088c5-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="088c5-106">Sie können die <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A>-Methode verwenden, um Verweise auf die im Paket definierten Verbindungs-Manager zwischenzuspeichern und um Verweise auf die Ereignisschnittstelle zwischenzuspeichern, die Sie verwenden können, um Fehler, Warnungen und Informationsmeldungen auszulösen.</span><span class="sxs-lookup"><span data-stu-id="088c5-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="088c5-107">Überprüfen des Enumerators</span><span class="sxs-lookup"><span data-stu-id="088c5-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="088c5-108">Überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A>-Methode, um zu überprüfen, ob der Enumerator ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="088c5-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="088c5-109">Wenn die Methode `Failure` zurückgibt, werden der Enumerator und das Paket, das den Enumerator enthält, nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="088c5-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="088c5-110">Die Implementierung dieser Methode ist für jeden Enumerator spezifisch. Wenn jedoch der Enumerator auf <xref:Microsoft.SqlServer.Dts.Runtime.Variable>- oder <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekten basiert, sollten Sie Code hinzufügen, um zu überprüfen, ob diese Objekte in den Auflistungen, die der Methode bereitgestellt werden, vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="088c5-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="088c5-111">Im folgenden Codebeispiel wird die Implementierung von <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> gezeigt, die nach einer in einer Eigenschaft des Enumerators angegebenen Variablen sucht.</span><span class="sxs-lookup"><span data-stu-id="088c5-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="088c5-112">Zurückgeben der Auflistung</span><span class="sxs-lookup"><span data-stu-id="088c5-112">Returning the Collection</span></span>  
 <span data-ttu-id="088c5-113">Während der Ausführung ruft der <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>-Container die <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>-Methode des benutzerdefinierten Enumerators auf.</span><span class="sxs-lookup"><span data-stu-id="088c5-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="088c5-114">In dieser Methode erstellt der Enumerator seine Auflistung von Elementen und füllt sie auf und gibt dann die Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="088c5-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="088c5-115"><xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> führt dann eine Iteration für die Elemente in der Auflistung durch und führt die Ablaufsteuerung für jedes Element in der Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="088c5-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="088c5-116">Im folgenden Beispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> gezeigt, wobei ein Array zufälliger ganzer Zahlen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="088c5-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="088c5-117">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="088c5-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="088c5-118">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="088c5-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="088c5-119">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="088c5-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="088c5-120">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="088c5-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088c5-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="088c5-121">See Also</span></span>  
 <span data-ttu-id="088c5-122">[Erstellen eines benutzerdefinierten Foreach-Enumerators](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="088c5-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="088c5-123">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten ForEach-Enumerator</span><span class="sxs-lookup"><span data-stu-id="088c5-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
