---
title: Schreiben von Meldungen zur Ablauf Verfolgung in das SQL Server-Agent-Fehlerprotokoll (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719366"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="99682-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="99682-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="99682-103">In diesem Thema wird beschrieben, wie der-Agent so konfiguriert wird, dass er Ablauf [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Verfolgungs Meldungen in der Fehlermeldung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von einschließt [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99682-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="99682-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="99682-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="99682-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="99682-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="99682-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99682-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="99682-107">Security</span><span class="sxs-lookup"><span data-stu-id="99682-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="99682-108">So schreiben Sie Meldungen zur Ablaufverfolgung in das SQL Server-Agent-Fehlerprotokoll mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99682-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99682-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="99682-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="99682-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99682-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="99682-111">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99682-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="99682-112">Schließen Sie Meldungen zur Ablaufverfolgung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokolle ein, wenn Sie ein bestimmtes Problem des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents untersuchen, denn die Option kann dazu führen, dass das Fehlerprotokoll sehr umfangreich wird.</span><span class="sxs-lookup"><span data-stu-id="99682-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99682-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="99682-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99682-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99682-114">Permissions</span></span>  
 <span data-ttu-id="99682-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="99682-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="99682-116">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="99682-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="99682-117">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="99682-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="99682-118">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="99682-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="99682-119">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="99682-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="99682-120">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="99682-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="99682-121">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="99682-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="99682-122">So schreiben Sie Meldungen zur Ablaufverfolgung in das SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="99682-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="99682-123">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen neben dem Server, der das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll enthält, in das Sie Meldungen zur Ablaufverfolgung schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="99682-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="99682-124">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="99682-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="99682-125">Aktivieren Sie im Dialogfeld **SQL Server-Agent Eigenschaften**_server_name_ unter **Fehlerprotokoll** auf der Seite **Allgemein** das Kontrollkästchen Ablauf **Verfolgungs Meldungen der Ablauf Verfolgung einschließen** .</span><span class="sxs-lookup"><span data-stu-id="99682-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="99682-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99682-126">Click **OK**.</span></span>  
  
  
