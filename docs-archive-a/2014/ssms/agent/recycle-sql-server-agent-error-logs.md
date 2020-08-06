---
title: Fehlerprotokolle des SQL Server-Agents wiederverwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.recyclesqlagenterrorlogs.f1
ms.assetid: 10bc2dd1-0505-4527-8ec7-d3b4e5d6352b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b30f0a2ba9a2d861d4a36a86489757cde512fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622360"
---
# <a name="recycle-sql-server-agent-error-logs"></a><span data-ttu-id="029b3-102">Fehlerprotokolle des SQL Server-Agents wiederverwenden</span><span class="sxs-lookup"><span data-stu-id="029b3-102">Recycle SQL Server Agent Error Logs</span></span>
  <span data-ttu-id="029b3-103">Mithilfe dieser Seite können Sie die Fehlerprotokolle des-Agents wieder verwenden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="029b3-103">Use this page to recycle the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Error Logs.</span></span> <span data-ttu-id="029b3-104">Beim Wiederverwenden des Protokolls werden das aktuelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll geschlossen und ein neues Fehlerprotokoll ohne Neustart des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstes gestartet.</span><span class="sxs-lookup"><span data-stu-id="029b3-104">Recycling the log closes the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="029b3-105">Beachten Sie, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die letzten neun Fehlerprotokolle speichert.</span><span class="sxs-lookup"><span data-stu-id="029b3-105">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs.</span></span> <span data-ttu-id="029b3-106">Wenn bereits neun Fehlerprotokolle vorhanden sind, führt das Wiederverwenden des Fehlerprotokolls dazu, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent das älteste Fehlerprotokoll entfernt.</span><span class="sxs-lookup"><span data-stu-id="029b3-106">If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to remove the oldest error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="029b3-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="029b3-107">See Also</span></span>  
 [<span data-ttu-id="029b3-108">SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="029b3-108">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
