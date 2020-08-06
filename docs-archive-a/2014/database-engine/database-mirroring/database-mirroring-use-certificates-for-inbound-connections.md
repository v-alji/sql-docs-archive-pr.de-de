---
title: Zulassen der Verwendung von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609417"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="bf2e2-102">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bf2e2-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="bf2e2-103">In diesem Thema werden die Schritte beschrieben, um Serverinstanzen so zu konfigurieren, dass bei der Datenbankspiegelung Zertifikate zur Authentifizierung von eingehenden Verbindungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="bf2e2-104">Bevor Sie eingehende Verbindungen einrichten können, müssen Sie ausgehende Verbindungen für jede Serverinstanz konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="bf2e2-105">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="bf2e2-106">Der Vorgang zum Konfigurieren der eingehenden Verbindungen umfasst die folgenden allgemeinen Schritte:</span><span class="sxs-lookup"><span data-stu-id="bf2e2-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="bf2e2-107">Erstellen eines Anmeldenamens für das andere System.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="bf2e2-108">Erstellen Sie einen Benutzer für den Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="bf2e2-109">Abrufen des Zertifikats für den Spiegelungsendpunkt der anderen Serverinstanz</span><span class="sxs-lookup"><span data-stu-id="bf2e2-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="bf2e2-110">Ordnen Sie das Zertifikat dem in Schritt 2 erstellten Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="bf2e2-111">Erteilen der CONNECT-Berechtigung für den Anmeldenamen für den entsprechenden Spiegelungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="bf2e2-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="bf2e2-112">Falls ein Zeuge vorhanden ist, müssen Sie auch eingehende Verbindungen für diesen einrichten.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="bf2e2-113">Hierfür ist es erforderlich, Anmeldenamen, Benutzer und Zertifikate für den Zeugen auf beiden Partnern (und umgekehrt) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="bf2e2-114">Die folgende Prozedur beschreibt diese Schritte detailliert.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="bf2e2-115">Für jeden Schritt enthält die Prozedur ein Beispiel für das Konfigurieren einer Serverinstanz auf einem System namens HOST_A.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="bf2e2-116">Im zugehörigen Beispielabschnitt werden dieselben Schritte für eine andere Serverinstanz auf einem System namens HOST_B beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="bf2e2-117">So konfigurieren Sie Serverinstanzen für eingehende Spiegelungsverbindungen (auf HOST_A)</span><span class="sxs-lookup"><span data-stu-id="bf2e2-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="bf2e2-118">Erstellen eines Anmeldenamens für das andere System</span><span class="sxs-lookup"><span data-stu-id="bf2e2-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="bf2e2-119">Das folgende Beispiel erstellt einen Anmeldenamen für das System HOST_B in der **master** -Datenbank der Serverinstanz auf HOST_A. In diesem Beispiel heißt der Anmeldename `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="bf2e2-120">Ersetzen Sie das Beispielkennwort durch ein Kennwort Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="bf2e2-121">Weitere Informationen finden Sie unter [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="bf2e2-122">Um die Anmeldenamen für diese Serverinstanz anzuzeigen, können Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="bf2e2-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="bf2e2-123">Weitere Informationen finden Sie unter [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="bf2e2-124">Erstellen Sie einen Benutzer für den Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="bf2e2-125">Das folgende Beispiel erstellt einen Benutzer namens `HOST_B_user` für den im vorherigen Schritt erstellten Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="bf2e2-126">Weitere Informationen finden Sie unter [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="bf2e2-127">Um die Benutzer für diese Serverinstanz anzuzeigen, können Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="bf2e2-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="bf2e2-128">Weitere Informationen finden Sie unter [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="bf2e2-129">Abrufen des Zertifikats für den Spiegelungsendpunkt der anderen Serverinstanz</span><span class="sxs-lookup"><span data-stu-id="bf2e2-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="bf2e2-130">Wenn dies noch nicht beim Konfigurieren ausgehender Verbindungen geschehen ist, rufen Sie eine Kopie des Zertifikats für den Spiegelungsendpunkt der Remoteserverinstanz ab.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="bf2e2-131">Sichern Sie zu diesem Zweck das Zertifikat für diese Serverinstanz wie unter [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="bf2e2-132">Verwenden Sie zum Kopieren eines Zertifikats zu einem anderen System eine sichere Kopiermethode.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="bf2e2-133">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="bf2e2-134">Weitere Informationen finden Sie unter [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="bf2e2-135">Ordnen Sie das Zertifikat dem in Schritt 2 erstellten Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="bf2e2-136">Das folgende Beispiel ordnet das Zertifikat von HOST_B seinem Benutzer auf HOST_A zu.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="bf2e2-137">Weitere Informationen finden Sie unter [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="bf2e2-138">Um die Zertifikate für diese Serverinstanz anzuzeigen, verwenden Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="bf2e2-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="bf2e2-139">Weitere Informationen finden Sie unter [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="bf2e2-140">Erteilen Sie die CONNECT-Berechtigung für den Anmeldenamen für den Remotespiegelungsendpunkt.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="bf2e2-141">Um beispielsweise auf HOST_A die Berechtigung für die Remoteserverinstanz auf HOST_B zum Herstellen der Verbindung mit ihrem lokalen Anmeldenamen zu erteilen, d.h., um eine Verbindung mit `HOST_B_login` herzustellen, verwenden Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="bf2e2-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="bf2e2-142">Weitere Informationen finden Sie unter [GRANT (Endpunktberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="bf2e2-143">Hiermit ist das Einrichten der Zertifikatsauthentifizierung für HOST_B zur Anmeldung bei HOST_A abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="bf2e2-144">Jetzt müssen die entsprechenden Schritte für eingehende Verbindungen für HOST_A auf HOST_B ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="bf2e2-145">Diese Schritte werden im Abschnitt zu eingehenden Verbindungen des folgenden Beispiels erläutert.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf2e2-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf2e2-146">Example</span></span>  
 <span data-ttu-id="bf2e2-147">Im folgenden Beispiel wird das Konfigurieren von HOST_B für eingehende Verbindungen erläutert.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf2e2-148">In diesem Beispiel wird eine Zertifikatsdatei mit dem Zertifikat von HOST_A verwendet, das durch einen Codeausschnitt in [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="bf2e2-149">Wenn Sie die Ausführung im Modus für hohe Sicherheit mit automatischem Failover planen, müssen Sie die gleichen Setupschritte zum Konfigurieren des Zeugen für aus- und eingehende Verbindungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="bf2e2-150">Weitere Informationen zum Erstellen einer Spiegeldatenbank, einschließlich eines Transact-SQL-Beispiels, finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="bf2e2-151">Ein Transact-SQL-Beispiel zum Einrichten einer Sitzung im Modus für hohe Leistung finden Sie unter [Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e2-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bf2e2-152">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bf2e2-152">.NET Framework Security</span></span>  
 <span data-ttu-id="bf2e2-153">Verwenden Sie zum Kopieren eines Zertifikats zu einem anderen System eine sichere Kopiermethode.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="bf2e2-154">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="bf2e2-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf2e2-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf2e2-155">See Also</span></span>  
 <span data-ttu-id="bf2e2-156">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="bf2e2-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="bf2e2-157">[GRANT (Endpunktberechtigungen) (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf2e2-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="bf2e2-158">[Einrichten einer verschlüsselten Spiegel Datenbank](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="bf2e2-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="bf2e2-159">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bf2e2-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="bf2e2-160">Problembehandlung für die Datenbankspiegelungskonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bf2e2-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
