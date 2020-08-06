---
title: Netzwerk Zugriff auf einen Datenbankspiegelungs-Endpunkt
description: Erfahren Sie, wie Sie den Windows authenticatcher-Netzwerk Zugriff auf einen Datenbankspiegelungs-Endpunkt für SQL Server erlauben.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620511"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="a201e-103">Zulassen des Netzwerkzugriffs auf einen Datenbank-Spiegelungsendpunkt mithilfe der Windows-Authentifizierung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a201e-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="a201e-104">Die Verwendung der Windows-Authentifizierung für die Verbindung der Datenbank, wodurch Endpunkte auf zwei Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gespiegelt werden, erfordert unter den folgenden Bedingungen eine manuelle Konfiguration der Anmeldekonten:</span><span class="sxs-lookup"><span data-stu-id="a201e-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="a201e-105">Wenn die Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] als Dienste unter unterschiedlichen Domänenkonten ausgeführt werden (in der gleichen oder einer vertrauenswürdigen Domäne), müssen die Anmeldeinformationen jedes Kontos in **master** auf jeder der Remoteserverinstanzen erstellt werden. Dieser Anmeldung müssen CONNECT-Berechtigungen für den Endpunkt gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="a201e-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="a201e-106">Wenn die Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] als Netzwerkdienstkonto ausgeführt werden, muss die Anmeldung zu jedem Hostcomputer-Konto (*Domänenname***\\***Computername$* ) in **master** auf jeder Remoteserverinstanz erstellt werden. Dieser Anmeldung müssen CONNECT-Berechtigungen für den Endpunkt gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="a201e-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="a201e-107">Das liegt daran, dass eine Serverinstanz, die unter dem Netzwerkdienstkonto ausgeführt wird, mit dem Domänenkonto des Hostcomputers authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a201e-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a201e-108">Stellen Sie sicher, dass für jede dieser Serverinstanzen ein Endpunkt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="a201e-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="a201e-109">Weitere Informationen finden Sie unter [Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a201e-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="a201e-110">So konfigurieren Sie Anmeldenamen für die Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a201e-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="a201e-111">Erstellen Sie auf den anderen Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]eine Anmeldung für das Benutzerkonto jeder Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a201e-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a201e-112">Verwenden Sie eine [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql)-Anweisung mit der FROM WINDOWS-Klausel.</span><span class="sxs-lookup"><span data-stu-id="a201e-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="a201e-113">Weitere Informationen finden Sie unter [Erstellen eines Anmeldenamens](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="a201e-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="a201e-114">Erteilen Sie für die Anmeldung die Berechtigung für eine Verbindung zum Endpunkt unter Verwendung der [GRANT](/sql/t-sql/statements/grant-transact-sql)-Anweisung, damit der angemeldete Benutzer auf den Endpunkt zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a201e-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="a201e-115">Wenn es sich beim Benutzer um den Administrator handelt, ist keine Berechtigung für eine Verbindung zum Endpunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a201e-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="a201e-116">Weitere Informationen finden Sie unter [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a201e-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a201e-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a201e-117">Example</span></span>  
 <span data-ttu-id="a201e-118">Im folgenden [!INCLUDE[tsql](../includes/tsql-md.md)] -Beispiel wird ein [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldename für ein Benutzerkonto namens `Otheruser` erstellt, das der Domäne `Adomain`angehört.</span><span class="sxs-lookup"><span data-stu-id="a201e-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="a201e-119">Anschließend erteilt das Beispiel diesem Benutzer die Berechtigungen zum Verbindungsaufbau mit einem bereits vorhandenen Datenbank-Spiegelungsendpunkt mit dem Namen `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="a201e-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a201e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a201e-120">See Also</span></span>  
 <span data-ttu-id="a201e-121">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a201e-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a201e-122">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a201e-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="a201e-123">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="a201e-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="a201e-124">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a201e-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
