---
title: Starten von SQL Server mit Minimalkonfiguration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608834"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="a38bc-102">Starten Sie von SQL Server mit Minimalkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a38bc-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="a38bc-103">Wenn Konfigurationsprobleme auftreten, die das Starten des Servers verhindern, können Sie eine Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe der Startoption für die Minimalkonfiguration starten.</span><span class="sxs-lookup"><span data-stu-id="a38bc-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="a38bc-104">Dies ist die Startoption **-f**.</span><span class="sxs-lookup"><span data-stu-id="a38bc-104">This is the startup option **-f**.</span></span> <span data-ttu-id="a38bc-105">Durch das Starten einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit Minimalkonfiguration wird der Server automatisch in den Einzelbenutzermodus versetzt.</span><span class="sxs-lookup"><span data-stu-id="a38bc-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="a38bc-106">Beachten Sie Folgendes, wenn Sie eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im Modus der Minimalkonfiguration starten:</span><span class="sxs-lookup"><span data-stu-id="a38bc-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="a38bc-107">Nur ein einziger Benutzer kann eine Verbindung herstellen, und der CHECKPOINT-Prozess wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a38bc-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="a38bc-108">Der Remotezugriff und das Read-Ahead werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a38bc-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="a38bc-109">Für den Startvorgang vorgesehene gespeicherte Prozeduren werden nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a38bc-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="a38bc-110">Nach dem Starten des Servers mit Minimalkonfiguration sollten Sie den oder die entsprechenden Optionswert(e) des Servers ändern, den Server dann beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="a38bc-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a38bc-111">Stellen Sie mithilfe des **sqlcmd** -Hilfsprogramms und der dedizierten Administratorverbindung (Dedicated Administrator Connection; DAC) eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a38bc-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a38bc-112">Wenn Sie eine typische Verbindung verwenden, sollten Sie den SQL Server-Agent-Dienst beenden, bevor Sie eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im Modus der Minimalkonfiguration herstellen.</span><span class="sxs-lookup"><span data-stu-id="a38bc-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="a38bc-113">Andernfalls verwendet der SQL Server-Agent-Dienst die Verbindung und blockiert sie dadurch.</span><span class="sxs-lookup"><span data-stu-id="a38bc-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38bc-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a38bc-114">See Also</span></span>  
 <span data-ttu-id="a38bc-115">[Starten, Beenden oder Anhalten des SQL Server-Agent-Dienstes](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="a38bc-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="a38bc-116">[Diagnoseverbindung für Datenbankadministratoren](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="a38bc-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="a38bc-117">[sqlcmd (Hilfsprogramm)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a38bc-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="a38bc-118">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a38bc-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="a38bc-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a38bc-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="a38bc-120">Startoptionen für den Datenbank-Engine-Dienst</span><span class="sxs-lookup"><span data-stu-id="a38bc-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
