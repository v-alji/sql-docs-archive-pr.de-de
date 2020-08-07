---
title: Fehler und Warnungen-Ereigniskategorie (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719885"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="7b53d-102">Fehler und Warnungen-Ereigniskategorie (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="7b53d-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="7b53d-103">Die **Fehler und Warnungen** -Ereigniskategorie enthält allgemeine Fehler- und Warnungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="7b53d-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b53d-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7b53d-104">In This Section</span></span>  
  
|<span data-ttu-id="7b53d-105">Thema</span><span class="sxs-lookup"><span data-stu-id="7b53d-105">Topic</span></span>|<span data-ttu-id="7b53d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b53d-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7b53d-107">Attention-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="7b53d-108">Zeigt an, dass ein **Attention** -Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7b53d-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="7b53d-109">Background Job Error-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="7b53d-110">Zeigt an, dass ein Hintergrundauftrag fehlerbedingt beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7b53d-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="7b53d-111">Bitmap Warning-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="7b53d-112">Zeigt an, dass das Filtern von Bitmaps in einer Abfrage deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7b53d-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="7b53d-113">Blocked Process Report-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="7b53d-114">Zeigt an, dass ein Task länger als die angegebene Zeitspanne blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7b53d-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="7b53d-115">CPU Threshold Exceeded (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="7b53d-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="7b53d-116">Zeigt an, dass die Ressourcenkontrolle eine Abfrage erkennt, die den angegebenen CPU-Schwellenwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="7b53d-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="7b53d-117">ErrorLog-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="7b53d-118">Zeigt an, dass Fehlerereignisse im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="7b53d-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="7b53d-119">EventLog-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="7b53d-120">Zeigt an, dass Ereignisse im Windows-Ereignisprotokoll protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="7b53d-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="7b53d-121">Exception-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="7b53d-122">Zeigt an, dass in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7b53d-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="7b53d-123">Exchange Spill (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="7b53d-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="7b53d-124">Zeigt an, dass Kommunikationspuffer in einem parallelen Abfrageplan in die tempdb-Datenbank geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="7b53d-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="7b53d-125">Execution Warnings (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="7b53d-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="7b53d-126">Zeigt an, dass während der Ausführung einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anweisung oder einer gespeicherten Prozedur Warnungen zur Arbeitsspeicherzuweisung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="7b53d-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="7b53d-127">Hash Warning-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="7b53d-128">Zeigt an, dass während eines Hashvorgangs eine Hashrekursion oder ein Hashabbruch aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7b53d-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="7b53d-129">Missing Column Statistics-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="7b53d-130">Zeigt an, dass Spaltenstatistiken, die vom Optimierer hätten verwendet werden können, nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7b53d-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="7b53d-131">Missing Join Predicate (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="7b53d-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="7b53d-132">Zeigt an, dass eine Abfrage ohne JOIN-Prädikat ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b53d-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="7b53d-133">Sort Warnings (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="7b53d-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="7b53d-134">Zeigt an, dass der Arbeitsspeicher für Sortiervorgänge nicht ausreicht.</span><span class="sxs-lookup"><span data-stu-id="7b53d-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="7b53d-135">User Error Message-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="7b53d-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="7b53d-136">Zeigt die dem Benutzer angezeigten Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="7b53d-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b53d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b53d-137">See Also</span></span>  
 [<span data-ttu-id="7b53d-138">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b53d-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
