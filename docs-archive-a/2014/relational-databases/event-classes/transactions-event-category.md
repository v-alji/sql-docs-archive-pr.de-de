---
title: Transaktionen-Ereigniskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620410"
---
# <a name="transactions-event-category"></a><span data-ttu-id="1a569-102">Transaktionen-Ereigniskategorie</span><span class="sxs-lookup"><span data-stu-id="1a569-102">Transactions Event Category</span></span>
  <span data-ttu-id="1a569-103">Die **Transaktionen** -Ereigniskategorie kann zum Überwachen des Status von Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a569-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="1a569-104">Die Ereignisklassennamen mit dem Präfix **TM:** werden zum Nachverfolgen von transaktionsbezogenen Vorgängen verwendet, die über die Schnittstelle zur Transaktionsverwaltung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a569-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a569-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1a569-105">In This Section</span></span>  
  
|<span data-ttu-id="1a569-106">Thema</span><span class="sxs-lookup"><span data-stu-id="1a569-106">Topic</span></span>|<span data-ttu-id="1a569-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a569-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1a569-108">DTCTransaction (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="1a569-109">Verfolgt Transaktionen nach, die vom [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) koordiniert werden.</span><span class="sxs-lookup"><span data-stu-id="1a569-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="1a569-110">Hierbei handelt es sich um Transaktionen, die zwischen mindestens zwei Datenbanken oder Instanzen von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="1a569-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1a569-111">SQLTransaction-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1a569-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="1a569-112">Verfolgt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen BEGIN TRAN, COMMIT TRAN, SAVE TRAN und ROLLBACK TRAN nach.</span><span class="sxs-lookup"><span data-stu-id="1a569-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="1a569-113">TM: Begin Tran Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="1a569-114">Gibt an, dass eine BEGIN TRANSACTION-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a569-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="1a569-115">TM: Begin Tran Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="1a569-116">Gibt an, dass eine BEGIN TRANSACTION-Anforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a569-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="1a569-117">TM: Commit Tran Completed-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1a569-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="1a569-118">Gibt an, dass eine COMMIT TRANSACTION-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a569-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="1a569-119">TM: Commit Tran Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="1a569-120">Gibt an, dass eine COMMIT TRANSACTION-Anforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a569-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="1a569-121">TM: Promote Tran Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="1a569-122">Gibt an, dass eine PROMOTE TRANSACTION-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a569-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="1a569-123">TM: Promote Tran Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="1a569-124">Gibt an, dass eine PROMOTE TRANSACTION-Anforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a569-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="1a569-125">TM: Rollback Tran Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="1a569-126">Gibt an, dass eine ROLLBACK TRANSACTION-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a569-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="1a569-127">TM: Rollback Tran Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="1a569-128">Gibt an, dass eine ROLLBACK TRANSACTION-Anforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a569-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="1a569-129">TM: Save Tran Completed-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1a569-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="1a569-130">Gibt an, dass eine SAVE TRANSACTION-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a569-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="1a569-131">TM: Save Tran Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1a569-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="1a569-132">Gibt an, dass eine SAVE TRANSACTION-Anforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a569-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="1a569-133">TransactionLog-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="1a569-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="1a569-134">Verfolgt nach, wenn Transaktionen in das Transaktionsprotokoll einer Datenbank geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1a569-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
