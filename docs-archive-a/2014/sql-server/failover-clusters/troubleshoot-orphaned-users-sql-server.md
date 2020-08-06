---
title: Problembehandlung bei verwaisten Benutzern (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617578"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="dcf57-102">Problembehandlung bei verwaisten Benutzern (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dcf57-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="dcf57-103">Der Prinzipal muss einen gültigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen besitzen, um sich bei einer Instanz von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="dcf57-104">Der Anmeldename wird bei der Authentifizierung benötigt, bei der überprüft wird, ob der Prinzipal eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz herstellen darf.</span><span class="sxs-lookup"><span data-stu-id="dcf57-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dcf57-105">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anmeldungen auf einer Serverinstanz werden in der Katalog Sicht **sys. server_principals** und in der Kompatibilitäts Ansicht **sys.sysAnmeldungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcf57-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="dcf57-106">-Anmeldenamen verwenden für den Zugriff auf die einzelnen Datenbanken einen Datenbankbenutzer, der dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dcf57-106">logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="dcf57-107">Es gibt jedoch zwei Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="dcf57-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="dcf57-108">Das Gastkonto.</span><span class="sxs-lookup"><span data-stu-id="dcf57-108">The guest account.</span></span>  
  
     <span data-ttu-id="dcf57-109">Wenn dieses Konto in der Datenbank aktiviert ist, können die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen, die keinem Datenbankbenutzer zugeordnet sind, die Datenbank als Gastbenutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="dcf57-110">Microsoft Windows-Gruppenmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="dcf57-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="dcf57-111">Ein von einem Windows-Benutzer erstellter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldename kann eine Datenbank verwenden, wenn der Windows-Benutzer Mitglied einer Windows-Gruppe ist, die auch ein Benutzer der Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="dcf57-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="dcf57-112">Die Informationen für die Zuordnung eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldenamens zu einem Datenbankbenutzer werden in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dcf57-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="dcf57-113">Hierzu zählen der Name des Datenbankbenutzers sowie die Sicherheits-ID (SID) des entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldenamens.</span><span class="sxs-lookup"><span data-stu-id="dcf57-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="dcf57-114">Die Berechtigungen dieses Datenbankbenutzers werden für die Autorisierung in der Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="dcf57-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="dcf57-115">Ein Datenbankbenutzer, für den ein entsprechender [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldename auf einer Serverinstanz nicht oder falsch definiert ist, kann sich bei der Instanz nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="dcf57-116">Diese Benutzer werden als *verwaiste Benutzer* der Datenbank dieser Serverinstanz bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dcf57-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="dcf57-117">Ein Datenbankbenutzer kann zu einem verwaisten Benutzer werden, wenn der entsprechende [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldename gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="dcf57-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="dcf57-118">Ein Datenbankbenutzer kann auch dann zu einem verwaisten Benutzer werden, wenn die Datenbank auf einer anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz wiederhergestellt oder an eine andere SQL Server-Instanz angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dcf57-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dcf57-119">Verwaisungen treten auf, wenn der Datenbankbenutzer einer SID zugeordnet wird, die auf der neuen Serverinstanz nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="dcf57-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf57-120">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anmelde Name kann nicht auf eine Datenbank zugreifen, in der er keinen entsprechenden Datenbankbenutzer besitzt, es sei denn, der **Gast** ist in dieser Datenbank</span><span class="sxs-lookup"><span data-stu-id="dcf57-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="dcf57-121">Weitere Informationen zum Erstellen eines Datenbank-Benutzerkontos finden Sie unter [Create User &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcf57-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="dcf57-122">So ermitteln Sie verwaiste Benutzer</span><span class="sxs-lookup"><span data-stu-id="dcf57-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="dcf57-123">Zum Ermitteln von verwaisten Benutzern führen Sie die folgenden Transact-SQL-Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="dcf57-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="dcf57-124">Die Ausgabe führt alle Benutzer der aktuellen Datenbank auf, die mit keinem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen verknüpft sind, sowie die entsprechenden SIDs (Sicherheits-IDs).</span><span class="sxs-lookup"><span data-stu-id="dcf57-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="dcf57-125">Weitere Informationen finden Sie unter [sp_change_users_login &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcf57-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf57-126">**sp_change_users_login** kann nicht mit Anmeldungen verwendet werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die aus Windows erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="dcf57-127">So lösen Sie einen verwaisten Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="dcf57-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="dcf57-128">Zum Auflösen eines verwaisten Benutzers führen Sie folgende Prozedur aus:</span><span class="sxs-lookup"><span data-stu-id="dcf57-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="dcf57-129">Mit dem folgenden Befehl wird das von *<login_name>* angegebene Server Anmelde Konto erneut mit dem Datenbankbenutzer verknüpft, der durch *<database_user>* angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dcf57-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="dcf57-130">Weitere Informationen finden Sie unter [sp_change_users_login &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcf57-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="dcf57-131">Nachdem Sie den im letzten Schritt angegebenen Code ausgeführt haben, kann der Benutzer wieder auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dcf57-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="dcf57-132">Der Benutzer kann dann das Kennwort des *<login_name>* Anmelde Kontos mithilfe der gespeicherten Prozedur **sp_password** wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="dcf57-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dcf57-133">Nur Anmeldenamen mit der Berechtigung ALTER ANY LOGIN können auch die Kennwörter von anderen Benutzernamen ändern.</span><span class="sxs-lookup"><span data-stu-id="dcf57-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="dcf57-134">Allerdings können die Kennwörter von Mitgliedern der **sysadmin** -Rolle nur von Mitgliedern der **sysadmin** -Rolle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcf57-135">**sp_password** können nicht für Windows-Konten verwendet werden [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf57-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="dcf57-136">Benutzer, die über das Windows-Netzwerkkonto eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen, werden durch Windows authentifiziert. Deshalb können ihre Kennwörter nur unter Windows geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dcf57-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="dcf57-137">Weitere Informationen finden Sie unter [sp_password &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcf57-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf57-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcf57-138">See Also</span></span>  
 <span data-ttu-id="dcf57-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-141">[sp_change_users_login &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-143">[sp_grantlogin &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-144">[sp_password &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="dcf57-145">[sys.sysBenutzer &#40;Transact-SQL-&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf57-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="dcf57-146">sys.sysAnmeldungen &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf57-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
