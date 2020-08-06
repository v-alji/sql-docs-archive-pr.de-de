---
title: Zulassen der Verwendung von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609416"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="1733f-102">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1733f-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="1733f-103">In diesem Thema werden die Schritte beschrieben, um Serverinstanzen so zu konfigurieren, dass bei der Datenbankspiegelung Zertifikate zur Authentifizierung von ausgehenden Verbindungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1733f-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="1733f-104">Die ausgehende Verbindung muss konfiguriert werden, bevor eingehende Verbindungen eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="1733f-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1733f-105">Alle Spiegelungsverbindungen auf einer Serverinstanz verwenden einen gemeinsamen Datenbankspiegelungsendpunkt. Sie müssen beim Erstellen dieses Endpunktes die Authentifizierungsmethode der Serverinstanz angeben.</span><span class="sxs-lookup"><span data-stu-id="1733f-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="1733f-106">Der Vorgang zum Konfigurieren der ausgehenden Verbindungen umfasst die folgenden allgemeinen Schritte:</span><span class="sxs-lookup"><span data-stu-id="1733f-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="1733f-107">Erstellen eines Datenbankhauptschlüssels in der **master** -Datenbank</span><span class="sxs-lookup"><span data-stu-id="1733f-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="1733f-108">Erstellen eines verschlüsselten Zertifikats für die Serverinstanz in der **master** -Datenbank</span><span class="sxs-lookup"><span data-stu-id="1733f-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="1733f-109">Erstellen eines Endpunktes für die Serverinstanz mithilfe ihres Zertifikats</span><span class="sxs-lookup"><span data-stu-id="1733f-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="1733f-110">Sichern des Zertifikats in einer Datei und sicheres Kopieren dieses Zertifikats zum anderen System bzw. zu den anderen Systemen</span><span class="sxs-lookup"><span data-stu-id="1733f-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="1733f-111">Diese Schritte müssen Sie für jeden Partner und ggf. den Zeugen ausführen.</span><span class="sxs-lookup"><span data-stu-id="1733f-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="1733f-112">Die folgende Prozedur beschreibt diese Schritte detailliert.</span><span class="sxs-lookup"><span data-stu-id="1733f-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="1733f-113">Für jeden Schritt enthält die Prozedur ein Beispiel für das Konfigurieren einer Serverinstanz auf einem System namens HOST_A.</span><span class="sxs-lookup"><span data-stu-id="1733f-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="1733f-114">Im zugehörigen Beispielabschnitt werden dieselben Schritte für eine andere Serverinstanz auf einem System namens HOST_B beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1733f-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="1733f-115">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1733f-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="1733f-116">So konfigurieren Sie Serverinstanzen für ausgehende Spiegelungsverbindungen (auf HOST_A)</span><span class="sxs-lookup"><span data-stu-id="1733f-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="1733f-117">Erstellen Sie in der **master** -Datenbank den Datenbankhauptschlüssel, sofern noch keiner vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1733f-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="1733f-118">Zum Anzeigen der für eine Datenbank vorhandenen Schlüssel verwenden Sie die Katalogsicht [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="1733f-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="1733f-119">Zum Erstellen des Datenbankhauptschlüssels verwenden Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Befehl:</span><span class="sxs-lookup"><span data-stu-id="1733f-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="1733f-120">Verwenden Sie ein eindeutiges und aussagekräftiges Kennwort, und hinterlegen Sie es an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="1733f-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="1733f-121">Weitere Informationen finden Sie unter [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) und [Erstellen eines Datenbank-Hauptschlüssels](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="1733f-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="1733f-122">Erstellen Sie in der **master** -Datenbank ein verschlüsseltes Zertifikat für die Serverinstanz, das für deren ausgehende Verbindungen zur Datenbankspiegelung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1733f-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="1733f-123">Um z. B. ein Zertifikat für das HOST_A-System zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1733f-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1733f-124">Wenn Sie beabsichtigen, das Zertifikat länger als ein Jahr zu verwenden, geben Sie das Ablaufdatum in UTC-Zeit mit der EXPIRY_DATE-Option in der CREATE CERTIFICATE-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="1733f-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="1733f-125">Es wird auch empfohlen, dass Sie SQL Server Management Studio verwenden, um eine richtlinienbasierte Verwaltungsregel zu erstellen, damit Sie benachrichtigt werden, wann die Zertifikate ablaufen.</span><span class="sxs-lookup"><span data-stu-id="1733f-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="1733f-126">Erstellen Sie mithilfe des Dialogfelds **Neue Bedingung erstellen** der Richtlinienverwaltung diese Regel im Feld **@ExpirationDate** des Facets **Zertifikat** .</span><span class="sxs-lookup"><span data-stu-id="1733f-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="1733f-127">Weitere Informationen finden Sie unter [Verwalten von Servern mit der richtlinienbasierten Verwaltung](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) und [Sichern von SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1733f-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="1733f-128">Weitere Informationen finden Sie unter [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1733f-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="1733f-129">Zum Anzeigen der Zertifikate in der **master** -Datenbank können Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="1733f-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="1733f-130">Weitere Informationen finden Sie unter [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1733f-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="1733f-131">Stellen Sie sicher, dass der Datenbank-Spiegelungsendpunkt auf jeder Serverinstanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1733f-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="1733f-132">Wenn für die Serverinstanz bereits ein Datenbank-Spiegelungsendpunkt vorhanden ist, sollten Sie diesen Endpunkt für alle anderen Sitzungen verwenden, die Sie auf der Serverinstanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="1733f-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="1733f-133">Um festzustellen, ob auf einer Serverinstanz bereits ein Datenbank-Spiegelungsendpunkt vorhanden ist und um dessen Konfiguration anzuzeigen, verwenden Sie folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="1733f-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="1733f-134">Wenn kein Endpunkt vorhanden ist, erstellen Sie einen Endpunkt, der dieses Zertifikat für ausgehende Verbindungen und für die Anmeldeinformationen des Zertifikats zur Überprüfung auf dem anderen System verwendet.</span><span class="sxs-lookup"><span data-stu-id="1733f-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="1733f-135">Dies ist ein serverweiter Endpunkt, der von allen Spiegelungssitzungen verwendet wird, an denen die Serverinstanz beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="1733f-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="1733f-136">So erstellen Sie beispielsweise einen Spiegelungsendpunkt für die Beispiel-Serverinstanz auf HOST_A:</span><span class="sxs-lookup"><span data-stu-id="1733f-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
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
  
     <span data-ttu-id="1733f-137">Weitere Informationen finden Sie unter [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1733f-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="1733f-138">Sichern Sie das Zertifikat, und kopieren Sie es zum anderen System bzw. zu den anderen Systemen.</span><span class="sxs-lookup"><span data-stu-id="1733f-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="1733f-139">Das ist erforderlich, um eingehende Verbindungen auf dem anderen System zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1733f-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="1733f-140">Weitere Informationen finden Sie unter [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1733f-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="1733f-141">Kopieren Sie dieses Zertifikat mit einer sicheren Methode Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="1733f-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="1733f-142">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1733f-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="1733f-143">Mit dem Beispielcode in den vorherigen Schritten werden ausgehende Verbindungen auf HOST_A konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1733f-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="1733f-144">Jetzt müssen die entsprechenden Schritte für ausgehende Verbindungen für HOST_B ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1733f-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="1733f-145">Diese Schritte werden im folgenden Beispielabschnitt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1733f-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1733f-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1733f-146">Example</span></span>  
 <span data-ttu-id="1733f-147">Das folgende Beispiel erläutert das Konfigurieren von HOST_B für ausgehende Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="1733f-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
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
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="1733f-148">Kopieren Sie das Zertifikat zum anderen System. Verwenden Sie dazu eine sichere Methode Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="1733f-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="1733f-149">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1733f-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1733f-150">Nach dem Einrichten von ausgehenden Verbindungen müssen Sie eingehende Verbindungen auf jeder Serverinstanz für die andere Serverinstanz bzw. die anderen Serverinstanzen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1733f-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="1733f-151">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="1733f-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="1733f-152">Weitere Informationen zum Erstellen einer Spiegeldatenbank, einschließlich eines Transact-SQL-Beispiels, finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1733f-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="1733f-153">Ein Transact-SQL-Beispiel zum Einrichten einer Sitzung im Modus für hohe Leistung finden Sie unter [Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1733f-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1733f-154">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1733f-154">.NET Framework Security</span></span>  
 <span data-ttu-id="1733f-155">Sofern Sie nicht garantieren können, dass Ihr Netzwerk sicher ist, wird das Verschlüsseln bei Verbindungen zur Datenbankspiegelung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1733f-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="1733f-156">Verwenden Sie zum Kopieren eines Zertifikats zu einem anderen System eine sichere Kopiermethode.</span><span class="sxs-lookup"><span data-stu-id="1733f-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1733f-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1733f-157">See Also</span></span>  
 <span data-ttu-id="1733f-158">[Auswählen eines Verschlüsselungsalgorithmus](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="1733f-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="1733f-159">[Vorbereiten einer Spiegeldatenbank auf die Spiegelung (SQL Server)](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1733f-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="1733f-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1733f-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="1733f-161">[Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="1733f-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="1733f-162">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1733f-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="1733f-163">[Problembehandlung für die Datenbankspiegelungskonfiguration (SQL Server)](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1733f-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="1733f-164">Einrichten einer verschlüsselten Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="1733f-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
