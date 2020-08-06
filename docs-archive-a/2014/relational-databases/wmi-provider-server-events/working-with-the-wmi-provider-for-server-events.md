---
title: Arbeiten mit dem WMI-Anbieter für Server Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event notifications [WMI]
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- Service Broker [WMI]
- WMI Provider for Server Events, connection strings
- WMI Provider for Server Events, Service Broker
- notifications [WMI]
- WMI Provider for Server Events, security
ms.assetid: cd974b3b-2309-4a20-b9be-7cfc93fc4389
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 79ee9c4402971807263284d10e31db702abeee86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697626"
---
# <a name="working-with-the-wmi-provider-for-server-events"></a><span data-ttu-id="278ea-102">Verwenden des WMI-Anbieters für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="278ea-102">Working with the WMI Provider for Server Events</span></span>
  <span data-ttu-id="278ea-103">Dieses Thema enthält Richtlinien, die Sie vor dem Programmieren mit dem WMI-Anbieter für Serverereignisse lesen sollten.</span><span class="sxs-lookup"><span data-stu-id="278ea-103">This topic provides guidelines you should consider before you program using the WMI Provider for Server Events.</span></span>  
  
## <a name="enabling-service-broker"></a><span data-ttu-id="278ea-104">Aktivieren von Service Broker</span><span class="sxs-lookup"><span data-stu-id="278ea-104">Enabling Service Broker</span></span>  
 <span data-ttu-id="278ea-105">Der WMI-Anbieter für Serverereignisse übersetzt WQL-Abfragen für Ereignisse in Ereignisbenachrichtigungen in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="278ea-105">The WMI Provider for Server Events works by translating WQL queries for events into event notifications in the database that you target.</span></span> <span data-ttu-id="278ea-106">Kenntnisse darüber, wie Ereignisbenachrichtigungen funktionieren, können bei der Programmierung mit dem Anbieter hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="278ea-106">An understanding of how event notifications work can be useful to you when programming against the provider.</span></span> <span data-ttu-id="278ea-107">Weitere Informationen finden Sie unter [Konzepte des WMI-Anbieters für Serverereignisse](https://technet.microsoft.com/library/ms180560.aspx).</span><span class="sxs-lookup"><span data-stu-id="278ea-107">For more information, see [WMI Provider for Server Events Concepts](https://technet.microsoft.com/library/ms180560.aspx).</span></span>  
  
 <span data-ttu-id="278ea-108">Da die vom WMI-Anbieter erstellten Ereignisbenachrichtigungen Meldungen zu Serverereignissen mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senden, muss dieser Dienst aktiviert sein, wenn die Ereignisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="278ea-108">In particular, because the event notifications created by the WMI Provider use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to send messages about server events, this service must be enabled wherever the events are generated.</span></span> <span data-ttu-id="278ea-109">Wenn Ihr Programm Ereignisse in einer Serverinstanz abfragt, muss der [!INCLUDE[ssSB](../../includes/sssb-md.md)] dieser Instanz in msdb aktiviert sein, da dies der Speicherort des [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Zieldiensts (mit dem Namen SQL/Notifications/ProcessWMIEventProviderNotification/v1.0) ist, der vom Anbieter erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="278ea-109">If your program queries events on a server instance, the [!INCLUDE[ssSB](../../includes/sssb-md.md)] in msdb of that instance must be enabled, because that is the location of the target [!INCLUDE[ssSB](../../includes/sssb-md.md)] service (named SQL/Notifications/ProcessWMIEventProviderNotification/v1.0) that is created by the provider.</span></span> <span data-ttu-id="278ea-110">Wenn Ihr Programm Ereignisse in einer Datenbank oder in einem bestimmten Datenbankobjekt abfragt, muss der [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Dienst in dieser Zieldatenbank aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="278ea-110">If your program queries events in a database or on a particular database object, the [!INCLUDE[ssSB](../../includes/sssb-md.md)] in that target database must be enabled.</span></span> <span data-ttu-id="278ea-111">Wenn der entsprechende [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Dienst nach dem Bereitstellen der Anwendung nicht aktiviert wird, werden die von der zugrundeliegenden Ereignisbenachrichtigung generierten Ereignisse an die Warteschlange des von der Ereignisbenachrichtigung verwendeten Diensts gesendet, aber erst nach der Aktivierung des [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Diensts an die WMI-Verwaltungsanwendung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="278ea-111">If the corresponding [!INCLUDE[ssSB](../../includes/sssb-md.md)] is not enabled after your application is deployed, any events generated by the underlying event notification are sent to the queue of the service used by the event notification, but are not returned to your WMI management application until [!INCLUDE[ssSB](../../includes/sssb-md.md)] is enabled.</span></span>  
  
 <span data-ttu-id="278ea-112">Mit der folgenden Abfrage wird bestimmt, welche Service Broker auf einer Serverinstanz aktiviert werden, und die GUID der Broker-Instanz wird festgelegt:</span><span class="sxs-lookup"><span data-stu-id="278ea-112">The following query determines which service brokers are enabled on a server instance, and the broker instance GUID:</span></span>  
  
```  
SELECT name, is_broker_enabled, service_broker_guid FROM sys.databases;  
```  
  
 <span data-ttu-id="278ea-113">Die Service Broker-GUID von msdb ist besonders interessant, da dies der Speicherort des Zieldiensts des Anbieters ist.</span><span class="sxs-lookup"><span data-stu-id="278ea-113">The service broker GUID of msdb is of particular interest because that is the location of the target service of the provider.</span></span>  
  
 <span data-ttu-id="278ea-114">Um [!INCLUDE[ssSB](../../includes/sssb-md.md)] in einer Datenbank zu aktivieren, verwenden Sie die ENABLE_BROKER SET-Option der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="278ea-114">To enable [!INCLUDE[ssSB](../../includes/sssb-md.md)] in a database, use the ENABLE_BROKER SET option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="278ea-115">Angeben einer Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="278ea-115">Specifying a Connection String</span></span>  
 <span data-ttu-id="278ea-116">Anwendungen leiten den WMI-Anbieter für Serverereignisse an eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weiter, indem sie eine Verbindung mit einem vom Anbieter definierten WMI-Namespace herstellen.</span><span class="sxs-lookup"><span data-stu-id="278ea-116">Applications direct the WMI Provider for Server Events to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="278ea-117">Der WMI-Dienst ordnet der Anbieter-DLL Sqlwep.dll diesen Namespace zu und lädt sie in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="278ea-117">The Windows WMI service maps this namespace to the provider DLL, Sqlwep.dll, and loads it into memory.</span></span> <span data-ttu-id="278ea-118">Jede Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügt über einen eigenen WMI-Namespace, der standardmäßig auf festgelegt ist \\ \\ . \\ *root*\microsoft\sqlserver\serverevents \\ *instance_name*.</span><span class="sxs-lookup"><span data-stu-id="278ea-118">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has its own WMI namespace, which defaults to: \\\\.\\*root*\Microsoft\SqlServer\ServerEvents\\*instance_name*.</span></span> <span data-ttu-id="278ea-119">*instance_name* in einer Standardinstallation von standardmäßig auf MSSQLSERVER festgelegt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="278ea-119">*instance_name* defaults to MSSQLSERVER in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="278ea-120">Berechtigungen und Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="278ea-120">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="278ea-121">Um auf den WMI-Anbieter für Serverereignisse zugreifen zu können, muss der Client, von dem eine WMI-Verwaltungsanwendung stammt, dem Windows-authentifizierten Benutzer- oder Gruppennamen in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entsprechen, die in der Verbindungszeichenfolge der Anwendung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="278ea-121">To access the WMI Provider for Server Events, the client on which a WMI management application originates must correspond to Windows authenticated login or group in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specified in the application's connection string of the application.</span></span>  
  
## <a name="permissions-and-event-notification-scope"></a><span data-ttu-id="278ea-122">Berechtigungen und Bereich der Ereignisbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="278ea-122">Permissions and Event Notification Scope</span></span>  
 <span data-ttu-id="278ea-123">Der WMI-Anbieter für Serverereignisse übersetzt WQL-Abfragen in Ereignisbenachrichtigungen in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="278ea-123">The WMI Provider for Server Events translates WQL queries into event notifications in the target database.</span></span> <span data-ttu-id="278ea-124">Daher muss die aufrufende Anwendung über die erforderlichen Mindestberechtigungen für den Zugriff auf den Anbieter sowie über die richtigen Berechtigungen in der Datenbank zum Erstellen der erforderlichen Ereignisbenachrichtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="278ea-124">Because of this, the calling application must have not only the required minimum permissions to access the provider, but must also have the correct permissions in the database to create the required event notifications.</span></span> <span data-ttu-id="278ea-125">Die folgenden Berechtigungen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="278ea-125">The following are the permissions:</span></span>  
  
-   <span data-ttu-id="278ea-126">Zum Erstellen einer Ereignisbenachrichtigung, die sich auf die Datenbank bezieht, ist mindestens die CREATE DATABASE DDL EVENT NOTIFICATION-Berechtigung in der aktuellen Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="278ea-126">To create an event notification that is scoped to the database, at a minimum, CREATE DATABASE DDL EVENT NOTIFICATION permission in the current database is required.</span></span>  
  
-   <span data-ttu-id="278ea-127">Zum Erstellen einer Ereignisbenachrichtigung für eine DDL-Anweisung, die sich auf den Server bezieht, ist mindestens die CREATE DDL EVENT NOTIFICATION-Berechtigung auf dem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="278ea-127">To create an event notification on a DDL statement that is scoped to the server, at a minimum, CREATE DDL EVENT NOTIFICATION permission in the server is required.</span></span>  
  
-   <span data-ttu-id="278ea-128">Zum Erstellen einer Ereignisbenachrichtigung für ein Ablaufverfolgungsereignis ist mindestens die CREATE TRACE EVENT NOTIFICATION-Berechtigung auf dem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="278ea-128">To create an event notification on a trace event, at a minimum, CREATE TRACE EVENT NOTIFICATION permission in the server is required.</span></span>  
  
-   <span data-ttu-id="278ea-129">Zum Erstellen einer Ereignisbenachrichtigung, die sich auf eine Warteschlange bezieht, ist mindestens die ALTER-Berechtigung für die Warteschlange erforderlich.</span><span class="sxs-lookup"><span data-stu-id="278ea-129">To create an event notification that is scoped to a queue, at a minimum, ALTER permission on the queue is required.</span></span>  
  
 <span data-ttu-id="278ea-130">Informationen dazu, wie WQL-Abfragen bezogen werden, finden [Sie unter Verwenden von WQL mit dem WMI-Anbieter für Server Ereignisse](https://technet.microsoft.com/library/ms180524\(v=sql.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="278ea-130">For information about how WQL queries are scoped, see [Using WQL with the WMI Provider for Server Events](https://technet.microsoft.com/library/ms180524\(v=sql.105\).aspx).</span></span>  
  
 <span data-ttu-id="278ea-131">Betrachten Sie zur Darstellung des Bereichs eine WMI-Anbieteranwendung, die die folgende WQL-Abfrage enthält:</span><span class="sxs-lookup"><span data-stu-id="278ea-131">To illustrate scope, consider a WMI Provider application that includes the following WQL query:</span></span>  
  
```  
SELECT * FROM ALTER_TABLE  
WHERE DatabaseName = "AdventureWorks2012"   
    AND SchemaName = "Person"  
    AND ObjectName = "Person"  
    AND ObjectType = "TABLE";  
```  
  
 <span data-ttu-id="278ea-132">Der WMI-Anbieter übersetzt diese Abfrage in eine Ereignisbenachrichtigung, die in der Datenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="278ea-132">The WMI provider translates this query into an event notification that is created in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="278ea-133">Das bedeutet, dass der Aufrufer über die erforderlichen Berechtigungen zum Erstellen einer Ereignisbenachrichtigung dieser Art, insbesondere über die CREATE DATABASE DDL EVENT NOTIFICATION-Berechtigung, in der Datenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="278ea-133">This means that the caller must have the required permissions to create such an event notification, specifically CREATE DATABASE DDL EVENT NOTIFICATION permission in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="278ea-134">Wenn eine WQL-Abfrage eine auf der Serverebene zugewiesene Ereignisbenachrichtigung beispielsweise durch die Ausgabe der Abfrage SELECT \* FROM ALTER_TABLE angibt, muss die aufrufende Anwendung über die Berechtigung CREATE DDL EVENT NOTIFICATION auf Serverebene verfügen.</span><span class="sxs-lookup"><span data-stu-id="278ea-134">If a WQL query specifies an event notification scoped at the server level, for example by issuing the query SELECT \* FROM ALTER_TABLE, the calling application must have the server-level CREATE DDL EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="278ea-135">Serverbezogene Ereignisbenachrichtigungen werden in der master-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="278ea-135">Note that server-scoped event notifications are stored in the master database.</span></span> <span data-ttu-id="278ea-136">Sie können die [sys. server_event_notifications](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql) -Katalog Sicht verwenden, um Ihre Metadaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="278ea-136">You can use the [sys.server_event_notifications](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql) catalog view to see their metadata.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="278ea-137">Der vom WMI-Anbieter (Server, Datenbank oder Objekt) erstellte Bereich der Ereignisbenachrichtigung ist letztlich von dem vom WMI-Anbieter verwendeten Ergebnis der Überprüfung der Berechtigungen abhängig.</span><span class="sxs-lookup"><span data-stu-id="278ea-137">The scope of the event notification that is created by the WMI Provider (server, database, or object) ultimately depends on the outcome of the permissions verification process that is used by the WMI provider.</span></span> <span data-ttu-id="278ea-138">Dies wird durch die Berechtigungen des Benutzers, der den Anbieter aufruft, sowie durch die Überprüfung der abgefragten Datenbank bestimmt.</span><span class="sxs-lookup"><span data-stu-id="278ea-138">This is affected by the permission set of the user that is calling the provider and on the verification of the database that is being queried.</span></span>  
>   
>  <span data-ttu-id="278ea-139">Im vorherigen Beispiel erstellt der Anbieter zunächst eine Ereignisbenachrichtigung, die sich auf die Datenbank bezieht (`ON DATABASE`).</span><span class="sxs-lookup"><span data-stu-id="278ea-139">In the previous example, the provider first tries to create an event notification scoped to the database (`ON DATABASE`).</span></span> <span data-ttu-id="278ea-140">Wenn der Anbieter bestätigt, dass die Datenbank vorhanden ist und dass der Aufrufer über die erforderlichen Berechtigungen zum Erstellen einer Ereignisbenachrichtigung in der Datenbank verfügt, ist die Registrierung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="278ea-140">If the provider verifies that the database exists and that the caller has the required permissions to create an event notification on it, the registration is successful.</span></span> <span data-ttu-id="278ea-141">Wenn die Registrierung nicht erfolgreich ist, erstellt der Anbieter eine Ereignisbenachrichtigung auf dem Server (`ON SERVER`).</span><span class="sxs-lookup"><span data-stu-id="278ea-141">If it is not successful, the provider tries to create an event notification on the server (`ON SERVER`).</span></span> <span data-ttu-id="278ea-142">Wenn diese Registrierung erfolgreich ist, werden alle auf dem Server auftretenden `ALTER_TABLE`-Ereignisse vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozess an den WMI-Dienstprozess gesendet.</span><span class="sxs-lookup"><span data-stu-id="278ea-142">Assuming that this attempt is successful, all `ALTER_TABLE` events that occur on the server are sent from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process to the WMI Service process.</span></span> <span data-ttu-id="278ea-143">Der Anbieter filtert jedoch alle Ereignisse heraus, die nicht für die `AdventureWorks`-Datenbank bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="278ea-143">However, the provider filters out any events that do not apply to the `AdventureWorks` database.</span></span> <span data-ttu-id="278ea-144">Durch diesen Prozess wird der Netzwerkverkehr, der für den Bereich des Ereignisses erforderlich ist, möglicherweise erhöht. Mithilfe dieses Prozesses können Sie jedoch WQL-Abfragen bereits vor dem Erstellen von Datenbanken auf den Datenbanken registrieren und nach dem Erstellen der Datenbank Ereignisdaten empfangen und DDL-Aktivitäten starten.</span><span class="sxs-lookup"><span data-stu-id="278ea-144">Although this process potentially increases the amount of network traffic necessary for the scope of the event, this process also enables you with the flexibility to register WQL queries on databases before they are created, and then receive event data after the database is created and DDL activity starts on it.</span></span>  
  
## <a name="permissions-and-message-verification"></a><span data-ttu-id="278ea-145">Berechtigungen und Meldungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="278ea-145">Permissions and Message Verification</span></span>  
 <span data-ttu-id="278ea-146">Der WMI-Anbieter sendet keine Meldungen für Ereignisbenachrichtigungen, wenn die beiden folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="278ea-146">The WMI Provider does not send messages for event notifications if both of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="278ea-147">Der Benutzer, der die Ereignisbenachrichtigung über den WMI-Anbieter erstellt hat, ist in der Datenbank nicht mehr vorhanden oder verfügt nicht mehr über die erforderliche Berechtigung zum Erstellen einer ähnlichen Ereignisbenachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="278ea-147">The user that created the event notification through the WMI Provider no longer exists in the database, or no longer has the required permission to create a similar event notification.</span></span>  
  
-   <span data-ttu-id="278ea-148">Die Ereignisbenachrichtigungen werden bei folgenden Ereignissen erstellt:</span><span class="sxs-lookup"><span data-stu-id="278ea-148">The event notifications are created on the following events:</span></span>  
  
    -   <span data-ttu-id="278ea-149">DROP_LOGIN</span><span class="sxs-lookup"><span data-stu-id="278ea-149">DROP_LOGIN</span></span>  
  
    -   <span data-ttu-id="278ea-150">ALTER_LOGIN</span><span class="sxs-lookup"><span data-stu-id="278ea-150">ALTER_LOGIN</span></span>  
  
    -   <span data-ttu-id="278ea-151">DROP_USER</span><span class="sxs-lookup"><span data-stu-id="278ea-151">DROP_USER</span></span>  
  
    -   <span data-ttu-id="278ea-152">ALTER_USER</span><span class="sxs-lookup"><span data-stu-id="278ea-152">ALTER_USER</span></span>  
  
    -   <span data-ttu-id="278ea-153">ADD_ROLE_MEMBER</span><span class="sxs-lookup"><span data-stu-id="278ea-153">ADD_ROLE_MEMBER</span></span>  
  
    -   <span data-ttu-id="278ea-154">DROP_ROLE_MEMBER</span><span class="sxs-lookup"><span data-stu-id="278ea-154">DROP_ROLE_MEMBER</span></span>  
  
    -   <span data-ttu-id="278ea-155">ADD_SERVER_ROLE_MEMBER</span><span class="sxs-lookup"><span data-stu-id="278ea-155">ADD_SERVER_ROLE_MEMBER</span></span>  
  
    -   <span data-ttu-id="278ea-156">DROP_SERVER_ROLE_MEMBER</span><span class="sxs-lookup"><span data-stu-id="278ea-156">DROP_SERVER_ROLE_MEMBER</span></span>  
  
    -   <span data-ttu-id="278ea-157">DENY oder REVOKE (Gilt nur für die Berechtigungen ALTER DATABASE, ALTER ANY DATABASE EVENT NOTIFICATION, CREATE DATABASE DDL EVENT NOTIFICATION, CONTROL SERVER, ALTER ANY EVENT NOTIFICATION, CREATE DDL EVENT NOTIFICATION oder CREATE TRACE EVENT NOTIFICATION.)</span><span class="sxs-lookup"><span data-stu-id="278ea-157">DENY or REVOKE (Applies only to ALTER DATABASE, ALTER ANY DATABASE EVENT NOTIFICATION, CREATE DATABASE DDL EVENT NOTIFICATION, CONTROL SERVER, ALTER ANY EVENT NOTIFICATION, CREATE DDL EVENT NOTIFICATION, OR CREATE TRACE EVENT NOTIFICATION permissions.)</span></span>  
  
## <a name="working-with-event-data-on-the-client-side"></a><span data-ttu-id="278ea-158">Verwenden von Ereignisdaten auf der Clientseite</span><span class="sxs-lookup"><span data-stu-id="278ea-158">Working with Event Data on the Client Side</span></span>  
 <span data-ttu-id="278ea-159">Nachdem der WMI-Anbieter für Server Ereignisse die erforderliche Ereignis Benachrichtigung in der Zieldatenbank erstellt hat, sendet die Ereignis Benachrichtigung Ereignisdaten an den Ziel Dienst in msdb mit dem Namen " **SQL/Benachrichtigungen/ProcessWMIEventProviderNotification/v 1.0**".</span><span class="sxs-lookup"><span data-stu-id="278ea-159">After the WMI Provider for Server Events creates the required event notification in the target database, the event notification sends event data to the target service in msdb that is named **SQL/Notifications/ProcessWMIEventProviderNotification/v1.0**.</span></span> <span data-ttu-id="278ea-160">Der Ziel Dienst fügt das Ereignis in eine Warteschlange mit dem `msdb` Namen **WMIEventProviderNotificationQueue**ein.</span><span class="sxs-lookup"><span data-stu-id="278ea-160">The target service puts the event into a queue in `msdb` that is named **WMIEventProviderNotificationQueue**.</span></span> <span data-ttu-id="278ea-161">(Sowohl der Dienst als auch die Warteschlange werden vom Anbieter dynamisch erstellt, wenn er zum ersten Mal eine Verbindung mit herstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .) Der Anbieter liest dann die XML-Ereignisdaten aus dieser Warteschlange und wandelt sie in das Managed Object Format (MOF) um, bevor Sie an die Client Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="278ea-161">(Both the service and the queue are dynamically created by the provider when it first connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].) The provider then reads the XML event data from this queue and transforms it into managed object format (MOF) before returning it to the client application.</span></span> <span data-ttu-id="278ea-162">Die MOF-Daten bestehen aus den Eigenschaften des Ereignisses, das von der WQL-Abfrage als CIM-Classendefinition (Common Information Model) angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="278ea-162">The MOF data is made up of the properties of the event that is requested by the WQL query as a Common Information Model (CIM) class definition.</span></span> <span data-ttu-id="278ea-163">Jede Eigenschaft verfügt über einen entsprechenden CIM-Typ.</span><span class="sxs-lookup"><span data-stu-id="278ea-163">Each property has a corresponding CIM type.</span></span> <span data-ttu-id="278ea-164">Die `SPID`-Eigenschaft wird beispielsweise als CIM-Typ `Sint32` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="278ea-164">For example, the `SPID` property is returned as CIM type `Sint32`.</span></span> <span data-ttu-id="278ea-165">Die CIM-Typen für jede Eigenschaft werden unter jeder Ereignisklasse in den [Klassen und Eigenschaften des WMI-Anbieters für Server Ereignisse](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-classes-and-properties.md)aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="278ea-165">The CIM types for each property are listed under each event class in [WMI Provider for Server Events Classes and Properties](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-classes-and-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278ea-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="278ea-166">See Also</span></span>  
 [<span data-ttu-id="278ea-167">Konzepte des WMI-Anbieters für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="278ea-167">WMI Provider for Server Events Concepts</span></span>](https://technet.microsoft.com/library/ms180560.aspx)  
  
  