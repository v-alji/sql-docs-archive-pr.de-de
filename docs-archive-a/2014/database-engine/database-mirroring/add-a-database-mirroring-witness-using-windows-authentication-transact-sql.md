---
title: Hinzufügen eines Zeugen für die Datenbankspiegelung mithilfe der Windows-Authentifizierung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615588"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="528dc-102">Hinzufügen eines Zeugen für die Datenbankspiegelung mithilfe der Windows-Authentifizierung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="528dc-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="528dc-103">Um einen Zeugen für eine Datenbank einzurichten, weist der Datenbankbesitzer einer Instanz der Datenbank-Engine die Rolle des Zeugenservers zu.</span><span class="sxs-lookup"><span data-stu-id="528dc-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="528dc-104">Die Zeugenserverinstanz kann auf demselben Computer wie die Prinzipal- oder Spiegelserverinstanz ausgeführt werden. Hierdurch wird jedoch die Zuverlässigkeit des automatischen Failovers erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="528dc-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="528dc-105">Wir raten dringend, den Zeugen auf einem separaten Computer zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="528dc-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="528dc-106">Ein Server kann an mehreren gleichzeitigen Datenbank-Spiegelungssitzungen mit den gleichen oder anderen Partnern teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="528dc-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="528dc-107">Ein Server kann bei manchen Sitzungen als Partnerserver und bei anderen Sitzungen als Zeugenserver dienen.</span><span class="sxs-lookup"><span data-stu-id="528dc-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="528dc-108">Der Zeugenserver ist ausschließlich für den Modus für hohe Sicherheit mit automatischem Failover gedacht.</span><span class="sxs-lookup"><span data-stu-id="528dc-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="528dc-109">Bevor Sie einen Zeugen festlegen, sollten Sie unbedingt sicherstellen, dass die SAFETY-Eigenschaft auf FULL festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="528dc-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="528dc-110">Es empfiehlt sich, die Konfiguration der Datenbankspiegelung außerhalb der Spitzenbetriebszeiten durchzuführen, da sich die Konfiguration auf die Leistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="528dc-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="528dc-111">So richten Sie einen Zeugen ein</span><span class="sxs-lookup"><span data-stu-id="528dc-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="528dc-112">Stellen Sie für die Zeugenserverinstanz sicher, dass ein Endpunkt für die Datenbankspiegelung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="528dc-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="528dc-113">Unabhängig von der Anzahl von Spiegelungssitzungen, die unterstützt werden sollen, darf die Serverinstanz nur einen Endpunkt der Datenbankspiegelung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="528dc-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="528dc-114">Wenn Sie diese Serverinstanz ausschließlich als Zeugen in Datenbank-Spiegelungs Sitzungen verwenden möchten, weisen Sie die Rolle des Zeugen dem Endpunkt zu (Rollen **=** Zeuge).</span><span class="sxs-lookup"><span data-stu-id="528dc-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="528dc-115">Wenn Sie diese Serverinstanz als Partner bei mindestens einer Datenbank-Spiegelungssitzung verwenden möchten, weisen Sie die Rolle des Endpunkts als ALL zu.</span><span class="sxs-lookup"><span data-stu-id="528dc-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="528dc-116">Zum Ausführen einer SET WITNESS-Anweisung muss die Datenbank-Spiegelungssitzung bereits gestartet sein (zwischen den Partnern), und als STATE muss für den Endpunkt des Zeugen STARTED festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="528dc-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="528dc-117">Zur Feststellung, ob die Zeugenserverinstanz einen Endpunkt der Datenbankspiegelung aufweist, und zur Feststellung von deren Rolle und Status verwenden Sie in dieser Instanz die folgende Transact-SQL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="528dc-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="528dc-118">Wenn ein Endpunkt für die Datenbankspiegelung vorhanden ist und bereits verwendet wird, empfiehlt es sich, diesen Endpunkt auf der Serverinstanz für jede Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="528dc-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="528dc-119">Durch Löschen eines verwendeten Endpunkts werden die Verbindungen der vorhandenen Sitzungen getrennt.</span><span class="sxs-lookup"><span data-stu-id="528dc-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="528dc-120">Wenn für eine Sitzung ein Zeuge festgelegt wurde, kann das Löschen des Endpunkts für die Datenbankspiegelung dazu führen, dass der Prinzipalserver der Sitzung das Quorum verliert. In diesem Fall wird die Datenbank offline geschaltet und die Verbindung mit den Benutzern getrennt.</span><span class="sxs-lookup"><span data-stu-id="528dc-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="528dc-121">Weitere Informationen finden Sie unter [Quorum: Auswirkungen eines Zeugen auf die Datenbankverfügbarkeit &#40;Datenbankspiegelung&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="528dc-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="528dc-122">Wenn für einen Zeugen kein Endpunkt vorhanden ist, informieren Sie sich unter [Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="528dc-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="528dc-123">Wenn die Partnerinstanzen unter unterschiedlichen Domänenbenutzerkonten ausgeführt werden, müssen Sie in der Master-Datenbank jeder Instanz eine Anmeldung für die einzelnen Konten erstellen.</span><span class="sxs-lookup"><span data-stu-id="528dc-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="528dc-124">Weitere Informationen finden Sie unter [Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="528dc-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="528dc-125">Stellen Sie anhand der folgenden Anweisung eine Verbindung mit dem Prinzipalserver her:</span><span class="sxs-lookup"><span data-stu-id="528dc-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="528dc-126">ALTER DATABASE *<database_name>* Set Witness **=** _<server_network_address_></span><span class="sxs-lookup"><span data-stu-id="528dc-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="528dc-127">Dabei ist *<Datenbankname>* der Name der zu spiegelnden Datenbank (dieser Name ist auf beiden Partnern gleich), und *<Servernetzwerkadresse>* ist die Servernetzwerkadresse der Zeugenserverinstanz.</span><span class="sxs-lookup"><span data-stu-id="528dc-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="528dc-128">Die Syntax für eine Server-Netzwerkadresse lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="528dc-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="528dc-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="528dc-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="528dc-130">Dabei ist \<*system-address>\* eine Zeichenfolge, die das Zielcomputersystem eindeutig identifiziert, und \<*port>\* ist die vom Spiegelungsendpunkt der Partnerserverinstanz verwendete Portnummer.</span><span class="sxs-lookup"><span data-stu-id="528dc-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="528dc-131">Weitere Informationen finden Sie unter [Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="528dc-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="528dc-132">Beispiel: Auf der Prinzipalserverinstanz wird mit folgender ALTER DATABASE-Anweisung der Zeuge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="528dc-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="528dc-133">Der Datenbankname ist **AdventureWorks**, die Systemadresse lautet DBSERVER3, der Name des Zeugensystems, und der vom Datenbankspiegelungsendpunkt des Zeugen verwendete Port ist `7022`:</span><span class="sxs-lookup"><span data-stu-id="528dc-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="528dc-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="528dc-134">Example</span></span>  
 <span data-ttu-id="528dc-135">Das folgende Beispiel erstellt einen Datenspiegelungszeugen.</span><span class="sxs-lookup"><span data-stu-id="528dc-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="528dc-136">Auf der Zeugenserverinstanz (Standardinstanz auf `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="528dc-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="528dc-137">Erstellen Sie einen Endpunkt für diese Serverinstanz für die WITNESS-Rolle, die ausschließlich Port `7022`verwendet.</span><span class="sxs-lookup"><span data-stu-id="528dc-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="528dc-138">Erstellen Sie eine Anmeldung für das Domänenbenutzerkonto der Partnerinstanzen, sofern dieses unterschiedlich ist. Wenn z. B. der Zeuge als `SOMEDOMAIN\witnessuser`ausgeführt wird, die Partner aber als `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="528dc-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="528dc-139">Erstellen Sie die Anmeldung für Partner wie folgt:</span><span class="sxs-lookup"><span data-stu-id="528dc-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="528dc-140">Erstellen Sie auf jeder Serverinstanz eine Anmeldung für die Zeugenserverinstanz:</span><span class="sxs-lookup"><span data-stu-id="528dc-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="528dc-141">Legen Sie auf dem Prinzipalserver den Zeugen fest (der sich auf `WITNESSHOST4`befindet):</span><span class="sxs-lookup"><span data-stu-id="528dc-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="528dc-142">Die Servernetzwerkadresse gibt die Zielserverinstanz über die Portnummer an, die auf den Spiegelungsendpunkt der Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="528dc-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="528dc-143">Ein vollständiges Beispiel für das Einrichten der Sicherheitskomponenten, das Vorbereiten der Spiegeldatenbank, das Einrichten der Partner und das Hinzufügen eines Zeugen finden Sie unter [Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="528dc-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528dc-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="528dc-144">See Also</span></span>  
 <span data-ttu-id="528dc-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="528dc-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="528dc-146">[Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung (SQL Server)](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="528dc-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="528dc-147">[Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="528dc-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="528dc-148">[Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung (Transact-SQL)](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="528dc-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="528dc-149">[Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server)](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="528dc-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="528dc-150">Datenbank-Spiegelungszeuge</span><span class="sxs-lookup"><span data-stu-id="528dc-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
