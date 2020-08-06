---
title: Konfigurieren des SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, configuring
- accounts [SQL Server], SQL Server Agent
- SQL Server Agent, permissions
- security [SQL Server], SQL Server Agent
ms.assetid: 2e361a62-9e92-4fcd-80d7-d6960f127900
author: stevestein
ms.author: sstein
ms.openlocfilehash: 81c78faf733fac5ffb9a6e74dbf03f8caaff03d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617363"
---
# <a name="configure-sql-server-agent"></a><span data-ttu-id="09370-102">Konfigurieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="09370-102">Configure SQL Server Agent</span></span>
  <span data-ttu-id="09370-103">In diesem Thema wird beschrieben, wie Sie einige Konfigurationsoptionen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent während der Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angeben.</span><span class="sxs-lookup"><span data-stu-id="09370-103">This topic describes how to specify some configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="09370-104">Die vollständigen Konfigurationsoptionen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent sind nur in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) oder den gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents verfügbar.</span><span class="sxs-lookup"><span data-stu-id="09370-104">The full set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent configuration options is only available within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures.</span></span>  
  
 <span data-ttu-id="09370-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="09370-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09370-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="09370-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09370-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09370-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="09370-108">Security</span><span class="sxs-lookup"><span data-stu-id="09370-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="09370-109">Sie konfigurieren Sie den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="09370-109">To configure SQL Server Agent</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09370-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="09370-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="09370-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09370-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="09370-112">Klicken Sie im Objekt-Explorer von **auf** SQL Server-Agent [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um Aufträge, Operatoren, Warnungen und den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="09370-112">Click **SQL Server Agent** in Object Explorer of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to administer jobs, operators, alerts, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="09370-113">Der Objekt-Explorer zeigt den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Knoten jedoch nur dann an, wenn Sie die Berechtigung haben, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="09370-113">However, Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="09370-114">Für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst oder den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst sollte in Failoverclusterinstanzen kein automatischer Neustart aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="09370-114">Auto-restart should not be enabled for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on failover cluster instances.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09370-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="09370-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09370-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="09370-116">Permissions</span></span>  
 <span data-ttu-id="09370-117">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="09370-117">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="09370-118">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="09370-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="09370-119">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="09370-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="09370-120">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09370-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="09370-121">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09370-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="09370-122">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="09370-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="09370-123">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="09370-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09370-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09370-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent"></a><span data-ttu-id="09370-125">Sie konfigurieren Sie den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="09370-125">To configure SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="09370-126">Klicken Sie auf die Schaltfläche **Start** und anschließend im Menü **Start**  auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="09370-126">Click the **Start** button, and then, on the **Start**  menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="09370-127">Klicken Sie in der Systemsteuerung unter **System und Sicherheit**auf **Verwaltung**, und wählen Sie dann **Lokale Sicherheitsrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="09370-127">In Control Panel, click **System and Security**, click **Administrative Tools**, and then select **Local Security Policy**.</span></span>  
  
3.  <span data-ttu-id="09370-128">Klicken Sie in Lokale Sicherheitsrichtlinie auf das Chevron, um den Ordner **Sicherheitsrichtlinien** zu erweitern, und klicken Sie dann auf den Ordner **Zuweisen von Benutzerrechten** .</span><span class="sxs-lookup"><span data-stu-id="09370-128">In Local Security Policy, click the chevron to expand the **Local Policies** folder, and then click the **User Rights Assignment** folder.</span></span>  
  
4.  <span data-ttu-id="09370-129">Klicken Sie mit der rechten Maustaste auf eine Berechtigung, die Sie zur Verwendung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] konfigurieren möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="09370-129">Right-click a permission that you want to configure for use with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="09370-130">Überprüfen Sie im Eigenschaftendialogfeld der Berechtigung, ob das Konto aufgeführt ist, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="09370-130">In the permission's properties dialog box, verify that the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs is listed.</span></span> <span data-ttu-id="09370-131">Falls dies nicht der Fall ist, klicken Sie auf **Benutzer oder Gruppe hinzufügen**, geben Sie im Dialogfeld zum Auswählen von Benutzern, Computern, Dienstkonten oder Gruppen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**das Konto ein, unter dem der** -Agent ausgeführt wird, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="09370-131">If not, click **Add User or Group**, enter the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="09370-132">Wiederholen Sie diese Schritte für jede Berechtigung, die Sie für die Ausführung mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="09370-132">Repeat for each permission that you want to add to run with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="09370-133">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="09370-133">When finished, click **OK**.</span></span>  
  
  
