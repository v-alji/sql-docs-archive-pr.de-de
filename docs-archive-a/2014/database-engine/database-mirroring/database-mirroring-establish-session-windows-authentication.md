---
title: Einrichten einer Datenbank-Spiegelungs Sitzung mithilfe der Windows-Authentifizierung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609430"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="f3dc1-102">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f3dc1-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="f3dc1-103">Verwenden Sie stattdessen [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3dc1-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="f3dc1-104">Nach der Vorbereitung der Spiegeldatenbank ( [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)) können Sie eine Sitzung zur Datenbankspiegelung beginnen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="f3dc1-105">Die Prinzipal-, Spiegel- und Zeugenserverinstanzen müssen separate Serverinstanzen sein, die auf getrennten Hostsystemen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f3dc1-106">Die Konfiguration der Datenbankspiegelung sollte außerhalb der Spitzenbetriebszeiten durchgeführt werden, da sich die Konfiguration der Spiegelung auf die Leistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3dc1-107">Eine Serverinstanz kann an mehreren gleichzeitigen Datenbank-Spiegelungssitzungen mit den gleichen oder anderen Partnern teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="f3dc1-108">Eine Serverinstanz kann bei manchen Sitzungen als Partner und bei anderen Sitzungen als Zeuge dienen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="f3dc1-109">Auf der Spiegelserverinstanz muss dieselbe Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wie auf der Prinzipalserverinstanz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="f3dc1-110">Die Datenbankspiegelung ist nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3dc1-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3dc1-111">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="f3dc1-112">Darüber hinaus wird die Ausführung auf vergleichbaren Systemen empfohlen, die identische Arbeitsauslastungen bewältigen können.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="f3dc1-113">So richten Sie eine Datenbank-Spiegelungssitzung ein</span><span class="sxs-lookup"><span data-stu-id="f3dc1-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="f3dc1-114">Erstellen Sie die Spiegeldatenbank.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-114">Create the mirror database.</span></span> <span data-ttu-id="f3dc1-115">Weitere Informationen finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="f3dc1-116">Richten Sie die Sicherheit auf jeder Serverinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="f3dc1-117">Jede Serverinstanz in einer Datenbank-Spiegelungssitzung benötigt einen eigenen Datenbank-Spiegelungsendpunkt.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="f3dc1-118">Falls der Endpunkt nicht vorhanden ist, müssen Sie ihn erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3dc1-119">Der für die Datenbankspiegelung von einer Serverinstanz verwendete Authentifizierungstyp ist eine Eigenschaft des Endpunkts der Datenbankspiegelung.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="f3dc1-120">Für die Datenbankspiegelung sind zwei Arten von Transportsicherheit verfügbar: die Windows-Authentifizierung oder die zertifikatbasierte Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="f3dc1-121">Weitere Informationen finden Sie unter [Transport Sicherheit für die Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="f3dc1-122">Stellen Sie sicher, dass auf allen Partnerservern ein Endpunkt für die Datenbankspiegelung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="f3dc1-123">Unabhängig von der Anzahl der zu unterstützenden Spiegelungssitzungen darf die Serverinstanz nur einen Endpunkt für die Datenbankspiegelung enthalten.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="f3dc1-124">Wenn Sie diese Serverinstanz in Sitzungen zur Datenbankspiegelung ausschließlich für Partner verwenden möchten, können Sie dem Endpunkt die Rolle Partner zuweisen (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="f3dc1-125">Wenn Sie auch den Server in anderen Datenbank-Spiegelungssitzungen für Zeugen verwenden möchten, weisen Sie dem Endpunkt die Rolle ALL zu.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="f3dc1-126">Zum Ausführen der SET PARTNER-Anweisung muss die Option STATE der Endpunkte beider Partner auf STARTED festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="f3dc1-127">Um zu erfahren, ob eine Serverinstanz einen Endpunkt für die Datenbankspiegelung besitzt, und um Informationen zu Rolle und Status der Serverinstanz zu erhalten, führen Sie auf der Instanz die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f3dc1-128">Ein bereits verwendeter Datenbankspiegelungs-Endpunkt darf nicht neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="f3dc1-129">Wenn ein Endpunkt für die Datenbankspiegelung vorhanden ist und bereits verwendet wird, empfiehlt es sich, diesen Endpunkt auf der Serverinstanz für jede Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="f3dc1-130">Wird ein bereits verwendeter Endpunkt gelöscht, kann dies zum erneuten Starten des Endpunkts führen, wodurch die Verbindungen der vorhandenen Sitzungen gestört werden, was von den anderen Serverinstanzen als Fehler interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="f3dc1-131">Dies ist vor allem im Modus für hohe Sicherheit mit automatischem Failover wichtig, bei dem das Neukonfigurieren des Endpunkts auf einem Partner zur Ausführung eines Failovers führen könnte.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="f3dc1-132">Wenn für eine Sitzung zudem ein Zeuge festgelegt wurde, kann das Entfernen des Endpunkts für die Datenbankspiegelung dazu führen, dass der Prinzipalserver der Sitzung das Quorum verliert. In diesem Fall wird die Datenbank offline gebracht und die Verbindung mit den Benutzern getrennt.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="f3dc1-133">Weitere Informationen finden Sie unter [Quorum: Auswirkungen eines Zeugen auf die Datenbankverfügbarkeit &#40;Datenbankspiegelung&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="f3dc1-134">Wenn einem der Partner ein Endpunkt fehlt, finden Sie eine Hilfestellung unter [Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="f3dc1-135">Wenn Serverinstanzen unter unterschiedlichen Domänenbenutzerkonten ausgeführt werden, erfordert jede Instanz eine Anmeldung bei der **master** -Datenbank der anderen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="f3dc1-136">Falls die Anmeldung nicht vorhanden ist, müssen Sie sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="f3dc1-137">Weitere Informationen finden Sie unter [Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="f3dc1-138">Um den Prinzipalserver als Partner auf der Spiegelungsdatenbank festzulegen, stellen Sie eine Verbindung mit dem Spiegelungsserver her, und geben Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="f3dc1-139">ALTER DATABASE *<Datenbankname>* SET PARTNER **=**_<Server-Netzwerkadresse>_</span><span class="sxs-lookup"><span data-stu-id="f3dc1-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="f3dc1-140">Dabei ist *<Datenbankname>* der Name der zu spiegelnden Datenbank (dieser Name ist für beide Partner gleich) und *<Server-Netzwerkadresse>* die Servernetzwerkadresse des Prinzipalservers.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="f3dc1-141">Die Syntax für eine Server-Netzwerkadresse lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="f3dc1-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="f3dc1-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="f3dc1-143">Dabei ist \<*system-address>\* eine Zeichenfolge, die das Zielcomputersystem eindeutig identifiziert, und \<*port>\* ist die vom Spiegelungsendpunkt der Partnerserverinstanz verwendete Portnummer.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="f3dc1-144">Weitere Informationen finden Sie unter [Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="f3dc1-145">Auf der Spiegelserverinstanz wird z. B. mit der folgenden ALTER DATABASE-Anweisung der Partner als ursprüngliche Prinzipalserverinstanz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="f3dc1-146">Der Datenbankname lautet **AdventureWorks**, die Systemadresse ist „DBSERVER1“ (der Name des Partnersystems) und der vom Endpunkt für die Datenbankspiegelung des Partners verwendete Port ist 7022:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="f3dc1-147">Diese Anweisung bereitet den Spiegelserver darauf vor, eine Sitzung einzurichten, wenn er durch den Prinzipalserver kontaktiert wird.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="f3dc1-148">Um den Spiegelserver als Partner auf der Prinzipaldatenbank festzulegen, stellen Sie eine Verbindung mit dem Prinzipalserver her, und geben Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="f3dc1-149">ALTER DATABASE *<Datenbankname>* SET PARTNER **=**_<Server-Netzwerkadresse>_</span><span class="sxs-lookup"><span data-stu-id="f3dc1-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="f3dc1-150">Weitere Informationen finden Sie unter Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="f3dc1-151">Auf der Prinzipalserverinstanz wird z. B. mit der folgenden ALTER DATABASE-Anweisung der Partner als ursprüngliche Spiegelserverinstanz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="f3dc1-152">Der Datenbankname lautet **AdventureWorks**, die Systemadresse ist „DBSERVER2“ (der Name des Partnersystems) und der vom Endpunkt für die Datenbankspiegelung des Partners verwendete Port ist 7025:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="f3dc1-153">Durch Eingeben dieser Anweisung auf dem Prinzipalserver beginnt die Datenbankspiegelungssitzung.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="f3dc1-154">Standardmäßig ist für eine Sitzung die Transaktionssicherheitsstufe FULL festgelegt (SAFETY ist auf FULL festgelegt), wodurch die Sitzung im synchronen Modus für hohe Sicherheit ohne automatisches Failover gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="f3dc1-155">Sie können die Sitzung wie folgt umkonfigurieren, sodass sie entweder im Modus für hohe Sicherheit mit automatischem Failover oder im asynchronen Modus für hohe Leistung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="f3dc1-156">**Modus für hohe Sicherheit mit automatischem Failover**</span><span class="sxs-lookup"><span data-stu-id="f3dc1-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="f3dc1-157">Wenn die Sitzung im Modus für hohe Sicherheit automatisches Failover unterstützen soll, fügen Sie eine Zeugenserverinstanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="f3dc1-158">Weitere Informationen finden Sie unter [Hinzufügen eines Zeugen für die Datenbankspiegelung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="f3dc1-159">**Modus mit hoher Leistung**</span><span class="sxs-lookup"><span data-stu-id="f3dc1-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="f3dc1-160">Wenn Sie kein automatisches Failover wünschen oder wenn Ihnen Leistung wichtiger als hohe Verfügbarkeit ist, können Sie alternativ die Transaktionssicherheit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="f3dc1-161">Weitere Informationen finden Sie unter [Ändern der Transaktionssicherheit in einer Datenbank-Spiegelungssitzung &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f3dc1-162">Im Modus für hohe Leistung sollte WITNESS auf OFF festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="f3dc1-163">Weitere Informationen finden Sie unter [Quorum: Auswirkungen eines Zeugen auf die Datenbankverfügbarkeit &#40;Datenbankspiegelung&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3dc1-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3dc1-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3dc1-165">Im folgenden Beispiel wird für eine vorhandene Spiegeldatenbank eine Datenbank-Spiegelungssitzung zwischen Partnern eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="f3dc1-166">Weitere Informationen zum Erstellen einer Spiegeldatenbank finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="f3dc1-167">Das Beispiel zeigt die grundlegenden Schritte zum Erstellen einer Datenbankspiegelungssitzung ohne einen Zeugen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="f3dc1-168">Die zwei Partner sind die Standardserverinstanzen auf zwei Computersystemen (PARTNERHOST1 und PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="f3dc1-169">Beide Partnerinstanzen führen dasselbe Windows-Domänenbenutzerkonto aus (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="f3dc1-170">Auf der Prinzipalserverinstanz (Standardinstanz auf PARTNERHOST1) erstellen Sie einen Endpunkt, der mithilfe von Port 7022 alle Rollen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3dc1-171">Ein Beispiel zum Einrichten einer Anmeldung finden Sie unter [Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="f3dc1-172">Auf der Spiegelserverinstanz (Standardinstanz auf PARTNERHOST5) erstellen Sie einen Endpunkt, der mithilfe von Port 7022 alle Rollen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="f3dc1-173">Auf der Prinzipalserverinstanz (auf PARTNERHOST1) sichern Sie die Datenbank:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="f3dc1-174">Stellen Sie auf der Spiegelserverinstanz (auf `PARTNERHOST5`) die Datenbank wieder her:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="f3dc1-175">Nach dem Erstellen der vollständigen Datenbanksicherung müssen Sie eine Protokollsicherung für die Prinzipaldatenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="f3dc1-176">Mit der folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wird beispielsweise das Protokoll in derselben Datei gesichert, die auch bei der vorhergehenden vollständigen Datenbanksicherung verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="f3dc1-177">Sie können erst mit der Spiegelung beginnen, nachdem Sie die erforderliche Protokollsicherung (und alle nachfolgenden Protokollsicherungen) angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="f3dc1-178">Mit der folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wird z. B. das erste Protokoll aus C:\AdventureWorks.bak wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="f3dc1-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="f3dc1-179">Legen Sie die Serverinstanz für die Spiegelserverinstanz auf PARTNERHOST1 als Partner fest (wodurch sie zum ersten Prinzipalserver wird):</span><span class="sxs-lookup"><span data-stu-id="f3dc1-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f3dc1-180">Eine Datenbankspiegelungssitzung wird standardmäßig im synchronen Modus ausgeführt, wozu die Transaktionssicherheitsstufe FULL verwendet wird (d. h., SAFETY auf FULL festgelegt sein muss).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="f3dc1-181">Um eine Sitzung im asynchronen Modus für hohe Leistung auszuführen, legen Sie SAFETY auf OFF fest.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="f3dc1-182">Weitere Informationen finden Sie unter [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="f3dc1-183">Legen Sie auf der Prinzipalserverinstanz die Serverinstanz auf `PARTNERHOST5` als Partner fest (wodurch sie zum ersten Spiegelserver wird):</span><span class="sxs-lookup"><span data-stu-id="f3dc1-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="f3dc1-184">Optional oder wenn Sie den Modus für hohe Sicherheit mit automatischem Failover verwenden möchten, richten Sie die Zeugenserverinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="f3dc1-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="f3dc1-185">Weitere Informationen finden Sie unter [Hinzufügen eines Zeugen für die Datenbankspiegelung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3dc1-186">Ein vollständiges Beispiel für das Einrichten der Sicherheitskomponenten, das Vorbereiten der Spiegeldatenbank, das Einrichten der Partner und das Hinzufügen eines Zeugen finden Sie unter [Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f3dc1-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dc1-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3dc1-187">See Also</span></span>  
 <span data-ttu-id="f3dc1-188">[Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="f3dc1-190">[Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung (SQL Server)](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="f3dc1-191">[Vorbereiten einer Spiegeldatenbank auf die Spiegelung (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-192">[Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="f3dc1-193">[Datenbankspiegelung und Protokollversand (SQL Server)](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-194">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-195">[Datenbankspiegelung und Replikation (SQL Server)](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-196">[Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="f3dc1-197">[Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc1-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="f3dc1-198">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="f3dc1-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
