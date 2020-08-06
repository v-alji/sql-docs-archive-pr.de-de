---
title: Datenbankintegrität überprüfen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.checkdatabaseintegritytask.f1
helpviewer_keywords:
- data integrity [Integration Services]
- Check Database Integrity task [Integration Services]
- checking database consistency
- database consistency checks [Integration Services]
- verifying database consistency
- integrity checking [Integration Services]
ms.assetid: 5a82fe99-4503-429f-9337-e6bac7649fe4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 99a2620a6f3f6a9a73c27fe6bb1abd34af73707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617238"
---
# <a name="check-database-integrity-task"></a><span data-ttu-id="c6045-102">Datenbankintegrität überprüfen (Task)</span><span class="sxs-lookup"><span data-stu-id="c6045-102">Check Database Integrity Task</span></span>
  <span data-ttu-id="c6045-103">Der Task Datenbankintegrität überprüfen überprüft die Zuordnung und strukturelle Integrität aller Objekte in der angegebenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c6045-103">The Check Database Integrity task checks the allocation and structural integrity of all the objects in the specified database.</span></span> <span data-ttu-id="c6045-104">Mit dem Task können Sie eine einzelne Datenbank oder mehrere Datenbanken überprüfen und auswählen, ob auch die Datenbankindizes überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6045-104">The task can check a single database or multiple databases, and you can choose whether to also check the database indexes.</span></span>  
  
 <span data-ttu-id="c6045-105">Der Task "Datenbankintegrität überprüfen" kapselt die DBCC CHECKDB-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c6045-105">The Check Database Integrity task encapsulates the DBCC CHECKDB statement.</span></span> <span data-ttu-id="c6045-106">Weitere Informationen finden Sie unter [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6045-106">For more information, see [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span></span>  
  
## <a name="configuration-of-the-check-database-integrity-task"></a><span data-ttu-id="c6045-107">Konfiguration des Tasks "Datenbankintegrität überprüfen"</span><span class="sxs-lookup"><span data-stu-id="c6045-107">Configuration of the Check Database Integrity Task</span></span>  
 <span data-ttu-id="c6045-108">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="c6045-108">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="c6045-109">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="c6045-109">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="c6045-110">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="c6045-110">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c6045-111">Task 'Datenbankintegrität überprüfen' &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="c6045-111">Check Database Integrity Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/check-database-integrity-task-maintenance-plan.md)  
  
 <span data-ttu-id="c6045-112">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="c6045-112">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c6045-113">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="c6045-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
