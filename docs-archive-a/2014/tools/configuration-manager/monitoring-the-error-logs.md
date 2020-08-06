---
title: Überwachen der Fehlerprotokolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617338"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="5a438-102">Überwachen der Fehlerprotokolle</span><span class="sxs-lookup"><span data-stu-id="5a438-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5a438-103">protokolliert bestimmte Systemereignisse und benutzerdefinierte Ereignisse im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll und im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="5a438-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="5a438-104">Beide Protokolle versehen alle aufgezeichneten Ereignisse automatisch mit einem Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="5a438-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="5a438-105">Sie können die Informationen im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll für die Problembehandlung bezüglich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a438-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5a438-106">Das Windows-Anwendungsprotokoll bietet eine Gesamtübersicht der Ereignisse, die im Windows-Betriebssystem auftreten, sowie der Ereignisse in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents.</span><span class="sxs-lookup"><span data-stu-id="5a438-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="5a438-107">Verwenden Sie die Windows-Ereignisanzeige, um das Windows-Anwendungsprotokoll anzuzeigen und die Informationen zu filtern.</span><span class="sxs-lookup"><span data-stu-id="5a438-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="5a438-108">So können Sie beispielsweise Ereignisse, wie Informationen, Warnung, Fehler, Erfolgsüberwachung und Fehlerüberwachung, filtern.</span><span class="sxs-lookup"><span data-stu-id="5a438-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="5a438-109">Vergleichen der Ausgabe des Fehler- und Anwendungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="5a438-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="5a438-110">Sie können sowohl das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll als auch das Windows-Anwendungsprotokoll verwenden, um die Ursache von Problemen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5a438-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="5a438-111">Möglicherweise erhalten Sie während der Überwachung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokolls Fehlermeldungen, die keine Informationen zu den Ursachen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a438-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="5a438-112">Durch Vergleichen der Daten und Zeiten der Ereignisse zwischen diesen Protokollen können Sie die Liste der wahrscheinlichen Ursachen eingrenzen.</span><span class="sxs-lookup"><span data-stu-id="5a438-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="5a438-113">Der Protokolldatei-Viewer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ermöglicht die Integration von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents und des Windows-Protokolls in eine einzelne Liste. Auf diese Weise können Sie zugehörige Serverereignisse und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ereignisse besser nachvollziehen.</span><span class="sxs-lookup"><span data-stu-id="5a438-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="5a438-114">Weitere Informationen finden Sie im Thema zum Protokolldatei-Viewer in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="5a438-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a438-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5a438-115">In This Section</span></span>  
  
|<span data-ttu-id="5a438-116">Thema</span><span class="sxs-lookup"><span data-stu-id="5a438-116">Topic</span></span>|<span data-ttu-id="5a438-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a438-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5a438-118">Anzeigen des SQL Server-Fehlerprotokolls</span><span class="sxs-lookup"><span data-stu-id="5a438-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="5a438-119">Enthält Informationen zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll und beschreibt das Anzeigen dieses Fehlerprotokolls.</span><span class="sxs-lookup"><span data-stu-id="5a438-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="5a438-120">Anzeigen des Windows-Anwendungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="5a438-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="5a438-121">Enthält Informationen zum Windows-Fehlerprotokoll und beschreibt das Anzeigen dieses Fehlerprotokolls.</span><span class="sxs-lookup"><span data-stu-id="5a438-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
