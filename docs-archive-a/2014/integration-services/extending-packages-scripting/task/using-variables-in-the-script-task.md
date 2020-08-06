---
title: Verwenden von Variablen im Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727065"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="f2477-102">Verwenden von Variablen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="f2477-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="f2477-103">Variablen ermöglichen es dem Skripttask, Daten mit anderen Objekten im Paket auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="f2477-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="f2477-104">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f2477-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="f2477-105">Mithilfe der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft des `Dts`-Objekts erhält der Skripttask Lese- und Schreibzugriff auf <xref:Microsoft.SqlServer.Dts.Runtime.Variable>-Objekte im Paket.</span><span class="sxs-lookup"><span data-stu-id="f2477-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2477-106">Die <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Dts.Runtime.Variable>-Klasse ist vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="f2477-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="f2477-107">Da für den Skripttask `Option Strict` aktiviert ist, müssen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>-Eigenschaft vor ihrer Verwendung in den richtigen Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="f2477-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="f2477-108">Um bestehende Variablen für das benutzerdefinierte Skript verfügbar zu machen, fügen Sie diese den Listen <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> und <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> im **Skripttask-Editor** hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2477-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="f2477-109">Beachten Sie, dass bei Variablennamen nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="f2477-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="f2477-110">Innerhalb des Skripts greifen Sie auf Variablen beider Typen über die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft des `Dts`-Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="f2477-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="f2477-111">Mithilfe der `Value`-Eigenschaft erhalten Sie Lese- und Schreibzugriff auf einzelne Variablen.</span><span class="sxs-lookup"><span data-stu-id="f2477-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="f2477-112">Der Skripttask verwaltet Sperren transparent, während das Skript die Werte von Variablen liest und ändert.</span><span class="sxs-lookup"><span data-stu-id="f2477-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="f2477-113">Mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Runtime.Variables>-Auflistung, die von der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft zurückgegeben wird, können Sie das Vorhandensein von Variablen vor ihrer Verwendung im Code überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f2477-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="f2477-114">Für die Arbeit mit Variablen im Skripttask können Sie auch die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>-Eigenschaft (Dts.VariableDispenser) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2477-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="f2477-115">Bei der Verwendung von <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> müssen Sie die Sperrsemantik und die Umwandlung von Datentypen für variable Werte in Ihrem Code berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f2477-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="f2477-116">Wenn Sie mit Variablen arbeiten möchten, die zur Entwurfszeit nicht zur Verfügung stehen, sondern programmgesteuert zur Laufzeit erstellt werden, müssen Sie möglicherweise auf die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>-Eigenschaft anstelle der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="f2477-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="f2477-117">Verwenden des Skripttasks in einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="f2477-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="f2477-118">Wenn ein Skripttask wiederholt innerhalb eines Foreach-Schleifencontainers ausgeführt wird, muss das Skript normalerweise auf den Inhalt des aktuellen Elements im Enumerator zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f2477-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="f2477-119">Bei der Verwendung eines Foreach-Dateienumerators muss das Skript beispielsweise über den aktuellen Dateinamen verfügen und bei der Verwendung eines Foreach-ADO-Enumerators über den Inhalt der Spalten in der aktuellen Datenzeile.</span><span class="sxs-lookup"><span data-stu-id="f2477-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="f2477-120">Variablen ermöglichen diese Kommunikation zwischen dem Foreach-Schleifencontainer und dem Skripttask.</span><span class="sxs-lookup"><span data-stu-id="f2477-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="f2477-121">Weisen Sie jedem Datenelement, das von einem Enumerationselement zurückgegeben wird, im **Foreach-Schleifen-Editor** auf der Seite **Variablenzuordnungen** Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="f2477-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="f2477-122">Ein Foreach-Dateienumerator gibt z. B. nur am Index 0 einen Dateinamen zurück und erfordert daher nur eine Variablenzuordnung. Bei einem Enumerator, der in jeder Zeile mehrere Datenspalten zurückgibt, müssen Sie hingegen für jede Spalte, die Sie im Skripttask verwenden möchten, eine andere Variable zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f2477-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="f2477-123">Nachdem Sie den Variablen Enumerationselemente zugeordnet haben, müssen Sie die zugeordneten Variablen der `ReadOnlyVariables` Eigenschaft auf der Seite **Skript** im **Skript Task-Editor** hinzufügen, um Sie für das Skript verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="f2477-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="f2477-124">Ein Beispiel eines Skripttasks innerhalb eines Foreach-Schleifencontainers zur Verarbeitung der Bilddateien in einem Ordner finden Sie unter [Arbeiten mit Bildern mithilfe des Skripttasks](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="f2477-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="f2477-125">Variablenbeispiel</span><span class="sxs-lookup"><span data-stu-id="f2477-125">Variables Example</span></span>  
 <span data-ttu-id="f2477-126">Das folgende Beispiel veranschaulicht den Zugriff auf und die Verwendung von Variablen in einem Skripttask zur Ermittlung des Pfads eines Paket-Workflows.</span><span class="sxs-lookup"><span data-stu-id="f2477-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="f2477-127">Im Beispiel wird davon ausgegangen, dass Sie ganzzahlige Variablen mit dem Namen `CustomerCount` und erstellt `MaxRecordCount` und Sie der-Auflistung `ReadOnlyVariables` im **Skript Task-Editor**hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="f2477-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="f2477-128">Die `CustomerCount`-Variable enthält die Anzahl an Kundendatensätzen, die importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2477-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="f2477-129">Falls der Wert höher als der Wert von `MaxRecordCount` ist, gibt der Skripttask eine Fehlermeldung aus.</span><span class="sxs-lookup"><span data-stu-id="f2477-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="f2477-130">Falls der Fehler auftritt, weil der `MaxRecordCount`-Schwellenwert überschritten wurde, kann der Fehlerpfad des Workflows alle erforderlichen Cleanup-Schritte implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2477-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="f2477-131">Um das Beispiel erfolgreich zu kompilieren, müssen Sie einen Verweis auf die Microsoft.SqlServer.ScriptTask-Assembly hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2477-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
    {  
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="f2477-132">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="f2477-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f2477-133">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="f2477-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f2477-134">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="f2477-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f2477-135">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f2477-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2477-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2477-136">See Also</span></span>  
 <span data-ttu-id="f2477-137">[Integration Services-Variablen &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f2477-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="f2477-138">Verwenden von Variablen in Paketen</span><span class="sxs-lookup"><span data-stu-id="f2477-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
