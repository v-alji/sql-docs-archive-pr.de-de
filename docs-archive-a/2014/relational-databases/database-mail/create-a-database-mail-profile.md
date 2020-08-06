---
title: Erstellen eines Profils für Datenbank-E-Mail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616100"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="73d30-102">Erstellen eines Profils für Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="73d30-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="73d30-103">Verwenden Sie den **Assistenten zum Konfigurieren von Datenbank-E-Mail** oder [!INCLUDE[tsql](../../includes/tsql-md.md)] , um öffentliche und private Datenbank-E-Mail-Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73d30-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="73d30-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="73d30-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="73d30-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="73d30-105">Prerequisites</span></span>  
 <span data-ttu-id="73d30-106">Erstellen Sie mindestens ein Datenbank-E-Mail-Konto für das Profil.</span><span class="sxs-lookup"><span data-stu-id="73d30-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="73d30-107">Weitere Informationen zum Erstellen von Datenbank-E-Mail-Konten finden Sie unter [Erstellen eines Kontos für Datenbank-E-Mail](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="73d30-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="73d30-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="73d30-108">Security</span></span>  
 <span data-ttu-id="73d30-109">Mit einem öffentlichen Profil kann jeder Benutzer mit Zugriff auf die **msdb** -Datenbank E-Mail mithilfe dieses Profils senden.</span><span class="sxs-lookup"><span data-stu-id="73d30-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="73d30-110">Ein privates Profil kann von einem Benutzer oder einer Rolle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73d30-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="73d30-111">Durch Gewähren des Rollenzugriffs auf Profile wird eine leichter zu verwaltende Architektur geschaffen.</span><span class="sxs-lookup"><span data-stu-id="73d30-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="73d30-112">Um E-Mail zu senden, müssen Sie Mitglied der **DatabaseMailUserRole** in der **msdb** -Datenbank sein und Zugriff auf mindestens ein Datenbankprofil besitzen.</span><span class="sxs-lookup"><span data-stu-id="73d30-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="73d30-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="73d30-113">Permissions</span></span>  
 <span data-ttu-id="73d30-114">Der Benutzer, der die Profilkonten erstellt und gespeicherte Prozeduren ausführt, sollte Mitglied der festen Serverrolle "sysadmin" sein.</span><span class="sxs-lookup"><span data-stu-id="73d30-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="73d30-115">Verwenden des Assistenten zum Konfigurieren von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="73d30-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="73d30-116">**So erstellen Sie ein Profil für Datenbank-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="73d30-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="73d30-117">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, auf der Datenbank-E-Mail konfiguriert werden soll, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="73d30-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="73d30-118">Erweitern Sie den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="73d30-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="73d30-119">Doppelklicken Sie auf Datenbank-E-Mail, um den Assistenten zum Konfigurieren von Datenbank-E-Mail zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73d30-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="73d30-120">Wählen Sie auf der Seite **Konfigurations Aufgabe auswählen** die Option **Datenbank-E-Mail Konten und Profile verwalten** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="73d30-121">Aktivieren Sie auf der Seite **Profile und Konten verwalten** , aktivieren Sie die Option **Neues Profil erstellen** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="73d30-122">Geben Sie auf der Seite **Neues Profil** den Profilnamen und die Beschreibung ein, und fügen Sie die ins Profil einzuschließenden Konten hinzu. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="73d30-123">Überprüfen Sie auf der Seite **Assistenten abschließen** die auszuführenden Aktionen, und klicken Sie auf **Fertig stellen** , um die Erstellung des neuen Profils abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="73d30-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="73d30-124">**So konfigurieren Sie ein privates Profil für Datenbank-E-Mail:**</span><span class="sxs-lookup"><span data-stu-id="73d30-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="73d30-125">Öffnen Sie den Assistenten zum Konfigurieren von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="73d30-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="73d30-126">Aktivieren Sie auf der Seite **Konfigurationsaufgabe auswählen** die Option **Konten und Profile für Datenbank-E-Mail verwalten** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-127">Aktivieren Sie auf der Seite **Profile und Konten verwalten** die Option **Profilsicherheit verwalten** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-128">Aktivieren Sie auf der Registerkarte **Private Profile** das Kontrollkästchen für das zu konfigurierende Profil, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-129">Überprüfen Sie auf der Seite **Assistenten abschließen** die auszuführenden Aktionen, und klicken Sie auf **Fertig stellen** , um die Konfiguration des Profils abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="73d30-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="73d30-130">**So konfigurieren Sie ein öffentliches Profil für Datenbank-E-Mail:**</span><span class="sxs-lookup"><span data-stu-id="73d30-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="73d30-131">Öffnen Sie den Assistenten zum Konfigurieren von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="73d30-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="73d30-132">Aktivieren Sie auf der Seite **Konfigurationsaufgabe auswählen** die Option **Konten und Profile für Datenbank-E-Mail verwalten** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-133">Aktivieren Sie auf der Seite **Profile und Konten verwalten** die Option **Profilsicherheit verwalten** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-134">Aktivieren Sie auf der Registerkarte **Öffentliche Profile** das Kontrollkästchen für das zu konfigurierende Profil, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73d30-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="73d30-135">Überprüfen Sie auf der Seite **Assistenten abschließen** die auszuführenden Aktionen, und klicken Sie auf **Fertig stellen** , um die Konfiguration des Profils abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="73d30-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="73d30-136">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73d30-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a><span data-ttu-id="73d30-137">So erstellen Sie ein Datenbank-E-Mail privates Profil</span><span class="sxs-lookup"><span data-stu-id="73d30-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="73d30-138">Stellen Sie eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz her.</span><span class="sxs-lookup"><span data-stu-id="73d30-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="73d30-139">Führen Sie die gespeicherte Systemprozedur [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) wie folgt durch, um ein neues Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73d30-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="73d30-141">*@profile_name*= '*Profil Name*'</span><span class="sxs-lookup"><span data-stu-id="73d30-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="73d30-142">*@description*= '*Desciption*'</span><span class="sxs-lookup"><span data-stu-id="73d30-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="73d30-143">dabei *@profile_name* steht für den Namen des Profils und für *@description* die Beschreibung des Profils.</span><span class="sxs-lookup"><span data-stu-id="73d30-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="73d30-144">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="73d30-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="73d30-145">Führen Sie für jedes Konto die gespeicherte Prozedur [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) wie folgt durch:</span><span class="sxs-lookup"><span data-stu-id="73d30-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="73d30-147">*@profile_name*= '*Name des Profils*'</span><span class="sxs-lookup"><span data-stu-id="73d30-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="73d30-148">*@account_name*= '*Name des Kontos*'</span><span class="sxs-lookup"><span data-stu-id="73d30-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="73d30-149">*@sequence_number*= '*Sequenznummer des Kontos innerhalb des Profils.*</span><span class="sxs-lookup"><span data-stu-id="73d30-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="73d30-150">'</span><span class="sxs-lookup"><span data-stu-id="73d30-150">'</span></span>  
  
     <span data-ttu-id="73d30-151">*@profile_name*dabei steht für den Namen des Profils und für *@account_name* den Namen des Kontos, das dem Profil hinzugefügt werden soll, und *@sequence_number* legt die Reihenfolge fest, in der die Konten im Profil verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73d30-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="73d30-152">Erteilen Sie für jede Datenbankrolle oder jeden Benutzer, der E-Mails über dieses Profil sendet, Zugriff auf das Profil.</span><span class="sxs-lookup"><span data-stu-id="73d30-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="73d30-153">Führen Sie dazu die gespeicherte Prozedur [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="73d30-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="73d30-155">*@profile_name*= '*Name des Profils*'</span><span class="sxs-lookup"><span data-stu-id="73d30-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="73d30-156">*@ principal_name* = '*Name des Datenbankbenutzers oder der Rolle*'</span><span class="sxs-lookup"><span data-stu-id="73d30-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="73d30-157">*@is_default*= '*Standardprofil Status* '</span><span class="sxs-lookup"><span data-stu-id="73d30-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="73d30-158">*@profile_name*dabei steht für den Namen des Profils und für *@principal_name* den Namen des Daten Bank Benutzers oder der Daten Bank Rolle, und *@is_default* bestimmt, ob dieses Profil die Standardeinstellung für den Datenbankbenutzer oder die Daten Bank Rolle ist.</span><span class="sxs-lookup"><span data-stu-id="73d30-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="73d30-159">Im folgenden Beispiel werden ein Datenbank-E-Mail-Konto und ein privates Konto für Datenbank-E-Mail erstellt. Anschließend wird das Konto zum Profil hinzugefügt und der Datenbankrolle **DBMailUsers** in der **msdb** -Datenbank Zugriff auf das Profil erteilt.</span><span class="sxs-lookup"><span data-stu-id="73d30-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a><span data-ttu-id="73d30-160">So erstellen Sie ein Datenbank-E-Mail Öffentliches Profil</span><span class="sxs-lookup"><span data-stu-id="73d30-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="73d30-161">Stellen Sie eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz her.</span><span class="sxs-lookup"><span data-stu-id="73d30-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="73d30-162">Führen Sie die gespeicherte Systemprozedur [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) wie folgt durch, um ein neues Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73d30-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="73d30-164">*@profile_name*= '*Profil Name*'</span><span class="sxs-lookup"><span data-stu-id="73d30-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="73d30-165">*@description*= '*Desciption*'</span><span class="sxs-lookup"><span data-stu-id="73d30-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="73d30-166">dabei *@profile_name* steht für den Namen des Profils und für *@description* die Beschreibung des Profils.</span><span class="sxs-lookup"><span data-stu-id="73d30-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="73d30-167">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="73d30-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="73d30-168">Führen Sie für jedes Konto die gespeicherte Prozedur [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) wie folgt durch:</span><span class="sxs-lookup"><span data-stu-id="73d30-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="73d30-170">*@profile_name*= '*Name des Profils*'</span><span class="sxs-lookup"><span data-stu-id="73d30-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="73d30-171">*@account_name*= '*Name des Kontos*'</span><span class="sxs-lookup"><span data-stu-id="73d30-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="73d30-172">*@sequence_number*= '*Sequenznummer des Kontos innerhalb des Profils.*</span><span class="sxs-lookup"><span data-stu-id="73d30-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="73d30-173">'</span><span class="sxs-lookup"><span data-stu-id="73d30-173">'</span></span>  
  
     <span data-ttu-id="73d30-174">*@profile_name*dabei steht für den Namen des Profils und für *@account_name* den Namen des Kontos, das dem Profil hinzugefügt werden soll, und *@sequence_number* legt die Reihenfolge fest, in der die Konten im Profil verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73d30-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="73d30-175">Führen Sie zum Erteilen öffentlichen Zugriffs die gespeicherte Prozedur [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="73d30-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="73d30-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="73d30-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="73d30-177">*@profile_name*= '*Name des Profils*'</span><span class="sxs-lookup"><span data-stu-id="73d30-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="73d30-178">*@ principal_name* = '**öffentlich** oder **0**'</span><span class="sxs-lookup"><span data-stu-id="73d30-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="73d30-179">*@is_default*= '*Standardprofil Status* '</span><span class="sxs-lookup"><span data-stu-id="73d30-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="73d30-180">*@profile_name*dabei ist der Name des Profils, und um anzugeben, dass es sich um *@principal_name* ein öffentliches Profil handelt, *@is_default* bestimmt, ob dieses Profil die Standardeinstellung für den Datenbankbenutzer oder die Daten Bank Rolle ist.</span><span class="sxs-lookup"><span data-stu-id="73d30-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="73d30-181">Im folgenden Beispiel werden ein Datenbank-E-Mail-Konto und ein privates Profil für Datenbank-E-Mail erstellt. Anschließend wird das Konto zum Profil hinzugefügt und öffentlicher Zugriff auf das Profil erteilt.</span><span class="sxs-lookup"><span data-stu-id="73d30-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
