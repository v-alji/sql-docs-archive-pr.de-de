---
title: SQL Server-Agent-Fehlerprotokoll |Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699165"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="6f2b0-102">SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="6f2b0-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6f2b0-103">Agent erstellt ein Fehlerprotokoll, in dem standardmäßig Warnungen und Fehler erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="6f2b0-104">Die folgenden Warnungen und Fehler werden im Protokoll angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6f2b0-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="6f2b0-105">Warnmeldungen, die Informationen zu möglichen Problemen bereitstellen, z. b. "Auftrag \<*job_name*> wurde während der Ausführung gelöscht".</span><span class="sxs-lookup"><span data-stu-id="6f2b0-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="6f2b0-106">Fehlermeldungen, die in der Regel Eingriff eines Systemadministrators erfordern, z. B. "Mailsitzung kann nicht gestartet werden".</span><span class="sxs-lookup"><span data-stu-id="6f2b0-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="6f2b0-107">Fehlermeldungen können mithilfe von **NET SEND**an bestimmte Benutzer oder Computer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6f2b0-108">verwaltet bis zu neun [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokolle.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="6f2b0-109">Jedes archivierte Fehlerprotokoll verfügt über eine Dateierweiterung, durch die das relative Alter des Protokolls angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="6f2b0-110">So gibt z. B. die Erweiterung ".1" das zuletzt archivierte Fehlerprotokoll an, während die Erweiterung ".9" das Fehlerprotokoll kennzeichnet, das zuerst archiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="6f2b0-111">Standardmäßig werden Meldungen zur Ablaufverfolgung nicht in das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll geschrieben, da das Protokoll dadurch zu schnell aufgefüllt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="6f2b0-112">Wenn das Fehlerprotokoll voll ist, sind Ihre Möglichkeiten zur Auswahl und Analyse schwierigerer Fehler eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="6f2b0-113">Da durch das Protokoll die Verarbeitungsmenge für den Server erhöht wird, sollten Sie genau überlegen, welche Vorteile Ihnen das Aufzeichnen der Meldungen zur Ablaufverfolgung im Fehlerprotokoll bietet.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="6f2b0-114">Im Allgemeinen ist es am besten, alle Meldungen nur beim Debuggen eines bestimmten Problems aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="6f2b0-115">Beim Beenden des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents können Sie den Speicherort des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokolls ändern.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="6f2b0-116">Leere Fehlerprotokolle können nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="6f2b0-117">Sie können das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Protokoll jederzeit durchlaufen, ohne den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent anhalten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="6f2b0-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="6f2b0-118">**So zeigen Sie das SQL Server-Agent-Fehlerprotokoll an**</span><span class="sxs-lookup"><span data-stu-id="6f2b0-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="6f2b0-119">Fehlerprotokoll des SQL Server-Agents anzeigen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f2b0-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="6f2b0-120">**So benennen Sie ein SQL Server-Agent-Fehlerprotokoll um**</span><span class="sxs-lookup"><span data-stu-id="6f2b0-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="6f2b0-121">Fehlerprotokoll des SQL Server-Agents umbenennen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f2b0-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="6f2b0-122">**So senden Sie SQL Server-Agent-Fehlermeldungen**</span><span class="sxs-lookup"><span data-stu-id="6f2b0-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="6f2b0-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="6f2b0-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="6f2b0-124">**So schreiben Sie Meldungen zur Ablaufverfolgung in das SQL Server-Agent-Fehlerprotokoll**</span><span class="sxs-lookup"><span data-stu-id="6f2b0-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="6f2b0-125">Schreiben von Meldungen zur Ablaufverfolgung in das SQL Server-Agent-Fehlerprotokoll &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f2b0-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
