---
title: Anforderungen an das Dienst Konto für das Upgrade auf SQL Server 2008 auf einem Domänen Controller | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617452"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="6fd7a-102">Dienstkontoanforderungen für das Upgrade auf SQL Server 2008 auf einem Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="6fd7a-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="6fd7a-103">Der Upgrade Advisor hat eine Instanz von erkannt, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unter einem Netzwerkdienst Konto oder einem lokalen Dienst Konto auf einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] Domänen Controller ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="6fd7a-104">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]-Domänencontroller installiert ist, können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste nicht unter Privilegien eines lokalen Dienstkontos oder eines Netzwerkdienstkontos ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6fd7a-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="6fd7a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="6fd7a-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="6fd7a-106">Corrective Action</span></span>  
 <span data-ttu-id="6fd7a-107">Stellen Sie sicher, dass alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienstkonten entweder Domänenkonten oder lokalen Systemkonten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="6fd7a-108">Wird diese Änderung vor dem Upgrade nicht vorgenommen, kann Setup nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="6fd7a-109">Die Dienstkonten "SQL Writer", "[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" und "Hilfsdienst für Active Directory" bilden eine Ausnahme, da sie für das Netzwerkdienstkonto hartcodiert sind und nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd7a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fd7a-110">See Also</span></span>  
 <span data-ttu-id="6fd7a-111">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6fd7a-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6fd7a-112">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="6fd7a-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
