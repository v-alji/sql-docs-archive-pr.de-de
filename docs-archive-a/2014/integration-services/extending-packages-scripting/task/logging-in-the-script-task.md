---
title: Protokollieren im Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- logs [Integration Services], scripts
- Integration Services packages, logs
- Log method
- SSIS Script task, logs
- Script task [Integration Services], logs
- packages [Integration Services], logs
ms.assetid: 2e11fc15-df18-4309-bd2d-fc58aa4b9b7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61f7a46088de5df2765d860bd4a43e4872a1be6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700035"
---
# <a name="logging-in-the-script-task"></a><span data-ttu-id="0611b-102">Protokollieren im Skripttask</span><span class="sxs-lookup"><span data-stu-id="0611b-102">Logging in the Script Task</span></span>
  <span data-ttu-id="0611b-103">Durch Verwendung der Protokollierung in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Paketen können Sie detaillierte Informationen über Status, Ergebnisse und Probleme der Ausführung aufzeichnen, indem Sie vordefinierte Ereignisse bzw. benutzerdefinierte Meldungen für die spätere Analyse erfassen.</span><span class="sxs-lookup"><span data-stu-id="0611b-103">The use of logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you record detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="0611b-104">Der Skripttask kann die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>-Methode des `Dts`-Objekts verwenden, um benutzerdefinierte Daten zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="0611b-104">The Script task can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method of the `Dts` object to log user-defined data.</span></span> <span data-ttu-id="0611b-105">Wenn die Protokollierung aktiviert ist und im Dialogfeld **SSIS-Protokolle konfigurieren** auf der Registerkarte **Details** das **ScriptTaskLogEntry**-Ereignis für die Protokollierung ausgewählt ist, dann speichert ein einzelner Aufruf der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>-Methode die Ereignisinformationen in allen Protokollanbietern, die für den Task konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="0611b-105">If logging is enabled, and the **ScriptTaskLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method stores the event information in all the log providers configured for the task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0611b-106">Obwohl Sie Protokollierungen direkt vom Skripttask aus ausführen können, ist ggf. eine Implementierung von Ereignissen einer Protokollierung vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="0611b-106">Although you can perform logging directly from your Script task, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="0611b-107">Bei der Verwendung von Ereignissen können Sie nicht nur die Protokollierung von Ereignismeldungen aktivieren, sondern auch mit standardmäßigen oder benutzerdefinierten Ereignishandlern auf das Ereignis reagieren.</span><span class="sxs-lookup"><span data-stu-id="0611b-107">When using events, not only can you enable the logging of event messages, but you can also respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="0611b-108">Weitere Informationen zur Protokollierung finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="0611b-108">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
## <a name="logging-example"></a><span data-ttu-id="0611b-109">Beispiel für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="0611b-109">Logging Example</span></span>  
 <span data-ttu-id="0611b-110">Im folgenden Beispiel wird die Protokollierung vom Skripttask aus durch Protokollierung eines Werts, der die Anzahl der verarbeiteten Zeilen darstellt, gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0611b-110">The following example demonstrates logging from the Script task by logging a value that represents the number of rows processed.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim rowsProcessed As Integer = 100  
    Dim emptyBytes(0) As Byte  
  
    Try  
        Dts.Log("Rows processed: " & rowsProcessed.ToString, _  
            0, _  
            emptyBytes)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
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
            //  
            int rowsProcessed = 100;  
            byte[] emptyBytes = new byte[0];  
  
            try  
            {  
                Dts.Log("Rows processed: " + rowsProcessed.ToString(), 0, emptyBytes);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                //An error occurred.  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
```  
  
 <span data-ttu-id="0611b-111">}</span><span class="sxs-lookup"><span data-stu-id="0611b-111">}</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="0611b-112">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0611b-112">External Resources</span></span>  
  
<span data-ttu-id="0611b-113">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="0611b-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0611b-114">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="0611b-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0611b-115">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="0611b-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0611b-116">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0611b-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0611b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0611b-117">See Also</span></span>  
 [<span data-ttu-id="0611b-118">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0611b-118">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
