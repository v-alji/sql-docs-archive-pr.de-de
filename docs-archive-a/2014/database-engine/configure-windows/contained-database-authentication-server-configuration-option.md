---
title: Serverkonfigurationsoption „Contained Database Authentication“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- contained_database_authentication_TSQL
- contained database authentication
helpviewer_keywords:
- contained database, enabling
- contained database authentication option
ms.assetid: b80768d2-ac20-4035-a335-d9adb74b3f6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf5bf07c8b0913ff81f31ff0ca64a18eee0f2ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619322"
---
# <a name="contained-database-authentication-server-configuration-option"></a><span data-ttu-id="7b8cb-102">Contained Database Authentication (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="7b8cb-102">contained database authentication Server Configuration Option</span></span>
  <span data-ttu-id="7b8cb-103">Verwenden Sie die **contained database authentication** -Option, um in der Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]eigenständige Datenbanken zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-103">Use the **contained database authentication** option to enable contained databases on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7b8cb-104">Mit dieser Serveroption können Sie **contained database authentication**steuern.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-104">This server option allows you to control **contained database authentication**.</span></span>  
  
-   <span data-ttu-id="7b8cb-105">Wenn **contained database authentication** für die Instanz deaktiviert (0) ist, können keine eigenständigen Datenbanken erstellt oder an das [!INCLUDE[ssDE](../../includes/ssde-md.md)]angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-105">When **contained database authentication** is off (0) for the instance, contained databases cannot be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="7b8cb-106">Wenn **contained database authentication** für die Instanz aktiviert (1) ist, können eigenständige Datenbanken erstellt oder an das [!INCLUDE[ssDE](../../includes/ssde-md.md)]angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-106">When **contained database authentication** is on (1) for the instance, contained databases can be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="7b8cb-107">Eine eigenständige Datenbank schließt alle erforderlichen Datenbankeinstellungen und Metadaten zum Definieren der Datenbank ein, und ihre Konfiguration ist nicht von der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz abhängig, in der die Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-107">A contained database includes all database settings and metadata required to define the database and has no configuration dependencies on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] where the database is installed.</span></span> <span data-ttu-id="7b8cb-108">Benutzer können eine Verbindung mit der Datenbank herstellen, ohne dass sie bei der Anmeldung auf der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Ebene eine Authentifizierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-108">Users can connect to the database without authenticating a login at the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level.</span></span> <span data-ttu-id="7b8cb-109">Das Isolieren der Datenbank von der Datenbank-Engine ermöglicht das einfache Verschieben der Datenbank in eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b8cb-109">Isolating the database from the Database Engine makes it possible to easily move the database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b8cb-110">Dadurch, dass alle Datenbankeinstellungen in der Datenbank enthalten sind, können Datenbankbesitzer sämtliche Konfigurationseinstellungen für die Datenbank verwalten.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-110">Including all the database settings in the database enables database owners to manage all the configuration settings for the database.</span></span> <span data-ttu-id="7b8cb-111">Weitere Informationen zu eigenständigen Datenbanken finden Sie unter [Eigenständige Datenbanken](../../relational-databases/databases/contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7b8cb-111">For more information about contained databases, see [Contained Databases](../../relational-databases/databases/contained-databases.md).</span></span>  
  
 <span data-ttu-id="7b8cb-112">Wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz über eigenständige Datenbanken verfügt, kann die Einstellung **contained database authentication** mit der **RECONFIGURE WITH OVERRIDE** -Anweisung auf 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-112">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has any contained databases the **contained database authentication** setting can be set to 0 by using the **RECONFIGURE WITH OVERRIDE** statement.</span></span> <span data-ttu-id="7b8cb-113">Indem **contained database authentication** auf 0 festgelegt wird, wird die Authentifizierung eigenständiger Datenbanken für diese Datenbanken deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-113">Setting **contained database authentication** to 0 will disable contained database authentication for the contained databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7b8cb-114">Wenn eigenständige Datenbanken aktiviert sind, können Datenbankbenutzer mit der Berechtigung ALTER ANY USER, wie z. B. Mitglieder der Rollen db_owner und db_accessadmin Zugriff auf Datenbanken gewähren und auf diese Weise auch Zugriff auf die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gewähren.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-114">When contained databases are enabled, database users with the ALTER ANY USER permission, such as members of the db_owner and db_accessadmin database roles, can grant access to databases and by doing so, grant access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b8cb-115">Das bedeutet, dass die Kontrolle über den Zugriff zum Server nicht mehr auf Mitglieder der festen Serverrollen „sysadmin“ und „securityadmin“ sowie Zugangsdaten mit den Serverebenenberechtigungen CONTROL SERVER und ALTER ANY LOGIN beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-115">This means that control over access to the server is no longer limited to members of the sysadmin and securityadmin fixed server role, and logins with the server level CONTROL SERVER and ALTER ANY LOGIN permission.</span></span> <span data-ttu-id="7b8cb-116">Bevor Sie eigenständige Datenbanken zulassen, sollten Sie die Risiken kennen, die eigenständige Datenbanken mit sich bringen.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-116">Before allowing contained databases, you should understand the risks associated with contained databases.</span></span> <span data-ttu-id="7b8cb-117">Weitere Informationen finden Sie unter [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7b8cb-117">For more information, see [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7b8cb-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7b8cb-118">Examples</span></span>  
 <span data-ttu-id="7b8cb-119">Im folgenden Beispiel werden enthaltene Datenbanken für die [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7b8cb-119">The following example enables contained databases on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b8cb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b8cb-120">See Also</span></span>  
 <span data-ttu-id="7b8cb-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b8cb-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="7b8cb-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b8cb-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 [<span data-ttu-id="7b8cb-123">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7b8cb-123">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
