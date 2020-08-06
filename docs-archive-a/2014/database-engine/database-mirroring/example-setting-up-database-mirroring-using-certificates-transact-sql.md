---
title: 'Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten (Transact-SQL) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726250"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="d9037-102">Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d9037-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="d9037-103">In diesem Beispiel werden sämtliche Schritte erläutert, die für das Erstellen einer Datenbank-Spiegelungssitzung mithilfe der zertifikatbasierten Authentifizierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d9037-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="d9037-104">In den Beispielen in diesem Thema wird [!INCLUDE[tsql](../../includes/tsql-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d9037-105">Sofern Sie nicht garantieren können, dass Ihr Netzwerk sicher ist, wird das Verschlüsseln bei Verbindungen zur Datenbankspiegelung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d9037-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="d9037-106">Verwenden Sie zum Kopieren eines Zertifikats zu einem anderen System eine sichere Kopiermethode.</span><span class="sxs-lookup"><span data-stu-id="d9037-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="d9037-107">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d9037-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a> <span data-ttu-id="d9037-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9037-108">Example</span></span>  
 <span data-ttu-id="d9037-109">Das folgende Beispiel zeigt, welche Aktionen für einen der Partner ausgeführt werden müssen, der auf HOST_A gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d9037-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="d9037-110">In diesem Beispiel sind die beiden Partner die Standardserverinstanzen auf drei Computersystemen.</span><span class="sxs-lookup"><span data-stu-id="d9037-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="d9037-111">Die beiden Serverinstanzen werden in nicht vertrauenswürdigen Windows-Domänen ausgeführt, daher ist zertifikatbasierte Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9037-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="d9037-112">HOST_A übernimmt die anfängliche Prinzipalrolle, während die Spiegelrolle von HOST_B übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="d9037-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="d9037-113">Das Einrichten der Datenbankspiegelung mithilfe von Zertifikaten umfasst vier allgemeine Phasen, von den drei Phasen, nämlich 1, 2 und 4, in diesem Beispiel demonstriert werden.</span><span class="sxs-lookup"><span data-stu-id="d9037-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="d9037-114">Diese Phasen sind im Folgenden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d9037-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="d9037-115">Konfigurieren ausgehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="d9037-116">Im Beispiel werden die Schritte für folgende Aufgaben veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d9037-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="d9037-117">Konfigurieren von Host_A für ausgehende Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="d9037-118">Konfigurieren von Host_B für ausgehende Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="d9037-119">Informationen zu dieser Phase der Einrichtung der Datenbankspiegelung finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="d9037-120">Konfigurieren eingehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="d9037-121">Im Beispiel werden die Schritte für folgende Aufgaben veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d9037-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="d9037-122">Konfigurieren von Host_A für eingehende Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="d9037-123">Konfigurieren von Host_B für eingehende Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="d9037-124">Informationen zu dieser Phase der Einrichtung der Datenbankspiegelung finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="d9037-125">Erstellen der Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="d9037-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="d9037-126">Weitere Informationen zum Erstellen einer Spiegeldatenbank finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="d9037-127">Konfigurieren der Spiegelungspartner</span><span class="sxs-lookup"><span data-stu-id="d9037-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="d9037-128">Konfigurieren ausgehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="d9037-129">**So konfigurieren Sie Host_A für ausgehende Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="d9037-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="d9037-130">Erstellen Sie in der master-Datenbank den Datenbankhauptschlüssel, sofern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9037-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="d9037-131">Erstellen Sie ein Zertifikat für diese Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="d9037-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="d9037-132">Erstellen Sie einen Spiegelungsendpunkt für die Serverinstanz, die das Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="d9037-133">Sichern Sie das Zertifikat von HOST_A, und kopieren Sie es auf das andere System, HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="d9037-134">Kopieren Sie C:\HOST_A_cert.cer mithilfe einer sicheren Kopiermethode auf HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="d9037-135">**So konfigurieren Sie Host_B für ausgehende Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="d9037-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="d9037-136">Erstellen Sie in der master-Datenbank den Datenbankhauptschlüssel, sofern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9037-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="d9037-137">Erstellen Sie ein Zertifikat auf der Serverinstanz HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="d9037-138">Erstellen Sie einen Spiegelungsendpunkt für die Serverinstanz auf HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_B_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="d9037-139">Sichern Sie das Zertifikat von HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="d9037-140">Kopieren Sie C:\HOST_B_cert.cer mithilfe einer sicheren Kopiermethode auf HOST_A.</span><span class="sxs-lookup"><span data-stu-id="d9037-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="d9037-141">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d9037-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="d9037-142">Konfigurieren eingehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9037-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="d9037-143">**So konfigurieren Sie Host_A für eingehende Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="d9037-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="d9037-144">Erstellen Sie auf HOST_A einen Anmeldenamen für HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="d9037-145">-- Erstellen Sie einen Benutzer für diesen Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="d9037-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="d9037-146">-- Ordnen Sie das Zertifikat dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="d9037-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="d9037-147">Erteilen Sie die CONNECT-Berechtigung für den Anmeldenamen für den Remotespiegelungsendpunkt.</span><span class="sxs-lookup"><span data-stu-id="d9037-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="d9037-148">**So konfigurieren Sie Host_B für eingehende Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="d9037-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="d9037-149">Erstellen Sie auf HOST_B einen Anmeldenamen für HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d9037-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="d9037-150">Erstellen Sie einen Benutzer für den Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="d9037-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="d9037-151">Ordnen Sie das Zertifikat dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="d9037-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="d9037-152">Erteilen Sie die CONNECT-Berechtigung für den Anmeldenamen für den Remotespiegelungsendpunkt.</span><span class="sxs-lookup"><span data-stu-id="d9037-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9037-153">Wenn Sie die Ausführung im Modus für hohe Sicherheit mit automatischem Failover planen, müssen Sie die gleichen Setupschritte zum Konfigurieren des Zeugen für aus- und eingehende Verbindungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9037-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="d9037-154">Für das Setup der eingehenden Verbindungen bei Verwendung eines Zeugen ist es erforderlich, Anmeldungen und Benutzer für den Zeugen auf beiden Partnern und für beide Partner auf dem Zeugen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d9037-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="d9037-155">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d9037-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="d9037-156">Erstellen der Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="d9037-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="d9037-157">Weitere Informationen zum Erstellen einer Spiegeldatenbank finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9037-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="d9037-158">Konfigurieren der Spiegelungspartner</span><span class="sxs-lookup"><span data-stu-id="d9037-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="d9037-159">Legen Sie für die Spiegelserverinstanz auf HOST_B die Serverinstanz auf HOST_A als Partner fest (hierdurch wird sie zur ersten Prinzipalserverinstanz):</span><span class="sxs-lookup"><span data-stu-id="d9037-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="d9037-160">Ersetzen Sie `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`durch eine gültige Netzwerkadresse.</span><span class="sxs-lookup"><span data-stu-id="d9037-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="d9037-161">Weitere Informationen finden Sie unter [Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="d9037-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="d9037-162">Legen Sie für die Prinzipalserverinstanz auf HOST_A die Serverinstanz auf HOST_B als Partner fest (hierdurch wird sie zur ersten Spiegelserverinstanz):</span><span class="sxs-lookup"><span data-stu-id="d9037-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="d9037-163">Ersetzen Sie `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`durch eine gültige Netzwerkadresse.</span><span class="sxs-lookup"><span data-stu-id="d9037-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="d9037-164">Dieses Beispiel geht davon aus, dass die Sitzung im Modus für hohe Verfügbarkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9037-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="d9037-165">Wenn Sie diese Sitzung für den Modus für hohe Verfügbarkeit konfigurieren möchten, legen Sie die Transaktionssicherheit für die Prinzipalserverinstanz (auf HOST_A) auf OFF fest.</span><span class="sxs-lookup"><span data-stu-id="d9037-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9037-166">Wenn Sie beabsichtigen, den Modus für hohe Sicherheit mit automatischem Failover auszuführen, lassen Sie die Option Transaktionssicherheit auf vollständig festgelegt (Standardeinstellung), und fügen Sie den Zeugen so bald wie möglich nach der Ausführung der zweiten Set Partner **' *`partner_server`* '** -Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d9037-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="d9037-167">Beachten Sie, dass der Zeuge zuerst für aus- und eingehende Verbindungen konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="d9037-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d9037-168">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d9037-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d9037-169">Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9037-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="d9037-170">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d9037-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="d9037-171">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d9037-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="d9037-172">Verwaltung von Anmeldenamen und Aufträgen nach einem Rollenwechsel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9037-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="d9037-173">[Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d9037-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="d9037-174">Problembehandlung für die Datenbankspiegelungskonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9037-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d9037-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9037-175">See Also</span></span>  
 <span data-ttu-id="d9037-176">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="d9037-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="d9037-177">[Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="d9037-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="d9037-178">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d9037-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="d9037-179">[Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt (Transact-SQL)](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d9037-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="d9037-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9037-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="d9037-181">Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9037-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
