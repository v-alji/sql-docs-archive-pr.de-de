---
title: Senden mit dem Skripttask an eine private Remotemeldungswarteschlange | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701294"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="04865-102">Senden mit dem Skripttask an eine private Remotemeldungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="04865-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="04865-103">Message Queuing (auch als MSMQ bezeichnet) bietet Entwicklern eine einfache Möglichkeit, durch das Senden und Empfangen von Meldungen schnell und zuverlässig mit Anwendungshilfsprogrammen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="04865-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="04865-104">Meldungswarteschlangen können sich auf einem lokalen oder einem Remotecomputer befinden und öffentlich oder privat sein.</span><span class="sxs-lookup"><span data-stu-id="04865-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="04865-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] unterstützen der MSMQ-Verbindungs-Manager und der Task Nachrichtenwarteschlange das Senden an eine private Warteschlange auf einem Remotecomputer nicht.</span><span class="sxs-lookup"><span data-stu-id="04865-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="04865-106">Mit dem Skripttask können Meldungen jedoch ganz einfach an eine private Remotewarteschlange gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="04865-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04865-107">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="04865-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="04865-108">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="04865-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="04865-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04865-109">Description</span></span>  
 <span data-ttu-id="04865-110">Im folgenden Beispiel werden ein vorhandener MSMQ-Verbindungs-Manager sowie Objekte und Methoden des System.Messaging-Namespace verwendet, um in einer Paketvariablen enthaltenen Text an eine private Remotemeldungswarteschlange zu senden.</span><span class="sxs-lookup"><span data-stu-id="04865-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="04865-111">Der Aufrufe der M:Microsoft.SqlServer.DTS.ManagedConnections.MSMQConn.AcquireConnection (System. Object)-Methode des MSMQ-Verbindungs-Managers gibt ein **MessageQueue** -Objekt zurück, dessen- `Send` Methode diese Aufgabe erfüllt.</span><span class="sxs-lookup"><span data-stu-id="04865-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="04865-112">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="04865-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="04865-113">Erstellen Sie einen MSMQ-Verbindungs-Manager mit dem Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="04865-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="04865-114">Geben Sie den Pfad einer gültigen privaten Remotewarteschlange im folgenden Format an:</span><span class="sxs-lookup"><span data-stu-id="04865-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="04865-115">Erstellen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Sie eine Variable namens **MessageText** des Typs `String` , um den Meldungs Text an das Skript zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="04865-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="04865-116">Geben Sie eine Standardmeldung als Wert der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="04865-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="04865-117">Fügen Sie der Entwurfsoberfläche einen Skripttask hinzu, und bearbeiten Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="04865-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="04865-118">Um die Variable im Skript verfügbar zu machen, fügen Sie die `MessageText`-Variable im **Scripttask-Editor** auf der Registerkarte **Skript** der **ReadOnlyVariables**-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="04865-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="04865-119">Klicken Sie auf **Skript bearbeiten**, um den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Tools für Anwendungen-Skript-Editor (VSTA) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04865-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="04865-120">Fügen Sie zum `System.Messaging`-Namespace einen Verweis im Skriptprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="04865-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="04865-121">Ersetzen Sie den Inhalt des Skriptfensters durch den Code im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="04865-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="04865-122">Code</span><span class="sxs-lookup"><span data-stu-id="04865-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="04865-123">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="04865-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="04865-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="04865-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="04865-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="04865-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="04865-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="04865-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04865-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04865-127">See Also</span></span>  
 [<span data-ttu-id="04865-128">Nachrichtenwarteschlange (Task)</span><span class="sxs-lookup"><span data-stu-id="04865-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
