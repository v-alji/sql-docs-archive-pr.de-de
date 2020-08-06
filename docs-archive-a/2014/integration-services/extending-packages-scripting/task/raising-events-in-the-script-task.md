---
title: Auslösen von Ereignissen im Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700029"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="cbae2-102">Auslösen von Ereignissen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="cbae2-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="cbae2-103">Ereignisse bieten eine Möglichkeit, Fehler, Warnungen und andere Informationen, wie z. B. den Fortschritt oder Status eines Tasks, an das entsprechende Paket zu melden.</span><span class="sxs-lookup"><span data-stu-id="cbae2-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="cbae2-104">Das Paket stellt Ereignishandler zum Verwalten von Ereignisbenachrichtigungen bereit.</span><span class="sxs-lookup"><span data-stu-id="cbae2-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="cbae2-105">Der Skripttask kann Ereignisse durch Aufrufen der Methoden in der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>-Eigenschaft des `Dts`-Objekts auslösen.</span><span class="sxs-lookup"><span data-stu-id="cbae2-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="cbae2-106">Weitere Informationen zum Umgang von [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Paketen mit Ereignissen finden Sie unter [Integration Services-Ereignishandler &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="cbae2-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="cbae2-107">Ereignisse können in jedem Protokollanbieter protokolliert werden, der im Paket aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cbae2-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="cbae2-108">Protokollanbieter speichern Informationen über Ereignisse in einem Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="cbae2-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="cbae2-109">Der Skripttask kann ebenfalls die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>-Methode verwenden, um Informationen in einem Protokollanbieter zu protokollieren, ohne ein Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="cbae2-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="cbae2-110">Weitere Informationen zur Verwendung der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>-Methode finden Sie unter [Logging in the Script Task](logging-in-the-script-task.md) (Protokollieren im Skripttask).</span><span class="sxs-lookup"><span data-stu-id="cbae2-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="cbae2-111">Um ein Ereignis auszulösen, ruft der Skripttask eine der Methoden auf, die von der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>-Eigenschaft verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cbae2-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="cbae2-112">In der folgenden Tabelle werden die Methoden aufgelistet, die von der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>-Eigenschaft verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cbae2-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="cbae2-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="cbae2-113">Event</span></span>|<span data-ttu-id="cbae2-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbae2-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="cbae2-115">Löst ein benutzerdefiniertes Ereignis im Paket aus.</span><span class="sxs-lookup"><span data-stu-id="cbae2-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="cbae2-116">Informiert das Paket über eine Fehlerbedingung.</span><span class="sxs-lookup"><span data-stu-id="cbae2-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="cbae2-117">Stellt Informationen für den Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="cbae2-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="cbae2-118">Informiert das Paket über den Fortschritt des Tasks.</span><span class="sxs-lookup"><span data-stu-id="cbae2-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="cbae2-119">Gibt einen Wert zurück, der angibt, ob das Paket erfordert, dass der Task vorzeitig geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cbae2-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="cbae2-120">Informiert das Paket darüber, dass der Task einen Status aufweist, der eine Benutzerbenachrichtigung erfordert, bei dem es sich jedoch nicht um eine Fehlerbedingung handelt.</span><span class="sxs-lookup"><span data-stu-id="cbae2-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="cbae2-121">Beispiel für ein Ereignis</span><span class="sxs-lookup"><span data-stu-id="cbae2-121">Events Example</span></span>  
 <span data-ttu-id="cbae2-122">Im folgenden Beispiel wird veranschaulicht, wie Ereignisse innerhalb des Skripttasks ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="cbae2-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="cbae2-123">Im Beispiel wird eine systemeigene Windows-API-Funktion verwendet, um zu bestimmen, ob eine Internetverbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cbae2-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="cbae2-124">Wenn keine Verbindung verfügbar ist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cbae2-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="cbae2-125">Wenn eine potenziell flüchtige Modemverbindung in Gebrauch ist, wird im Beispiel eine Warnung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cbae2-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="cbae2-126">Andernfalls wird die Informationsmeldung zurückgegeben, dass eine Internetverbindung erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="cbae2-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="cbae2-127">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="cbae2-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cbae2-128">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="cbae2-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cbae2-129">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="cbae2-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cbae2-130">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cbae2-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbae2-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbae2-131">See Also</span></span>  
 <span data-ttu-id="cbae2-132">[Integration Services-Ereignishandler &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="cbae2-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="cbae2-133">Hinzufügen eines Ereignishandlers zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="cbae2-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
