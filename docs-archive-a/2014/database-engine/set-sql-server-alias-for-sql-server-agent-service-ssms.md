---
title: Festlegen eines SQL Server Alias für den SQL Server-Agent Dienst (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608820"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="90594-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="90594-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="90594-103">In diesem Thema wird beschrieben, wie ein Alias festgelegt wird, mit [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dem der-Agent mithilfe von eine Verbindung mit herstellen kann [!INCLUDE[ssDE](../includes/ssde-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90594-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="90594-104">Standardmäßig stellt der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Dienst eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] über Named Pipes mithilfe dynamischer Servernamen her, die keine zusätzliche Clientkonfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="90594-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="90594-105">Einen Serververbindungsalias müssen Sie nur konfigurieren, wenn Sie nicht den standardmäßigen Netzwerktransport verwenden oder wenn Sie eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] herstellen, die an einer alternativen Named Pipe lauscht.</span><span class="sxs-lookup"><span data-stu-id="90594-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="90594-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="90594-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="90594-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="90594-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="90594-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="90594-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="90594-109">Security</span><span class="sxs-lookup"><span data-stu-id="90594-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="90594-110">So legen Sie einen SQL Server-Alias für den für den SQL Server-Agent-Dienst mithilfe von SQL Server Management Studio fest</span><span class="sxs-lookup"><span data-stu-id="90594-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90594-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="90594-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="90594-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="90594-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="90594-113">-Agent wird nur dann ordnungsgemäß ausgeführt, wenn Sie einen Aliasnamen auswählen, der auf die lokale Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90594-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="90594-114">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="90594-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90594-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="90594-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90594-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="90594-116">Permissions</span></span>  
 <span data-ttu-id="90594-117">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="90594-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="90594-118">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="90594-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="90594-119">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="90594-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="90594-120">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="90594-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="90594-121">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="90594-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="90594-122">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="90594-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="90594-123">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="90594-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="90594-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90594-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="90594-125">So legen Sie einen SQL Server-Alias für den SQL Server-Agent-Dienst fest</span><span class="sxs-lookup"><span data-stu-id="90594-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="90594-126">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] her, und erweitern Sie diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="90594-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="90594-127">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="90594-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="90594-128">Wählen Sie im Dialogfeld **SQL Server-Agent Eigenschaften**_server_name_ unter **Seite auswählen**die Option **Verbindung**aus.</span><span class="sxs-lookup"><span data-stu-id="90594-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="90594-129">geben Sie im Feld **Aliasname für den lokalen Hostserver** den Alias des Servers ein, mit dem der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent verbunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="90594-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="90594-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="90594-130">Click **OK**.</span></span>  
  
  
