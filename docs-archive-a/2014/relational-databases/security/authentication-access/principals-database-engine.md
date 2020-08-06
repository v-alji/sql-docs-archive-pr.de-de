---
title: Prinzipale (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622510"
---
# <a name="principals-database-engine"></a><span data-ttu-id="1a489-102">Prinzipale (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1a489-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="1a489-103">*Prinzipale* sind Entitäten, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Ressourcen anfordern können.</span><span class="sxs-lookup"><span data-stu-id="1a489-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="1a489-104">Wie bei anderen Komponenten des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Autorisierungsmodells können Prinzipale hierarchisch angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1a489-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="1a489-105">Der Einflussbereich eines Prinzipals hängt vom Gültigkeitsbereich der Definition des Prinzipals ab: Windows, Server, Datenbank und ob der Prinzipal unteilbar oder eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="1a489-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="1a489-106">Ein Windows-Anmeldename ist ein Beispiel eines unteilbaren Prinzipals und eine Windows-Gruppe das eines Prinzipals, der eine Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1a489-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="1a489-107">Jeder Prinzipal weist eine Sicherheits-ID (SID) auf.</span><span class="sxs-lookup"><span data-stu-id="1a489-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="1a489-108">**Prinzipale auf Windows-Ebene**</span><span class="sxs-lookup"><span data-stu-id="1a489-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="1a489-109">Windows-Domänenanmeldename</span><span class="sxs-lookup"><span data-stu-id="1a489-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="1a489-110">Lokaler Windows-Anmeldename</span><span class="sxs-lookup"><span data-stu-id="1a489-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="1a489-111">**SQL Server** - **levelprinzipale** **principals**</span><span class="sxs-lookup"><span data-stu-id="1a489-111">**SQL Server**-**level** **principals**</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="1a489-112">-Anmeldename</span><span class="sxs-lookup"><span data-stu-id="1a489-112">Login</span></span>  
  
-   <span data-ttu-id="1a489-113">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="1a489-113">Server Role</span></span>  
  
 <span data-ttu-id="1a489-114">**Prinzipale auf Datenbankebene**</span><span class="sxs-lookup"><span data-stu-id="1a489-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="1a489-115">Datenbankbenutzer</span><span class="sxs-lookup"><span data-stu-id="1a489-115">Database User</span></span>  
  
-   <span data-ttu-id="1a489-116">Datenbankrolle</span><span class="sxs-lookup"><span data-stu-id="1a489-116">Database Role</span></span>  
  
-   <span data-ttu-id="1a489-117">Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="1a489-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="1a489-118">Der SQL Server-Anmeldename sa</span><span class="sxs-lookup"><span data-stu-id="1a489-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="1a489-119">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldename „sa“ ist ein Prinzipal auf Serverebene.</span><span class="sxs-lookup"><span data-stu-id="1a489-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="1a489-120">Er wird standardmäßig bei der Installation einer Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a489-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="1a489-121">Ab [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]ist die Standarddatenbank von sa „Master“.</span><span class="sxs-lookup"><span data-stu-id="1a489-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="1a489-122">Dieses Verhalten unterscheidet sich von früheren Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a489-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="1a489-123">Datenbankrolle public</span><span class="sxs-lookup"><span data-stu-id="1a489-123">public Database Role</span></span>  
 <span data-ttu-id="1a489-124">Jeder Datenbankbenutzer gehört der Datenbankrolle public an.</span><span class="sxs-lookup"><span data-stu-id="1a489-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="1a489-125">Wenn einem Benutzer keine bestimmten Berechtigungen für ein sicherungsfähiges Element erteilt oder verweigert werden, erbt der Benutzer die Berechtigungen, die der Datenbankrolle public für dieses sicherungsfähige Element erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="1a489-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="1a489-126">INFORMATION_SCHEMA und sys</span><span class="sxs-lookup"><span data-stu-id="1a489-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="1a489-127">Jede Datenbank enthält zwei Entitäten, die in Katalogsichten als Benutzer angezeigt werden: INFORMATION_SCHEMA und sys.</span><span class="sxs-lookup"><span data-stu-id="1a489-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="1a489-128">Diese Entitäten werden von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]benötigt.</span><span class="sxs-lookup"><span data-stu-id="1a489-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1a489-129">Es handelt sich dabei nicht um Prinzipale, die geändert oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="1a489-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="1a489-130">Zertifikatbasierte SQL Server-Anmeldenamen</span><span class="sxs-lookup"><span data-stu-id="1a489-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="1a489-131">Serverprinzipale, deren Name von doppelten Nummernzeichen (##) eingeschlossen ist, sind nur für die systeminterne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1a489-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="1a489-132">Die folgenden Prinzipale werden bei der Installation von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aus Zertifikaten erstellt und sollten nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="1a489-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="1a489-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="1a489-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="1a489-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="1a489-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="1a489-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="1a489-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="1a489-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="1a489-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="1a489-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="1a489-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="1a489-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="1a489-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="1a489-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="1a489-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="1a489-140">Der guest-Benutzer</span><span class="sxs-lookup"><span data-stu-id="1a489-140">The guest User</span></span>  
 <span data-ttu-id="1a489-141">Jede Datenbank enthält einen **Gast**.</span><span class="sxs-lookup"><span data-stu-id="1a489-141">Each database includes a **guest**.</span></span> <span data-ttu-id="1a489-142">Dem **guest** -Benutzer erteilte Berechtigungen werden von Benutzern geerbt, die Zugriff auf die Datenbank, jedoch kein Benutzerkonto in der Datenbank besitzen.</span><span class="sxs-lookup"><span data-stu-id="1a489-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="1a489-143">Der **Gast** Benutzer kann nicht gelöscht werden. er kann jedoch deaktiviert werden, indem die Berechtigung aufgehoben wird `CONNECT` .</span><span class="sxs-lookup"><span data-stu-id="1a489-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="1a489-144">Die `CONNECT` Berechtigung kann durch Ausführen `REVOKE CONNECT FROM GUEST` innerhalb einer anderen Datenbank als der Master-oder tempdb-Datenbank aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="1a489-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="1a489-145">Client und Datenbankserver</span><span class="sxs-lookup"><span data-stu-id="1a489-145">Client and Database Server</span></span>  
 <span data-ttu-id="1a489-146">Laut Definition sind ein Client und ein Datenbankserver Sicherheitsprinzipale und können gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="1a489-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="1a489-147">Diese Entitäten können gegenseitig authentifiziert werden, bevor eine sichere Netzwerkverbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1a489-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="1a489-148">unterstützt das [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) -Authentifizierungsprotokoll, das definiert, wie Clients mit einem Netzwerk Authentifizierungsdienst interagieren.</span><span class="sxs-lookup"><span data-stu-id="1a489-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1a489-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1a489-149">Related Tasks</span></span>  
 <span data-ttu-id="1a489-150">Dieser Abschnitt der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Onlinedokumentation umfasst die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1a489-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="1a489-151">Verwalten von Anmeldungen, Benutzern und Schemas: Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1a489-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="1a489-152">Rollen auf Serverebene</span><span class="sxs-lookup"><span data-stu-id="1a489-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="1a489-153">Rollen auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="1a489-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="1a489-154">Anwendungsrollen</span><span class="sxs-lookup"><span data-stu-id="1a489-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a489-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a489-155">See Also</span></span>  
 <span data-ttu-id="1a489-156">[Sichern von SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a489-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="1a489-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a489-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="1a489-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a489-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="1a489-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a489-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="1a489-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a489-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="1a489-161">[Rollen auf Serverebene](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="1a489-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="1a489-162">Rollen auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="1a489-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
