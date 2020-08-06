---
title: Erkennen einer leeren flachen Datei mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618772"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="e1d7b-102">Erkennen einer leeren flachen Datei mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="e1d7b-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="e1d7b-103">Die Flatfilequelle ermittelt vor dem Verarbeitungsversuch nicht, ob eine Flatfile Datenzeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="e1d7b-104">Möglicherweise möchten Sie die Effizienz eines Pakets verbessern, insbesondere bei Paketen, die eine Iteration durch zahlreiche Faltfiles durchführen. Dazu können Sie die Dateien auslassen, die keine Datenzeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="e1d7b-105">Der Skripttask kann nach leeren Flatfiles suchen, bevor das Paket mit der Verarbeitung des Datenflusses beginnt.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1d7b-106">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="e1d7b-107">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="e1d7b-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="e1d7b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1d7b-108">Description</span></span>  
 <span data-ttu-id="e1d7b-109">Im folgenden Beispiel wird mithilfe von Methoden des `System.IO`-Namespace das in einem Verbindungs-Manager für Flatfiles angegebene Flatfile getestet, um zu ermitteln, ob die Datei leer ist oder ob sie nur erwartete Nichtdatenzeilen wie z. B. Spaltenkopfzeilen oder eine leere Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="e1d7b-110">Das Skript prüft zuerst die Größe der Datei; bei einer Größe von 0 (null) Bytes ist die Datei leer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="e1d7b-111">Ist die Datei größer als 0 (null), liest das Skript die Zeilen aus der Datei so lange, bis keine weiteren Zeilen mehr vorhanden sind, oder bis die Anzahl der Zeilen höher ist als die erwartete Anzahl der Nichtdatenzeilen.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="e1d7b-112">Ist die Anzahl der Zeilen der Datei kleiner oder gleich der erwarteten Anzahl der Nichtdatenzeilen, dann wird davon ausgegangen, dass die Datei leer ist.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="e1d7b-113">Das Ergebnis wird dann als boolescher Wert in einer Benutzervariablen zurückgegeben, deren Wert für die Verzweigung in der Paketablaufsteuerung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="e1d7b-114">Die- `FireInformation` Methode zeigt das Ergebnis auch im **Ausgabe** Fenster der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) an.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="e1d7b-115">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="e1d7b-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="e1d7b-116">Erstellen und konfigurieren Sie einen Flatfile-Verbindungs-Manager mit dem Namen `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="e1d7b-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="e1d7b-117">Erstellen Sie eine ganzzahlige Variable mit dem Namen `FFNonDataRows` und legen sie ihren Wert auf die Anzahl der in der Flatfile erwarteten Nichtdatenzeilen fest.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="e1d7b-118">Erstellen Sie eine boolesche Variable mit dem Namen `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="e1d7b-119">Fügen Sie die `FFNonDataRows`-Variable der Eigenschaft **ReadOnlyVariables** des Skripttasks hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="e1d7b-120">Fügen Sie die `FFIsEmpty`-Variable der Eigenschaft **ReadWriteVariables** des Skripttasks hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="e1d7b-121">Importieren Sie in Ihrem Code den `System.IO`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="e1d7b-122">Bei der Iteration durch Dateien mit einem Foreach-Schleifen-Editor müssen Sie anstelle der Verwendung eines einzelnen Flatfile-Verbindungs-Managers den unten aufgeführten Beispielcode ändern, um den Namen und Pfad der Datei von der Variable, in der der Enumerationswert gespeichert ist, und nicht vom Verbindungsmanager, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e1d7b-123">Code</span><span class="sxs-lookup"><span data-stu-id="e1d7b-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="e1d7b-124">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="e1d7b-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e1d7b-125">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="e1d7b-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e1d7b-126">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="e1d7b-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e1d7b-127">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d7b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1d7b-128">See Also</span></span>  
 [<span data-ttu-id="e1d7b-129">Skripttask-Beispiele</span><span class="sxs-lookup"><span data-stu-id="e1d7b-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
