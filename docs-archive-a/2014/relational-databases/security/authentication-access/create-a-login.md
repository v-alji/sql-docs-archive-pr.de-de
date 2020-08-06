---
title: Erstellen eines Anmeldenamens | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697755"
---
# <a name="create-a-login"></a><span data-ttu-id="fa6b7-102">Erstellen eines Anmeldenamens</span><span class="sxs-lookup"><span data-stu-id="fa6b7-102">Create a Login</span></span>
  <span data-ttu-id="fa6b7-103">In diesem Thema wird beschrieben, wie eine Anmeldung in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fa6b7-104">Ein Anmeldename ist die Identität von Personen oder Prozessen, die eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]herstellen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fa6b7-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fa6b7-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fa6b7-107">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="fa6b7-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="fa6b7-108">Security</span><span class="sxs-lookup"><span data-stu-id="fa6b7-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fa6b7-109">**So erstellen Sie eine Anmeldung mit**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="fa6b7-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa6b7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fa6b7-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa6b7-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="fa6b7-112">**Nachverfolgung:**  [Erforderliche Schritte nach Erstellen eines Anmeldenamens](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="fa6b7-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="fa6b7-113">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="fa6b7-113">Background</span></span>  
 <span data-ttu-id="fa6b7-114">Eine Anmeldung ist ein Sicherheitsprinzipal oder eine Entität, die von einem sicheren System authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="fa6b7-115">Benutzer benötigen einen Anmeldenamen, um eine Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]herstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fa6b7-116">Sie können auf Grundlage eines Windows-Prinzipals (z. B. ein Domänenbenutzer oder eine Windows-Domänengruppe) eine Anmeldung erstellen, oder Sie können eine Anmeldung erstellen, die nicht auf einem Windows-Prinzipal (z. B. eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung) basiert.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa6b7-117">Für die Verwendung der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Authentifizierung muss [!INCLUDE[ssDE](../../../includes/ssde-md.md)] die Authentifizierung im gemischten Modus verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="fa6b7-118">Weitere Informationen finden Sie unter [Auswählen eines Authentifizierungsmodus](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="fa6b7-119">Als Sicherheitsprinzipale können Anmeldenamen Berechtigungen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="fa6b7-120">Der Gültigkeitsbereich eines Anmeldenamens ist das gesamte [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa6b7-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="fa6b7-121">Um eine bestimmte Datenbank mit einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]zu verbinden, muss ein Anmeldename einem Datenbankbenutzer zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="fa6b7-122">Die Berechtigungen innerhalb der Datenbank werden dem Datenbankbenutzer, nicht dem Anmeldenamen, gewährt bzw. verweigert.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="fa6b7-123">Berechtigungen, bei denen der Gültigkeitsbereich die gesamte Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] abdeckt (z. B. die `CREATE ENDPOINT`-Berechtigung), kann ein Anmeldung gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fa6b7-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fa6b7-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="fa6b7-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fa6b7-125">Permissions</span></span>  
 <span data-ttu-id="fa6b7-126">Erfordert die `ALTER ANY LOGIN`-Berechtigung oder die `ALTER LOGIN`-Berechtigung für den Server.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fa6b7-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa6b7-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="fa6b7-128">So erstellen Sie eine SQL Server-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="fa6b7-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="fa6b7-129">Erweitern Sie im Objekt-Explorer den Ordner der Serverinstanz, in dem Sie eine neue Anmeldung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="fa6b7-130">Klicken Sie mit der rechten Maustaste auf den Ordner **Sicherheit**, zeigen Sie auf **Neu**, und wählen Sie dann **Anmeldung...** aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="fa6b7-131">Geben Sie in das Dialogfeld **Anmeldung - Neu** auf der Seite **Allgemein** einen Benutzernamen in das Feld **Anmeldename** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="fa6b7-132">Klicken Sie alternativ auf **Suchen...** , um das Dialogfeld **Benutzer oder Gruppe auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="fa6b7-133">Wenn Sie auf **Suchen...** klicken:</span><span class="sxs-lookup"><span data-stu-id="fa6b7-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="fa6b7-134">Klicken Sie unter **Wählen Sie den Objekttyp aus** auf **Objekttypen...** , um das Dialogfeld **Objekttypen** zu öffnen, und wählen Sie beliebige oder alle der folgenden Optionen aus: **Integrierte Sicherheitsprinzipale**, **Gruppen** und **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="fa6b7-135">Die Optionen**Integrierte Sicherheitsprinzipale** und **Benutzer** sind standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="fa6b7-136">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="fa6b7-137">Klicken Sie unter **Suchpfad** auf **Speicherorte...** , um das Dialogfeld **Speicherorte** zu öffnen, und wählen Sie einen der verfügbaren Serverspeicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="fa6b7-138">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="fa6b7-139">Geben Sie unter **Geben Sie die zu verwendenden Objektnamen ein (Beispiele)** den Benutzer- oder Gruppennamen ein, den Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="fa6b7-140">Weitere Informationen finden Sie unter [Benutzer, Computer oder Gruppen auswählen (Dialogfeld)](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="fa6b7-141">Klicken Sie auf **Erweitert...** für erweiterte Suchoptionen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="fa6b7-142">Weitere Informationen finden Sie unter [Auswählen von Benutzern, Computern oder Gruppen (Dialogfeld) – Erweitert (Seite)](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="fa6b7-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="fa6b7-144">Um auf Grundlage eines Windows-Prinzipals eine Anmeldung zu erstellen, wählen Sie **Windows-Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="fa6b7-145">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="fa6b7-146">Um eine Anmeldung zu erstellen, die auf einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank gespeichert wird, wählen Sie **SQL Server-Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="fa6b7-147">Geben Sie im Feld **Kennwort** ein Kennwort für den neuen Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="fa6b7-148">Geben Sie dieses Kennwort erneut im Feld **Kennwort bestätigen** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="fa6b7-149">Wenn Sie ein vorhandenes Kennwort ändern, wählen Sie **Altes Kennwort angeben**aus, und geben Sie dann das alte Kennwort im Feld **Altes Kennwort** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="fa6b7-150">Um Kennwortrichtlinienoptionen für Komplexität und Erzwingung zu erzwingen, wählen Sie **Kennwortrichtlinie erzwingen**aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="fa6b7-151">Weitere Informationen finden Sie unter [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="fa6b7-152">Dies ist eine Standardoption, wenn **SQL Server-Authentifizierung** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="fa6b7-153">Um den Ablauf von Kennwortrichtlinienoptionen zu erzwingen, wählen Sie **Ablauf des Kennworts erzwingen**aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="fa6b7-154">**Kennwortrichtlinie erzwingen** muss ausgewählt sein, damit dieses Kontrollkästchen aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="fa6b7-155">Dies ist eine Standardoption, wenn **SQL Server-Authentifizierung** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="fa6b7-156">Wählen Sie **Benutzer muss das Kennwort bei der nächsten Anmeldung ändern**aus, um den Benutzer zu zwingen, nach der ersten Anmeldung ein neues Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="fa6b7-157">Die Option**Ablauf des Kennworts erzwingen** muss ausgewählt sein, damit dieses Kontrollkästchen aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="fa6b7-158">Dies ist eine Standardoption, wenn **SQL Server-Authentifizierung** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="fa6b7-159">Um einem eigenständigen Sicherheitszertifikat die Anmeldung zuzuordnen, wählen Sie **Zugeordnet zu Zertifikat** aus, und wählen Sie anschließend den Namen eines vorhandenen Zertifikats aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="fa6b7-160">Um einem eigenständigen asymmetrischen Schlüssel die Anmeldung zuzuordnen, wählen Sie **Zugeordnet zu asymmetrischem Schlüssel** aus, und wählen Sie anschließend den Namen eines vorhandenen Schlüssels aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="fa6b7-161">Um Sicherheitsanmeldeinformationen die Anmeldung zuzuordnen, aktivieren Sie das Kontrollkästchen **Zugeordnet zu Anmeldeinformationen** , und wählen Sie anschließend entweder einen vorhandenen Anmeldenamen aus der Liste aus, oder klicken Sie auf **Hinzufügen** , um einen neuen Anmeldenamen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="fa6b7-162">Um eine Zuordnung zu Sicherheitsanmeldeinformationen aus der Anmeldung zu entfernen, wählen Sie die Anmeldeinformationen aus der Liste **Zugeordnete Anmeldeinformationen** aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="fa6b7-163">Weitere Informationen über Anmeldenamen im Allgemeinen finden Sie unter [Anmeldeinformationen &#40;Datenbank-Engine&#41;](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="fa6b7-164">Wählen Sie eine Standarddatenbank für die Anmeldung aus der Liste **Standarddatenbank** aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="fa6b7-165">**Master** ist der Standardwert für diese Option.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="fa6b7-166">Wählen Sie eine Standardsprache für die Anmeldung aus der Liste **Standardsprache** aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="fa6b7-167">Zusätzliche Optionen</span><span class="sxs-lookup"><span data-stu-id="fa6b7-167">Additional Options</span></span>  
 <span data-ttu-id="fa6b7-168">Im Dialogfeld **Anmeldung – Neu** sind auch Optionen auf vier zusätzlichen Seiten verfügbar: **Serverrollen**, **Benutzerzuordnung**, **Sicherungsfähige Elemente** und **Status**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="fa6b7-169">Serverrollen</span><span class="sxs-lookup"><span data-stu-id="fa6b7-169">Server Roles</span></span>  
 <span data-ttu-id="fa6b7-170">Die Seite **Serverrollen** listet alle möglichen Rollen auf, die der neuen Anmeldung zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="fa6b7-171">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fa6b7-171">The following options are available:</span></span>  
  
 <span data-ttu-id="fa6b7-172">Kontrollkästchen**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-173">Mitglieder der festen Serverrolle **bulkadmin** können die BULK INSERT-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="fa6b7-174">Kontrollkästchen**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="fa6b7-175">Mitglieder der festen Serverrolle **dbcreator** können beliebige Datenbanken erstellen, ändern, löschen und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="fa6b7-176">Kontrollkästchen**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-177">Mitglieder der festen Serverrolle **diskadmin** können Datenträgerdateien verwalten.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="fa6b7-178">Kontrollkästchen**processadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-178">**processadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-179">Mitglieder der festen Serverrolle **processadmin** können Prozesse beenden, die in einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="fa6b7-180">Kontrollkästchen**public**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-180">**public** check box</span></span>  
 <span data-ttu-id="fa6b7-181">Alle SQL Server-Benutzer, -Gruppen und -Rollen gehören standardmäßig zur festen Serverrolle **public** .</span><span class="sxs-lookup"><span data-stu-id="fa6b7-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="fa6b7-182">Kontrollkästchen**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-183">Mitglieder der festen Serverrolle **securityadmin** können Anmeldungen und deren Eigenschaften verwalten.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="fa6b7-184">Sie verfügen für Berechtigungen auf Serverebene über die Berechtigungen GRANT, DENY und REVOKE.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="fa6b7-185">Sie verfügen für Berechtigungen auf Datenbankebene ebenfalls über die Berechtigungen GRANT, DENY und REVOKE.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="fa6b7-186">Sie können außerdem Kennwörter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldungen zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="fa6b7-187">Kontrollkästchen**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="fa6b7-188">Mitglieder der festen Serverrolle **serveradmin** können serverweite Konfigurationsoptionen ändern und den Server herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="fa6b7-189">Kontrollkästchen**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-190">Mitglieder der festen Serverrolle **setupadmin** können Verbindungsserver hinzufügen und entfernen, und sie können einige gespeicherte Systemprozeduren ausführen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="fa6b7-191">Kontrollkästchen**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="fa6b7-192">Mitglieder der festen Serverrolle **sysadmin** können in [!INCLUDE[ssDE](../../../includes/ssde-md.md)]beliebige Aktivitäten ausführen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="fa6b7-193">Benutzerzuordnung</span><span class="sxs-lookup"><span data-stu-id="fa6b7-193">User Mapping</span></span>  
 <span data-ttu-id="fa6b7-194">Die Seite **Benutzerzuordnung** listet alle möglichen Datenbanken und die Mitgliedschaften in der Datenbankrolle auf jenen Datenbanken auf, die für die Anmeldung übernommen werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="fa6b7-195">Die ausgewählten Datenbanken bestimmen die Rollenmitgliedschaften, die für die Anmeldung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="fa6b7-196">Die folgenden Optionen sind auf dieser Seite verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fa6b7-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="fa6b7-197">**Benutzer, die dieser Anmeldung zugeordnet sind**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="fa6b7-198">Wählt die Datenbanken aus, auf die von dieser Anmeldung zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-198">Select the databases that this login can access.</span></span> <span data-ttu-id="fa6b7-199">Wenn Sie eine Datenbank auswählen, werden die gültigen Datenbankrollen im Bereich **Mitgliedschaft in Datenbankrolle für:** _Datenbankname_ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="fa6b7-200">**Map**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-200">**Map**</span></span>  
 <span data-ttu-id="fa6b7-201">Ermöglicht der Anmeldung den Zugriff auf die nachfolgend aufgeführten Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="fa6b7-202">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-202">**Database**</span></span>  
 <span data-ttu-id="fa6b7-203">Führt die auf dem Server verfügbaren Datenbanken in einer Liste auf.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="fa6b7-204">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-204">**User**</span></span>  
 <span data-ttu-id="fa6b7-205">Geben Sie einen Datenbankbenutzer an, der der Anmeldung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="fa6b7-206">Standardmäßig ist der Name des Datenbankbenutzers mit dem Anmeldenamen identisch.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="fa6b7-207">**Standardschema**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-207">**Default Schema**</span></span>  
 <span data-ttu-id="fa6b7-208">Gibt das Standardschema des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="fa6b7-209">Wenn ein Benutzer zum ersten Mal erstellt wird, wird als Standardschema **dbo**verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="fa6b7-210">Es kann auch ein Standardschema angegeben werden, das noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="fa6b7-211">Für Benutzer, die einer Windows-Gruppe, einem Zertifikat oder einem asymmetrischen Schlüssel zugeordnet sind, kann kein Standardschema angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="fa6b7-212">**Gastkonto aktiviert für:** _Datenbankname_</span><span class="sxs-lookup"><span data-stu-id="fa6b7-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="fa6b7-213">Ein Nur-Lese-Attribut, das angibt, ob das Gastkonto für die ausgewählte Datenbank aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="fa6b7-214">Verwenden Sie die Seite **Status** des Dialogfelds **Anmeldungseigenschaften** des Gastkontos, um das Gastkonto zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="fa6b7-215">**Mitgliedschaft in Datenbankrolle für:** _Datenbankname_</span><span class="sxs-lookup"><span data-stu-id="fa6b7-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="fa6b7-216">Wählen Sie die Rollen für den Benutzer in der angegebenen Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="fa6b7-217">Alle Benutzer sind Mitglieder der **public** -Rolle in allen Datenbanken und können nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="fa6b7-218">Weitere Informationen zu Datenbankrollen finden Sie unter [Rollen auf Datenbankebene](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="fa6b7-219">Sicherungsfähige Elemente</span><span class="sxs-lookup"><span data-stu-id="fa6b7-219">Securables</span></span>  
 <span data-ttu-id="fa6b7-220">Auf der Seite **Sicherungsfähige Elemente** werden alle möglichen sicherungsfähigen Elemente und die Berechtigungen für diese sicherungsfähigen Elemente aufgelistet, die für die Anmeldung gewährt werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="fa6b7-221">Die folgenden Optionen sind auf dieser Seite verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fa6b7-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="fa6b7-222">**Oberes Raster**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-222">**Upper Grid**</span></span>  
 <span data-ttu-id="fa6b7-223">Enthält ein oder mehrere Elemente, für die Berechtigungen festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="fa6b7-224">Die im oberen Raster angezeigten Spalten variieren je nach Prinzipal oder sicherungsfähigem Element.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="fa6b7-225">So fügen Sie dem oberen Raster Elemente hinzu</span><span class="sxs-lookup"><span data-stu-id="fa6b7-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="fa6b7-226">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="fa6b7-227">Wählen Sie im Dialogfeld **Objekte hinzufügen** eine der folgenden Optionen aus: **bestimmte Objekte...**, **alle Objekte des Typs...** oder **der Server**_server_name_.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa6b7-228">Wenn Sie die Option **Der Server**_Servername_ auswählen, wird das obere Raster automatisch mit allen sicherungsfähigen Objekten des Servers gefüllt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="fa6b7-229">Bei Auswahl der Option **Bestimmte Objekte...** :</span><span class="sxs-lookup"><span data-stu-id="fa6b7-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="fa6b7-230">Klicken Sie im Dialogfeld **Objekte auswählen** unter **Wählen Sie Objekttypen aus** auf **Objekttypen...** .</span><span class="sxs-lookup"><span data-stu-id="fa6b7-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="fa6b7-231">Wählen Sie im Dialogfeld **Objekttypen auswählen** beliebige oder alle der folgenden Objekttypen aus: **Endpunkte**, **Anmeldungen**, **Server**, **Verfügbarkeitsgruppen** und **Serverrollen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="fa6b7-232">Klicken Sie unter **Geben Sie die Namen der auszuwählenden Objekte ein (Beispiele)** auf **Durchsuchen...** .</span><span class="sxs-lookup"><span data-stu-id="fa6b7-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="fa6b7-233">Wählen Sie im Dialogfeld **Nach Objekten suchen** eines der verfügbaren Objekte vom Typ aus, den Sie im Dialogfeld **Objekttypen auswählen** ausgewählt haben, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="fa6b7-234">Klicken Sie im Dialogfeld **Objekte auswählen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="fa6b7-235">Wenn Sie im Dialogfeld **Objekttypen auswählen** die Option **All objects of the types...** (Alle Objekte der Typen...) auswählen, wählen Sie beliebige oder alle der folgenden Objekttypen aus: **Endpunkte**, **Anmeldungen**, **Server**, **Verfügbarkeitsgruppen** und **Serverrollen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="fa6b7-236">**Name**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-236">**Name**</span></span>  
 <span data-ttu-id="fa6b7-237">Die Namen der Prinzipale oder sicherungsfähigen Elemente, die dem Raster hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="fa6b7-238">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-238">**Type**</span></span>  
 <span data-ttu-id="fa6b7-239">Beschreibt den Typ jedes Elements.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="fa6b7-240">**Registerkarte 'Explizit'**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="fa6b7-241">Listet die möglichen Berechtigungen für die im oberen Raster ausgewählten sicherungsfähigen Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="fa6b7-242">Für einige explizite Berechtigungen sind nicht alle Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="fa6b7-243">**Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-243">**Permissions**</span></span>  
 <span data-ttu-id="fa6b7-244">Der Name der Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="fa6b7-245">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-245">**Grantor**</span></span>  
 <span data-ttu-id="fa6b7-246">Der Prinzipal, der die Berechtigung erteilt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="fa6b7-247">**Erteilen**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-247">**Grant**</span></span>  
 <span data-ttu-id="fa6b7-248">Aktivieren Sie diese Option, um der Anmeldung diese Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="fa6b7-249">Deaktivieren Sie diese Option, um diese Berechtigung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="fa6b7-250">**Mit Erteilung**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-250">**With Grant**</span></span>  
 <span data-ttu-id="fa6b7-251">Zeigt den Status der WITH GRANT-Option für die angezeigte Berechtigung an.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="fa6b7-252">Dieses Feld ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-252">This box is read-only.</span></span> <span data-ttu-id="fa6b7-253">Verwenden Sie die [GRANT](/sql/t-sql/statements/grant-transact-sql) -Anweisung, um diese Berechtigung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="fa6b7-254">**Deny**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-254">**Deny**</span></span>  
 <span data-ttu-id="fa6b7-255">Aktivieren Sie diese Option, um der Anmeldung diese Berechtigung zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="fa6b7-256">Deaktivieren Sie diese Option, um diese Berechtigung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="fa6b7-257">Status</span><span class="sxs-lookup"><span data-stu-id="fa6b7-257">Status</span></span>  
 <span data-ttu-id="fa6b7-258">Die Seite **Status** enthält einige Authentifizierungs- und Autorisierungsoptionen, die auf der ausgewählten [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="fa6b7-259">Die folgenden Optionen sind auf dieser Seite verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fa6b7-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="fa6b7-260">**Berechtigung zum Herstellen einer Verbindung mit Datenbank-Engine**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="fa6b7-261">Wenn Sie diese Einstellung verwenden, müssen Sie die ausgewählte Anmeldung als einen Prinzipal betrachten, dem für das sicherungsfähige Element Berechtigungen erteilt oder verweigert werden können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="fa6b7-262">Wählen Sie **Erteilen** aus, um der Anmeldung die CONNECT SQL-Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="fa6b7-263">Wählen Sie **Verweigern** aus, um der Anmeldung die CONNECT SQL-Berechtigung zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="fa6b7-264">**Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-264">**Login**</span></span>  
 <span data-ttu-id="fa6b7-265">Wenn Sie diese Einstellung verwenden, muss der ausgewählte Anmeldename als Datensatz in einer Tabelle betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="fa6b7-266">Änderungen an den hier aufgeführten Werten werden auf den Datensatz angewendet.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="fa6b7-267">Ein deaktivierter Anmeldename bleibt weiterhin als Datensatz bestehen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="fa6b7-268">Beim Herstellen der Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]wird der Anmeldename jedoch nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="fa6b7-269">Wählen Sie diese Option aus, um diesen Anmeldenamen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="fa6b7-270">Für diese Option wird die ALTER LOGIN-Anweisung mit der Option ENABLE oder DISABLE verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="fa6b7-271">**SQL Server-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="fa6b7-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="fa6b7-272">Das Kontrollkästchen **Anmeldung ist gesperrt** ist nur verfügbar, wenn der ausgewählte Anmeldename die Verbindung mithilfe der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung herstellt, und wenn der Anmeldename gesperrt ist. Diese Einstellung ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="fa6b7-273">Führen Sie ALTER LOGIN mit der Option UNLOCK aus, wenn Sie die Sperre für eine Anmeldung aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fa6b7-274">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa6b7-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="fa6b7-275">So erstellen Sie eine Anmeldung mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa6b7-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="fa6b7-276">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fa6b7-277">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fa6b7-278">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="fa6b7-279">So erstellen Sie eine Anmeldung mit SQL Server-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa6b7-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="fa6b7-280">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fa6b7-281">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fa6b7-282">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="fa6b7-283">Weitere Informationen finden Sie unter [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a><span data-ttu-id="fa6b7-284">Nächster Schritt: Erforderliche Schritte nach dem Erstellen eines Anmeldenamens</span><span class="sxs-lookup"><span data-stu-id="fa6b7-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="fa6b7-285">Nach der Erstellung eines Anmeldenamens kann dieser zwar eine Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]herstellen, er verfügt jedoch nicht unbedingt über ausreichende Berechtigungen, um damit sinnvolle Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="fa6b7-286">Die folgende Liste enthält Links zu häufigen Anmeldeaktionen.</span><span class="sxs-lookup"><span data-stu-id="fa6b7-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="fa6b7-287">Informationen darüber, wie ein Anmeldename einer Datenbankrolle beitreten kann, finden Sie unter [Verknüpfen einer Rolle](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="fa6b7-288">Informationen zum Autorisieren eines Anmeldenamens für die Verwendung einer Datenbank finden Sie unter [Erstellen eines Datenbankbenutzers](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="fa6b7-289">Informationen zum Erteilen einer Berechtigung für einen Anmeldenamen finden Sie unter [Erteilen einer Berechtigung für einen Prinzipal](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b7-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
