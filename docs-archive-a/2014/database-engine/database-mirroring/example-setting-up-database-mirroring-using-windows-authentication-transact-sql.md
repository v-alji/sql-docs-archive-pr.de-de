---
title: 'Beispiel: Einrichten der Daten Bank Spiegelung mithilfe der Windows-Authentifizierung (Transact-SQL) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609399"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="89fce-102">Beispiel: Einrichten der Datenbankspiegelung mithilfe der Windows-Authentifizierung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="89fce-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="89fce-103">In diesem Beispiel werden sämtliche Schritte erläutert, die für die Erstellung einer Datenbank-Spiegelungssitzung mit einem Zeugen mithilfe der Windows-Authentifizierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="89fce-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="89fce-104">In den Beispielen in diesem Thema wird [!INCLUDE[tsql](../../includes/tsql-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="89fce-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="89fce-105">Beachten Sie Folgendes: Anstelle der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Schritte können Sie für die Einrichtung von Datenbankspiegelungen den Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung verwenden.</span><span class="sxs-lookup"><span data-stu-id="89fce-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="89fce-106">Weitere Informationen finden Sie unter [Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="89fce-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="89fce-107">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="89fce-107">Prerequisite</span></span>  
 <span data-ttu-id="89fce-108">In diesem Beispiel wird die **AdventureWorks** -Beispieldatenbank verwendet, in der standardmäßig das einfache Wiederherstellungsmodell zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="89fce-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="89fce-109">Um diese Datenbank für die Datenbankspiegelung verwenden zu können, muss sie dahin gehend geändert werden, dass das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="89fce-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="89fce-110">Verwenden Sie zu diesem Zweck in [!INCLUDE[tsql](../../includes/tsql-md.md)] die ALTER DATABASE-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89fce-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="89fce-111">Informationen zum Ändern von Wiederherstellungsmodellen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] finden Sie unter [Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="89fce-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="89fce-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="89fce-112">Permissions</span></span>  
 <span data-ttu-id="89fce-113">Erfordert die ALTER-Berechtigung für die Datenbank und die CREATE ENDPOINT-Berechtigung oder die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="89fce-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89fce-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89fce-114">Example</span></span>  
 <span data-ttu-id="89fce-115">In diesem Beispiel sind die beiden Partner und der Zeuge die standardmäßigen Serverinstanzen auf drei Computersystemen.</span><span class="sxs-lookup"><span data-stu-id="89fce-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="89fce-116">Von den drei Serverinstanzen wird dieselbe Windows-Domäne ausgeführt, das (als Dienststartkonto verwendete) Benutzerkonto für die Zeugenserverinstanz im Beispiel weicht jedoch ab.</span><span class="sxs-lookup"><span data-stu-id="89fce-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="89fce-117">In der folgenden Tabelle finden Sie eine Zusammenfassung der in diesem Beispiel verwendeten Werte.</span><span class="sxs-lookup"><span data-stu-id="89fce-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="89fce-118">Rolle bei der ersten Spiegelung</span><span class="sxs-lookup"><span data-stu-id="89fce-118">Initial mirroring role</span></span>|<span data-ttu-id="89fce-119">Hostsystem</span><span class="sxs-lookup"><span data-stu-id="89fce-119">Host system</span></span>|<span data-ttu-id="89fce-120">Domänenbenutzerkonto</span><span class="sxs-lookup"><span data-stu-id="89fce-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="89fce-121">Prinzipal</span><span class="sxs-lookup"><span data-stu-id="89fce-121">Principal</span></span>|<span data-ttu-id="89fce-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="89fce-122">PARTNERHOST1</span></span>|<span data-ttu-id="89fce-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="89fce-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="89fce-124">Spiegel</span><span class="sxs-lookup"><span data-stu-id="89fce-124">Mirror</span></span>|<span data-ttu-id="89fce-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="89fce-125">PARTNERHOST5</span></span>|<span data-ttu-id="89fce-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="89fce-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="89fce-127">Zeuge</span><span class="sxs-lookup"><span data-stu-id="89fce-127">Witness</span></span>|<span data-ttu-id="89fce-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="89fce-128">WITNESSHOST4</span></span>|<span data-ttu-id="89fce-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="89fce-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="89fce-130">Erstellen Sie einen Endpunkt auf der Prinzipalserverinstanz (Standardinstanz auf PARTNERHOST1).</span><span class="sxs-lookup"><span data-stu-id="89fce-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="89fce-131">Erstellen Sie einen Endpunkt auf der Spiegelserverinstanz (Standardinstanz auf PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="89fce-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="89fce-132">Erstellen Sie einen Endpunkt auf der Zeugenserverinstanz (Standardinstanz auf WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="89fce-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="89fce-133">Erstellen Sie die Spiegeldatenbank.</span><span class="sxs-lookup"><span data-stu-id="89fce-133">Create the mirror database.</span></span> <span data-ttu-id="89fce-134">Weitere Informationen finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="89fce-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="89fce-135">Legen Sie auf der Spiegelserverinstanz auf PARTNERHOST5 die Serverinstanz auf PARTNERHOST1 als Partner fest (hierdurch wird sie zur ersten Prinzipalserverinstanz).</span><span class="sxs-lookup"><span data-stu-id="89fce-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="89fce-136">Legen Sie auf der Prinzipalserverinstanz auf PARTNERHOST1 die Serverinstanz auf PARTNERHOST5 als Partner fest (hierdurch wird sie zur ersten Spiegelserverinstanz).</span><span class="sxs-lookup"><span data-stu-id="89fce-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="89fce-137">Legen Sie auf dem Prinzipalserver den Zeugen fest (der sich auf WITNESSHOST4 befindet).</span><span class="sxs-lookup"><span data-stu-id="89fce-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="89fce-138">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="89fce-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="89fce-139">Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="89fce-140">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="89fce-141">Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="89fce-142">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="89fce-143">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="89fce-144">Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89fce-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="89fce-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89fce-145">See Also</span></span>  
 <span data-ttu-id="89fce-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89fce-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="89fce-147">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="89fce-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="89fce-148">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="89fce-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="89fce-149">[Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="89fce-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="89fce-150">Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="89fce-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
