---
title: Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615574"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="58525-102">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="58525-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="58525-103">In diesem Thema wird beschrieben, wie ein Datenbankspiegelungs-Endpunkt in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird, der die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="58525-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="58525-104">Um die Datenbankspiegelung oder [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] unterstützen zu können, benötigt jede Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen Datenspiegelungs-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="58525-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="58525-105">Eine Serverinstanz kann nur über einen Datenbankspiegelungsendpunkt verfügen, der einen einzelnen Port besitzt.</span><span class="sxs-lookup"><span data-stu-id="58525-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="58525-106">Ein Datenbankspiegelungsendpunkt kann einen beliebigen Port verwenden, der auf dem lokalen System verfügbar ist, wenn der Endpunkt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="58525-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="58525-107">Alle Datenbankspiegelungssitzungen auf einer Serverinstanz lauschen an diesem Port, und alle eingehenden Verbindungen für die Datenbankspiegelung verwenden diesen Port.</span><span class="sxs-lookup"><span data-stu-id="58525-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58525-108">Wenn ein Datenbankspiegelungs-Endpunkt vorhanden und bereits in Gebrauch ist, empfiehlt es sich, diesen Endpunkt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="58525-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="58525-109">Wenn ein in Gebrauch befindlicher Endpunkt gelöscht wird, kann dies zu Störungen bei vorhandenen Sitzungen führen.</span><span class="sxs-lookup"><span data-stu-id="58525-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="58525-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="58525-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="58525-111">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="58525-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="58525-112">**So erstellen Sie einen Datenbankspiegelungsendpunkt:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="58525-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="58525-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="58525-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="58525-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="58525-114">Security</span></span>  
 <span data-ttu-id="58525-115">Die Authentifizierungs- und Verschlüsselungsmethoden der Serverinstanz werden vom Systemadministrator festgelegt.</span><span class="sxs-lookup"><span data-stu-id="58525-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58525-116">Der RC4-Algorithmus ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="58525-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="58525-117">Stattdessen wird die Verwendung von AES empfohlen.</span><span class="sxs-lookup"><span data-stu-id="58525-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="58525-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="58525-118">Permissions</span></span>  
 <span data-ttu-id="58525-119">Erfordert die CREATE ENDPOINT-Berechtigung oder die Mitgliedschaft in der festen Serverrolle "sysadmin".</span><span class="sxs-lookup"><span data-stu-id="58525-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="58525-120">Weitere Informationen finden Sie unter [GRANT (Endpunktberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58525-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="58525-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58525-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="58525-122">So erstellen Sie einen Datenbankspiegelungs-Endpunkt, der die Windows-Authentifizierung verwendet</span><span class="sxs-lookup"><span data-stu-id="58525-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="58525-123">Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, für die Sie einen Endpunkt für die Datenbankspiegelung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="58525-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="58525-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="58525-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="58525-125">Ermitteln Sie mithilfe der folgenden Anweisung, ob ein Endpunkt für die Datenbankspiegelung bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="58525-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="58525-126">Falls bereits ein Endpunkt der Datenbankspiegelung für die Serverinstanz vorhanden ist, verwenden Sie diesen Endpunkt für alle anderen Sitzungen, die Sie für die Serverinstanz einrichten.</span><span class="sxs-lookup"><span data-stu-id="58525-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="58525-127">Wenn Sie Transact-SQL zum Erstellen eines Endpunktes verwenden möchten, der mit Windows-Authentifizierung verwendet werden soll, verwenden Sie eine CREATE ENDPOINT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="58525-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="58525-128">Die Anweisung weist folgende allgemeine Form auf:</span><span class="sxs-lookup"><span data-stu-id="58525-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="58525-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="58525-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="58525-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="58525-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="58525-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="58525-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="58525-132">FOR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="58525-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="58525-133">(</span><span class="sxs-lookup"><span data-stu-id="58525-133">(</span></span>  
  
     <span data-ttu-id="58525-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="58525-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="58525-135">]</span><span class="sxs-lookup"><span data-stu-id="58525-135">]</span></span>  
  
     <span data-ttu-id="58525-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="58525-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="58525-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="58525-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="58525-138">]</span><span class="sxs-lookup"><span data-stu-id="58525-138">]</span></span>  
  
     <span data-ttu-id="58525-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="58525-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="58525-140">)</span><span class="sxs-lookup"><span data-stu-id="58525-140">)</span></span>  
  
     <span data-ttu-id="58525-141">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="58525-141">where</span></span>  
  
    -   <span data-ttu-id="58525-142">*\<endpointName>* ist der eindeutige Name für den Endpunkt der Datenbankspiegelung der Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="58525-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="58525-143">STARTED gibt an, dass der Endpunkt gestartet werden und mit der Überwachung auf Verbindungen beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="58525-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="58525-144">Ein Endpunkt der Datenbankspiegelung wird in der Regel im Status STARTED erstellt.</span><span class="sxs-lookup"><span data-stu-id="58525-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="58525-145">Alternativ können Sie eine Sitzung in einem Status STOPPED (die Standardeinstellung) oder DISABLED erstellen.</span><span class="sxs-lookup"><span data-stu-id="58525-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="58525-146">*\<listenerPortList>* ist eine einzelne Portnummer (*nnnn*), an dem der Server auf Datenbankspiegelungsnachrichten lauschen soll.</span><span class="sxs-lookup"><span data-stu-id="58525-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="58525-147">Nur TCP ist zulässig; wenn Sie ein anderes Protokoll angeben, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58525-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="58525-148">Eine Portnummer kann in einem Computersystem nur einmal verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58525-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="58525-149">Ein Datenbankspiegelungsendpunkt kann einen beliebigen Port verwenden, der auf dem lokalen System verfügbar ist, wenn der Endpunkt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="58525-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="58525-150">Verwenden Sie die folgende Transact-SQL-Anweisung, um den Port anzugeben, der zurzeit von TCP-Endpunkten im System verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="58525-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="58525-151">Für jede Serverinstanz ist ein und nur ein eindeutiger Überwachungsport erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58525-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="58525-152">Bei der Windows-Authentifizierung ist die AUTHENTICATION-Option optional, es sei denn, der Endpunkt soll nur NTLM oder Kerberos zum Authentifzieren von Verbindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="58525-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="58525-153">*\<authorizationMethod>* gibt die Methode zum Authentifizieren von Verbindungen an: NTLM, KERBEROS oder NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="58525-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="58525-154">Die Standardeinstellung, NEGOTIATE, bewirkt, dass der Endpunkt das Aushandlungsprotokoll von Windows verwendet, um NTLM oder Kerberos auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="58525-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="58525-155">Die Verbindungsverhandlung ermöglicht abhängig von der Authentifizierungsebene des gegenüberliegenden Endpunktes Verbindungen mit oder ohne Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="58525-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="58525-156">ENCRYPTION wird standardmäßig auf REQUIRED festgelegt.</span><span class="sxs-lookup"><span data-stu-id="58525-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="58525-157">Dies bedeutet, dass alle Verbindungen mit diesem Endpunkt Verschlüsselungen verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="58525-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="58525-158">Sie können die Verschlüsselung jedoch auch deaktivieren oder als optional für einen Endpunkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="58525-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="58525-159">Die Alternativen lauten folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="58525-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="58525-160">Wert</span><span class="sxs-lookup"><span data-stu-id="58525-160">Value</span></span>|<span data-ttu-id="58525-161">Definition</span><span class="sxs-lookup"><span data-stu-id="58525-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="58525-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="58525-162">DISABLED</span></span>|<span data-ttu-id="58525-163">Gibt an, dass über eine Verbindung gesendete Daten nicht verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="58525-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="58525-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="58525-164">SUPPORTED</span></span>|<span data-ttu-id="58525-165">Gibt an, dass die Daten nur verschlüsselt werden, wenn der gegenüberliegende Endpunkt SUPPORTED oder REQUIRED angibt.</span><span class="sxs-lookup"><span data-stu-id="58525-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="58525-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="58525-166">REQUIRED</span></span>|<span data-ttu-id="58525-167">Gibt an, dass über eine Verbindung gesendete Daten verschlüsselt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="58525-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="58525-168">Wenn ein Endpunkt Verschlüsselung erfordert, muss für den anderen Endpunkt ENCRYPTION auf SUPPORTED oder REQUIRED festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="58525-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="58525-169">*\<algorithm>* stellt die Option zum Angeben der Verschlüsselungsstandards für den Endpunkt bereit.</span><span class="sxs-lookup"><span data-stu-id="58525-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="58525-170">Der Wert von *\<algorithm>* kann einer der folgenden Algorithmen oder eine Kombination aus Algorithmen sein: RC4, AES, AES RC4 oder RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="58525-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="58525-171">AES RC4 gibt an, dass dieser Endpunkt den Verschlüsselungsalgorithmus verhandelt, wobei der AES-Algorithmus bevorzugt wird.</span><span class="sxs-lookup"><span data-stu-id="58525-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="58525-172">RC4 AES gibt an, dass dieser Endpunkt den Verschlüsselungsalgorithmus verhandelt, wobei der RC4-Algorithmus bevorzugt wird.</span><span class="sxs-lookup"><span data-stu-id="58525-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="58525-173">Wenn beide Endpunkte beide Algorithmen angeben, jedoch in unterschiedlicher Reihenfolge, gewinnt der Endpunkt, der die Verbindung annimmt.</span><span class="sxs-lookup"><span data-stu-id="58525-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="58525-174">Der RC4-Algorithmus ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="58525-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="58525-175">Stattdessen wird die Verwendung von AES empfohlen.</span><span class="sxs-lookup"><span data-stu-id="58525-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="58525-176">*\<role>* definiert die Rolle bzw. Rollen, die der Server ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="58525-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="58525-177">Die Angabe von ROLE ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58525-177">Specifying ROLE is required.</span></span> <span data-ttu-id="58525-178">Die Rolle des Endpunkts ist jedoch nur für die Datenbankspiegelung relevant.</span><span class="sxs-lookup"><span data-stu-id="58525-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="58525-179">Für [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]wird die Rolle des Endpunkts ignoriert.</span><span class="sxs-lookup"><span data-stu-id="58525-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="58525-180">Damit eine Serverinstanz als eine Rolle für eine Datenbankspiegelungssitzung und eine andere Rolle für eine andere Sitzung fungieren kann, geben Sie ROLE=ALL an.</span><span class="sxs-lookup"><span data-stu-id="58525-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="58525-181">Wenn Sie eine Serverinstanz auf die Partner- oder Zeugenrolle beschränken möchten, geben Sie ROLE=PARTNER bzw. ROLE=WITNESS an.</span><span class="sxs-lookup"><span data-stu-id="58525-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="58525-182">Weitere Informationen zu den Optionen für die Daten Bank Spiegelung für verschiedene Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finden Sie [unter von den Editionen von SQL Server 2014 unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="58525-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="58525-183">Eine vollständige Beschreibung der CREATE ENDPOINT-Syntax finden Sie unter [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql)erstellt wird, der die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="58525-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58525-184">Um einen vorhandenen Endpunkt zu ändern, verwenden Sie [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql)erstellt wird, der die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="58525-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="58525-185">Beispiel: Erstellen von Endpunkten mit Unterstützung der Datenbankspiegelung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="58525-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="58525-186">Im folgenden Beispiel werden Datenbankspiegelungs-Endpunkte für die Standardserverinstanzen auf drei separaten Computersystemen erstellt:</span><span class="sxs-lookup"><span data-stu-id="58525-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="58525-187">Rolle der Serverinstanz</span><span class="sxs-lookup"><span data-stu-id="58525-187">Role of server instance</span></span>|<span data-ttu-id="58525-188">Name des Hostcomputers</span><span class="sxs-lookup"><span data-stu-id="58525-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="58525-189">Partner (anfangs die Prinzipalrolle)</span><span class="sxs-lookup"><span data-stu-id="58525-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="58525-190">Partner (anfangs die Spiegelrolle)</span><span class="sxs-lookup"><span data-stu-id="58525-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="58525-191">Zeuge</span><span class="sxs-lookup"><span data-stu-id="58525-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="58525-192">In diesem Beispiel verwenden alle drei Endpunkte die Portnummer 7022, wobei jede verfügbare Portnummer möglich wäre.</span><span class="sxs-lookup"><span data-stu-id="58525-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="58525-193">Die Option AUTHENTICATION ist unnötig, da die Endpunkte den Standardtyp, also die Windows-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="58525-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="58525-194">Die Option ENCRYPTION ist ebenfalls überflüssig, da alle Endpunkte das Authentifizierungsverfahren für eine Verbindung aushandeln sollen, was bei der Windows-Authentifizierung das Standardverhalten darstellt.</span><span class="sxs-lookup"><span data-stu-id="58525-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="58525-195">Außerdem erfordern alle Endpunkte die Verschlüsselung, was ebenfalls zum Standardverhalten gehört.</span><span class="sxs-lookup"><span data-stu-id="58525-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="58525-196">Jede Serverinstanz ist darauf beschränkt, entweder als Partner oder als Zeuge zu agieren, und der Endpunkt jedes Servers legt die Rolle ausdrücklich fest (ROLE=PARTNER oder ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="58525-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58525-197">Jede Serverinstanz kann nur einen Endpunkt besitzen.</span><span class="sxs-lookup"><span data-stu-id="58525-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="58525-198">Wenn Sie daher wollen, dass eine Serverinstanz in einigen Sitzungen als Partner und in anderen als Zeuge agiert, müssen Sie ROLE=ALL festlegen.</span><span class="sxs-lookup"><span data-stu-id="58525-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="58525-199">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="58525-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="58525-200">So konfigurieren Sie einen Datenbankspiegelungs-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="58525-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="58525-201">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="58525-202">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="58525-203">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="58525-204">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="58525-205">Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="58525-206">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="58525-207">**So zeigen Sie Informationen zum Datenbankspiegelungs-Endpunkt an**</span><span class="sxs-lookup"><span data-stu-id="58525-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="58525-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="58525-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58525-209">See Also</span></span>  
 <span data-ttu-id="58525-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="58525-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="58525-211">[Auswählen eines Verschlüsselungsalgorithmus](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="58525-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="58525-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="58525-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="58525-213">[Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="58525-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="58525-214">[Beispiel: Einrichten der Datenbankspiegelung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="58525-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="58525-215">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58525-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
