---
title: Erstellen einer Serverrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620784"
---
# <a name="create-a-server-role"></a><span data-ttu-id="d9e7d-102">Erstellen einer Serverrolle</span><span class="sxs-lookup"><span data-stu-id="d9e7d-102">Create a Server Role</span></span>
  <span data-ttu-id="d9e7d-103">In diesem Thema wird beschrieben, wie Sie einen neuen Server in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d9e7d-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d9e7d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d9e7d-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d9e7d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d9e7d-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d9e7d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d9e7d-107">Security</span><span class="sxs-lookup"><span data-stu-id="d9e7d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d9e7d-108">**So erstellen Sie eine neue Serverrolle mit**</span><span class="sxs-lookup"><span data-stu-id="d9e7d-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="d9e7d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9e7d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d9e7d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d9e7d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d9e7d-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d9e7d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d9e7d-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d9e7d-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d9e7d-113">Serverrollen kann keine Berechtigung für sicherungsfähige Elemente auf Datenbankebene gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="d9e7d-114">Informationen zum Erstellen von Datenbankrollen finden Sie unter [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9e7d-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d9e7d-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d9e7d-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d9e7d-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d9e7d-116">Permissions</span></span>  
  
-   <span data-ttu-id="d9e7d-117">Erfordert die CREATE SERVER ROLE-Berechtigung oder die Mitgliedschaft in der festen sysadmin-Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="d9e7d-118">Erfordert für Anmeldenamen außerdem IMPERSONATE für den *server_principal* , die ALTER-Berechtigung für Serverrollen, die als *server_principal* verwendet werden, oder die Mitgliedschaft in einer Windows-Gruppe, die als server_principal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="d9e7d-119">Wenn Sie die AUTHORIZATION-Option verwenden, um den Besitz für Serverrollen zuzuweisen, sind außerdem folgende Berechtigungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d9e7d-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="d9e7d-120">Um einer Serverrolle einen anderen Anmeldenamen als Besitzer zuzuweisen, ist die IMPERSONATE-Berechtigung für diesen Anmeldenamen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="d9e7d-121">Um einer Serverrolle eine andere Serverrolle als Besitzer zuzuweisen, ist die Mitgliedschaft in der Empfängerserverrolle oder die ALTER-Berechtigung für diese Serverrolle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d9e7d-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9e7d-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="d9e7d-123">So erstellen Sie eine neue Serverrolle</span><span class="sxs-lookup"><span data-stu-id="d9e7d-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="d9e7d-124">Erweitern Sie im Objekt-Explorer den Server, auf dem Sie die neue Serverrolle erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="d9e7d-125">Erweitern Sie den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="d9e7d-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="d9e7d-126">Klicken Sie mit der rechten Maustaste auf den Ordner **Serverrollen**, und klicken Sie dann auf **Neue Serverrolle...** .</span><span class="sxs-lookup"><span data-stu-id="d9e7d-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="d9e7d-127">Geben Sie im Dialogfeld **neue Server Rolle-**_server_role_name_ auf der Seite **Allgemein** einen Namen für die neue Server Rolle in das Feld **Server Rollenname** ein.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="d9e7d-128">Geben Sie im Feld **Besitzer** den Namen des Serverprinzipals ein, der die neue Rolle besitzt.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="d9e7d-129">Klicken Sie alternativ auf die Auslassungspunkte **(...)** , um das Dialogfeld **Serveranmeldenamen oder -rolle auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="d9e7d-130">Wählen Sie unter **Sicherungsfähige Elemente**ein oder mehrere sicherungsfähige Elemente auf Serverebene aus.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="d9e7d-131">Wenn ein sicherungsfähiges Element ausgewählt ist, können dieser Serverrolle Berechtigungen für dieses sicherungsfähige Element gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="d9e7d-132">Aktivieren Sie im Feld **Berechtigungen: Explizit** das Kontrollkästchen, um für die ausgewählten sicherungsfähigen Elemente Berechtigungen zu gewähren, als Berechtigung mit Recht zum Erteilen zu gewähren oder zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="d9e7d-133">Wenn eine Berechtigung nicht für alle ausgewählten sicherungsfähigen Elemente gewährt oder verweigert werden kann, wird die Berechtigung als teilweise ausgewählt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="d9e7d-134">Fügen Sie auf der Seite **Mitglieder** über die Schaltfläche **Hinzufügen** Anmeldungen hinzu, die Einzelpersonen oder Gruppen für die neue Serverrolle darstellen.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="d9e7d-135">Eine benutzerdefinierte Serverrolle kann Mitglied einer anderen Serverrolle sein.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="d9e7d-136">Aktivieren Sie auf der Seite **Mitgliedschaften** ein Kontrollkästchen, um die aktuelle benutzerdefinierte Serverrolle als Mitglied einer ausgewählten Serverrolle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d9e7d-137">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d9e7d-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="d9e7d-138">So erstellen Sie eine neue Serverrolle</span><span class="sxs-lookup"><span data-stu-id="d9e7d-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="d9e7d-139">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d9e7d-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d9e7d-141">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d9e7d-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="d9e7d-142">Weitere Informationen finden Sie unter [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9e7d-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
