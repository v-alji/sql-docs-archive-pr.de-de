---
title: Protokolldatei-Viewer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616537"
---
# <a name="log-file-viewer"></a><span data-ttu-id="5305b-102">Protokolldatei-Viewer</span><span class="sxs-lookup"><span data-stu-id="5305b-102">Log File Viewer</span></span>
  <span data-ttu-id="5305b-103">Sie können mithilfe des Protokolldatei-Viewers in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf Informationen zu Fehlern und Ereignissen zugreifen, die in Protokollen aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="5305b-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="5305b-104">Vorteile der Verwendung des Protokolldatei-Viewers</span><span class="sxs-lookup"><span data-stu-id="5305b-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="5305b-105">Sie können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokolldateien aus einer lokalen oder Remoteinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzeigen, wenn die Zielinstanz offline ist oder nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5305b-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="5305b-106">Auf die Offlineprotokolldateien können Sie von Registrierte Server oder programmgesteuert mit WMI- und WQL (WMI Query Language)-Abfragen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5305b-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="5305b-107">Weitere Informationen finden Sie unter [Anzeigen von Offlineprotokolldateien](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="5305b-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="5305b-108">Mithilfe des Protokolldatei-Viewers können Sie auf die folgenden Arten von Protokolldateien zugreifen:</span><span class="sxs-lookup"><span data-stu-id="5305b-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="5305b-109">Überwachungsauflistung</span><span class="sxs-lookup"><span data-stu-id="5305b-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="5305b-110">Datensammlung</span><span class="sxs-lookup"><span data-stu-id="5305b-110">Data Collection</span></span>  
  
-   <span data-ttu-id="5305b-111">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="5305b-111">Database Mail</span></span>  
  
-   <span data-ttu-id="5305b-112">Auftragsverlauf</span><span class="sxs-lookup"><span data-stu-id="5305b-112">Job History</span></span>  
  
-   <span data-ttu-id="5305b-113">Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="5305b-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="5305b-114">Remotewartungspläne</span><span class="sxs-lookup"><span data-stu-id="5305b-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="5305b-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5305b-115">SQL Server</span></span>  
  
-   <span data-ttu-id="5305b-116">SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="5305b-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="5305b-117">Windows NT (Windows-Ereignisse, auf die auch mithilfe der Windows-Ereignisanzeige zugegriffen werden kann.)</span><span class="sxs-lookup"><span data-stu-id="5305b-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="5305b-118">Tasks im Protokolldatei-Viewer</span><span class="sxs-lookup"><span data-stu-id="5305b-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="5305b-119">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5305b-119">Task Description</span></span>|<span data-ttu-id="5305b-120">Thema</span><span class="sxs-lookup"><span data-stu-id="5305b-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="5305b-121">Beschreibt, wie der Protokolldatei-Viewer in Abhängigkeit der Informationen, die Sie anzeigen möchten, geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="5305b-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="5305b-122">Öffnen des Protokolldatei-Viewers</span><span class="sxs-lookup"><span data-stu-id="5305b-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="5305b-123">Beschreibt, wie Offlineprotokolldateien über registrierte Server angezeigt werden und wie WMI-Berechtigungen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="5305b-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="5305b-124">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="5305b-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="5305b-125">Öffnet die F1-Hilfe für den Protokolldatei-Viewer.</span><span class="sxs-lookup"><span data-stu-id="5305b-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="5305b-126">Protokolldatei-Viewer (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="5305b-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="5305b-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5305b-127">See Also</span></span>  
 <span data-ttu-id="5305b-128">[SQL Server Audit &#40;Datenbank-Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="5305b-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="5305b-129">SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="5305b-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
