---
title: Starten, Beenden oder Anhalten des SQL Server-Agent-Dienstes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695249"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="8f684-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="8f684-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="8f684-103">In diesem Thema wird beschrieben, wie Sie den SQL Server-Agent-Dienst in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten, beenden oder neu starten.</span><span class="sxs-lookup"><span data-stu-id="8f684-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8f684-104">Sie können den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst so konfigurieren, dass er automatisch zusammen mit dem Betriebssystem gestartet wird, oder ihn manuell starten, wenn Sie Aufträge ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="8f684-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="8f684-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst kann beendet oder angehalten werden, um Aufträge, Operatorbenachrichtigungen und Warnungen auszusetzen.</span><span class="sxs-lookup"><span data-stu-id="8f684-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="8f684-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8f684-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8f684-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8f684-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f684-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8f684-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8f684-109">Security</span><span class="sxs-lookup"><span data-stu-id="8f684-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="8f684-110">Starten, Beenden oder Neustarten des SQL Server-Agent-Diensts mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f684-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f684-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8f684-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8f684-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8f684-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="8f684-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Der-Agent muss als Dienst ausgeführt werden, um administrative Tasks zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="8f684-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="8f684-114">Weitere Informationen finden Sie unter [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="8f684-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="8f684-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f684-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f684-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8f684-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8f684-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8f684-117">Permissions</span></span>  
 <span data-ttu-id="8f684-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="8f684-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8f684-119">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="8f684-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="8f684-120">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="8f684-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="8f684-121">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="8f684-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="8f684-122">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="8f684-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="8f684-123">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="8f684-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="8f684-124">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8f684-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f684-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f684-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="8f684-126">So können Sie den SQL Server-Agent-Dienst starten, beenden oder neu starten</span><span class="sxs-lookup"><span data-stu-id="8f684-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="8f684-127">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie den SQL Server-Agent-Dienst verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="8f684-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="8f684-128">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und wählen Sie dann **Starten**, **Beenden**oder **Neu starten**aus.</span><span class="sxs-lookup"><span data-stu-id="8f684-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="8f684-129">Klicken Sie im Dialogfeld **Benutzerkontensteuerung** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8f684-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="8f684-130">Klicken Sie bei der Frage, ob die Aktion ausgeführt werden soll, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8f684-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="8f684-131">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="8f684-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="8f684-132">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="8f684-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="8f684-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8f684-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
