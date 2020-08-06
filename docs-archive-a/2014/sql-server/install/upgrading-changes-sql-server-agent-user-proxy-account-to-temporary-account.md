---
title: Beim Upgrade wird das SQL Server-Agent Benutzer Proxy Konto in das temporäre UpgradedProxyAccount geändert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608226"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="7af90-102">Beim Upgrade wird das Benutzerproxykonto des SQL Server-Agents in das temporäre 'UpgradedProxyAccount' geändert.</span><span class="sxs-lookup"><span data-stu-id="7af90-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="7af90-103">Datenbankwartungspläne, bei denen der Protokollversand aktiviert ist, werden nach dem Upgrade nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7af90-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7af90-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="7af90-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7af90-105">-Agent</span><span class="sxs-lookup"><span data-stu-id="7af90-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="7af90-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7af90-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7af90-107">stellt einen neuen Satz Protokollversandfunktionen bereit, die nicht direkt kompatibel mit Datenbankwartungsplänen sind.</span><span class="sxs-lookup"><span data-stu-id="7af90-107">provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7af90-108">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="7af90-108">Corrective Action</span></span>  
 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]<span data-ttu-id="7af90-109">-Benutzer mit Datenbankwartungsplänen, die Protokollversandfunktionen enthalten, müssen den Protokollversand mit den neuen Funktionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7af90-109">users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="7af90-110">Weitere Informationen finden Sie, wenn Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation nach "Protokollversand" suchen.</span><span class="sxs-lookup"><span data-stu-id="7af90-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af90-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7af90-111">See Also</span></span>  
 <span data-ttu-id="7af90-112">[SQL Server-Agent Protokoll Versand-Auftrags Kategorie bewirkt, dass das Upgrade fehlschlägt](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="7af90-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="7af90-113">Protokollversand wird nach Update nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="7af90-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
