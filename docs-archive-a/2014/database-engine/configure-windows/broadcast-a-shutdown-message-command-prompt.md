---
title: Senden einer Nachricht über das Herunterfahren (Befehlszeile) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701882"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="5a630-102">Senden einer Nachricht über das Herunterfahren (Befehlszeile)</span><span class="sxs-lookup"><span data-stu-id="5a630-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="5a630-103">In diesem Thema wird beschrieben, wie Sie mit dem Befehl [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] net send **eine Nachricht zum Herunterfahren in** übertragen.</span><span class="sxs-lookup"><span data-stu-id="5a630-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="5a630-104">Schließen Sie den Zeitpunkt, zu dem die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beendet wird, in die Nachricht ein, damit alle Benutzer ihre Aufgaben beenden können.</span><span class="sxs-lookup"><span data-stu-id="5a630-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="5a630-105">So senden Sie eine Nachricht über das Herunterfahren</span><span class="sxs-lookup"><span data-stu-id="5a630-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="5a630-106">Geben Sie in einer Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5a630-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="5a630-107">**net send /users "Nachricht"**</span><span class="sxs-lookup"><span data-stu-id="5a630-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="5a630-108">Durch die Option **/users** wird angegeben, dass die Nachricht an alle Benutzer gesendet wird, die mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5a630-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a630-109">Der Befehl **net send** erfordert, dass der Nachrichtendienst sowohl auf dem sendenden als auch auf den empfangenden Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a630-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="5a630-110">Der Nachrichtendienst ist in Windows Server 2003 standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5a630-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="5a630-111">Weitere Informationen zu **net send**finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5a630-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="5a630-112">Es könnte im Netzwerk geeigneter sein, die Benutzer per E-Mail oder telefonisch zu verständigen.</span><span class="sxs-lookup"><span data-stu-id="5a630-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="5a630-113">Verwenden Sie zum Bestimmen, welche Benutzer gerade mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verbunden sind, den Aktivitätsmonitor.</span><span class="sxs-lookup"><span data-stu-id="5a630-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="5a630-114">Informationen zum Aktivitätsmonitor finden Sie unter [Aktivitätsmonitor](../../relational-databases/performance-monitor/activity-monitor.md) und [Öffnen des Aktivitätsmonitors &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5a630-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a630-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a630-115">See Also</span></span>  
 [<span data-ttu-id="5a630-116">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="5a630-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
