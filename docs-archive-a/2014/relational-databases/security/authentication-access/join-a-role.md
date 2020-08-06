---
title: Verknüpfen einer Rolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609767"
---
# <a name="join-a-role"></a><span data-ttu-id="25e57-102">Verknüpfen einer Rolle</span><span class="sxs-lookup"><span data-stu-id="25e57-102">Join a Role</span></span>
  <span data-ttu-id="25e57-103">In diesem Thema wird beschrieben, wie Rollen in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]Anmeldenamen und Datenbankbenutzern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="25e57-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="25e57-104">Für die effiziente Verwaltung von Berechtigungen in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwenden Sie Rollen.</span><span class="sxs-lookup"><span data-stu-id="25e57-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="25e57-105">Weisen Sie Rollen Berechtigungen zu, und fügen Sie den Rollen dann Benutzer und Anmeldenamen hinzu, oder entfernen Sie solche.</span><span class="sxs-lookup"><span data-stu-id="25e57-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="25e57-106">Bei Verwendung von Rollen müssen Berechtigungen nicht für jeden Benutzer einzeln verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="25e57-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="25e57-107">unterstützt vier Typen von Rollen.</span><span class="sxs-lookup"><span data-stu-id="25e57-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="25e57-108">Feste Serverrollen</span><span class="sxs-lookup"><span data-stu-id="25e57-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="25e57-109">Benutzerdefinierte Serverrollen</span><span class="sxs-lookup"><span data-stu-id="25e57-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="25e57-110">Feste Datenbankrollen</span><span class="sxs-lookup"><span data-stu-id="25e57-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="25e57-111">Benutzerdefinierte Datenbankrollen</span><span class="sxs-lookup"><span data-stu-id="25e57-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="25e57-112">Die festen Rollen sind in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]automatisch verfügbar.</span><span class="sxs-lookup"><span data-stu-id="25e57-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25e57-113">Feste Rollen verfügen über die erforderlichen Berechtigungen zum Ausführen häufiger Tasks.</span><span class="sxs-lookup"><span data-stu-id="25e57-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="25e57-114">Weitere Informationen zu festen Rollen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="25e57-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="25e57-115">Benutzerdefinierte Rollen werden von Ihnen erstellt und können mit den von Ihnen ausgewählten Berechtigungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="25e57-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="25e57-116">Weitere Informationen zu benutzerdefinierten Rollen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="25e57-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="25e57-117">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="25e57-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="25e57-118">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="25e57-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="25e57-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="25e57-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="25e57-120">Security</span><span class="sxs-lookup"><span data-stu-id="25e57-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="25e57-121">**Zuweisen von Rollen zu Anmeldenamen und Datenbankbenutzern mit:**</span><span class="sxs-lookup"><span data-stu-id="25e57-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="25e57-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25e57-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="25e57-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25e57-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="25e57-124">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="25e57-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="25e57-125">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="25e57-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="25e57-126">Durch das Ändern des Namens einer Datenbankrolle werden die ID-Nummer, der Besitzer oder Berechtigungen der Rolle nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="25e57-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="25e57-127">Datenbankrollen werden in den Katalogsichten sys.database_role_members und sys.database_principals angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25e57-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="25e57-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="25e57-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="25e57-129">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="25e57-129">Permissions</span></span>  
 <span data-ttu-id="25e57-130">Erfordert `ALTER ANY ROLE` die-Berechtigung für die Datenbank, `ALTER` die-Berechtigung für die Rolle oder die Mitgliedschaft in **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="25e57-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="25e57-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25e57-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="25e57-132">So fügen Sie einer festen Serverrolle ein Mitglied hinzu</span><span class="sxs-lookup"><span data-stu-id="25e57-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="25e57-133">Erweitern Sie im Objekt-Explorer den Server, für den Sie eine feste Serverrolle bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="25e57-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="25e57-134">Erweitern Sie den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="25e57-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="25e57-135">Erweitern Sie den Ordner **Serverrollen** .</span><span class="sxs-lookup"><span data-stu-id="25e57-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="25e57-136">Klicken Sie mit der rechten Maustaste auf die Rolle, die Sie bearbeiten möchten, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="25e57-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="25e57-137">Klicken Sie im Dialogfeld **Eigenschaften von Server Rolle-**_server_role_name_ auf der Seite **Mitglieder** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="25e57-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="25e57-138">Geben Sie im Dialogfeld **Serveranmeldenamen oder -rolle auswählen** unter **Geben Sie die Namen der auszuwählenden Objekte ein (Beispiele)** den Anmeldenamen oder die Serverrolle ein, den bzw. die Sie dieser Serverrolle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="25e57-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="25e57-139">Alternativ können Sie auf **Durchsuchen** klicken und verfügbare Objekte im Dialogfeld **Nach Objekten suchen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="25e57-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="25e57-140">Klicken Sie auf **OK** , um zum Dialogfeld **Eigenschaften von Server Rolle-**_server_role_name_ zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="25e57-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="25e57-141">So fügen Sie einer benutzerdefinierten Datenbankrolle ein Mitglied hinzu</span><span class="sxs-lookup"><span data-stu-id="25e57-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="25e57-142">Erweitern Sie im Objekt-Explorer den Server, für den Sie eine benutzerdefinierte Datenbankrolle bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="25e57-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="25e57-143">Erweitern Sie den Ordner **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="25e57-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="25e57-144">Erweitern Sie die Datenbank, in der Sie eine benutzerdefinierte Datenbankrolle bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="25e57-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="25e57-145">Erweitern Sie den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="25e57-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="25e57-146">Erweitern Sie den Ordner **Rollen** .</span><span class="sxs-lookup"><span data-stu-id="25e57-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="25e57-147">Erweitern Sie den Ordner **Serverrollen** .</span><span class="sxs-lookup"><span data-stu-id="25e57-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="25e57-148">Klicken Sie mit der rechten Maustaste auf die Rolle, die Sie bearbeiten möchten, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="25e57-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="25e57-149">Klicken Sie im Dialogfeld **Eigenschaften der Daten Bank Rolle-**_database_role_name_ auf der Seite **Allgemein** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="25e57-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="25e57-150">Geben Sie im Dialogfeld **Datenbankbenutzer oder -rolle auswählen** unter **Geben Sie die Namen der auszuwählenden Objekte ein (Beispiele)** den Anmeldenamen oder die Datenbankrolle ein, den bzw. die Sie dieser Datenbankrolle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="25e57-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="25e57-151">Alternativ können Sie auf **Durchsuchen** klicken und verfügbare Objekte im Dialogfeld **Nach Objekten suchen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="25e57-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="25e57-152">Klicken Sie auf **OK** , um zum Dialogfeld **Eigenschaften der Daten Bank Rolle-**_database_role_name_ zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="25e57-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="25e57-153">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25e57-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="25e57-154">So fügen Sie einer festen Serverrolle ein Mitglied hinzu</span><span class="sxs-lookup"><span data-stu-id="25e57-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="25e57-155">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="25e57-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="25e57-156">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="25e57-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="25e57-157">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="25e57-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="25e57-158">Weitere Informationen finden Sie unter [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25e57-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="25e57-159">So fügen Sie einer benutzerdefinierten Datenbankrolle ein Mitglied hinzu</span><span class="sxs-lookup"><span data-stu-id="25e57-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="25e57-160">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="25e57-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="25e57-161">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="25e57-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="25e57-162">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="25e57-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="25e57-163">Weitere Informationen finden Sie unter [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25e57-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e57-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25e57-164">See Also</span></span>  
 <span data-ttu-id="25e57-165">[Rollen auf Serverebene](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="25e57-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="25e57-166">[Rollen auf Datenbankebene](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="25e57-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="25e57-167">Anwendungsrollen</span><span class="sxs-lookup"><span data-stu-id="25e57-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
