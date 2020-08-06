---
title: INFORMATION_SCHEMA. Schemata gibt Schema Namen in einer Datenbank zurück, nicht Datenbanken in einer Instanz. Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621828"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="66fa0-102">INFORMATION_SCHEMA.SCHEMATA gibt Schemanamen in einer Datenbank, nicht Datenbanken in einer Instanz zurück</span><span class="sxs-lookup"><span data-stu-id="66fa0-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="66fa0-103">Der Upgrade Advisor hat Anweisungen erkannt, die auf die INFORMATION_SCHEMA.SCHEMATA-Sicht verweisen.</span><span class="sxs-lookup"><span data-stu-id="66fa0-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="66fa0-104">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gab diese Sicht alle Datenbanken in einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurück.</span><span class="sxs-lookup"><span data-stu-id="66fa0-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="66fa0-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höher gibt die Sicht alle Schemas in einer Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="66fa0-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="66fa0-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="66fa0-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="66fa0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="66fa0-107">Description</span></span>  
 <span data-ttu-id="66fa0-108">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gab die INFORMATION_SCHEMA.SCHEMATA-Sicht alle Datenbanken in einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurück.</span><span class="sxs-lookup"><span data-stu-id="66fa0-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="66fa0-109">Jetzt gibt die Sicht alle Schemas in einer Datenbank zurück, die dem SQL-Standard entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66fa0-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="66fa0-110">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="66fa0-110">Corrective Action</span></span>  
 <span data-ttu-id="66fa0-111">Ändern Sie die Anwendung so, dass Sie auf die **sys. Datenbanken** -Katalog Sicht verweist, um alle Datenbanken in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanz von zurückzugeben</span><span class="sxs-lookup"><span data-stu-id="66fa0-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fa0-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66fa0-112">See Also</span></span>  
 <span data-ttu-id="66fa0-113">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="66fa0-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="66fa0-114">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="66fa0-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
