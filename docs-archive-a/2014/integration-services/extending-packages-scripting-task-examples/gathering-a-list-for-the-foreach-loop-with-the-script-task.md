---
title: Erfassen einer Liste für die ForEach-Schleife mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696993"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="a203b-102">Erfassen einer Liste für die ForEach-Schleife mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="a203b-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="a203b-103">Der Foreach-Enumerator für Daten aus Variable führt die Elemente in einer Liste auf, die ihm in einer Variablen übergeben wird, und führt für alle Elemente dieselben Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="a203b-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="a203b-104">Sie können benutzerdefinierten Code in einem Skripttask verwenden, um eine Liste für diesen Zweck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a203b-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="a203b-105">Weitere Informationen zum Enumerator finden Sie unter [Foreach Loop Container](../control-flow/foreach-loop-container.md) (Foreach-Schleifencontainer).</span><span class="sxs-lookup"><span data-stu-id="a203b-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a203b-106">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a203b-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="a203b-107">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="a203b-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="a203b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a203b-108">Description</span></span>  
 <span data-ttu-id="a203b-109">Im folgenden Beispiel werden Methoden des `System.IO`-Namespace verwendet, um eine Liste von Excel-Arbeitsmappen auf dem Computer zu sammeln, die älter oder neuer als eine vom Benutzer in der Variablen definierte Anzahl von Tagen sind.</span><span class="sxs-lookup"><span data-stu-id="a203b-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="a203b-110">Verzeichnisse des Laufwerks C werden rekursiv nach Dateien durchsucht, die eine .xls-Erweiterung aufweisen. Anschließend wird das Datum der letzten Änderung der Datei überprüft, um festzustellen, ob die Datei in die Liste gehört.</span><span class="sxs-lookup"><span data-stu-id="a203b-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="a203b-111">Geeignete Dateien werden einer `ArrayList` hinzugefügt, und die `ArrayList` wird für die spätere Verwendung in einem Foreach-Schleifencontainer in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a203b-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="a203b-112">Der Foreach-Schleifencontainer wird für die Verwendung des Foreach-Enumerators für Daten aus Variable konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a203b-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a203b-113">Variablen, die Sie mit dem Foreach-Enumerator für Daten aus Variable verwenden, müssen den Typ `Object` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a203b-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="a203b-114">Objekte, die Sie in den Variablen platzieren, müssen eine der folgenden Schnittstellen implementieren: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource` oder `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span><span class="sxs-lookup"><span data-stu-id="a203b-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="a203b-115">Häufig wird ein `Array` oder eine `ArrayList` verwendet.</span><span class="sxs-lookup"><span data-stu-id="a203b-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="a203b-116">Die `ArrayList` erfordert einen Verweis und eine `Imports`-Anweisung für den `System.Collections`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a203b-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="a203b-117">Sie können mit diesem Task experimentieren, indem Sie verschiedene positive und negative Werte für die Paketvariable `FileAge` einsetzen.</span><span class="sxs-lookup"><span data-stu-id="a203b-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="a203b-118">Sie können z. B. den Wert 5 eingeben, um nach Dateien zu suchen, die in den letzten fünf Tagen erstellt wurden, oder den Wert -3 für Dateien, die vor mehr als drei Tagen angelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="a203b-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="a203b-119">Diese Aufgabe kann bei Laufwerken, die viele zu durchsuchende Ordner enthalten, ein bis zwei Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="a203b-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="a203b-120">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="a203b-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="a203b-121">Erstellen Sie eine Paketvariable vom Typ integer mit dem Namen `FileAge`, und geben Sie einen positiven oder negativen ganzzahligen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="a203b-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="a203b-122">Ist der Wert positiv, sucht der Code nach Dateien, die neuer als die angegebene Anzahl von Tagen ist. Bei negativen Werten wird nach Dateien gesucht, die älter als die genannte Anzahl von Tagen sind.</span><span class="sxs-lookup"><span data-stu-id="a203b-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="a203b-123">Erstellen Sie eine Paketvariable vom Typ `Object` mit dem Namen `FileList`, um zur späteren Verwendung mit dem Foreach-Enumerator für Daten aus Variable die Liste der Dateien aufzunehmen, die vom Skripttask erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="a203b-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="a203b-124">Fügen Sie die `FileAge`-Variable der `ReadOnlyVariables`-Eigenschaft des Skripttasks sowie die `FileList`-Variable der `ReadWriteVariables`-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="a203b-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="a203b-125">Importieren Sie in Ihren Code die Namespaces `System.Collections` und `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="a203b-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a203b-126">Code</span><span class="sxs-lookup"><span data-stu-id="a203b-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="a203b-127">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a203b-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a203b-128">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a203b-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a203b-129">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a203b-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a203b-130">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a203b-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a203b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a203b-131">See Also</span></span>  
 <span data-ttu-id="a203b-132">[Foreach-Schleifen Container](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="a203b-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="a203b-133">Konfigurieren eines Foreach-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="a203b-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  
