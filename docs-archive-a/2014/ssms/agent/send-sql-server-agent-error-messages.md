---
title: Senden von SQL Server-Agent-Fehlermeldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619534"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="388a3-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="388a3-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="388a3-103">In diesem Thema wird beschrieben, wie der-Agent so konfiguriert [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird, dass Fehlermeldungen mithilfe von net send in mithilfe von gesendet werden [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="388a3-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="388a3-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="388a3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="388a3-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="388a3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="388a3-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="388a3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="388a3-107">Security</span><span class="sxs-lookup"><span data-stu-id="388a3-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="388a3-108">So senden Sie SQL Server-Agent-Fehlermeldungen mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="388a3-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="388a3-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="388a3-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="388a3-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="388a3-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="388a3-111">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="388a3-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="388a3-112">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger-Dienst muss ausgeführt werden, damit NET SEND-Ereignisse empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="388a3-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="388a3-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="388a3-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="388a3-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="388a3-114">Permissions</span></span>  
 <span data-ttu-id="388a3-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="388a3-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="388a3-116">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="388a3-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="388a3-117">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="388a3-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="388a3-118">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="388a3-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="388a3-119">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="388a3-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="388a3-120">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="388a3-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="388a3-121">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="388a3-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="388a3-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="388a3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="388a3-123">So senden Sie SQL Server-Agent-Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="388a3-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="388a3-124">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen neben dem Server, der das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll enthält, von dem Sie Fehlermeldungen über NET SEND senden möchten.</span><span class="sxs-lookup"><span data-stu-id="388a3-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="388a3-125">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="388a3-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="388a3-126">Geben Sie im Dialogfeld **SQL Server-Agent Eigenschaften-**_server_name_ unter **Fehlerprotokoll** auf der Seite **Allgemein** den Benutzernamen oder den Computernamen, an den Sie die Fehlermeldungen senden möchten, in das Feld **NET SEND-Empfänger** ein.</span><span class="sxs-lookup"><span data-stu-id="388a3-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="388a3-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="388a3-127">Click **OK**.</span></span>  
  
  
