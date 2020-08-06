---
title: FOR Browse ist in Sichten im Kompatibilitätsmodus 90 oder höher nicht zulässig. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 251e0ae2ff6f19dfcff3b0f8056f6697c1bfc40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620175"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a><span data-ttu-id="e46d0-102">FOR BROWSE ist in Sichten im Kompatibilitätsmodus 90 oder höher nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="e46d0-102">FOR BROWSE is not allowed in views in 90 or later compatibility modes</span></span>
  <span data-ttu-id="e46d0-103">Upgrade Advisor hat die Verwendung der FOR BROWSE-Klausel in einer Sicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="e46d0-103">Upgrade Advisor detected the use of the FOR BROWSE clause in a view.</span></span> <span data-ttu-id="e46d0-104">Die FOR BROWSE-Klausel ist in Sichten zulässig (und wird ignoriert), wenn der Datenbank-Kompatibilitätsmodus auf 80 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e46d0-104">The FOR BROWSE clause is allowed (and ignored) in views when the database compatibility mode is set to 80.</span></span> <span data-ttu-id="e46d0-105">Die FOR BROWSE-Klausel ist nicht in Sichten zulässig, wenn der Datenbank-Kompatibilitätsmodus auf 90 oder höher festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e46d0-105">The FOR BROWSE clause is not allowed in views when the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e46d0-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="e46d0-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="e46d0-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="e46d0-107">Corrective Action</span></span>  
 <span data-ttu-id="e46d0-108">Beim Upgrade behalten die Benutzerdatenbanken ihren Kompatibilitätsmodus bei.</span><span class="sxs-lookup"><span data-stu-id="e46d0-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="e46d0-109">Bevor Sie den Datenbank-Kompatibilitätsmodus in 90 oder höher ändern, entfernen Sie die FOR BROWSE-Klausel aus den Sichtdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="e46d0-109">Before you change the database compatibility mode to 90 or later, remove the FOR BROWSE clause from view definitions.</span></span> <span data-ttu-id="e46d0-110">Weitere Informationen finden Sie unter "sp_dbcmptlevel" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e46d0-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46d0-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e46d0-111">See Also</span></span>  
 <span data-ttu-id="e46d0-112">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e46d0-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e46d0-113">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="e46d0-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
