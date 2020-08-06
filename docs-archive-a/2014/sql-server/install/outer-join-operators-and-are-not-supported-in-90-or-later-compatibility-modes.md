---
title: Outer Join-Operatoren *= und =* werden im Kompatibilitätsmodus 90 oder höher nicht unterstützt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720866"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="af1ea-102">Die Operatoren für äußere Joins \*= und =\* werden im Kompatibilitätsmodus 90 oder höher nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="af1ea-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="af1ea-103">Der Upgrade Advisor hat die Verwendung von Outer Join \* -Operatoren = und = erkannt \* .</span><span class="sxs-lookup"><span data-stu-id="af1ea-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="af1ea-104">Diese Operatoren werden im Kompatibilitätsmodus 90 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="af1ea-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="af1ea-105">Beim Upgrade behalten die Benutzerdatenbanken ihren Kompatibilitätsmodus bei.</span><span class="sxs-lookup"><span data-stu-id="af1ea-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="af1ea-106">Anweisungen, die diese Operatoren verwenden, führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="af1ea-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="af1ea-107">Komponente</span><span class="sxs-lookup"><span data-stu-id="af1ea-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="af1ea-108">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="af1ea-108">Corrective Action</span></span>  
 <span data-ttu-id="af1ea-109">Bevor Sie den Datenbank-Kompatibilitätsmodus auf 90 oder höher ändern, ändern Sie die-Anweisungen, die die Outer Join-Operatoren \* = und = verwenden, \* um äquivalente äußere joinschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="af1ea-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="af1ea-110">Im folgenden Beispiel wird eine Abfrage gezeigt, die den `\*=`-Operator verwendet, sowie eine entsprechende Abfrage, die das `LEFT OUTER JOIN`-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="af1ea-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="af1ea-111">Weitere Informationen zu äußeren Joins finden Sie unter "Verwenden von äußeren Joins" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="af1ea-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1ea-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af1ea-112">See Also</span></span>  
 <span data-ttu-id="af1ea-113">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="af1ea-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="af1ea-114">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="af1ea-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
