---
title: Behandeln von SMO-Ereignissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- events [SMO]
- SQL Server Management Objects, events
- SMO [SQL Server], events
- events [SMO], about events
ms.assetid: b4f120dd-ba78-46ff-99c5-e47effac8544
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7ea438142ac283c5ad19670fa827b5e248e80f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621991"
---
# <a name="handling-smo-events"></a><span data-ttu-id="6d7e5-102">Behandeln von SMO-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="6d7e5-102">Handling SMO Events</span></span>
  <span data-ttu-id="6d7e5-103">Es gibt Serverereignistypen, die über einen Ereignishandler und das <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt abonniert werden können.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-103">There are server event types that can be subscribed to by using an event handler and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
 <span data-ttu-id="6d7e5-104">Viele der Instanzklassen in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) können Ereignisse auslösen, wenn bestimmte Aktionen auf dem Server auftreten.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-104">Many of the instance classes in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) can trigger events when certain actions on the server occur.</span></span>  
  
 <span data-ttu-id="6d7e5-105">Diese Ereignisse können programmgesteuert behandelt werden, indem ein Ereignishandler eingerichtet und ein Abonnement für die zugehörigen Ereignisse vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-105">These events can be handled programmatically by setting up an event handler and subscribing to the associated events.</span></span> <span data-ttu-id="6d7e5-106">Diese Art der Ereignisbehandlung ist vorübergehend, da alle Abonnements gelöscht werden, sobald das SMO-Clientprogramm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-106">This type of event handling is transient because all the subscriptions are removed when the SMO client program exits.</span></span>  
  
## <a name="connectioncontext-event-handling"></a><span data-ttu-id="6d7e5-107">ConnectionContext-Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="6d7e5-107">ConnectionContext Event Handling</span></span>  
 <span data-ttu-id="6d7e5-108">Das <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt unterstützt mehrere Ereignistypen.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-108">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object supports several event types.</span></span> <span data-ttu-id="6d7e5-109">Die Ereigniseigenschaft muss auf die Instanz eines geeigneten Ereignishandlers gesetzt sein, und das Ereignishandlerobjekt muss als geschützte Funktion definiert sein, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-109">The event property must be set to an instance of an appropriate event handler, and the event handler object must be defined as a protected function that handles the event.</span></span>  
  
## <a name="event-subscription"></a><span data-ttu-id="6d7e5-110">Ereignisabonnement</span><span class="sxs-lookup"><span data-stu-id="6d7e5-110">Event Subscription</span></span>  
 <span data-ttu-id="6d7e5-111">Sie behandeln Ereignisse, indem Sie eine Ereignishandlerklasse schreiben, eine Instanz dieser Klasse erstellen, den Ereignishandler dem übergeordneten Objekt zuordnen und dann das Ereignis abonnieren.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-111">You handle events by writing an event handler class, creating an instance of it, assigning the event handler to the parent object, and then subscribing to the event.</span></span>  
  
 <span data-ttu-id="6d7e5-112">Eine Ereignishandlerklasse muss geschrieben werden, um Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-112">An event handler class must be written to handle events.</span></span> <span data-ttu-id="6d7e5-113">Die Ereignishandlerklasse kann mehr als eine Ereignishandlerfunktion enthalten und muss für die zu behandelnden Ereignisse installiert sein.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-113">The event handler class can contain more than one event handler function, and must be installed for the events to be handled.</span></span> <span data-ttu-id="6d7e5-114">Die Ereignishandlerfunktionen empfangen Informationen über das Ereignis vom *ServerEventNotificatificationArgs* -Parameter, der zum Melden von Informationen über das Ereignis verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-114">The event handler functions receive information about the event from the *ServerEventNotificatificationArgs* parameter that can be used to report information about the event.</span></span>  
  
 <span data-ttu-id="6d7e5-115">Die Typen von Datenbank-und Server Ereignissen, die behandelt werden können, sind in der <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> -Klasse und der- <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet> Klasse aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-115">The types of database and server events that can be handled are listed in the <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> class and the <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet>class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d7e5-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d7e5-116">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-basic"></a><span data-ttu-id="6d7e5-117">Registrieren von Ereignishandlern und Abonnieren der Ereignisbehandlung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d7e5-117">Registering Event Handlers and Subscribing to Event Handling in Visual Basic</span></span>  
 <span data-ttu-id="6d7e5-118">Dieses Codebeispiel zeigt, wie der Ereignishandler eingerichtet wird und wie die Datenbankereignisse abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-118">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEvents1](SMO How to#SMO_VBEvents1)]  -->  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-c"></a><span data-ttu-id="6d7e5-119">Registrieren von Ereignishandlern und Abonnieren der Ereignisbehandlung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="6d7e5-119">Registering Event Handlers and Subscribing to Event Handling in Visual C#</span></span>  
 <span data-ttu-id="6d7e5-120">Dieses Codebeispiel zeigt, wie der Ereignishandler eingerichtet wird und wie die Datenbankereignisse abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="6d7e5-120">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
```  
//Create an event handler subroutine that runs when a table is created.   
private void MyCreateEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been added to the AdventureWorks2012 database.");   
}   
//Create an event handler subroutine that runs when a table is deleted.   
private void MyDropEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been dropped from the AdventureWorks2012 database.");   
}   
public void Main()   
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Create a database event set that contains the CreateTable event only.   
DatabaseEventSet databaseCreateEventSet = new DatabaseEventSet();   
databaseCreateEventSet.CreateTable = true;   
//Create a server event handler and set it to the first event handler subroutine.   
ServerEventHandler serverCreateEventHandler;   
serverCreateEventHandler = new ServerEventHandler(MyCreateEventHandler);   
//Subscribe to the first server event handler when a CreateTable event occurs.   
db.Events.SubscribeToEvents(databaseCreateEventSet, serverCreateEventHandler);   
    //Create a database event set that contains the DropTable event only.   
DatabaseEventSet databaseDropEventSet = new DatabaseEventSet();   
databaseDropEventSet.DropTable = true;   
//Create a server event handler and set it to the second event handler subroutine.   
ServerEventHandler serverDropEventHandler;   
serverDropEventHandler = new ServerEventHandler(MyDropEventHandler);   
//Subscribe to the second server event handler when a DropTable event occurs.   
db.Events.SubscribeToEvents(databaseDropEventSet, serverDropEventHandler);   
//Start event handling.   
db.Events.StartEvents();   
//Create a table on the database.   
Table tb;   
tb = new Table(db, "Test_Table");   
Column mycol1;   
mycol1 = new Column(tb, "Name", DataType.NChar(50));   
mycol1.Collation = "Latin1_General_CI_AS";   
mycol1.Nullable = true;   
tb.Columns.Add(mycol1);   
tb.Create();   
//Remove the table.   
tb.Drop();   
//Wait until the events have occured.   
int x;   
int y;   
for (x = 1; x <= 1000000000; x++) {   
    y = x * 2;   
}   
//Stop event handling.   
db.Events.StopEvents();   
}  
```  
  
  
