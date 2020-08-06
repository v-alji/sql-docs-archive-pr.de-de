---
title: Entfernen Sie DDL-Vorgänge für die eingefügten und gelöschten Tabellen in DML-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720905"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="c9c22-102">Entfernen Sie DDL-Vorgänge aus den eingefügten und gelöschten Tabellen innerhalb von DML-Triggern</span><span class="sxs-lookup"><span data-stu-id="c9c22-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="c9c22-103">DDL (Data Definition Language)-Anweisungen (z. b. Create Index) können nicht für die eingefügten und gelöschten Tabellen innerhalb von DML-Triggern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9c22-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="c9c22-104">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sind einige DDL-Anweisungen für die inserted-Tabelle und die deleted-Tabelle zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9c22-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9c22-105">Weitere Informationen finden Sie unter "Verwenden der Tabellen inserted und deleted" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="c9c22-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c9c22-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="c9c22-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="c9c22-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="c9c22-107">Corrective Action</span></span>  
 <span data-ttu-id="c9c22-108">Entfernen Sie DDL-Vorgänge, die für die inserted-Tabelle und die deleted-Tabelle in DML-Triggern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9c22-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c22-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9c22-109">See Also</span></span>  
 <span data-ttu-id="c9c22-110">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c9c22-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c9c22-111">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="c9c22-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
