---
title: Überwachen und Reagieren auf Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699182"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="4b7fc-102">Überwachen und Reagieren auf Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4b7fc-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4b7fc-103">Der-Agent kann Ereignisse überwachen und automatisch auf *Ereignisse*reagieren, wie z. b. Nachrichten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , bestimmte Leistungsbedingungen und Windows-Verwaltungsinstrumentation (WMI)-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b7fc-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4b7fc-104">In This Section</span></span>  
 [<span data-ttu-id="4b7fc-105">Warnungen</span><span class="sxs-lookup"><span data-stu-id="4b7fc-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="4b7fc-106">Enthält Informationen zum Benennen von Warnungen und Auswählen von Ereignissen oder Leistungsbedingungen, für die Warnungen ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="4b7fc-107">Erstellen eines benutzerdefinierten Ereignisses</span><span class="sxs-lookup"><span data-stu-id="4b7fc-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="4b7fc-108">Enthält Informationen zum Erstellen von Ereignissen, die nicht von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]vordefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4b7fc-109">Operatoren</span><span class="sxs-lookup"><span data-stu-id="4b7fc-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="4b7fc-110">Enthält Informationen zum Erstellen von Aliasen für Administratoren, die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zum Versenden von Benachrichtigungen verwendet werden können, wenn Aufträge einen Fehler erzeugen oder erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="4b7fc-111">Informationen zum Überwachen von und Reagieren auf Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4b7fc-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="4b7fc-112">Automatische Reaktionen auf Ereignisse werden als *Warnungen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="4b7fc-113">Sie können Warnungen für Ereignisse definieren um anzugeben, wie vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent auf das Auftreten dieser Ereignisse reagiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="4b7fc-114">Von einer Warnung kann auf ein Ereignis reagiert werden, indem ein Administrator benachrichtigt oder ein Auftrag ausgeführt wird, oder indem beide Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="4b7fc-115">Von einer Warnung kann ein Ereignis auch an das Microsoft Windows-Anwendungsprotokoll auf einem anderen Computer weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="4b7fc-116">Sie können beispielsweise angeben, dass bei einem Ereignis mit dem Schweregrad 19 sofort ein Operator benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="4b7fc-117">Durch das Definieren von Warnungen können Datenbankadministratoren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]effektiver überwachen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4b7fc-118">Agent reagiert nur auf Ereignisse, für die eine Warnung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="4b7fc-119">Die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zum Überwachen von Ereignissen verwendete Methode hängt vom Typ des Ereignisses ab.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="4b7fc-120">Wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Warnung für einen Leistungsindikator definiert ist, wird der Leistungsindikator direkt vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent überwacht.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="4b7fc-121">Bei einem WMI-Ereignis wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent eine Ereignisabfrage für das WMI-Ereignis registriert.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="4b7fc-122">Um auf Meldungen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu reagieren, wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent das Windows-Anwendungsprotokoll überwacht.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4b7fc-123">Agent kann nur auf Meldungen reagieren, die in diesem Protokoll aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="4b7fc-124">Standardmäßig protokolliert SQL Server die folgenden Meldungen im Windows-Anwendungsprotokoll:</span><span class="sxs-lookup"><span data-stu-id="4b7fc-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="4b7fc-125">sysmessages-Fehler des Schweregrades 19 oder höher.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="4b7fc-126">Wenn auch bestimmte sysmessages-Fehler mit einem Schweregrad niedriger als 19 protokolliert werden sollen, verwenden Sie die gespeicherte Prozedur „sp_altermessage“, um solche Fehler als „immer protokolliert“ zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="4b7fc-127">Jede RAISERROR-Anweisung, die durch Verwenden der WITH LOG-Syntax aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="4b7fc-128">Das Verwenden von RAISERROR WITH LOG wird empfohlen, um von einer Instanz von SQL Server in das Windows-Anwendungsprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="4b7fc-129">Jedes mithilfe von „xp_logevent“ protokollierte Anwendungsereignis.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b7fc-130">Das Protokollieren von Anwendungsereignissen belegt Protokollspeicher und kann dazu führen, dass das Windows-Anwendungsprotokoll die Maximalgröße überschreitet.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="4b7fc-131">Stellen Sie sicher, dass das Windows-Anwendungsprotokoll über eine ausreichende Größe verfügt, damit es nicht zu einem Verlust von SQL Server-Ereignisinformationen kommt.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="4b7fc-132">Wenn von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Meldung protokolliert wird, vergleicht der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst die Meldung mit den Warnungen, die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Administrator definiert worden sind.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="4b7fc-133">Unabhängig von der Ereignisquelle reagiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst auf das Ereignis, indem die Tasks ausgeführt werden, die in der Warnung für das Ereignis angegeben worden sind.</span><span class="sxs-lookup"><span data-stu-id="4b7fc-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7fc-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b7fc-134">See Also</span></span>  
 [<span data-ttu-id="4b7fc-135">sp_altermessage &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="4b7fc-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
