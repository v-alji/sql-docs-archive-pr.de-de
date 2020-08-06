---
title: TSQL-Ereigniskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695642"
---
# <a name="tsql-event-category"></a><span data-ttu-id="a15ea-102">TSQL-Ereigniskategorie</span><span class="sxs-lookup"><span data-stu-id="a15ea-102">TSQL Event Category</span></span>
  <span data-ttu-id="a15ea-103">Die **TSQL** -Ereigniskategorie enthält allgemeine TSQL-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="a15ea-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a15ea-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a15ea-104">In This Section</span></span>  
  
|<span data-ttu-id="a15ea-105">Thema</span><span class="sxs-lookup"><span data-stu-id="a15ea-105">Topic</span></span>|<span data-ttu-id="a15ea-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a15ea-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a15ea-107">Exec Prepared SQL (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="a15ea-108">Zeigt an, dass von SqlClient, ODBC, OLE DB oder DB-Library mindestens eine vorbereitete [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a15ea-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="a15ea-109">Prepare SQL-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="a15ea-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="a15ea-110">Zeigt an, dass von SqlClient, ODBC, OLE DB oder DB-Library mindestens eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung zum Verwenden vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="a15ea-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="a15ea-111">SQL:BatchCompleted (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="a15ea-112">Zeigt an, dass der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batch abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a15ea-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="a15ea-113">SQL:BatchStarting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="a15ea-114">Zeigt an, dass der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a15ea-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="a15ea-115">SQL:StmtCompleted (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="a15ea-116">Zeigt an, dass eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a15ea-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="a15ea-117">SQL:StmtRecompile (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="a15ea-118">Zeigt Neukompilierungen auf Anweisungsebene an, die durch jegliche Arten von Batches, z. B. gespeicherte Prozeduren, Trigger, Ad-hoc-Batches sowie Abfragen, verursacht wurden.</span><span class="sxs-lookup"><span data-stu-id="a15ea-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="a15ea-119">SQL:StmtStarting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="a15ea-120">Zeigt an, dass eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a15ea-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="a15ea-121">Unprepare SQL-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="a15ea-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="a15ea-122">Zeigt an, dass von SqlClient, ODBC, OLE DB oder DB-Library mindestens eine vorbereitete [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="a15ea-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="a15ea-123">XQuery Static Type (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="a15ea-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="a15ea-124">Tritt auf, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen XQuery-Ausdruck ausführt.</span><span class="sxs-lookup"><span data-stu-id="a15ea-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a15ea-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a15ea-125">See Also</span></span>  
 [<span data-ttu-id="a15ea-126">Transact-SQL-Referenz &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="a15ea-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
