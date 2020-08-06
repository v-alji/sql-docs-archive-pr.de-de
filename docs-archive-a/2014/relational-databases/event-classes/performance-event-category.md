---
title: Leistung (Ereigniskategorie) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619813"
---
# <a name="performance-event-category"></a><span data-ttu-id="d9342-102">Leistung (Ereigniskategorie)</span><span class="sxs-lookup"><span data-stu-id="d9342-102">Performance Event Category</span></span>
  <span data-ttu-id="d9342-103">Verwenden Sie die **Leistung** -Ereigniskategorie zum Überwachen von **Showplan** -Ereignisklassen und von Ereignisklassen, die durch das Ausführen von SQL-DML-Operatoren (SQL Data Manipulation Language) erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="d9342-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9342-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d9342-104">In This Section</span></span>  
  
|<span data-ttu-id="d9342-105">Thema</span><span class="sxs-lookup"><span data-stu-id="d9342-105">Topic</span></span>|<span data-ttu-id="d9342-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d9342-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d9342-107">Auto Stats-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="d9342-108">Gibt an, dass eine automatische Aktualisierung der Index- und Spaltenstatistiken aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d9342-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="d9342-109">Degree of Parallelism &#40;7.0 Insert&#41;-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="d9342-110">Zeigt an, dass von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine SELECT-, INSERT-, UPDATE- oder DELETE-Anweisung mit einem seriellen oder parallelen Plan ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d9342-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="d9342-111">Darüber hinaus wird die Anzahl der CPUs, die für den Vorgang verwendet wurden, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9342-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="d9342-112">Performance Statistics-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="d9342-113">Überwacht die Leistung der Abfragen, die ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9342-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="d9342-114">Showplan All (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="d9342-115">Identifiziert **Showplan** -Operatoren in einer SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9342-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="d9342-116">Showplan All for Query Compile-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="d9342-117">Zeigt Kompilierzeitdaten für **Showplan** -Operatoren an.</span><span class="sxs-lookup"><span data-stu-id="d9342-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="d9342-118">Showplan Statistics Profile (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="d9342-119">Zeigt die geschätzten Kosten einer Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="d9342-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="d9342-120">Showplan XML (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="d9342-121">Identifiziert die **Showplan** -Operatoren in einer SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9342-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="d9342-122">Die Ereignisklasse speichert jedes Ereignis als definiertes XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="d9342-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="d9342-123">Showplan XML for Query Compile (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="d9342-124">Zeigt Kompilierzeitdaten für **Showplan** -Operatoren im XML-Format an.</span><span class="sxs-lookup"><span data-stu-id="d9342-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="d9342-125">Showplan XML Statistics Profile-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="d9342-126">Identifiziert die einer SQL-Anweisung zugeordneten **Showplan** -Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d9342-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="d9342-127">Die Ausgabe erfolgt als XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="d9342-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="d9342-128">SQL:FullTextQuery-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d9342-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="d9342-129">Gibt an, dass in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Volltextabfrage ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d9342-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="d9342-130">Plan Guide Successful (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="d9342-131">Zeigt an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erfolgreich einen Ausführungsplan für eine Abfrage oder einen Batch mit einer Planhinweisliste erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="d9342-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="d9342-132">Plan Guide Unsuccessful (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d9342-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="d9342-133">Zeigt an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] keinen Ausführungsplan für eine Abfrage oder einen Batch mit einer Planhinweisliste erzeugen konnte.</span><span class="sxs-lookup"><span data-stu-id="d9342-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9342-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9342-134">See Also</span></span>  
 [<span data-ttu-id="d9342-135">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d9342-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
