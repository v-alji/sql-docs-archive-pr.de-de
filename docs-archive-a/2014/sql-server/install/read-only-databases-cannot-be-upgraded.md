---
title: Schreibgeschützte Datenbanken können nicht aktualisiert werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620702"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="61182-102">Schreibgeschützte Datenbanken können nicht aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="61182-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="61182-103">Upgrade Advisor hat festgestellt, dass ein Upgrade einiger Datenbanken dieser Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="61182-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="61182-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="61182-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="61182-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61182-105">Description</span></span>  
 <span data-ttu-id="61182-106">Eine schreibgeschützte Datenbank wurde erkannt.</span><span class="sxs-lookup"><span data-stu-id="61182-106">A read-only database has been detected.</span></span> <span data-ttu-id="61182-107">Um die Datenbank zu aktualisieren, muss das Setupprogramm in die Datenbank schreiben können.</span><span class="sxs-lookup"><span data-stu-id="61182-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="61182-108">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="61182-108">Corrective Action</span></span>  
 <span data-ttu-id="61182-109">Wenn Sie die Datenbank nicht verwenden, verwenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] oder die ALTER DATABASE-Anweisung, um die Datenbank in Lese-/Schreibzugriff zu ändern.</span><span class="sxs-lookup"><span data-stu-id="61182-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="61182-110">Die folgende Anweisung gewährt Lese-/Schreibzugriff auf eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="61182-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="61182-111">Weitere Informationen über die ALTER DATABASE-Anweisung finden Sie im Thema "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="61182-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61182-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61182-112">See Also</span></span>  
 <span data-ttu-id="61182-113">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="61182-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="61182-114">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="61182-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
