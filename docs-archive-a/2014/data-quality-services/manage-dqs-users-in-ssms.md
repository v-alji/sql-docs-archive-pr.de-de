---
title: Verwalten von DQS-Benutzern in SSMS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621674"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="8ad24-102">Verwalten von DQS-Benutzern in SSMS</span><span class="sxs-lookup"><span data-stu-id="8ad24-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="8ad24-103">In diesem Thema wird beschrieben, wie mit SQL Server Management Studio zusätzliche Benutzer in der SQL Server-Instanz erstellt werden und wie ihnen entsprechende [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS)-Rollen für die DQS_MAIN-Datenbank gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="8ad24-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ad24-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8ad24-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ad24-105">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8ad24-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ad24-106">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8ad24-106">Permissions</span></span>  
 <span data-ttu-id="8ad24-107">Ihr Windows-Benutzerkonto muss Mitglied der entsprechenden festen Serverrolle (z. B. securityadmin, serveradmin oder sysadmin) sein, um eine SQL-Anmeldung zu erstellen und ihr entsprechende DQS-Rollen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8ad24-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="8ad24-108">Erstellen einer SQL-Anmeldung und erteilen der DQS-Rolle</span><span class="sxs-lookup"><span data-stu-id="8ad24-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="8ad24-109">Starten Sie Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8ad24-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="8ad24-110">Erweitern Sie in Microsoft SQL Server Management Studio die SQL Server-Instanz, und erweitern Sie **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="8ad24-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="8ad24-111">Klicken Sie mit der rechten Maustaste auf den Ordner **Sicherheit** , zeigen Sie auf **Neu**, und wählen Sie dann **Anmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="8ad24-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="8ad24-112">Geben Sie im Dialogfeld **Anmeldung – Neu** den Namen eines Windows-Benutzers im Feld **Anmeldename** ein, geben Sie für den Authentifizierungstyp **Windows-Authentifizierung** an, und klicken Sie auf **Suchen**, um den Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8ad24-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ad24-113">DQS unterstützt nur die Windows-Authentifizierung. Die SQL Server-Authentifizierung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8ad24-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="8ad24-114">Klicken Sie nach der Überprüfung des Benutzers auf die Seite **Benutzerzuordnung** im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="8ad24-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="8ad24-115">Aktivieren Sie im rechten Bereich das Kontrollkästchen unter der Spalte **Zuordnen** für die **DQS_MAIN** -Datenbank, und aktivieren Sie dann das Kontrollkästchen **dqs_administrator**, **dqs_kb_editor**oder **dqs_kb_operator** im Bereich **Mitgliedschaft in Datenbankrolle für: DQS_MAIN** , je nachdem, welche Zugriffsebene für den Benutzer benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ad24-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="8ad24-116">Klicken Sie im Dialogfeld **Anmeldung – Neu** auf **OK**, um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="8ad24-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ad24-117">Wenn Sie einem Benutzer die **dqs_administrator** -Rolle gewähren, übernehmen Sie die Änderungen, und überprüfen Sie dann erneut die Benutzerberechtigungen und ob die beiden anderen Kontrollkästchen für DQS-Rollen (**dq_kb_editor** und **dqs_kb_operator**) auch aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8ad24-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
