---
title: Entfernen Sie Anweisungen, die Berechtigungen auf Spaltenebene für Systemobjekte ändern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620150"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="62355-102">Entfernen von Anweisungen, die Berechtigungen auf Spaltenebene für Systemobjekte ändern</span><span class="sxs-lookup"><span data-stu-id="62355-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="62355-103">Der Upgrade Advisor hat nicht dem Standard entsprechende Berechtigungen auf Spaltenebene für Systemobjekte erkannt.</span><span class="sxs-lookup"><span data-stu-id="62355-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="62355-104">Diese Berechtigungsänderungen werden nicht beibehalten, wenn Sie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="62355-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="62355-105">Darüber hinaus werden Berechtigungen auf Spaltenebene für Systemobjekte nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62355-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="62355-106">Entfernen Sie Anweisungen aus den Anwendungen, die Berechtigungen auf Spaltenebene für Systemobjekte festlegen.</span><span class="sxs-lookup"><span data-stu-id="62355-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="62355-107">Komponente</span><span class="sxs-lookup"><span data-stu-id="62355-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="62355-108">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="62355-108">Corrective Action</span></span>  
 <span data-ttu-id="62355-109">Entfernen Sie Anweisungen aus den Anwendungen, die Berechtigungen auf Spaltenebene für Systemobjekte gewähren, verweigern oder aufheben.</span><span class="sxs-lookup"><span data-stu-id="62355-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62355-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62355-110">See Also</span></span>  
 <span data-ttu-id="62355-111">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="62355-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="62355-112">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="62355-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
