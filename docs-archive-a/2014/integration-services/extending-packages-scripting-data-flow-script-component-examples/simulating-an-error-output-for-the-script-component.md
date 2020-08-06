---
title: Simulieren einer Fehlerausgabe für die Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696994"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="9cb57-102">Simulieren einer Fehlerausgabe für die Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="9cb57-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="9cb57-103">Zur automatischen Bearbeitung von Fehlerzeilen können Sie eine Ausgabe in der Skriptkomponente zwar nicht direkt als Fehlerausgabe konfigurieren, aber Sie können die Funktion einer integrierten Fehlerausgabe reproduzieren, indem Sie eine weitere Ausgabe erstellen und im Skript Bedingungslogik verwenden, um Zeilen gegebenenfalls an diese Ausgabe weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="9cb57-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="9cb57-104">Möglicherweise möchten Sie das Verhalten einer integrierten Fehlerausgabe imitieren, indem Sie zwei zusätzliche Ausgabespalten hinzufügen, sodass Sie die Fehlernummer und die ID der Spalte erhalten, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9cb57-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="9cb57-105">Wenn Sie die Fehlerbeschreibung hinzufügen möchten, die einem spezifischen vordefinierten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehlercode entspricht, können Sie dazu die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle verwenden. Diese wird über die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>-Eigenschaft der Skriptkomponente bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9cb57-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cb57-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cb57-106">Example</span></span>  
 <span data-ttu-id="9cb57-107">Das hier dargestellte Beispiel verwendet eine Skriptkomponente, die als Transformation konfiguriert ist und über zwei synchrone Ausgaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="9cb57-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="9cb57-108">Der Zweck der Skriptkomponente besteht darin, Fehlerzeilen aus Adressdaten in der AdventureWorks-Beispieldatenbank herauszufiltern.</span><span class="sxs-lookup"><span data-stu-id="9cb57-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="9cb57-109">Dieses fiktive Beispiel geht von der Annahme aus, dass wir eine Werbeaktion für Kunden in Nordamerika vorbereiten und dazu Adressen herausfiltern müssen, die sich nicht in Nordamerika befinden.</span><span class="sxs-lookup"><span data-stu-id="9cb57-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="9cb57-110">So konfigurieren Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cb57-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="9cb57-111">Erstellen Sie einen Verbindungs-Manager, bevor Sie die neue Skriptkomponente erzeugen, und konfigurieren Sie eine Datenflussquelle, die Adressdaten aus der AdventureWorks-Beispieldatenbank herausfiltert.</span><span class="sxs-lookup"><span data-stu-id="9cb57-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="9cb57-112">Für dieses Beispiel hat nur die Spalte CountryRegionName Bedeutung. Sie können einfach die Ansicht Person.vStateCountryProvinceRegion verwenden, oder Sie können Daten auswählen, indem Sie die Tabellen Person.Address, Person.StateProvince und Person.CountryRegion miteinander verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="9cb57-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="9cb57-113">Fügen Sie der Datenfluss-Designeroberfläche eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Transformation.</span><span class="sxs-lookup"><span data-stu-id="9cb57-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="9cb57-114">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="9cb57-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="9cb57-115">Legen Sie auf der Seite **Skript** die **ScriptLanguage**-Eigenschaft auf die Skriptsprache fest, die Sie zum Codieren des Skripts verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9cb57-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="9cb57-116">Klicken Sie auf **Skript bearbeiten**, um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9cb57-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="9cb57-117">Geben Sie den unten dargestellten Beispielcode in die `Input0_ProcessInputRow`-Methode ein, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="9cb57-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="9cb57-118">Schließen Sie VSTA.</span><span class="sxs-lookup"><span data-stu-id="9cb57-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="9cb57-119">Wählen Sie auf der Seite **Eingabespalten** die Spalten aus, die Sie in der Skripttransformation verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="9cb57-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="9cb57-120">In diesem Beispiel wird nur die CountryRegionName-Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cb57-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="9cb57-121">Verfügbare Eingabespalten, die Sie nicht auswählen, werden einfach unverändert im Datenfluss durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9cb57-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="9cb57-122">Fügen Sie auf der Seite **Eingaben und Ausgaben** eine neue, zweite Ausgabe hinzu, und legen Sie Ihren `SynchronousInputID` Wert auf die ID der Eingabe fest, die auch der Wert der- `SynchronousInputID` Eigenschaft der Standardausgabe ist.</span><span class="sxs-lookup"><span data-stu-id="9cb57-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="9cb57-123">Legen Sie die `ExclusionGroup`-Eigenschaft beider Ausgaben auf denselben Wert ungleich Null (z. B. 1) fest, um anzugeben, dass jede Zeile nur an eine der beiden Ausgaben weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9cb57-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="9cb57-124">Geben Sie der neuen Fehlerausgabe einen aussagekräftigen Namen, z. B. "MeineFehlerausgabe".</span><span class="sxs-lookup"><span data-stu-id="9cb57-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="9cb57-125">Fügen Sie der neuen Fehlerausgabe zusätzliche Ausgabespalten hinzu, um die gewünschten Fehlerinformationen aufzuzeichnen, zu denen zum Beispiel der Fehlercode, die ID der Spalte mit dem Fehler und möglicherweise die Fehlerbeschreibung zählen können.</span><span class="sxs-lookup"><span data-stu-id="9cb57-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="9cb57-126">In diesem Beispiel werden die neuen Spalten, ErrorColumn und ErrorMessage, erstellt.</span><span class="sxs-lookup"><span data-stu-id="9cb57-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="9cb57-127">Wenn Sie vordefinierte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehler in Ihren eigenen Implementierungen erkennen, stellen Sie sicher, dass Sie eine ErrorCode-Spalte für die Fehlernummer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9cb57-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="9cb57-128">Beachten Sie den ID-Wert der Eingabezeile oder -zeilen, die die Skriptkomponente auf Fehlerbedingungen untersucht.</span><span class="sxs-lookup"><span data-stu-id="9cb57-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="9cb57-129">In diesem Beispiel wird dieser Spaltenbezeichner dazu verwendet, den ErrorColumn-Wert aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="9cb57-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="9cb57-130">Schließen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="9cb57-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="9cb57-131">Fügen Sie die Ausgaben der Skriptkomponente an geeignete Ziele an.</span><span class="sxs-lookup"><span data-stu-id="9cb57-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="9cb57-132">Flatfileziele sind die einfachste Möglichkeit zur Konfiguration bei Ad-hoc-Tests.</span><span class="sxs-lookup"><span data-stu-id="9cb57-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="9cb57-133">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="9cb57-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="9cb57-134">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="9cb57-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9cb57-135">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="9cb57-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9cb57-136">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="9cb57-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9cb57-137">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9cb57-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb57-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cb57-138">See Also</span></span>  
 <span data-ttu-id="9cb57-139">[Fehlerbehandlung in Daten](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="9cb57-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="9cb57-140">[Verwenden von Fehler Ausgaben in einer Datenfluss Komponente](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="9cb57-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="9cb57-141">Erstellen einer synchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="9cb57-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
