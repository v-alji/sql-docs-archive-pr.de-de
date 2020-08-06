---
title: Erweitern einer Fehlerausgabe mit der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622225"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="81af6-102">Erweitern einer Fehlerausgabe mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="81af6-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="81af6-103">Standardmäßig enthalten die beiden zusätzlichen Spalten in einer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehlerausgabe (ErrorCode und ErrorColumn) nur numerische Codes, die eine Fehlernummer darstellen, und die ID der Spalte, in der der Fehler auftrat.</span><span class="sxs-lookup"><span data-stu-id="81af6-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="81af6-104">Diese numerischen Werte sind ohne die entsprechende Fehlerbeschreibung nur von begrenztem Nutzen.</span><span class="sxs-lookup"><span data-stu-id="81af6-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="81af6-105">In diesem Thema wird beschrieben, wie Sie mithilfe der Skriptkomponente den im Datenfluss vorhandenen Fehlerausgabedaten eine Spalte zur Fehlerbeschreibung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81af6-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="81af6-106">Im Beispiel wird die Fehlerbeschreibung einem bestimmten vordefinierten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehlercode hinzugefügt. Dazu wird die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle verwendet, die von der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>-Eigenschaft der Skriptkomponente bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="81af6-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81af6-107">Wenn Sie eine Komponente erstellen möchten, die Sie einfacher in mehreren Datenflusstasks und Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skriptkomponentenbeispiel als Ausgangspunkt für eine benutzerdefinierte Datenflusskomponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="81af6-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="81af6-108">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="81af6-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81af6-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81af6-109">Example</span></span>  
 <span data-ttu-id="81af6-110">In diesem Beispiel wird gezeigt, wie mit einer Skriptkomponente, die als Transformation konfiguriert ist, den im Datenfluss vorhandenen Fehlerausgabedaten eine Spalte zur Fehlerbeschreibung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="81af6-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="81af6-111">Weitere Informationen zum Konfigurieren der Skript Komponente für die Verwendung als Transformation im Datenfluss finden Sie unter [Erstellen einer synchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)und [Erstellen einer asynchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="81af6-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="81af6-112">So konfigurieren Sie dieses Skriptkomponentenbeispiel</span><span class="sxs-lookup"><span data-stu-id="81af6-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="81af6-113">Konfigurieren Sie vor dem Erstellen der neuen Skriptkomponente eine Upstreamkomponente im Datenfluss, um Zeilen zur zugehörigen Fehlerausgabe umzuleiten, sobald ein Fehler auftritt oder Daten abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="81af6-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="81af6-114">Zu Testzwecken sollten Sie eine Komponente so konfigurieren, dass auf jeden Fall Fehler auftreten, beispielsweise, indem Sie eine Transformation zum Suchen zwischen zwei Tabellen konfigurieren, und die Suche einen Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="81af6-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="81af6-115">Fügen Sie der Datenfluss-Designeroberfläche eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Transformation.</span><span class="sxs-lookup"><span data-stu-id="81af6-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="81af6-116">Verbinden Sie die Fehlerausgabe der Upstreamkomponente mit der neuen Skriptkomponente.</span><span class="sxs-lookup"><span data-stu-id="81af6-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="81af6-117">Öffnen Sie den **Transformations-Editor für Skripterstellung**, und wählen Sie auf der Seite **Skript** für die **ScriptLanguage**-Eigenschaft die Skriptsprache aus.</span><span class="sxs-lookup"><span data-stu-id="81af6-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="81af6-118">Klicken Sie auf **Skript bearbeiten**, um die IDE der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Tools for Applications (VSTA) zu öffnen und den unten dargestellten Beispielcode einzufügen.</span><span class="sxs-lookup"><span data-stu-id="81af6-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="81af6-119">Schließen Sie VSTA.</span><span class="sxs-lookup"><span data-stu-id="81af6-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="81af6-120">Wählen Sie im Transformations-Editor für Skripterstellung auf der Seite **Eingabe Spalten** die Spalte ErrorCode aus.</span><span class="sxs-lookup"><span data-stu-id="81af6-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="81af6-121">Fügen Sie auf der Seite **Eingaben und Ausgaben** eine neue Ausgabe Spalte des Typs mit dem `String` Namen **ErrorDescription**hinzu.</span><span class="sxs-lookup"><span data-stu-id="81af6-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="81af6-122">Vergrößern Sie die Standardlänge der neuen Spalte auf 255, damit auch lange Meldungen angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="81af6-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="81af6-123">Schließen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="81af6-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="81af6-124">Fügen Sie die Ausgabe der Skriptkomponente an ein geeignetes Ziel an.</span><span class="sxs-lookup"><span data-stu-id="81af6-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="81af6-125">Ein Flatfileziel ist die einfachste Möglichkeit zur Konfiguration bei Ad-hoc-Tests.</span><span class="sxs-lookup"><span data-stu-id="81af6-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="81af6-126">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="81af6-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="81af6-127">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="81af6-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="81af6-128">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="81af6-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="81af6-129">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="81af6-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="81af6-130">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="81af6-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81af6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81af6-131">See Also</span></span>  
 <span data-ttu-id="81af6-132">[Fehlerbehandlung in Daten](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="81af6-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="81af6-133">[Verwenden von Fehlerausgaben in einer Datenflusskomponente](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="81af6-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="81af6-134">Erstellen einer synchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="81af6-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
