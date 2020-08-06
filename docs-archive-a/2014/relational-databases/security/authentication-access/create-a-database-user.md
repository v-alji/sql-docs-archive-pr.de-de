---
title: Erstellen eines Datenbankbenutzers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697761"
---
# <a name="create-a-database-user"></a><span data-ttu-id="f1b41-102">Erstellen eines Datenbankbenutzers</span><span class="sxs-lookup"><span data-stu-id="f1b41-102">Create a Database User</span></span>
  <span data-ttu-id="f1b41-103">In diesem Thema wird beschrieben, wie Sie einen einer Anmeldung zugeordneten Datenbankbenutzer in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f1b41-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f1b41-104">Der Datenbankbenutzer ist die Identität der Anmeldung, wenn er mit einer Datenbank verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f1b41-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="f1b41-105">Der Datenbankbenutzer kann den gleichen Namen verwenden wie die Anmeldung, dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f1b41-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="f1b41-106">In diesem Thema wird davon ausgegangen, dass in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]bereits eine Anmeldung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1b41-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f1b41-107">Weitere Informationen zum Erstellen einer Anmeldung finden Sie unter [Erstellen eines Anmelde](create-a-login.md)namens.</span><span class="sxs-lookup"><span data-stu-id="f1b41-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="f1b41-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f1b41-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f1b41-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f1b41-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f1b41-110">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="f1b41-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f1b41-111">Security</span><span class="sxs-lookup"><span data-stu-id="f1b41-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f1b41-112">**So erstellen Sie einen Datenbankbenutzer mit**</span><span class="sxs-lookup"><span data-stu-id="f1b41-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="f1b41-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1b41-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f1b41-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1b41-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1b41-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f1b41-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="f1b41-116">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="f1b41-116">Background</span></span>  
 <span data-ttu-id="f1b41-117">Ein Benutzer ist ein Sicherheitsprinzipal auf Datenbankebene.</span><span class="sxs-lookup"><span data-stu-id="f1b41-117">A user is a database level security principal.</span></span> <span data-ttu-id="f1b41-118">Anmeldungen müssen einem Datenbankbenutzer zugeordnet werden, damit eine Verbindung zu einer Datenbank hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1b41-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="f1b41-119">Eine Anmeldung kann unterschiedlichen Datenbanken als unterschiedliche Benutzer zugeordnet werden, aber kann nur als ein Benutzer in jeder Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f1b41-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="f1b41-120">In einer teilweise eigenständigen Datenbank kann ein Benutzer erstellt werden, der über keinen Anmeldenamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="f1b41-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="f1b41-121">Weitere Informationen zu eigenständigen Datenbankbenutzern finden Sie unter [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1b41-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="f1b41-122">Wenn in einer Datenbank Gastbenutzer aktiviert sind, kann eine Anmeldung, die keinem Datenbankbenutzer zugeordnet ist, als Gastbenutzer auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1b41-123">Gastbenutzer sind normalerweise deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f1b41-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="f1b41-124">Aktivieren Sie Gastbenutzer nur, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="f1b41-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="f1b41-125">Als Sicherheitsprinzipalen können Benutzern Berechtigungen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="f1b41-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="f1b41-126">Die Datenbank ist der Bereich eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f1b41-126">The scope of a user is the database.</span></span> <span data-ttu-id="f1b41-127">Um eine bestimmte Datenbank mit einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]zu verbinden, muss ein Anmeldename einem Datenbankbenutzer zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f1b41-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="f1b41-128">Die Berechtigungen innerhalb der Datenbank werden dem Datenbankbenutzer, nicht dem Anmeldenamen, gewährt bzw. verweigert.</span><span class="sxs-lookup"><span data-stu-id="f1b41-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1b41-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f1b41-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1b41-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f1b41-130">Permissions</span></span>  
 <span data-ttu-id="f1b41-131">Erfordert die `ALTER ANY USER`-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f1b41-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1b41-132">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1b41-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="f1b41-133">So erstellen Sie einen Datenbankbenutzer</span><span class="sxs-lookup"><span data-stu-id="f1b41-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="f1b41-134">Erweitern Sie im Objekt-Explorer den Ordner **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="f1b41-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="f1b41-135">Erweitern Sie die Datenbank, in der der neue Datenbankbenutzer erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1b41-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="f1b41-136">Klicken Sie mit der rechten Maustaste auf den Ordner **Sicherheit**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **Benutzer...** .</span><span class="sxs-lookup"><span data-stu-id="f1b41-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="f1b41-137">Wählen Sie im Dialogfeld **Datenbankbenutzer-neu** auf der Seite **Allgemein** einen der folgenden Benutzer Typen aus der Liste **Benutzertyp** aus: **SQL-Benutzer mit Anmelde**Name, **SQL-Benutzer ohne Anmelde**Name, Benutzer, der **einem Zertifikat**zugeordnet ist, Benutzer, der **einem asymmetrischen Schlüssel**zugeordnet ist oder **Windows-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f1b41-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="f1b41-138">Geben Sie in das Feld **Benutzername** den Namen für den neuen Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="f1b41-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="f1b41-139">Wenn Sie **Windows-Benutzer** aus der Liste **Benutzertyp** ausgewählt haben, können Sie zudem auf die Auslassungspunkte **(…)** klicken, um das Dialogfeld **Benutzer oder Gruppe auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="f1b41-140">Geben Sie im Feld **Anmeldename** den Anmeldenamen für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="f1b41-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="f1b41-141">Klicken Sie alternativ auf die Auslassungspunkte **(…)** , um das Dialogfeld **Anmeldenamen auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="f1b41-142">**Anmeldename** ist verfügbar, wenn Sie entweder **SQL-Benutzer mit Anmeldename** oder **Windows-Benutzer** aus der Liste **Benutzertyp** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="f1b41-143">Im Feld **Standardschema** wird das Schema angegeben, das von diesem Benutzer erstellte Objekte besitzen wird.</span><span class="sxs-lookup"><span data-stu-id="f1b41-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="f1b41-144">Klicken Sie alternativ auf die Auslassungspunkte **(…)** , um das Dialogfeld **Schema auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="f1b41-145">**Standardschema** ist verfügbar, wenn Sie entweder **SQL-Benutzer mit Anmeldename**, **SQL-Benutzer ohne Anmeldename**oder **Windows-Benutzer** aus der Liste **Benutzertyp** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="f1b41-146">Geben Sie im Feld **Zertifikatsname** das Zertifikat an, das für den Datenbankbenutzer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1b41-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="f1b41-147">Klicken Sie alternativ auf die Auslassungspunkte **(…)** , um das Dialogfeld **Zertifikat auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="f1b41-148">**Zertifikatname** ist verfügbar, wenn Sie die Option **Benutzer, der einem Zertifikat zugeordnet ist** aus der Liste **Benutzertyp** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="f1b41-149">Geben Sie im Feld **Asymmetrischer Schlüsselname**  den Schlüssel an, der für den Datenbankbenutzer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1b41-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="f1b41-150">Klicken Sie alternativ auf die Auslassungspunkte **(…)** , um das Dialogfeld **Asymmetrischen Schlüssel auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="f1b41-151">Die Option für den **asymmetrischen Schlüsselnamen** ist verfügbar, wenn Sie die Option **Benutzer, der einem asymmetrischen Schlüssel zugeordnet ist** aus der Liste **Benutzertyp** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="f1b41-152">Zusätzliche Optionen</span><span class="sxs-lookup"><span data-stu-id="f1b41-152">Additional Options</span></span>  
 <span data-ttu-id="f1b41-153">Im Dialogfeld **Datenbankbenutzer – Neu** sind auch Optionen auf vier zusätzlichen Seiten verfügbar: **Schemas im Besitz**, **Mitgliedschaft**, **Sicherungsfähige Elemente** und **Erweiterte Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f1b41-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="f1b41-154">Auf der Seite **Schemas im Besitz** werden alle möglichen Schemas aufgelistet, die dem neuen Datenbankbenutzer gehören können.</span><span class="sxs-lookup"><span data-stu-id="f1b41-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="f1b41-155">Aktivieren oder deaktivieren Sie unter **Schemas im Besitz dieses Benutzers**die Kontrollkästchen, die sich neben den Schemas befinden, um einem Datenbankbenutzer Schemas hinzuzufügen oder diese von diesem zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="f1b41-156">Auf der Seite **Mitgliedschaft** werden alle möglichen Datenbank-Mitgliedschaftsrollen aufgelistet, die dem neuen Datenbankbenutzer gehören können.</span><span class="sxs-lookup"><span data-stu-id="f1b41-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="f1b41-157">Aktivieren oder deaktivieren Sie unter **Mitgliedschaft in Datenbankrolle**die Kontrollkästchen, die sich neben den Rollen befinden, um einem Datenbankbenutzer Rollen hinzuzufügen oder diese von diesem zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="f1b41-158">Auf der Seite **Sicherungsfähige Elemente** werden alle möglichen sicherungsfähigen Elemente und die Berechtigungen für diese sicherungsfähigen Elemente aufgelistet, die für die Anmeldung gewährt werden können.</span><span class="sxs-lookup"><span data-stu-id="f1b41-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="f1b41-159">Mithilfe der Seite **Erweiterte Eigenschaften** können Sie Datenbankbenutzern benutzerdefinierte Eigenschaften hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="f1b41-160">Die folgenden Optionen sind auf dieser Seite verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1b41-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="f1b41-161">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f1b41-161">**Database**</span></span>  
     <span data-ttu-id="f1b41-162">Zeigt den Namen der ausgewählten Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="f1b41-162">Displays the name of the selected database.</span></span> <span data-ttu-id="f1b41-163">Dieses Feld ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="f1b41-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="f1b41-164">**Sortierung**</span><span class="sxs-lookup"><span data-stu-id="f1b41-164">**Collation**</span></span>  
     <span data-ttu-id="f1b41-165">Zeigt die für die ausgewählte Datenbank verwendete Sortierung an.</span><span class="sxs-lookup"><span data-stu-id="f1b41-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="f1b41-166">Dieses Feld ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="f1b41-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="f1b41-167">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="f1b41-167">**Properties**</span></span>  
     <span data-ttu-id="f1b41-168">Zeigt bzw. gibt die erweiterten Eigenschaften für das Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f1b41-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="f1b41-169">Jede erweiterte Eigenschaft besteht aus einem aus Name und Wert bestehenden Paar von Metadaten, das dem Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f1b41-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="f1b41-170">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="f1b41-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="f1b41-171">Klicken Sie auf die Auslassungspunkte **(…)** hinter **Wert**, um das Dialogfeld **Wert für erweiterte Eigenschaft** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1b41-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="f1b41-172">Geben Sie den Wert der erweiterten Eigenschaft an diesem größeren Speicherort ein, bzw. zeigen Sie ihn an.</span><span class="sxs-lookup"><span data-stu-id="f1b41-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="f1b41-173">Weitere Informationen finden Sie unter [Wert für erweiterte Eigenschaft (Dialogfeld)](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f1b41-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="f1b41-174">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="f1b41-174">**Delete**</span></span>  
     <span data-ttu-id="f1b41-175">Entfernt die ausgewählte erweiterte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f1b41-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1b41-176">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1b41-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="f1b41-177">So erstellen Sie einen Datenbankbenutzer</span><span class="sxs-lookup"><span data-stu-id="f1b41-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="f1b41-178">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f1b41-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1b41-179">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f1b41-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1b41-180">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f1b41-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="f1b41-181">Weitere Informationen finden Sie unter [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1b41-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b41-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1b41-182">See Also</span></span>  
 [<span data-ttu-id="f1b41-183">Prinzipale &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="f1b41-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
