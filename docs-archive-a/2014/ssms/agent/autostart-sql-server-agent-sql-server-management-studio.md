---
title: Autostart SQL Server Agent (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619542"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="1d864-102">Autostart SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1d864-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1d864-103">In diesem Thema wird beschrieben, wie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sie den-Agent so konfigurieren, dass er in unerwartet beendet wird [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d864-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="1d864-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1d864-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1d864-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1d864-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1d864-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d864-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1d864-107">Security</span><span class="sxs-lookup"><span data-stu-id="1d864-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="1d864-108">So konfigurieren Sie den automatischen Neustart des SQL Server-Agents mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d864-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d864-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1d864-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1d864-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d864-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1d864-111">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d864-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d864-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1d864-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1d864-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1d864-113">Permissions</span></span>  
 <span data-ttu-id="1d864-114">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="1d864-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1d864-115">Das Konto muss über die folgenden Windows-Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="1d864-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="1d864-116">Anmelden als Dienst (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="1d864-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="1d864-117">Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1d864-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="1d864-118">Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1d864-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="1d864-119">Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="1d864-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="1d864-120">Weitere Informationen zu den Windows-Berechtigungen, die für das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto erforderlich sind, finden [Sie unter Auswählen eines Kontos für den SQL Server-Agent Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1d864-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1d864-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d864-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="1d864-122">So konfigurieren Sie den automatischen Neustart des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="1d864-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="1d864-123">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie den automatischen Neustart des SQL Server Agents konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1d864-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="1d864-124">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1d864-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1d864-125">Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **SQL Server-Agent nach unerwartetem Beenden automatisch neu starten**.</span><span class="sxs-lookup"><span data-stu-id="1d864-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
