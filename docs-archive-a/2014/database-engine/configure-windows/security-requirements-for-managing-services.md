---
title: Sicherheitsanforderungen für das Verwalten von Diensten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723062"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="6026a-102">Sicherheitsanforderungen für das Verwalten von Diensten</span><span class="sxs-lookup"><span data-stu-id="6026a-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="6026a-103">Verwenden Sie entweder den SQL Server-Konfigurations-Manager oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], um den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-und den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Dienst zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6026a-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6026a-104">Auf gruppierten Servern verwalten Sie die Dienste mit der Clusterverwaltung.</span><span class="sxs-lookup"><span data-stu-id="6026a-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="6026a-105">Um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst zu verwalten und die Konfigurationsoptionen für den Server festzulegen, müssen Sie Mitglied der festen Serverrolle **serveradmin** oder der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="6026a-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="6026a-106">Mitglieder der Windows-Gruppe **Administratoren** können Dienste starten und beenden und die unter Windows verfügbaren Serveroptionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6026a-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6026a-107">Um eine ordnungsgemäße Funktionsweise sicherzustellen, müssen die für die Dienste verwendeten Konten mit der richtigen Domäne, dem richtigen Dateisystem und den richtigen Registrierungsberechtigungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6026a-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="6026a-108">Weitere Informationen zu erforderlichen Berechtigungen finden Sie unter [Konfigurieren von Windows-Dienstkonten und -Berechtigungen](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6026a-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="6026a-109">Windows-Verwaltungsinstrumentation</span><span class="sxs-lookup"><span data-stu-id="6026a-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="6026a-110">Der SQL Server-Konfigurations-Manager und [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden zum Anzeigen und Bearbeiten einiger Servereigenschaften die Windows-Verwaltungsinstrumentation (WMI, Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="6026a-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="6026a-111">Um Dienste zu verwalten und den Status der Dienste abzufragen, muss der Benutzer über eine Zugriffsberechtigung für das WMI-Objekt verfügen.</span><span class="sxs-lookup"><span data-stu-id="6026a-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="6026a-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]wird die WMI auf den folgenden Servereigenschaftenseiten verwendet:</span><span class="sxs-lookup"><span data-stu-id="6026a-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="6026a-113">Dienste automatisch starten</span><span class="sxs-lookup"><span data-stu-id="6026a-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="6026a-114">Startparameter</span><span class="sxs-lookup"><span data-stu-id="6026a-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="6026a-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6026a-115">Security</span></span>  
  
-   <span data-ttu-id="6026a-116">Sonstige Servereinstellungen</span><span class="sxs-lookup"><span data-stu-id="6026a-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6026a-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6026a-117">Related Tasks</span></span>  
 [<span data-ttu-id="6026a-118">Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools</span><span class="sxs-lookup"><span data-stu-id="6026a-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="6026a-119">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6026a-119">Related Content</span></span>  
 [<span data-ttu-id="6026a-120">Konzepte des WMI-Anbieters für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6026a-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
