---
title: Erstellen von Anmeldeinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697778"
---
# <a name="create-a-credential"></a><span data-ttu-id="06f32-102">Create a Credential</span><span class="sxs-lookup"><span data-stu-id="06f32-102">Create a Credential</span></span>
  <span data-ttu-id="06f32-103">In diesem Thema wird beschrieben, wie Anmeldeinformationen in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="06f32-104">Anmeldeinformationen ermöglichen Benutzern der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung eine Identität außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06f32-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="06f32-105">Hauptsächlich wird dies für die Ausführung von Code in Assemblys mit dem Berechtigungssatz EXTERNAL_ACCESS verwendet.</span><span class="sxs-lookup"><span data-stu-id="06f32-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="06f32-106">Anmeldeinformationen können auch verwendet werden, wenn ein Benutzer der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung Zugriff auf eine Domänenressource (z. B. auf einen Dateispeicherort zum Speichern einer Sicherung) benötigt.</span><span class="sxs-lookup"><span data-stu-id="06f32-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="06f32-107">Anmeldeinformationen können verschiedenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldungen gleichzeitig zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="06f32-108">Eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung kann nur einer Anmeldeinformation zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="06f32-109">Verwenden Sie nach dem Erstellen einer Anmeldeinformation das Dialogfeld **Anmeldungseigenschaften (Seite „Allgemein“)** , um einer Anmeldung eine Anmeldeinformation zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="06f32-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="06f32-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="06f32-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="06f32-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="06f32-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="06f32-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="06f32-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="06f32-113">Security</span><span class="sxs-lookup"><span data-stu-id="06f32-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="06f32-114">**Erstellen von Anmeldeinformationen mit**</span><span class="sxs-lookup"><span data-stu-id="06f32-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="06f32-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06f32-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="06f32-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06f32-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="06f32-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="06f32-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="06f32-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="06f32-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="06f32-119">Falls für den Anbieter kein mit einem Anmeldenamen verknüpfter Identitätsnachweis vorliegt, werden die dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienstkonto zugeordneten Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="06f32-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="06f32-120">Einem Anmeldenamen können mehrere Anmeldeinformationen zugeordnet werden, solange sie für unterschiedliche Anbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="06f32-121">Pro Anbieter und Anmeldung darf es jedoch nur einen zugeordneten Identitätsnachweis geben.</span><span class="sxs-lookup"><span data-stu-id="06f32-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="06f32-122">Die gleichen Anmeldeinformationen können jedoch auch anderen Anmeldenamen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="06f32-123">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="06f32-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06f32-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06f32-124">Permissions</span></span>  
 <span data-ttu-id="06f32-125">Zum Erstellen oder Ändern von Anmeldeinformationen ist eine ALTER ANY CREDENTIAL-Berechtigung erforderlich. Damit eine Anmeldung Anmeldeinformationen zugeordnet werden kann, ist die ALTER ANY LOGIN-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06f32-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="06f32-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06f32-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="06f32-127">Erstellen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="06f32-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="06f32-128">Erweitern Sie im Objekt-Explorer den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="06f32-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="06f32-129">Klicken Sie mit der rechten Maustaste auf den Ordner **Anmeldeinformationen**, und wählen Sie **Neue Anmeldeinformationen**aus.</span><span class="sxs-lookup"><span data-stu-id="06f32-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="06f32-130">Geben Sie im Dialogfeld **Neue Anmeldeinformationen** im Feld **Anmeldungsname** einen Namen für die Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="06f32-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="06f32-131">Geben Sie im Feld **Identität** den Namen des für ausgehende Verbindungen verwendeten Kontos ein (das beim Verlassen des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Kontexts verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="06f32-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="06f32-132">In der Regel ist dies ein Windows-Benutzerkonto, aber die Identität kann ein Konto eines anderen Typs sein.</span><span class="sxs-lookup"><span data-stu-id="06f32-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="06f32-133">Klicken Sie alternativ auf die Auslassungspunkte **(...)** , um das Dialogfeld **Benutzer oder Gruppe auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="06f32-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="06f32-134">Geben Sie in den Feldern **Kennwort** und **Kennwort bestätigen** das Kennwort für das im Feld **Identität** festgelegte Konto ein.</span><span class="sxs-lookup"><span data-stu-id="06f32-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="06f32-135">Falls **Identität** ein Windows-Benutzerkonto ist, handelt es sich dabei um das Windows-Kennwort.</span><span class="sxs-lookup"><span data-stu-id="06f32-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="06f32-136">Falls kein Kennwort erforderlich ist, können Sie das Feld **Kennwort** leer lassen.</span><span class="sxs-lookup"><span data-stu-id="06f32-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="06f32-137">Wählen Sie **Verschlüsselungsanbieter verwenden** aus, um festzulegen, dass die Anmeldeinformationen von einem Anbieter für die erweiterbare Schlüsselverwaltung (Extensible Key Management, EKM) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="06f32-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="06f32-138">Weitere Informationen über die erweiterbare Schlüsselverwaltung finden Sie unter [Erweiterbare Schlüsselverwaltung &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md).</span><span class="sxs-lookup"><span data-stu-id="06f32-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="06f32-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06f32-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="06f32-140">So erstellen Sie Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="06f32-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="06f32-141">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="06f32-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06f32-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="06f32-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06f32-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="06f32-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="06f32-144">Weitere Informationen finden Sie unter [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06f32-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
