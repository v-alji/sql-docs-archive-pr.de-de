---
title: Zuweisen von DQS-Rollen an Benutzer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721757"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="eb95d-102">Zuweisen von DQS-Rollen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb95d-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="eb95d-103">In diesem Thema wird beschrieben, wie SQL-Anmeldungen auf Grundlage eines Windows-Prinzipals erstellt werden und wie ihnen [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS)-Rollen für die DQS_MAIN-Datenbank gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="eb95d-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb95d-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="eb95d-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="eb95d-105">Sie müssen die Installation des [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] durch Ausführen der Datei DQSInstaller.exe abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="eb95d-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="eb95d-106">Weitere Informationen finden Sie unter [Ausführen von DQSInstaller.exe zum Abschließen der Installation von Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="eb95d-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="eb95d-107">Ihr Windows-Benutzerkonto muss Mitglied der entsprechenden festen Serverrolle (z. B. securityadmin, serveradmin, sysadmin) sein, um eine SQL-Anmeldung zu erstellen und ihr DQS-Rollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eb95d-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="eb95d-108">So erstellen Sie eine SQL-Anmeldung und gewähren DQS-Rollen</span><span class="sxs-lookup"><span data-stu-id="eb95d-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="eb95d-109">Starten Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb95d-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb95d-110">Erweitern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die SQL Server-Instanz, und erweitern Sie dann **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="eb95d-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="eb95d-111">Klicken Sie mit der rechten Maustaste auf den Ordner **Sicherheit** , zeigen Sie auf **Neu**, und wählen Sie dann **Anmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="eb95d-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="eb95d-112">Geben Sie im Dialogfeld **Anmeldung – Neu** den Namen eines Windows-Benutzers im Feld **Anmeldename** ein, geben Sie für den Authentifizierungstyp **Windows-Authentifizierung** an, und klicken Sie auf **Suchen**, um den Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eb95d-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="eb95d-113">Klicken Sie nach der Überprüfung des Benutzers auf die Seite **Benutzerzuordnung** im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="eb95d-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="eb95d-114">Aktivieren Sie im rechten Bereich das Kontrollkästchen unter der Spalte **Zuordnen** für die **DQS_MAIN** -Datenbank, und aktivieren Sie dann das Kontrollkästchen **dqs_administrator**, **dqs_kb_editor**oder **dqs_kb_operator** im Bereich **Mitgliedschaft in Datenbankrolle für: DQS_MAIN** , je nachdem, welche Zugriffsebene für den Benutzer benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="eb95d-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="eb95d-115">Weitere Informationen zu den drei DQS-Rollen finden Sie unter [DQS-Sicherheit](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="eb95d-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="eb95d-116">Klicken Sie im Dialogfeld **Anmeldung – Neu** auf **OK**, um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="eb95d-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb95d-117">Wenn Sie einem Benutzer die **dqs_administrator** -Rolle gewähren, übernehmen Sie die Änderungen, und überprüfen Sie dann erneut die Benutzerberechtigungen und ob die beiden anderen Kontrollkästchen für DQS-Rollen (**dq_kb_editor** und **dqs_kb_operator**) auch aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="eb95d-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb95d-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="eb95d-118">Next Steps</span></span>  
 <span data-ttu-id="eb95d-119">Melden Sie sich mit dem soeben erstellten Windows-Benutzerkonto, dem Sie die DQS-Rolle gewährt haben, beim [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="eb95d-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb95d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb95d-120">See Also</span></span>  
 <span data-ttu-id="eb95d-121">[Installieren von Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="eb95d-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="eb95d-122">Erstellen eines Anmeldenamens</span><span class="sxs-lookup"><span data-stu-id="eb95d-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
