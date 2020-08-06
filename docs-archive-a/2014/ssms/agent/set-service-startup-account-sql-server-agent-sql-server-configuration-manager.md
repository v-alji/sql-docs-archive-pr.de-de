---
title: Festlegen des Dienst Start Kontos für SQL Server-Agent (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699171"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="09af1-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="09af1-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="09af1-103">Das Dienststartkonto des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents definiert das Windows-Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt wird, sowie die zugehörigen Netzwerkberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="09af1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="09af1-104">In diesem Thema wird beschrieben, wie Sie das Dienstkonto für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]festlegen.</span><span class="sxs-lookup"><span data-stu-id="09af1-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="09af1-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="09af1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09af1-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="09af1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09af1-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09af1-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="09af1-108">Security</span><span class="sxs-lookup"><span data-stu-id="09af1-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="09af1-109">So legen Sie das Dienststartkonto für den SQL Server-Agent mit SQL Server Management Studio fest</span><span class="sxs-lookup"><span data-stu-id="09af1-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09af1-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="09af1-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="09af1-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09af1-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="09af1-112">Seit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]muss das Dienststartkonto für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent nicht mehr ein Mitglied der Administratorengruppe von [!INCLUDE[msCoName](../../includes/msconame-md.md)] sein.</span><span class="sxs-lookup"><span data-stu-id="09af1-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="09af1-113">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienststartkonto muss jedoch ein Mitglied der festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Serverrolle „sysadmin“ sein.</span><span class="sxs-lookup"><span data-stu-id="09af1-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="09af1-114">Das Konto muss Mitglied der „msdb“-Datenbankrolle „TargetServersRole“ auf dem Masterserver sein, um die Multiserver-Auftragsverarbeitung verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="09af1-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="09af1-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="09af1-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09af1-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="09af1-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09af1-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="09af1-117">Permissions</span></span>  
 <span data-ttu-id="09af1-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Der-Agent muss für die Verwendung der Anmelde Informationen eines Kontos konfiguriert werden, das Mitglied der `sysadmin` Fixed-Server Rolle in ist, um seine Funktionen ausführen zu können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09af1-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="09af1-119">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="09af1-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="09af1-120">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="09af1-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="09af1-121">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09af1-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="09af1-122">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09af1-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="09af1-123">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09af1-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="09af1-124">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="09af1-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09af1-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09af1-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="09af1-126">So legen Sie das Dienststartkonto für den SQL Server-Agent fest</span><span class="sxs-lookup"><span data-stu-id="09af1-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="09af1-127">Klicken Sie in **Registrierte Server**auf das Pluszeichen, um **Datenbank-Engine**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="09af1-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="09af1-128">Klicken Sie auf das Pluszeichen, um den Ordner **Lokale Servergruppen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="09af1-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="09af1-129">Klicken Sie mit der rechten Maustaste auf die Serverinstanz, auf der Sie das Dienststartkonto festlegen möchten, und wählen Sie dann **SQL Server-Konfigurations-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="09af1-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="09af1-130">Klicken Sie im Dialogfeld **Benutzerkontensteuerung** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="09af1-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="09af1-131">Wählen Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager im Konsolenbereich **SQL Server-Dienste**aus.</span><span class="sxs-lookup"><span data-stu-id="09af1-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="09af1-132">Klicken Sie im Detailbereich mit der rechten Maustaste auf **SQL Server-Agent**_(Servername)_, wobei *Servername* der Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Instanz ist, für die Sie das Dienststartkonto ändern möchten. Wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="09af1-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="09af1-133">Wählen Sie im Dialogfeld **Eigenschaften** von **SQL Server-Agent**_(server_name)_ auf der Registerkarte **Anmelden** eine der folgenden Optionen unter **Anmelden als**aus:</span><span class="sxs-lookup"><span data-stu-id="09af1-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="09af1-134">**Integriertes Konto**: Wählen Sie diese Option aus, wenn die Aufträge nur Ressourcen vom lokalen Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="09af1-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="09af1-135">Informationen zum Auswählen eines integrierten Kontotyps finden Sie unter [Auswählen eines Kontos für den SQL Server-Agent-Dienst](https://msdn.microsoft.com/library/ms191543.aspx).</span><span class="sxs-lookup"><span data-stu-id="09af1-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="09af1-136"> Das lokale Dienstkonto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in\ \*\*\** wird nicht für den [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Agentdienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09af1-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="09af1-137">**Dieses Konto**: Wählen Sie diese Option aus, wenn die Aufträge Ressourcen aus dem gesamten Netzwerk benötigen, einschließlich Anwendungsressourcen, wenn Sie Ereignisse an andere Windows-Anwendungsprotokolle weiterleiten möchten oder wenn Sie Operatoren per E-Mail oder Pager benachrichtigen möchten.</span><span class="sxs-lookup"><span data-stu-id="09af1-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="09af1-138">Bei Auswahl dieser Option:</span><span class="sxs-lookup"><span data-stu-id="09af1-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="09af1-139">Geben Sie das Konto, das verwendet wird, um den SQL Server-Agent auszuführen, in das Feld **Kontoname** ein.</span><span class="sxs-lookup"><span data-stu-id="09af1-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="09af1-140">Klicken Sie alternativ auf **Durchsuchen** , um das Dialogfeld **Benutzer oder Gruppe auswählen** zu öffnen, und wählen Sie das zu verwendende Konto aus.</span><span class="sxs-lookup"><span data-stu-id="09af1-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="09af1-141">Geben Sie im Feld **Kennwort** das Kennwort für das Konto ein.</span><span class="sxs-lookup"><span data-stu-id="09af1-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="09af1-142">Geben Sie im Feld **Kennwort bestätigen** das Kennwort erneut ein.</span><span class="sxs-lookup"><span data-stu-id="09af1-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="09af1-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="09af1-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="09af1-144">Klicken Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager auf die Schaltfläche **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="09af1-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
