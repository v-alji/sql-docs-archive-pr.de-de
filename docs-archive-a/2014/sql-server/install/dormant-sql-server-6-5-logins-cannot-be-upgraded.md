---
title: Ruhende SQL Server 6,5-Anmeldungen können nicht aktualisiert werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617479"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="37a8f-102">Ein Upgrade ruhender SQL Server 6.5-Anmeldungen kann nicht durchgeführt werden</span><span class="sxs-lookup"><span data-stu-id="37a8f-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="37a8f-103">Upgrade Advisor hat eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldung erkannt, deren Kennwort nicht direkt auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="37a8f-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="37a8f-104">Sie müssen das entsprechende Kennwort neu festlegen, um diese Anmeldung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="37a8f-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="37a8f-105">Sie können das Kennwort mithilfe von ALTER LOGIN neu festlegen:</span><span class="sxs-lookup"><span data-stu-id="37a8f-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="37a8f-106">Das neue Kennwort wird auf die Erfüllung der Richtlinie für die Kennwortkomplexität Ihres Systems überprüft, es sei denn, die Richtlinienüberprüfung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="37a8f-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="37a8f-107">Es wird empfohlen, komplexe Kennwörter zu verwenden und die Richtlinienüberprüfung nicht zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="37a8f-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="37a8f-108">Durch die Option MUST_CHANGE wird der Benutzer zum Auswählen eines neuen Kennworts gezwungen.</span><span class="sxs-lookup"><span data-stu-id="37a8f-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="37a8f-109">Dies wird empfohlen, ist aber nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37a8f-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="37a8f-110">Sie können ruhende Anmeldungen mithilfe der folgenden Abfrage identifizieren:</span><span class="sxs-lookup"><span data-stu-id="37a8f-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="37a8f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37a8f-111">See Also</span></span>  
 <span data-ttu-id="37a8f-112">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="37a8f-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="37a8f-113">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="37a8f-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
