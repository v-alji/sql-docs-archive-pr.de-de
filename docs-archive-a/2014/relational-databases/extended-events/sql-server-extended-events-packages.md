---
title: Pakete für erweiterte Ereignisse von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608658"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="30021-102">Pakete für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="30021-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="30021-103">Ein Paket ist ein Container für Objekte für erweiterte Ereignisse von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30021-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="30021-104">Es gibt drei Arten von Paketen für erweiterte Ereignisse, dazu zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="30021-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="30021-105">package0 - Extended Events-Systemobjekte.</span><span class="sxs-lookup"><span data-stu-id="30021-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="30021-106">Dies ist das Standardpaket.</span><span class="sxs-lookup"><span data-stu-id="30021-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="30021-107">sqlserver - Objekte für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30021-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="30021-108">sqlos - Objekte für das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Betriebssystem (SQLOS).</span><span class="sxs-lookup"><span data-stu-id="30021-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30021-109">Das SecAudit-Paket wird von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit verwendet.</span><span class="sxs-lookup"><span data-stu-id="30021-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="30021-110">Kein Objekt im Paket ist über die Datendefinitionssprache (Data Definition Language, DDL) für erweiterte Ereignisse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30021-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="30021-111">Pakete werden durch einen Namen, eine GUID und das binäre Modul identifiziert, in dem das Paket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="30021-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="30021-112">Weitere Informationen finden Sie unter [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30021-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="30021-113">Ein Paket kann eines oder alle der folgenden Objekte enthalten. Eine detailliertere Beschreibung der Objekte finden Sie weiter unten in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="30021-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="30021-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="30021-114">Events</span></span>  
  
-   <span data-ttu-id="30021-115">Ziele</span><span class="sxs-lookup"><span data-stu-id="30021-115">Targets</span></span>  
  
-   <span data-ttu-id="30021-116">Aktionen</span><span class="sxs-lookup"><span data-stu-id="30021-116">Actions</span></span>  
  
-   <span data-ttu-id="30021-117">Typen</span><span class="sxs-lookup"><span data-stu-id="30021-117">Types</span></span>  
  
-   <span data-ttu-id="30021-118">Prädikate</span><span class="sxs-lookup"><span data-stu-id="30021-118">Predicates</span></span>  
  
