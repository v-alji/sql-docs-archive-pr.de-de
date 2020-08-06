---
title: osql unterstützt nicht länger 'ED'- und '!!'- Befehle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ED command
- osql utility [SQL Server]
- '!! command'
ms.assetid: 7cc2852f-94e8-4292-9326-c3f1a1acd281
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1ad92a32c47002c8f56e56a5b3695d42d3bdd671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618444"
---
# <a name="osql-no-longer-supports-the-ed-and--commands"></a><span data-ttu-id="a7160-103">osql unterstützt nicht länger 'ED'- und '!!'-</span><span class="sxs-lookup"><span data-stu-id="a7160-103">osql no longer supports the ED and !!</span></span> <span data-ttu-id="a7160-104">commands</span><span class="sxs-lookup"><span data-stu-id="a7160-104">commands</span></span>
  <span data-ttu-id="a7160-105">Das Hilfsprogramm **osql** unterstützt nicht die Funktionen " **Ed** " und " **!!** "</span><span class="sxs-lookup"><span data-stu-id="a7160-105">The **osql** utility does not support the **ED** and **!!**</span></span> <span data-ttu-id="a7160-106">nicht.</span><span class="sxs-lookup"><span data-stu-id="a7160-106">commands.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a7160-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="a7160-107">Corrective Action</span></span>  
 <span data-ttu-id="a7160-108">Entfernen Sie Verweise auf das **Ed** -und das **!!**</span><span class="sxs-lookup"><span data-stu-id="a7160-108">Remove references to the **ED** and **!!**</span></span> <span data-ttu-id="a7160-109">aus den Skripts.</span><span class="sxs-lookup"><span data-stu-id="a7160-109">commands from your scripts.</span></span>  
  
 <span data-ttu-id="a7160-110">Wenn Sie " **Ed** " und " **!!** " verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="a7160-110">If you want to use the **ED** and **!!**</span></span> <span data-ttu-id="a7160-111">Verwenden Sie das Hilfsprogramm **sqlcmd** anstelle von **osql**.</span><span class="sxs-lookup"><span data-stu-id="a7160-111">commands, use the **sqlcmd** utility instead of **osql**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7160-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7160-112">See Also</span></span>  
 <span data-ttu-id="a7160-113">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a7160-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a7160-114">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="a7160-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
