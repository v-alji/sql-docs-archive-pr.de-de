---
title: Erstellen einer SQL Server-Datenbankwarnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], alerts
- alerts [SQL Server], creating
- thresholds [SQL Server]
- database alerts [SQL Server]
- tuning databases [SQL Server], alerts
- monitoring performance [SQL Server], alerts
- monitoring server performance [SQL Server], alerts
- database monitoring [SQL Server], alerts
- server performance [SQL Server], alerts
ms.assetid: 0511136a-1b6b-4095-aa45-39e77b67aba2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fd0cc926412d64f7686744ee60840a32473d2386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723733"
---
# <a name="create-a-sql-server-database-alert"></a><span data-ttu-id="3de1e-102">Erstellen einer SQL Server-Datenbankwarnung</span><span class="sxs-lookup"><span data-stu-id="3de1e-102">Create a SQL Server Database Alert</span></span>
  <span data-ttu-id="3de1e-103">Sie können mithilfe des Systemmonitors eine Warnung erstellen, die ausgelöst wird, sobald ein Schwellenwert für einen Leistungsindikator des Systemmonitors erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="3de1e-103">You can use System Monitor to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="3de1e-104">Als Reaktion auf die Warnung startet der Systemmonitor eine Anwendung, z. B. eine für die Verarbeitung der Warnung geschriebene benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3de1e-104">In response to the alert, System Monitor launches an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="3de1e-105">Sie könnten beispielsweise eine Warnung erstellen, die ausgelöst wird, wenn die Anzahl der Deadlocks einen bestimmten Wert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="3de1e-105">For example, you could create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="3de1e-106">Sie können Warnungen auch mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents erstellen.</span><span class="sxs-lookup"><span data-stu-id="3de1e-106">Alerts also can be defined by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="3de1e-107">Weitere Informationen finden Sie unter [Warnungen](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="3de1e-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
 <span data-ttu-id="3de1e-108">Weitere Informationen zum Verwenden des Systemmonitors zum Einrichten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbankwarnung finden Sie unter [Einrichten einer SQL Server-Datenbankwarnung &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md).</span><span class="sxs-lookup"><span data-stu-id="3de1e-108">For more information about using System Monitor to set up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database alert, see [Set Up a SQL Server Database Alert &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de1e-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3de1e-109">See Also</span></span>  
 <span data-ttu-id="3de1e-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3de1e-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span></span>  
 [<span data-ttu-id="3de1e-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3de1e-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysperfinfo-transact-sql)  
  
  
