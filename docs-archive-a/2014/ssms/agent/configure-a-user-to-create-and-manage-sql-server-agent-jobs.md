---
title: Konfigurieren eines Benutzers zum Erstellen und Verwalten von SQL Server-Agent-Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622373"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="3d773-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="3d773-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="3d773-103">In diesem Thema wird beschrieben, wie Sie einen Benutzer zum Erstellen oder Ausführen von- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträgen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d773-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="3d773-104">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="3d773-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3d773-105">**Konfigurieren eines Benutzers zum Erstellen und Verwalten von SQL Server-Agent-Aufträgen mit:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="3d773-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d773-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3d773-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d773-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3d773-107">Security</span></span>  
 <span data-ttu-id="3d773-108">Wenn Sie einen Benutzer zum Erstellen oder Ausführen von-Agent-Aufträgen konfigurieren möchten [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , müssen Sie zunächst eine vorhandene SQL Server-Anmeldung oder eine msdb-Rolle einer der folgenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Fixed-Agent-Daten bankrollen in der msdb-Datenbank hinzufügen: SQLAgentUserRole, SQLAgentReaderRole oder SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="3d773-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="3d773-109">Standardmäßig können Mitglieder dieser Datenbankrollen ihre eigenen Auftragsschritte erstellen, die unter ihrem Konto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3d773-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="3d773-110">Falls Benutzer, die keine Administratoren sind, Aufträge ausführen möchten, mit denen andere Arten von Auftragsschritten ausgeführt werden (z. B. [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Pakete), benötigen sie Zugriff auf ein Proxykonto.</span><span class="sxs-lookup"><span data-stu-id="3d773-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="3d773-111">Alle Mitglieder der festen Serverrolle sysadmin haben die Berechtigung zum Erstellen, Ändern und Löschen von Proxykonten.</span><span class="sxs-lookup"><span data-stu-id="3d773-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="3d773-112">Weitere Informationen zu den Berechtigungen, die jeder dieser festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Datenbankrollen zugeordnet sind, finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3d773-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d773-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3d773-113">Permissions</span></span>  
 <span data-ttu-id="3d773-114">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3d773-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3d773-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d773-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3d773-116">**So fügen Sie einer festen Datenbankrolle des SQL Server-Agents einen SQL-Anmeldenamen oder eine msdb-Rolle hinzu**</span><span class="sxs-lookup"><span data-stu-id="3d773-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="3d773-117">Erweitern Sie im **Objekt-Explorer**einen Server.</span><span class="sxs-lookup"><span data-stu-id="3d773-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="3d773-118">Erweitern Sie **Sicherheit**und anschließend **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="3d773-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="3d773-119">Klicken Sie mit der rechten Maustaste auf den Anmeldenamen, den Sie der festen Datenbankrolle des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents hinzufügen möchten, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3d773-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="3d773-120">Wählen Sie auf der Seite **Benutzer Zuordnung** des Dialog Felds **Anmeldungs Eigenschaften** die Zeile aus, die enthält `msdb` .</span><span class="sxs-lookup"><span data-stu-id="3d773-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="3d773-121">Aktivieren Sie unter **Mitgliedschaft in Datenbankrolle für: msdb**das Kontrollkästchen für die entsprechende feste Datenbankrolle des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents.</span><span class="sxs-lookup"><span data-stu-id="3d773-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="3d773-122">**So konfigurieren Sie ein Proxykonto zum Erstellen und Verwalten von Auftragsschritten des SQL Server-Agents**</span><span class="sxs-lookup"><span data-stu-id="3d773-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="3d773-123">Erweitern Sie im **Objekt-Explorer**einen Server.</span><span class="sxs-lookup"><span data-stu-id="3d773-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="3d773-124">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="3d773-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3d773-125">Klicken Sie mit der rechten Maustaste auf **Proxys** , und klicken Sie dann auf **Neuer Proxy**.</span><span class="sxs-lookup"><span data-stu-id="3d773-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="3d773-126">Geben Sie im Dialogfeld **Neues Proxykonto** auf der Seite **Allgemein** den Proxynamen, den Anmeldeinformationsnamen und eine Beschreibung für den neuen Proxy an.</span><span class="sxs-lookup"><span data-stu-id="3d773-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="3d773-127">Beachten Sie, dass Sie Anmeldeinformationen erstellen müssen, bevor Sie ein Proxykonto des SQL Server-Agents erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d773-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="3d773-128">Weitere Informationen zum Erstellen von Anmelde Informationen finden Sie unter [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) und [Create Credential &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3d773-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="3d773-129">Aktivieren Sie die entsprechenden Subsysteme für diesen Proxy.</span><span class="sxs-lookup"><span data-stu-id="3d773-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="3d773-130">Auf der Seite **Prinzipale** können Sie Anmeldenamen oder Rollen hinzufügen oder entfernen, um den Zugriff auf das Proxykonto zu erteilen oder zu entziehen.</span><span class="sxs-lookup"><span data-stu-id="3d773-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d773-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d773-131">See Also</span></span>  
 [<span data-ttu-id="3d773-132">Implementieren der SQL Server-Agent-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3d773-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
