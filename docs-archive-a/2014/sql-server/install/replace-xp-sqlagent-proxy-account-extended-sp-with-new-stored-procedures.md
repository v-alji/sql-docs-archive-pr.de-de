---
title: Ersetzen Sie die Verwendung der erweiterten gespeicherten Prozedur xp_sqlagent_proxy_account durch neue gespeicherte Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620137"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="91d89-102">Ersetzen der erweiterten gespeicherten Prozedur xp_sqlagent_proxy_account durch neue gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="91d89-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  <span data-ttu-id="91d89-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent unterstützt mehrere Proxys.</span><span class="sxs-lookup"><span data-stu-id="91d89-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supports multiple proxies.</span></span> <span data-ttu-id="91d89-104">Diese Proxys werden anhand eines neuen Satzes gespeicherter Prozeduren definiert.</span><span class="sxs-lookup"><span data-stu-id="91d89-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="91d89-105">Weitere Informationen über die neuen gespeicherten Prozeduren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agents finden Sie unter den folgenden Themen in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation:</span><span class="sxs-lookup"><span data-stu-id="91d89-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="91d89-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="91d89-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="91d89-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91d89-117">Nachdem Sie auf aktualisiert [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] haben, funktionieren alle-Anweisungen, die die **xp_sqlagent_proxy_account** erweiterten gespeicherten Prozeduren verwenden, nicht.</span><span class="sxs-lookup"><span data-stu-id="91d89-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="91d89-118">Verwenden Sie **sp_xp_cmdshell_proxy_account** anstelle von **xp_sqlagent_proxy_account** , um den Proxy für **xp_cmdshell**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91d89-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="91d89-119">Komponente</span><span class="sxs-lookup"><span data-stu-id="91d89-119">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="91d89-120">-Agent</span><span class="sxs-lookup"><span data-stu-id="91d89-120">Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d89-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91d89-121">See Also</span></span>  
 [<span data-ttu-id="91d89-122">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="91d89-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
