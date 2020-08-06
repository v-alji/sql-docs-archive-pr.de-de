---
title: Entfernen von Anweisungen, die Systemobjekte löschen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608242"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="5e5e1-102">Entfernen Sie Anweisungen, mit denen Systemobjekte gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="5e5e1-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="5e5e1-103">Der Upgrade Advisor hat Anweisungen erkannt, die Systemobjekte löschen.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="5e5e1-104">System Objekte, einschließlich erweiterter gespeicherter Prozeduren, werden in der schreibgeschützten **Ressourcen** Datenbank (mssqlsystemresource) bereitgestellt und können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="5e5e1-105">Ändern Sie Ihre Anwendungen, sodass sie EXECUTE-Berechtigungen für Systemobjekte aufheben oder verweigern.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5e5e1-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="5e5e1-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="5e5e1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e5e1-107">Description</span></span>  
 <span data-ttu-id="5e5e1-108">Anweisungen wie DROP TABLE, DROP PROCEDURE und **sp_dropextendedproc** können nicht zum Entfernen von System Objekten verwendet werden, da diese Objekte in der schreibgeschützten **Ressourcen** Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="5e5e1-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="5e5e1-109">Corrective Action</span></span>  
 <span data-ttu-id="5e5e1-110">Entfernen Sie alle Anweisungen, mit denen Systemobjekte aus Ihren Anwendungen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="5e5e1-111">Ändern Sie Ihre Anwendungen, sodass sie EXECUTE-Berechtigungen für Systemobjekte aufheben oder verweigern.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="5e5e1-112">Alternativ können Sie auch das Tool zur Oberflächenkonfiguration (Surface Area Configuration, SAC) verwenden, um einige dieser Objekte zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="5e5e1-113">Beispielsweise kann die erweiterte gespeicherte Prozedur **xp_cmdshell** mit dem SAC-Tool deaktiviert oder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5e5e1-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5e1-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e5e1-114">See Also</span></span>  
 <span data-ttu-id="5e5e1-115">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5e5e1-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="5e5e1-116">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="5e5e1-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
