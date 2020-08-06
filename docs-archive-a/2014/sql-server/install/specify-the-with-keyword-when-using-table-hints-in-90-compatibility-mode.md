---
title: Geben Sie das with-Schlüsselwort bei Verwendung von Tabellen hinweisen im Kompatibilitätsmodus 90 an. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- table hints [SQL Server]
ms.assetid: 7636cc85-5155-44db-baf6-df807761adb8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ecd13475395cef4257d97eb7480f32420932e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617447"
---
# <a name="specify-the-with-keyword-when-using-table-hints-in-90-compatibility-mode"></a><span data-ttu-id="3c349-102">Angeben des WITH-Schlüsselworts bei Verwendung von Tabellenhinweisen im Kompatibilitätsmodus 90</span><span class="sxs-lookup"><span data-stu-id="3c349-102">Specify the WITH keyword when using table hints in 90 compatibility mode</span></span>
  <span data-ttu-id="3c349-103">Bis auf einige Ausnahmen werden Tabellenhinweise nur dann in der FROM-Klausel einer Abfrage unterstützt, wenn die Hinweise mithilfe des WITH-Schlüsselworts angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3c349-103">With some exceptions, table hints are supported in the FROM clause of a query only when the hints are specified by using the WITH keyword.</span></span> <span data-ttu-id="3c349-104">Weitere Informationen hierzu finden Sie in den Themen "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" und "Tabellenhinweis ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c349-104">For more information, see the topics "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" and "Table Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3c349-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="3c349-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="3c349-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="3c349-106">Corrective Action</span></span>  
 <span data-ttu-id="3c349-107">Ändern Sie Abfragen, die Tabellenhinweise in der FROM-Klausel enthalten, indem Sie das WITH-Schlüsselwort vor den Tabellenhinweisen einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c349-107">Modify queries that include table hints in the FROM clause by including the WITH keyword before the table hints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c349-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c349-108">See Also</span></span>  
 <span data-ttu-id="3c349-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3c349-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3c349-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="3c349-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
