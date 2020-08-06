---
title: Ändern des Serverauthentifizierungsmodus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724198"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="9684e-102">Ändern des Serverauthentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="9684e-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="9684e-103">In diesem Thema wird beschrieben, wie Sie den Serverauthentifizierungsmodus in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern können.</span><span class="sxs-lookup"><span data-stu-id="9684e-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9684e-104">Während der Installation wird [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] entweder auf den **Windows-Authentifizierungsmodus** oder den **SQL Server- und Windows-Authentifizierungsmodus**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9684e-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="9684e-105">Nach der Installation können Sie jederzeit den Authentifizierungsmodus ändern.</span><span class="sxs-lookup"><span data-stu-id="9684e-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="9684e-106">Wird während der Installation der **Windows-Authentifizierungsmodus** ausgewählt, wird die Systemadministratoranmeldung deaktiviert und ein Kennwort durch das Setup zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9684e-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="9684e-107">Wenn Sie den Authentifizierungsmodus später zu **SQL Server- und Windows-Authentifizierungsmodus**ändern, bleibt die Systemadministratoranmeldung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9684e-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="9684e-108">Um die Systemadministratoranmeldung zu verwenden, nutzen Sie die ALTER LOGIN-Anweisung, um die Systemadministratoranmeldung zu aktivieren und ein neues Kennwort zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9684e-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="9684e-109">Die Systemadministratoranmeldung kann nur mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung eine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="9684e-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="9684e-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9684e-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9684e-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9684e-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9684e-112">Security</span><span class="sxs-lookup"><span data-stu-id="9684e-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9684e-113">**So ändern Sie den Serverauthentifizierungsmodus mit**</span><span class="sxs-lookup"><span data-stu-id="9684e-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="9684e-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9684e-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9684e-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9684e-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9684e-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9684e-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9684e-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9684e-117">Security</span></span>  
 <span data-ttu-id="9684e-118">Das Systemadministratorkonto ist ein bekanntes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto und oft das Ziel böswilliger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9684e-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="9684e-119">Aktivieren Sie das Systemadministratorkonto nur dann, wenn die Anwendung es erfordert.</span><span class="sxs-lookup"><span data-stu-id="9684e-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="9684e-120">Es ist sehr wichtig, dass Sie für die Systemadministratoranmeldung ein sicheres Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="9684e-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9684e-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9684e-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="9684e-122">So ändern Sie den Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="9684e-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="9684e-123">Klicken Sie im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9684e-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9684e-124">Wählen Sie auf der Seite **Sicherheit** unter **Serverauthentifizierung**den neuen Serverauthentifizierungsmodus aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9684e-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9684e-125">Klicken Sie im Dialogfeld [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf **OK** , um den notwendigen Neustart von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9684e-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="9684e-126">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf Ihren Server, und klicken Sie dann auf **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="9684e-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="9684e-127">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss ebenfalls neu gestartet werden, sofern er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9684e-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="9684e-128">Informationen zum Aktivieren des Anmeldenamens "sa"</span><span class="sxs-lookup"><span data-stu-id="9684e-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="9684e-129">Erweitern Sie in Objekt-Explorer den Knoten **Sicherheit**, erweitern Sie Anmeldungen, klicken Sie mit der rechten Maustaste `sa` , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9684e-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9684e-130">Auf der Seite **Allgemein** müssen Sie möglicherweise ein Kennwort für die Anmeldung erstellen und bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9684e-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="9684e-131">Klicken Sie auf der Seite **Status** im Abschnitt **Anmeldung** auf **Aktiviert**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9684e-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9684e-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9684e-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="9684e-133">**Informationen zum Aktivieren des Anmeldenamens "sa"**</span><span class="sxs-lookup"><span data-stu-id="9684e-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="9684e-134">Stellen Sie mithilfe des Objekt-Explorers eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9684e-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9684e-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9684e-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9684e-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9684e-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9684e-137">Im folgenden Beispiel wird die Systemadministratoranmeldung aktiviert, und es wird ein neues Kennwort festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9684e-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9684e-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9684e-138">See Also</span></span>  
 <span data-ttu-id="9684e-139">[Sichere Kennwörter](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="9684e-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="9684e-140">[Sicherheitsüberlegungen für eine SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="9684e-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="9684e-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9684e-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="9684e-142">Herstellen einer Verbindung mit SQL Server, wenn Systemadministratoren gesperrt sind</span><span class="sxs-lookup"><span data-stu-id="9684e-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
