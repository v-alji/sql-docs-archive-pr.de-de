---
title: Befehlszeilenoptionen für das Verwaltungstool (Distributed Replay-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618958"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="ddbfa-102">Befehlszeilenoptionen für das Verwaltungstool (Distributed Replay Utility)</span><span class="sxs-lookup"><span data-stu-id="ddbfa-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="ddbfa-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Verwaltungs Tool, `DReplay.exe` , ist ein Befehlszeilen Tool, das Sie für die Kommunikation mit dem verteilten Replay-Controller verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="ddbfa-104">Mit dem Verwaltungstool können Sie Vorgänge auf dem Controller initiieren, überwachen und abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="ddbfa-105">![Artikellinksymbol](../../database-engine/media/topic-link.gif "Symbol für Themenlink") Weitere Informationen zu den Syntaxkonventionen für das Verwaltungstool finden Sie unter [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ddbfa-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbfa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddbfa-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="ddbfa-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ddbfa-107">Remarks</span></span>  
 <span data-ttu-id="ddbfa-108">Sie können mit `DReplay.exe` die folgenden Befehlszeilenoptionen ausgeben:</span><span class="sxs-lookup"><span data-stu-id="ddbfa-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="ddbfa-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="ddbfa-109">**preprocess**</span></span>  
 <span data-ttu-id="ddbfa-110">Initiiert die Vorverarbeitungsphase.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="ddbfa-111">Der Controller bereitet die Eingabedaten der Ablaufverfolgung, die Sie aus der Produktionsumgebung aufgezeichnet haben, für die Wiedergabe anhand des Zielservers vor.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="ddbfa-112">**Wiedergabe (replay)**</span><span class="sxs-lookup"><span data-stu-id="ddbfa-112">**replay**</span></span>  
 <span data-ttu-id="ddbfa-113">Initiiert die Ereigniswiedergabephase.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-113">Initiates the event replay stage.</span></span> <span data-ttu-id="ddbfa-114">Der Controller leitet Wiedergabedaten an die angegebenen Clients weiter, startet die verteilte Wiedergabe und synchronisiert die Clients.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="ddbfa-115">Optional zeichnet jeder ausgewählte Client die Wiedergabeaktivität auf und speichert Ergebnisdateien der Ablaufverfolgung lokal.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="ddbfa-116">**status**</span><span class="sxs-lookup"><span data-stu-id="ddbfa-116">**status**</span></span>  
 <span data-ttu-id="ddbfa-117">Fragt den Controller ab und zeigt den aktuellen Status an.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="ddbfa-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="ddbfa-118">**cancel**</span></span>  
 <span data-ttu-id="ddbfa-119">Bricht den Vorgang ab, der derzeit auf dem Controller ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="ddbfa-120">Ausführliche Informationen zur Syntax, einschließlich Befehlsargumenten und Beispielen, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ddbfa-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ddbfa-121">Vorverarbeitungsoption &#40;Verwaltungstool „Distributed Replay“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddbfa-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="ddbfa-122">Wiedergabeoption &#40;Verwaltungstool „Distributed Replay“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddbfa-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="ddbfa-123">Statusoption &#40;Verwaltungstool „Distributed Replay“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddbfa-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="ddbfa-124">Option zum Abbrechen &#40;Verwaltungstool „Distributed Replay“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddbfa-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="ddbfa-125">RPCs werden als RPCs wiedergegeben und nicht als Sprachereignisse.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="ddbfa-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ddbfa-126">Permissions</span></span>  
 <span data-ttu-id="ddbfa-127">Sie müssen das Verwaltungstool als interaktiver Benutzer mit einem lokalen Benutzerkonto oder Domänenbenutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="ddbfa-128">Um ein lokales Benutzerkonto zu verwenden, müssen das Verwaltungstool und der Controller auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ddbfa-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="ddbfa-129">Weitere Informationen finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="ddbfa-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbfa-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddbfa-130">See Also</span></span>  
 [<span data-ttu-id="ddbfa-131">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="ddbfa-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
