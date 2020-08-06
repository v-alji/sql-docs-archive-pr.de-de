---
title: Suchen installierter Drucker mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721634"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="1d1c5-102">Suchen installierter Drucker mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1d1c5-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="1d1c5-103">Die Daten, die von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen transformiert werden, weisen oft einen gedruckten Bericht als abschließendes Ziel auf.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="1d1c5-104">Der- `System.Drawing.Printing` Namespace in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stellt Klassen zum Arbeiten mit Druckern bereit.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="1d1c5-105">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="1d1c5-106">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="1d1c5-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="1d1c5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1d1c5-107">Description</span></span>
 <span data-ttu-id="1d1c5-108">Im folgenden Beispiel werden auf dem Server installierte Drucker gesucht, die Papier im Legal-Format, wie es in den USA verwendet wird, unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="1d1c5-109">Der Code, um unterstützte Papierformate zu überprüfen, wird in einer privaten Funktion gekapselt.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="1d1c5-110">Damit Sie den Prozess verfolgen können, den das Skript beim Überprüfen der Einstellungen der einzelnen Drucker durchläuft, verwendet das Skript die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>-Methode, um eine Informationsmeldung von Druckern mit Papier im Legal-Format sowie eine Warnung von Druckern ohne dieses Papierformat auszulösen.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="1d1c5-111">Diese Meldungen werden im IDE-Fenster **Ausgabe** der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) angezeigt, wenn Sie das Paket im Designer ausführen.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="1d1c5-112">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="1d1c5-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="1d1c5-113">Erstellen Sie die Variable namens `PrinterList` mit dem Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="1d1c5-114">Fügen Sie auf der Seite **Skript** im **Skripttask-Editor** diese Variable der ReadWriteVariables-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="1d1c5-115">Fügen Sie im Skriptprojekt dem **System.Drawing**-Namespace einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="1d1c5-116">Verwenden Sie im Code `Imports` -Anweisungen, um die **System. Collections** und die `System.Drawing.Printing` Namespaces zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="1d1c5-117">Code</span><span class="sxs-lookup"><span data-stu-id="1d1c5-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="1d1c5-118">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="1d1c5-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1d1c5-119">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="1d1c5-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1d1c5-120">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="1d1c5-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1d1c5-121">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1d1c5-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d1c5-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d1c5-122">See Also</span></span>
 [<span data-ttu-id="1d1c5-123">Skripttask-Beispiele</span><span class="sxs-lookup"><span data-stu-id="1d1c5-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


