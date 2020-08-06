---
title: Überwachen von Leistungsindikatoren mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721610"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="40e22-102">Überwachen von Leistungsindikatoren mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="40e22-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="40e22-103">Administratoren müssen möglicherweise die Leistung von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen überwachen, die komplexe Transformationen mit großen Datenmengen durchführen.</span><span class="sxs-lookup"><span data-stu-id="40e22-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="40e22-104">Der Namespace **System.Diagnostics** von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stellt Klassen zur Verwendung vorhandener sowie zur Erstellung eigener Leistungsindikatoren bereit.</span><span class="sxs-lookup"><span data-stu-id="40e22-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="40e22-105">Leistungsindikatoren speichern Leistungsdaten von Anwendungen, anhand derer Sie die Leistung von Software über einen bestimmten Zeitraum analysieren können.</span><span class="sxs-lookup"><span data-stu-id="40e22-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="40e22-106">Leistungsindikatoren können mit dem Tool **Systemmonitor** lokal oder remote überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="40e22-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="40e22-107">Für die spätere Verzweigung der Ablaufsteuerung im Paket können Sie die Werte der Leistungsindikatoren in Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="40e22-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="40e22-108">Als Alternative zu Leistungsindikatoren haben Sie auch die Möglichkeit, das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>-Ereignis über die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>-Eigenschaft des `Dts`-Objekts auszulösen.</span><span class="sxs-lookup"><span data-stu-id="40e22-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="40e22-109">Das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>-Ereignis gibt sowohl inkrementelle Status- als auch abgeschlossene Prozentsatzinformationen an die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Laufzeit zurück.</span><span class="sxs-lookup"><span data-stu-id="40e22-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40e22-110">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="40e22-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="40e22-111">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="40e22-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="40e22-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40e22-112">Description</span></span>  
 <span data-ttu-id="40e22-113">Im folgenden Beispiel wird ein benutzerdefinierter Leistungsindikator erstellt und anschließend inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="40e22-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="40e22-114">Zuerst wird ermittelt, ob der Leistungsindikator bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="40e22-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="40e22-115">Falls der Leistungsindikator noch nicht erstellt wurde, ruft das Skript die `Create`-Methode des `PerformanceCounterCategory`-Objekts auf, um ihn zu generieren.</span><span class="sxs-lookup"><span data-stu-id="40e22-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="40e22-116">Anschließend inkrementiert das Skript den Leistungsindikator.</span><span class="sxs-lookup"><span data-stu-id="40e22-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="40e22-117">Zum Abschluss wird die `Close`-Methode für den Leistungsindikator aufgerufen, sobald dieser nicht mehr benötigt wird (bewährte Methode).</span><span class="sxs-lookup"><span data-stu-id="40e22-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40e22-118">Zum Erstellen einer neuen Leistungsindikatorkategorie und eines Leistungsindikators sind Administratorrechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40e22-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="40e22-119">Außerdem bleiben die neue Kategorie und der Leistungsindikator nach der Erstellung auf dem Computer erhalten.</span><span class="sxs-lookup"><span data-stu-id="40e22-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="40e22-120">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="40e22-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="40e22-121">Verwenden Sie eine- `Imports` Anweisung im Code, um den **System. Diagnostics** -Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="40e22-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="40e22-122">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="40e22-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="40e22-123">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="40e22-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="40e22-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="40e22-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="40e22-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="40e22-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="40e22-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40e22-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