-   <span data-ttu-id="30021-119">Karten</span><span class="sxs-lookup"><span data-stu-id="30021-119">Maps</span></span>  
  
 <span data-ttu-id="30021-120">Objekte aus verschiedenen Paketen können in einer Ereignissitzung gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="30021-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="30021-121">Weitere Informationen finden Sie unter [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="30021-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="30021-122">Paketinhalt</span><span class="sxs-lookup"><span data-stu-id="30021-122">Package Contents</span></span>  
 <span data-ttu-id="30021-123">In der folgenden Abbildung werden die Objekte dargestellt, die in den in einem Modul enthaltenen Paketen vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="30021-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="30021-124">Bei einem Modul kann es sich um eine ausführbare Datei oder eine DLL (Dynamic Link Library) handeln.</span><span class="sxs-lookup"><span data-stu-id="30021-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="30021-125">![Die Beziehung zwischen einem Modul, Paketen und einem Objekt](../../database-engine/media/xepackagesobjects.gif "Die Beziehung zwischen einem Modul, Paketen und einem Objekt")</span><span class="sxs-lookup"><span data-stu-id="30021-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="30021-126">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="30021-126">Events</span></span>  
 <span data-ttu-id="30021-127">Mithilfe von Ereignissen werden relevante Punkte im Ausführungspfad eines Programms überwacht, z. B. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30021-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="30021-128">Das Auslösen eines Ereignisses bedeutet immer auch, dass der relevante Punkt erreicht wurde, und liefert Informationen über den Status zu dem Zeitpunkt, an dem das Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="30021-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="30021-129">Ereignisse können ausschließlich für Ablaufverfolgungszwecke oder auslösende Aktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30021-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="30021-130">Diese Aktionen können synchron oder asynchron sein.</span><span class="sxs-lookup"><span data-stu-id="30021-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30021-131">Ein Ereignis hat keine Kenntnis der Aktionen, die in Reaktion auf das Auslösen des Ereignisses ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="30021-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="30021-132">Eine Gruppe von Ereignissen in einem Paket kann nicht geändert werden, nachdem das Paket mit Extended Events registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="30021-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="30021-133">Alle Ereignisse weisen ein versionsspezifisches Schema auf, mit dem der Inhalt definiert wird.</span><span class="sxs-lookup"><span data-stu-id="30021-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="30021-134">Dieses Schema besteht aus Ereignisspalten mit wohldefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="30021-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="30021-135">Ein Ereignis eines bestimmten Typs muss seine Daten stets in genau der Reihenfolge bereitstellen, die im Schema angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="30021-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="30021-136">Allerdings muss ein Ereignisziel nicht alle Daten verarbeiten, die bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="30021-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="30021-137">Ereigniskategorisierung</span><span class="sxs-lookup"><span data-stu-id="30021-137">Event Categorization</span></span>  
 <span data-ttu-id="30021-138">Extended Events verwendet ein Ereigniskategorisierungsmodell ähnlich der Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW).</span><span class="sxs-lookup"><span data-stu-id="30021-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="30021-139">Zwei Ereigniseigenschaften werden für die Kategorisierung verwendet, und zwar Kanal und Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="30021-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="30021-140">Durch die Verwendung dieser Eigenschaften wird die Integration von Extended Events in ETW und die zugehörigen Tools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="30021-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="30021-141">**Kanal**</span><span class="sxs-lookup"><span data-stu-id="30021-141">**Channel**</span></span>  
  
 <span data-ttu-id="30021-142">Ein Kanal identifiziert die Zielgruppe für ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="30021-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="30021-143">Eine Beschreibung zu diesen Kanälen finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="30021-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="30021-144">Begriff</span><span class="sxs-lookup"><span data-stu-id="30021-144">Term</span></span>|<span data-ttu-id="30021-145">Definition</span><span class="sxs-lookup"><span data-stu-id="30021-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="30021-146">Admin</span><span class="sxs-lookup"><span data-stu-id="30021-146">Admin</span></span>|<span data-ttu-id="30021-147">Admin-Ereignisse sind hauptsächlich für Endbenutzer, Administratoren und Supportmitarbeiter vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="30021-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="30021-148">Die Ereignisse, die in den Admin-Kanälen gefunden werden, weisen auf ein Problem mit einer wohldefinierten Lösung hin, zu dessen Behebung ein Administrator Maßnahmen ergreifen kann.</span><span class="sxs-lookup"><span data-stu-id="30021-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="30021-149">Ein Beispiel für ein Admin-Ereignis ist, wenn beim Herstellen einer Verbindung mit einem Drucker ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="30021-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="30021-150">Diese Ereignisse sind entweder umfassend beschrieben oder weisen eine Meldung mit Hinweisen zur Behebung des Fehlers auf.</span><span class="sxs-lookup"><span data-stu-id="30021-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="30021-151">Bei Betrieb</span><span class="sxs-lookup"><span data-stu-id="30021-151">Operational</span></span>|<span data-ttu-id="30021-152">Operational-Ereignisse werden zum Analysieren und Diagnostizieren eines Problems oder eines Vorkommens verwendet.</span><span class="sxs-lookup"><span data-stu-id="30021-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="30021-153">Sie können zum Auslösen von Tools oder Aufgaben anhand des Problems oder des Vorkommens verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30021-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="30021-154">Ein Beispiel für ein solches Ereignis ist, wenn ein Drucker einem System hinzugefügt oder daraus entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="30021-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="30021-155">Analytic</span><span class="sxs-lookup"><span data-stu-id="30021-155">Analytic</span></span>|<span data-ttu-id="30021-156">Analytic-Ereignisse werden in großem Umfang veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="30021-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="30021-157">Sie beschreiben Programmvorgänge und werden in der Regel in Leistungsuntersuchungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="30021-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="30021-158">Debug</span><span class="sxs-lookup"><span data-stu-id="30021-158">Debug</span></span>|<span data-ttu-id="30021-159">Debug-Ereignisse werden ausschließlich von Entwicklern zum Diagnostizieren eines Problems verwendet, das Debuggen erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="30021-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="30021-160">Hinweis: Ereignisse im Debug-Kanal geben interne Implementierungs spezifische Zustandsdaten zurück.</span><span class="sxs-lookup"><span data-stu-id="30021-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="30021-161">Die Schemas und Daten, die die von den Ereignissen zurückgegeben werden, werden in künftigen Versionen von SQL Server möglicherweise geändert oder werden ungültig.</span><span class="sxs-lookup"><span data-stu-id="30021-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="30021-162">Daher werden Ereignisse im Debug-Kanal in künftigen Versionen von SQL Server unter Umständen ohne vorherigen Hinweis geändert oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="30021-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="30021-163">**Schlüsselwort**</span><span class="sxs-lookup"><span data-stu-id="30021-163">**Keyword**</span></span>  
  
 <span data-ttu-id="30021-164">Ein Schlüsselwort ist anwendungsspezifisch und ermöglicht eine differenziertere Gruppierung ähnlicher Ereignisse. Auf diese Weise wird das Angeben und Abrufen eines Ereignisses zum Verwenden in einer Sitzung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="30021-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="30021-165">Mithilfe der folgenden Abfrage können Sie Schlüsselwortinformationen abrufen.</span><span class="sxs-lookup"><span data-stu-id="30021-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="30021-166">Schlüsselwörter weisen eine hohe Übereinstimmung mit der aktuellen Gruppierung von Ereignissen der SQL-Ablaufverfolgung auf.</span><span class="sxs-lookup"><span data-stu-id="30021-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="30021-167">Ziele</span><span class="sxs-lookup"><span data-stu-id="30021-167">Targets</span></span>  
 <span data-ttu-id="30021-168">Ziele sind Ereignisconsumer.</span><span class="sxs-lookup"><span data-stu-id="30021-168">Targets are event consumers.</span></span> <span data-ttu-id="30021-169">Ziele verarbeiten Ereignisse entweder synchron für den Thread, der das Ereignis auslöst, oder asynchron für einen vom System bereitgestellten Thread.</span><span class="sxs-lookup"><span data-stu-id="30021-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="30021-170">Erweiterte Ereignisse stellt mehrere Ziele zur Verfügung, mit denen Sie die Ereignisausgabe lenken können.</span><span class="sxs-lookup"><span data-stu-id="30021-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="30021-171">Weitere Informationen finden Sie unter [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="30021-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="30021-172">Aktionen</span><span class="sxs-lookup"><span data-stu-id="30021-172">Actions</span></span>  
 <span data-ttu-id="30021-173">Eine Aktion ist eine programmgesteuerte Reaktion oder Folge von Reaktionen auf ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="30021-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="30021-174">Aktionen sind an ein Ereignis gebunden, und jedes Ereignis kann eine eindeutige Gruppe von Aktionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="30021-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30021-175">Aktionen, die für eine bestimmte Gruppe von Ereignissen bestimmt sind, können nicht an unbekannte Ereignisse gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="30021-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="30021-176">Eine an ein Ereignis gebundene Aktion wird synchron für den Thread aufgerufen, der das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="30021-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="30021-177">Es gibt zahlreiche Typen von Aktionen, die alle eine Vielzahl von Funktionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="30021-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="30021-178">Aktionen können folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="30021-178">Actions can:</span></span>  
  
-   <span data-ttu-id="30021-179">Aufzeichnen eines Stapeldumps und Überprüfen von Daten</span><span class="sxs-lookup"><span data-stu-id="30021-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="30021-180">Speichern von Statusinformationen in einem lokalen Kontext mithilfe der variablen Speicherung</span><span class="sxs-lookup"><span data-stu-id="30021-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="30021-181">Aggregieren von Ereignisdaten</span><span class="sxs-lookup"><span data-stu-id="30021-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="30021-182">Anfügen von Daten an Ereignisdaten</span><span class="sxs-lookup"><span data-stu-id="30021-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="30021-183">Nachfolgend werden typische und bekannte Beispiele für Aktionen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="30021-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="30021-184">Stapeldumper</span><span class="sxs-lookup"><span data-stu-id="30021-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="30021-185">Ausführungsplanerkennung (nur[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="30021-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="30021-186">Stapelauflistung (nur[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="30021-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="30021-187">Ausführen von Zeitstatistikberechnungen</span><span class="sxs-lookup"><span data-stu-id="30021-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="30021-188">Sammeln von Benutzereingaben bei Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="30021-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="30021-189">Prädikate</span><span class="sxs-lookup"><span data-stu-id="30021-189">Predicates</span></span>  
 <span data-ttu-id="30021-190">Prädikate sind eine Gruppe logischer Regeln, mit denen Ereignisse während ihrer Verarbeitung ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="30021-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="30021-191">Dadurch kann der Extended Events-Benutzer anhand bestimmter Kriterien ausgewählte Ereignisdaten erfassen.</span><span class="sxs-lookup"><span data-stu-id="30021-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="30021-192">Prädikate können Daten in einem lokalen Kontext speichern, mit dem Prädikate erstellt werden können, die alle *n* Minuten oder alle *n* Male, dass ein Ereignis ausgelöst wird, den Wert TRUE zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="30021-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="30021-193">Durch das Speichern in lokalem Kontext kann das Prädikat zudem dynamisch aktualisiert werden, wodurch ein zukünftiges Auslösen von Ereignissen unterdrückt werden kann, wenn die Ereignisse ähnliche Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="30021-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="30021-194">Prädikate können Kontextinformationen wie die Thread-ID sowie ereignisspezifische Daten abrufen.</span><span class="sxs-lookup"><span data-stu-id="30021-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="30021-195">Prädikate werden als vollständige boolesche Ausdrücke ausgewertet und unterstützen Kurzschlussoperationen am ersten Punkt, an dem der gesamte Ausdruck mit FALSE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="30021-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30021-196">Prädikate mit Nebeneffekten können ggf. nicht ausgewertet werden, wenn bei einer vorherigen Prädikatüberprüfung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="30021-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="30021-197">Typen</span><span class="sxs-lookup"><span data-stu-id="30021-197">Types</span></span>  
 <span data-ttu-id="30021-198">Da es sich bei Daten um eine Auflistung aneinandergereihter Bytes handelt, werden zum Interpretieren der Daten die Länge und die Eigenschaften der Byte-Auflistung benötigt.</span><span class="sxs-lookup"><span data-stu-id="30021-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="30021-199">Diese Informationen werden im Typ-Objekt gekapselt.</span><span class="sxs-lookup"><span data-stu-id="30021-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="30021-200">Die folgenden Typen werden für Paketobjekte bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="30021-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="30021-201">event</span><span class="sxs-lookup"><span data-stu-id="30021-201">event</span></span>  
  
-   <span data-ttu-id="30021-202">action</span><span class="sxs-lookup"><span data-stu-id="30021-202">action</span></span>  
  
-   <span data-ttu-id="30021-203">target</span><span class="sxs-lookup"><span data-stu-id="30021-203">target</span></span>  
  
-   <span data-ttu-id="30021-204">pred_source</span><span class="sxs-lookup"><span data-stu-id="30021-204">pred_source</span></span>  
  
-   <span data-ttu-id="30021-205">pred_compare</span><span class="sxs-lookup"><span data-stu-id="30021-205">pred_compare</span></span>  
  
-   <span data-ttu-id="30021-206">Typ</span><span class="sxs-lookup"><span data-stu-id="30021-206">type</span></span>  
  
 <span data-ttu-id="30021-207">Weitere Informationen finden Sie unter [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30021-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="30021-208">Karten</span><span class="sxs-lookup"><span data-stu-id="30021-208">Maps</span></span>  
 <span data-ttu-id="30021-209">In einer Zuordnungstabelle wird ein interner Wert einer Zeichenfolge zugeordnet, sodass der Benutzer erkennt, was durch den Wert dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="30021-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="30021-210">Statt lediglich eines numerischen Werts erhält der Benutzer eine aussagekräftige Beschreibung des internen Werts.</span><span class="sxs-lookup"><span data-stu-id="30021-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="30021-211">In der folgenden Abfrage wird dargestellt, wie Zuordnungswerte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30021-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="30021-212">Die vorhergehende Abfrage erzeugt die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="30021-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="30021-213">Ausgehend von dieser Tabelle wird als Beispiel eine Spalte mit dem Namen mode und dem Wert 5 angenommen.</span><span class="sxs-lookup"><span data-stu-id="30021-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="30021-214">Die Tabelle gibt an, dass 5 zu X zugeordnet wird. Das bedeutet, dass der Sperrentyp Exclusive ist.</span><span class="sxs-lookup"><span data-stu-id="30021-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30021-215">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30021-215">See Also</span></span>  
 <span data-ttu-id="30021-216">[SQL Server Sitzungen für erweiterte Ereignisse](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="30021-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="30021-217">[SQL Server-Engine für erweiterte Ereignisse](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="30021-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="30021-218">Ziele für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="30021-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
