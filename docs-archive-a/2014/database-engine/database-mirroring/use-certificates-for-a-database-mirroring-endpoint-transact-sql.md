---
title: Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt (Transact-SQL) | Microsoft-Dokumentation
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
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616678"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="4ca86-102">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4ca86-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="4ca86-103">Um die Zertifikatsauthentifizierung für die Datenbankspiegelung für eine bestimmte Serverinstanz zu aktivieren, muss der Systemadministrator jede Serverinstanz konfigurieren, um Zertifikate sowohl für ausgehende als auch für eingehende Verbindungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ca86-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="4ca86-104">Ausgehende Verbindungen müssen zuerst konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4ca86-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ca86-105">Alle Spiegelungsverbindungen auf einer Serverinstanz verwenden einen gemeinsamen Datenbankspiegelungsendpunkt. Sie müssen beim Erstellen dieses Endpunktes die Authentifizierungsmethode der Serverinstanz angeben.</span><span class="sxs-lookup"><span data-stu-id="4ca86-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="4ca86-106">Aus diesem Grund können Sie pro Serverinstanz jeweils nur eine Art der Authentifizierung für die Datenbankspiegelung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ca86-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="4ca86-107">Konfigurieren ausgehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4ca86-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="4ca86-108">Führen Sie die folgenden Schritte für jede Serverinstanz aus, die Sie für die Datenbankspiegelung konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4ca86-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="4ca86-109">Erstellen Sie einen Datenbankhauptschlüssel in der **master** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4ca86-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="4ca86-110">Erstellen eines verschlüsselten Zertifikats für die Serverinstanz in der **master** -Datenbank</span><span class="sxs-lookup"><span data-stu-id="4ca86-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="4ca86-111">Erstellen eines Endpunktes für die Serverinstanz mithilfe ihres Zertifikats</span><span class="sxs-lookup"><span data-stu-id="4ca86-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="4ca86-112">Sichern des Zertifikats in einer Datei und sicheres Kopieren dieses Zertifikats zum anderen System bzw. zu den anderen Systemen</span><span class="sxs-lookup"><span data-stu-id="4ca86-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="4ca86-113">Diese Schritte müssen Sie für jeden Partner und ggf. den Zeugen ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ca86-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="4ca86-114">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4ca86-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="4ca86-115">Konfigurieren eingehender Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4ca86-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="4ca86-116">Führen Sie anschließend die folgenden Schritte für jeden Partner durch, den Sie für die Datenbankspiegelung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ca86-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="4ca86-117">In der **master** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="4ca86-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="4ca86-118">Erstellen eines Anmeldenamens für das andere System</span><span class="sxs-lookup"><span data-stu-id="4ca86-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="4ca86-119">Erstellen Sie einen Benutzer für den Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="4ca86-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="4ca86-120">Abrufen des Zertifikats für den Spiegelungsendpunkt der anderen Serverinstanz</span><span class="sxs-lookup"><span data-stu-id="4ca86-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="4ca86-121">Ordnen Sie das Zertifikat dem in Schritt 2 erstellten Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="4ca86-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="4ca86-122">Erteilen der CONNECT-Berechtigung für den Anmeldenamen für den entsprechenden Spiegelungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="4ca86-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="4ca86-123">Falls ein Zeuge vorhanden ist, müssen Sie auch eingehende Verbindungen für diesen einrichten.</span><span class="sxs-lookup"><span data-stu-id="4ca86-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="4ca86-124">Hierfür ist es erforderlich, Anmeldenamen, Benutzer und Zertifikate für den Zeugen auf beiden Partnern (und umgekehrt) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4ca86-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="4ca86-125">Weitere Informationen finden Sie unter [Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4ca86-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="4ca86-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4ca86-126">Security</span></span>  
 <span data-ttu-id="4ca86-127">Sofern Sie nicht garantieren können, dass Ihr Netzwerk sicher ist, wird das Verschlüsseln bei Verbindungen zur Datenbankspiegelung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4ca86-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="4ca86-128">Weitere Informationen finden Sie unter [Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ca86-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="4ca86-129">Verwenden Sie zum Kopieren eines Zertifikats zu einem anderen System eine sichere Kopiermethode.</span><span class="sxs-lookup"><span data-stu-id="4ca86-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="4ca86-130">Seien Sie äußerst vorsichtig, um Ihre Zertifikate zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4ca86-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca86-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ca86-131">See Also</span></span>  
 <span data-ttu-id="4ca86-132">[Erstellen eines Datenbank-Hauptschlüssels](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="4ca86-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="4ca86-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ca86-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="4ca86-134">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="4ca86-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="4ca86-135">[Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="4ca86-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="4ca86-136">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4ca86-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
